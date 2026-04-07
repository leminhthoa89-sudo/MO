# Chương 6: Tracking, Data Flow & Dashboard

## 6.1 Data Flow tổng thể

```
USER JOURNEY:                          DATA FLOW:
═══════════════                        ═════════
                                       
User thấy Ad                           Ad Platform ghi nhận impression
    ↓                                      ↓
User click Ad                          Click tracked (click ID generated)
    ↓                                      ↓
User đến Pre-lander                    Tracker ghi nhận visit (sub IDs captured)
    ↓                                      ↓
User đến Landing Page                  LP view tracked
    ↓                                      ↓
User điền form (Lead)                  Lead data → CRM / AffScale
    ↓                                      ↓ Postback "lead" fired
Call Center gọi                        Status update: confirmed/rejected
    ↓                                      ↓ Postback "confirmed" fired
Ship hàng                              Status: shipped
    ↓                                      ↓
Delivered + Paid                       Status: approved
                                           ↓ Postback "approved" fired
                                           ↓
                                       AffScale ghi nhận conversion
                                           ↓
                                       Affiliate thấy trong dashboard
```

## 6.2 Tracking hoạt động như thế nào?

### Click Tracking

```
1. Affiliate nhận tracking link từ AffScale:
   https://track.affscale.com/click?offer_id=1234&aff_id=567&sub1={campaign}&sub2={adset}&sub3={ad}

2. User click vào quảng cáo → redirect qua AffScale:
   - AffScale ghi nhận: click_id, timestamp, IP, user agent, GEO
   - AffScale redirect user đến landing page
   - Click ID được pass qua URL parameter

3. Trên landing page, click_id được embed vào form:
   <input type="hidden" name="click_id" value="abc123xyz">

4. Khi user submit form, lead data + click_id gửi về CRM/AffScale
```

### Postback System (S2S Tracking)

```
Postback = HTTP request tự động gửi từ server A → server B khi có event

VÍ DỤ: Khi lead được approved:

Advertiser CRM → fires postback → AffScale
    URL: https://track.affscale.com/postback?click_id=abc123&status=approved&payout=10

AffScale nhận postback → ghi nhận conversion → fires postback → Affiliate Tracker
    URL: https://affiliate-tracker.com/postback?click_id=abc123&status=approved&payout=8
```

### Các event tracking quan trọng:

| Event | Từ đâu → Đâu | Trigger |
|-------|--------------|---------|
| **Click** | Affiliate → AffScale | User click ad |
| **Lead** | Landing Page → AffScale/CRM | User submit form |
| **Confirmed** | CRM → AffScale | Call center confirm |
| **Rejected** | CRM → AffScale | Call center reject |
| **Trash** | CRM → AffScale | Invalid lead |
| **Shipped** | Warehouse → CRM | Package sent |
| **Approved** | CRM → AffScale | Delivered & paid |
| **Returned** | Logistics → CRM | Package returned |

### Sub IDs — Tracking dimensions

```
Sub IDs cho phép segment data chi tiết:

sub1 = Campaign name       (VD: "weight_loss_women_35plus")
sub2 = Ad set / Placement  (VD: "facebook_feed")
sub3 = Ad creative         (VD: "video_testimonial_v3")
sub4 = Keyword / Interest  (VD: "fitness_interest")
sub5 = Custom              (VD: "lp_version_b")

Tại sao quan trọng?
→ Biết CHÍNH XÁC traffic nào convert tốt
→ Biết creative nào có AR cao nhất
→ Optimize chi tiêu đến từng dimension
```

## 6.3 Cấu trúc Dashboard

### Dashboard Level 1: Overview (Nhìn mỗi sáng)

```
┌─────────────────────────────────────────────────────────────────┐
│                    DAILY PERFORMANCE OVERVIEW                    │
│                    Date: 2026-04-03                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  TODAY          YESTERDAY       WoW CHANGE      MTD              │
│  ─────          ─────────       ──────────      ───              │
│  Leads: 1,250   Leads: 1,180   +5.9%           Leads: 3,750     │
│  Rev:   $8,400  Rev:   $7,900  +6.3%           Rev:   $24,500   │
│  Cost:  $5,600  Cost:  $5,400  +3.7%           Cost:  $16,200   │
│  Margin: $2,800 Margin: $2,500 +12.0%          Margin: $8,300   │
│  AR:    38.2%   AR:    36.5%   +1.7pp          AR:    37.1%     │
│  ROI:   50.0%   ROI:   46.3%   +3.7pp          ROI:   51.2%    │
│                                                                  │
│  ⚠️ ALERTS:                                                     │
│  • Offer #1234 (RU) AR dropped to 28% (threshold: 35%)         │
│  • Offer #5678 (BR) OOS - stock depleted                        │
│  • Affiliate #890 trash rate 45% (threshold: 20%)               │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

### Dashboard Level 2: By GEO

```
┌────────────────────────────────────────────────────────────────┐
│                    PERFORMANCE BY GEO                           │
├──────┬───────┬────────┬───────┬────────┬──────┬───────┬───────┤
│ GEO  │ Leads │ Apprvd │ AR    │ Rev    │ Cost │ Margin│ ROI   │
├──────┼───────┼────────┼───────┼────────┼──────┼───────┼───────┤
│ RU   │ 450   │ 180    │ 40.0% │ $2,700 │$1,800│ $900  │ 50.0% │
│ KZ   │ 200   │ 110    │ 55.0% │ $1,100 │ $660 │ $440  │ 66.7% │
│ UA   │ 150   │ 60     │ 40.0% │ $840   │ $540 │ $300  │ 55.6% │
│ TH   │ 180   │ 63     │ 35.0% │ $504   │ $378 │ $126  │ 33.3% │
│ VN   │ 120   │ 36     │ 30.0% │ $252   │ $180 │ $72   │ 40.0% │
│ BR   │ 100   │ 30     │ 30.0% │ $390   │ $270 │ $120  │ 44.4% │
│ MX   │ 50    │ 18     │ 36.0% │ $198   │ $126 │ $72   │ 57.1% │
├──────┼───────┼────────┼───────┼────────┼──────┼───────┼───────┤
│TOTAL │ 1,250 │ 497    │ 39.8% │ $5,984 │$3,954│$2,030 │ 51.3% │
└──────┴───────┴────────┴───────┴────────┴──────┴───────┴───────┘
```

### Dashboard Level 3: By Offer

```
┌──────────────────────────────────────────────────────────────────┐
│                    PERFORMANCE BY OFFER                           │
├──────┬──────────────┬─────┬──────┬───────┬──────┬───────┬───────┤
│ ID   │ Offer Name   │ GEO │Leads │ AR    │Trash │ Margin│ Status│
├──────┼──────────────┼─────┼──────┼───────┼──────┼───────┼───────┤
│ 1001 │ SlimFit Pro  │ RU  │ 200  │ 45.0% │ 12%  │ $800  │ ✅    │
│ 1002 │ JointFlex    │ RU  │ 150  │ 38.0% │ 15%  │ $450  │ ✅    │
│ 1003 │ ManPower     │ KZ  │ 120  │ 52.0% │ 10%  │ $360  │ ✅    │
│ 1004 │ SkinGlow     │ TH  │ 100  │ 32.0% │ 18%  │ $120  │ ⚠️    │
│ 1005 │ HairMax      │ BR  │ 80   │ 28.0% │ 22%  │ $64   │ ⚠️    │
│ 1006 │ SlimFit V2   │ VN  │ 50   │ 25.0% │ 25%  │ $30   │ 🔴    │
│ 1007 │ VeinClear    │ UA  │ 40   │ 42.0% │ 8%   │ $120  │ ✅    │
├──────┴──────────────┴─────┴──────┴───────┴──────┴───────┴───────┤
│ ✅ = Healthy    ⚠️ = Needs attention    🔴 = Critical            │
└──────────────────────────────────────────────────────────────────┘
```

### Dashboard Level 4: By Affiliate

```
┌──────────────────────────────────────────────────────────────────┐
│                    TOP AFFILIATES PERFORMANCE                     │
├──────┬──────────────┬──────┬───────┬──────┬───────┬─────────────┤
│ ID   │ Name         │Leads │ AR    │Trash │ Rev   │ Trend (7d)  │
├──────┼──────────────┼──────┼───────┼──────┼───────┼─────────────┤
│ A001 │ MediaPro     │ 350  │ 48.0% │ 8%   │$2,100 │ ↑ +12%     │
│ A002 │ ClickMaster  │ 280  │ 42.0% │ 12%  │$1,540 │ → stable   │
│ A003 │ TrafficKing  │ 200  │ 35.0% │ 15%  │ $840  │ ↓ -8%      │
│ A004 │ NutraBuyer   │ 150  │ 28.0% │ 22%  │ $420  │ ↓ -15%     │
│ A005 │ NewGuy       │ 30   │ 20.0% │ 35%  │ $36   │ 🔴 NEW     │
└──────┴──────────────┴──────┴───────┴──────┴───────┴─────────────┘

ACTIONS NEEDED:
• A003 TrafficKing: AR declining, investigate traffic source changes
• A004 NutraBuyer: High trash rate, issue warning
• A005 NewGuy: Trash rate 35%, pause and review
```

## 6.4 Các báo cáo cần làm

### Daily Report (Mỗi sáng, 9-10AM)

```
DAILY REPORT FORMAT:
════════════════════

1. HEADLINE METRICS (so với hôm qua & tuần trước)
   - Total leads
   - Total approved
   - Overall AR
   - Total revenue / cost / margin
   - Overall ROI

2. TOP MOVERS (thay đổi lớn nhất)
   - Offer/GEO tăng mạnh nhất
   - Offer/GEO giảm mạnh nhất

3. ALERTS & ISSUES
   - Offers dưới threshold
   - Affiliates có vấn đề
   - OOS alerts
   - Tech issues

4. ACTION ITEMS
   - Cần pause gì?
   - Cần escalate gì?
   - Cần review gì?

Gửi cho: CMO, AM team lead, AR team lead
Format: Email/Slack
```

### Weekly Report (Mỗi thứ Hai)

```
WEEKLY REPORT FORMAT:
═════════════════════

1. EXECUTIVE SUMMARY (3-5 bullets)

2. WEEK PERFORMANCE vs TARGETS
   - Bảng so sánh actual vs target

3. GEO BREAKDOWN
   - Performance by GEO with trends

4. OFFER ANALYSIS
   - New offers launched
   - Offers paused/killed
   - Top/bottom performers

5. AFFILIATE HIGHLIGHTS
   - New affiliates onboarded
   - Top performer changes
   - Quality issues

6. FINANCIAL SUMMARY
   - Revenue, Cost, Margin
   - Outstanding payments
   - Cash flow status

7. NEXT WEEK PRIORITIES
   - Plans and focus areas

Gửi cho: CMO, Board (if applicable)
```

### Monthly Report (Đầu tháng)

```
MONTHLY REPORT FORMAT:
══════════════════════

1. EXECUTIVE SUMMARY

2. P&L OVERVIEW
   - Tổng revenue, cost, margin
   - Month-over-month comparison
   - Variance vs budget

3. GEO DEEP DIVE
   - Mỗi GEO: performance, trends, opportunities, risks

4. OFFER PORTFOLIO REVIEW
   - Portfolio composition
   - Lifecycle status (new/growing/stable/declining)
   - Kill/launch decisions

5. AFFILIATE BASE ANALYSIS
   - Active vs churned
   - Tier distribution
   - Concentration risk

6. OPERATIONAL METRICS
   - SLA compliance
   - Escalation count & resolution time
   - Process improvements

7. STRATEGIC RECOMMENDATIONS
   - Scale opportunities
   - Risk mitigation
   - Resource needs

8. NEXT MONTH FORECAST
   - Volume projections by GEO
   - Revenue forecast
   - Key milestones

Gửi cho: CMO, CEO/COO, Board
```

## 6.5 Metrics Deep Dive — Cách tính & ý nghĩa

### Core Metrics Formulas

```
CR (Conversion Rate) = Leads / Clicks × 100%
├── Click → Lead: phản ánh landing page quality
├── Benchmark: 5-15% cho nutra COD
└── Low CR? → LP issue, traffic mismatch, or offer fatigue

AR (Approval Rate) = Approved / Total Leads × 100%
├── Phản ánh toàn bộ chuỗi: traffic quality + call center + delivery
├── Benchmark: 30-55% tùy GEO
└── Low AR? → nhiều nguyên nhân, cần phân tích sâu

Trash Rate = Trash Leads / Total Leads × 100%
├── Phản ánh traffic quality
├── Target: < 15%
└── High trash? → bot traffic, incentivized traffic, or fraud

EPL (Earnings Per Lead) = Total Revenue / Total Leads
├── Bao nhiêu tiền kiếm được per lead
├── EPL > CPL = có lãi
└── Ví dụ: EPL $4.50, CPL $3.00 → ROI = 50%

EPC (Earnings Per Click) = Total Revenue / Total Clicks
├── Bao nhiêu tiền kiếm được per click
├── So sánh với CPC (cost per click) để biết profitable
└── Ví dụ: EPC $0.45, CPC $0.20 → có lãi

ROI = (Revenue - Cost) / Cost × 100%
├── Phản ánh profitability
├── Target: > 30%
├── ROI 0% = hòa vốn
└── ROI < 0% = lỗ

Margin Rate = (Revenue - Payout) / Revenue × 100%
├── Network giữ lại bao nhiêu %
├── Target: 20-40%
└── Margin quá thấp → rủi ro, margin quá cao → affiliate sẽ đi

Cap Fill Rate = Actual Leads / Cap × 100%
├── Bao nhiêu % cap đang được sử dụng
├── < 70% = under-utilized
├── > 95% = cần thêm cap
└── 100% = affiliates đang bị reject leads → bad UX
```

### Advanced Metrics

```
Effective AR = Approved / (Total Leads - Trash) × 100%
├── AR thực sau khi loại trash
└── Cho thấy quality thực sự

Confirm-to-Approve Ratio = Approved / Confirmed × 100%
├── % đơn confirmed mà thực sự deliver thành công
├── Phản ánh delivery quality
└── Low? → logistics issue

Time-to-Call = Thời gian trung bình từ lead → first call
├── Target: < 15 phút
├── > 1 giờ = bad
└── Impact trực tiếp lên confirm rate

Lead-to-Cash Days = Số ngày từ lead → nhận tiền
├── Cash flow indicator
├── Shorter = better
└── Typical: 30-60 ngày
```

## 6.6 Alert System — Khi nào cần hành động?

### Thiết lập alert thresholds:

```
CRITICAL (Hành động NGAY trong 1 giờ):
├── AR drop > 15% so với 7-day average
├── OOS on key offer
├── Tracking broken (0 leads khi expected > 0)
├── Affiliate trash rate > 40%
└── Advertiser payment overdue > 7 ngày

WARNING (Review trong ngày):
├── AR drop 5-15%
├── Cap fill rate < 50%
├── New affiliate trash rate > 25%
├── Offer volume drop > 20% day-over-day
└── Margin < 20% on any offer

INFO (Review hàng tuần):
├── Affiliate churn
├── GEO composition shift
├── Seasonal pattern changes
└── Competitor payout changes
```

## 6.7 Cách đọc Dashboard — Workflow hàng ngày

```
MORNING ROUTINE (9:00 - 9:30 AM):
═══════════════════════════════════

Step 1: Mở Overview Dashboard
├── Leads hôm qua vs ngày trước, vs tuần trước
├── Revenue/Margin trending up hay down?
└── Có alert nào critical không?

Step 2: Check GEO Performance
├── GEO nào đang healthy (AR > threshold)?
├── GEO nào đang decline?
└── Any GEO with 0 leads? (possible tracking issue)

Step 3: Check Top Offers
├── Top 10 offers by volume — AR stable?
├── Any offer below threshold?
└── Cap fill rate?

Step 4: Check Affiliates
├── Top 10 affiliates — volume/quality OK?
├── Any affiliate with sudden volume spike? (verify quality)
├── New affiliates — trash rate acceptable?

Step 5: Check Financials
├── Yesterday's margin
├── Any payment overdue?
└── Cash flow forecast

Step 6: Action Items
├── List issues found
├── Prioritize (Critical > Warning > Info)
├── Assign actions (self, AM team, AR team, tech)
└── Update daily report
```
