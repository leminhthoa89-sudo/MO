# Chương 13: SQL & Data Analysis cho MKT Ops

## 13.1 Tại sao SQL là skill bắt buộc?

Không biết SQL = phụ thuộc hoàn toàn vào Tech team mỗi khi cần data. Trong thực tế:
- Dashboard chỉ show cái **đã được build sẵn**
- Khi cần ad-hoc analysis (VD: "show tôi AR theo giờ trong ngày cho offer X tuần trước") → phải tự query
- Thời gian chờ Tech team: 1-3 ngày. Tự query: 5 phút.

## 13.2 SQL Cơ bản — Những gì cần trong tuần đầu

### Database schema điển hình trong affiliate platform:

```
TABLES CHÍNH:

clicks
├── click_id (PK)
├── affiliate_id
├── offer_id
├── geo
├── timestamp
├── ip_address
├── user_agent
├── sub1, sub2, sub3, sub4, sub5
└── landing_page_id

leads
├── lead_id (PK)
├── click_id (FK → clicks)
├── affiliate_id
├── offer_id
├── geo
├── status (new/trash/confirmed/rejected/hold)
├── created_at
├── phone
├── name
└── address

conversions
├── conversion_id (PK)
├── lead_id (FK → leads)
├── click_id (FK → clicks)
├── affiliate_id
├── offer_id
├── status (confirmed/approved/returned/cancelled)
├── payout (số tiền trả affiliate)
├── revenue (số tiền từ advertiser)
├── approved_at
└── created_at

affiliates
├── affiliate_id (PK)
├── name
├── email
├── tier (A/B/C)
├── status (active/paused/banned)
├── payment_terms
└── created_at

offers
├── offer_id (PK)
├── name
├── advertiser_id
├── category
├── geo
├── payout
├── revenue
├── cap_daily
├── status (active/paused/test)
└── created_at
```

### Queries bạn PHẢI biết viết:

```sql
-- 1. Daily leads + approved + AR theo GEO (hôm qua)
SELECT 
    geo,
    COUNT(*) as total_leads,
    SUM(CASE WHEN status = 'trash' THEN 1 ELSE 0 END) as trash,
    SUM(CASE WHEN status = 'approved' THEN 1 ELSE 0 END) as approved,
    ROUND(SUM(CASE WHEN status = 'approved' THEN 1 ELSE 0 END) * 100.0 
          / COUNT(*), 1) as approval_rate,
    ROUND(SUM(CASE WHEN status = 'trash' THEN 1 ELSE 0 END) * 100.0 
          / COUNT(*), 1) as trash_rate
FROM leads
WHERE DATE(created_at) = CURRENT_DATE - INTERVAL 1 DAY
GROUP BY geo
ORDER BY total_leads DESC;

-- 2. Top 10 affiliates by volume tuần này
SELECT 
    a.name as affiliate_name,
    COUNT(l.lead_id) as leads,
    SUM(CASE WHEN l.status = 'approved' THEN 1 ELSE 0 END) as approved,
    ROUND(AVG(CASE WHEN l.status = 'approved' THEN 1.0 ELSE 0.0 END) * 100, 1) as ar,
    ROUND(AVG(CASE WHEN l.status = 'trash' THEN 1.0 ELSE 0.0 END) * 100, 1) as trash_rate,
    SUM(c.revenue) as total_revenue,
    SUM(c.payout) as total_payout,
    SUM(c.revenue) - SUM(c.payout) as margin
FROM leads l
JOIN affiliates a ON l.affiliate_id = a.affiliate_id
LEFT JOIN conversions c ON l.lead_id = c.lead_id
WHERE l.created_at >= DATE_TRUNC('week', CURRENT_DATE)
GROUP BY a.name
ORDER BY leads DESC
LIMIT 10;

-- 3. Hourly lead pattern (phát hiện bot traffic)
SELECT 
    EXTRACT(HOUR FROM created_at) as hour,
    COUNT(*) as leads,
    COUNT(DISTINCT ip_address) as unique_ips,
    ROUND(COUNT(*) * 1.0 / NULLIF(COUNT(DISTINCT ip_address), 0), 1) 
        as leads_per_ip
FROM leads
WHERE affiliate_id = 'A015'
  AND DATE(created_at) = '2026-04-01'
GROUP BY EXTRACT(HOUR FROM created_at)
ORDER BY hour;

-- 4. Offer performance trend (tuần qua, daily)
SELECT 
    DATE(l.created_at) as date,
    COUNT(*) as leads,
    SUM(CASE WHEN l.status = 'approved' THEN 1 ELSE 0 END) as approved,
    ROUND(SUM(CASE WHEN l.status = 'approved' THEN 1 ELSE 0 END) * 100.0 
          / COUNT(*), 1) as ar,
    SUM(c.revenue) as revenue,
    SUM(c.payout) as payout,
    SUM(c.revenue) - SUM(c.payout) as margin
FROM leads l
LEFT JOIN conversions c ON l.lead_id = c.lead_id
WHERE l.offer_id = 1234
  AND l.created_at >= CURRENT_DATE - INTERVAL 7 DAY
GROUP BY DATE(l.created_at)
ORDER BY date;

-- 5. Cohort analysis — AR theo ngày lead vào
SELECT 
    DATE(l.created_at) as lead_date,
    COUNT(*) as total_leads,
    SUM(CASE WHEN c.status = 'approved' 
         AND c.approved_at <= l.created_at + INTERVAL 7 DAY 
         THEN 1 ELSE 0 END) as approved_7d,
    SUM(CASE WHEN c.status = 'approved' 
         AND c.approved_at <= l.created_at + INTERVAL 14 DAY 
         THEN 1 ELSE 0 END) as approved_14d,
    SUM(CASE WHEN c.status = 'approved' THEN 1 ELSE 0 END) as approved_total
FROM leads l
LEFT JOIN conversions c ON l.lead_id = c.lead_id
WHERE l.offer_id = 1234
  AND l.created_at >= '2026-03-01'
GROUP BY DATE(l.created_at)
ORDER BY lead_date;

-- 6. Duplicate phone detection
SELECT 
    phone,
    COUNT(*) as times_submitted,
    COUNT(DISTINCT affiliate_id) as from_affiliates,
    MIN(created_at) as first_submit,
    MAX(created_at) as last_submit
FROM leads
WHERE created_at >= CURRENT_DATE - INTERVAL 7 DAY
GROUP BY phone
HAVING COUNT(*) > 1
ORDER BY times_submitted DESC
LIMIT 50;

-- 7. Revenue waterfall — this month vs last month by offer
SELECT 
    o.name as offer_name,
    o.geo,
    SUM(CASE WHEN MONTH(c.approved_at) = MONTH(CURRENT_DATE) 
         THEN c.revenue ELSE 0 END) as this_month,
    SUM(CASE WHEN MONTH(c.approved_at) = MONTH(CURRENT_DATE) - 1 
         THEN c.revenue ELSE 0 END) as last_month,
    SUM(CASE WHEN MONTH(c.approved_at) = MONTH(CURRENT_DATE) 
         THEN c.revenue ELSE 0 END) -
    SUM(CASE WHEN MONTH(c.approved_at) = MONTH(CURRENT_DATE) - 1 
         THEN c.revenue ELSE 0 END) as change
FROM conversions c
JOIN offers o ON c.offer_id = o.offer_id
WHERE c.approved_at >= DATE_TRUNC('month', CURRENT_DATE) - INTERVAL 1 MONTH
GROUP BY o.name, o.geo
ORDER BY change DESC;
```

### Window Functions — Level trung cấp

```sql
-- Moving average AR 7 ngày (trend analysis)
SELECT 
    date,
    daily_ar,
    ROUND(AVG(daily_ar) OVER (
        ORDER BY date ROWS BETWEEN 6 PRECEDING AND CURRENT ROW
    ), 1) as ma_7d_ar
FROM (
    SELECT 
        DATE(created_at) as date,
        ROUND(SUM(CASE WHEN status='approved' THEN 1 ELSE 0 END)*100.0 
              / COUNT(*), 1) as daily_ar
    FROM leads
    WHERE offer_id = 1234
      AND created_at >= CURRENT_DATE - INTERVAL 30 DAY
    GROUP BY DATE(created_at)
) daily
ORDER BY date;

-- Rank affiliates by AR within each GEO
SELECT 
    geo,
    affiliate_name,
    leads,
    ar,
    RANK() OVER (PARTITION BY geo ORDER BY ar DESC) as rank_in_geo
FROM affiliate_performance_view
WHERE leads >= 50;
```

## 13.3 Google Sheets / Excel — Power User Skills

### Formulas bạn dùng hàng ngày:

```
VLOOKUP — match data giữa 2 sheets
=VLOOKUP(A2, Sheet2!A:D, 4, FALSE)

INDEX MATCH — linh hoạt hơn VLOOKUP
=INDEX(B:B, MATCH(D2, A:A, 0))

SUMIFS — tổng có điều kiện
=SUMIFS(Revenue, Geo, "RU", Status, "approved", Date, ">="&B1)

COUNTIFS — đếm có điều kiện
=COUNTIFS(Status, "trash", Affiliate, A2)

IF + AND/OR — logic
=IF(AND(AR>=0.4, Trash<=0.15), "🟢", IF(AR>=0.3, "🟡", "🔴"))

Percentage change
=(B2-B1)/B1

Conditional formatting rules:
• AR > 40% → green background
• AR 30-40% → yellow
• AR < 30% → red
• Trash > 20% → red text
```

### Pivot Tables — PHẢI thạo

```
Dùng pivot table để nhanh chóng answer:
• "AR trung bình theo GEO + Offer?"    → Rows: GEO, Offer | Values: AVG(AR)
• "Revenue theo tuần?"                  → Rows: Week | Values: SUM(Revenue)
• "Top affiliate theo mỗi GEO?"        → Rows: GEO, Affiliate | Values: SUM(Leads) | Sort DESC
• "Trend AR theo ngày + offer?"         → Rows: Date | Columns: Offer | Values: AVG(AR)
```

## 13.4 Tài nguyên học

### SQL (Ưu tiên 1)
- **SQLBolt** — https://sqlbolt.com — Interactive, miễn phí, 2-3 ngày xong
- **Mode SQL Tutorial** — https://mode.com/sql-tutorial — Thực hành trên data thật
- **W3Schools SQL** — https://www.w3schools.com/sql — Reference nhanh
- **SQLZoo** — https://sqlzoo.net — Bài tập thực hành
- **LeetCode SQL** — https://leetcode.com/problemset/database/ — Nâng cao

### Google Sheets (Ưu tiên 2)
- **Google Sheets Training** — https://support.google.com/a/users/answer/9282959 — Official
- **Ben Collins** — https://www.benlcollins.com — Google Sheets tips & tutorials
- **Spreadsheet Class** — https://spreadsheetclass.com — Free course

### BI / Dashboard tools
- **Metabase** — https://www.metabase.com/learn — Free BI tool, dễ dùng
- **Google Looker Studio** — https://lookerstudio.google.com — Free, connect Google Sheets/BigQuery
- **Tableau Public** — https://public.tableau.com — Free version, powerful
