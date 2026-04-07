# Chương 7: Đọc số liệu & Phân tích hiệu suất

## 7.1 Tư duy đọc số liệu

### Quy tắc #1: Luôn so sánh, KHÔNG nhìn số tuyệt đối

```
SAI:  "Hôm nay có 1,200 leads" → không biết tốt hay xấu
ĐÚNG: "Hôm nay 1,200 leads, tăng 8% vs hôm qua, giảm 3% vs tuần trước"

SAI:  "AR offer này 35%" → không biết tốt hay xấu
ĐÚNG: "AR 35%, thấp hơn benchmark GEO (42%), giảm 5pp vs tuần trước"
```

**So sánh với cái gì?**
- **DoD** (Day over Day): so với hôm qua
- **WoW** (Week over Week): so với cùng ngày tuần trước
- **MoM** (Month over Month): so với tháng trước
- **Benchmark**: so với target/KPI đã set
- **Peer**: so với offer/GEO/affiliate tương tự

### Quy tắc #2: Tìm nguyên nhân gốc (Root Cause)

```
Symptom: AR giảm từ 42% → 35%
                    ↓
Question 1: Giảm ở GEO nào?
    → Russia giảm, KZ stable
                    ↓
Question 2: Giảm ở offer nào trong Russia?
    → Offer SlimFit giảm, JointFlex stable
                    ↓
Question 3: Giảm ở affiliate nào trên SlimFit RU?
    → Affiliate A003 AR 22%, A001 vẫn 48%
                    ↓
Question 4: A003 thay đổi gì?
    → Đổi traffic source từ FB sang Push
                    ↓
ROOT CAUSE: Push traffic quality thấp hơn FB cho offer này
                    ↓
ACTION: Yêu cầu A003 quay lại FB hoặc giảm cap push traffic
```

### Quy tắc #3: Correlation ≠ Causation

```
Observation: AR giảm + Volume tăng đồng thời
    
CÓ THỂ:
a) Volume tăng → affiliate mới quality thấp → AR giảm (causal)
b) Mùa sale → nhiều người đặt bừa → cả volume và AR thay đổi (common cause)
c) Call center tuyển thêm nhân sự → handle nhiều hơn nhưng kém hơn (causal)

→ Cần investigate thêm trước khi kết luận
```

## 7.2 Scenario Analysis — Đọc số trong thực tế

### Scenario 1: AR giảm đột ngột

```
TÌNH HUỐNG:
Offer "JointFlex" Russia: AR từ 45% xuống 30% trong 3 ngày

DIAGNOSTIC CHECKLIST:
                                                        
1. Check Trash Rate        → Tăng từ 12% lên 28%       
   ╰→ NGUYÊN NHÂN CÓ THỂ: Traffic quality giảm         
                                                        
2. Check by Affiliate      → Affiliate mới A007 trash 55%
   ╰→ XÁC NHẬN: A007 đang gửi lead rác                 
                                                        
3. Check Traffic Source     → A007 chạy push traffic    
   ╰→ ROOT CAUSE: Push traffic → trash cao → AR tụt     

ACTION:
├── Immediate: Pause A007, set daily cap = 0
├── Short-term: Review tất cả affiliates chạy push cho offer này
├── Long-term: Thêm rule auto-pause affiliate khi trash > 25%
└── Follow-up: Check AR recover trong 2-3 ngày
```

### Scenario 2: Volume drop mà không rõ nguyên nhân

```
TÌNH HUỐNG:
Total leads giảm 30% (1,200 → 840) trong 2 ngày, AR stable

DIAGNOSTIC:

1. Check by GEO
   ╰→ Russia giảm 40%, others stable
   
2. Check by Affiliate (Russia)
   ╰→ Top affiliate A001 (350 leads/day) → 50 leads/day
   
3. Check A001 status
   ╰→ A001 báo: Facebook account bị ban
   
ROOT CAUSE: Top affiliate mất account FB → volume crash

ACTION:
├── Immediate: Reallocate cap cho các affiliates khác
├── Short-term: Help A001 recover (cung cấp offer alternatives)
├── Long-term: Reduce concentration risk
│   (Rule: No affiliate > 25% total volume)
└── Alert CMO: Revenue forecast giảm ~30% tuần này
```

### Scenario 3: Revenue tăng nhưng Margin giảm

```
TÌNH HUỐNG:
Revenue tăng 20%, nhưng Margin giảm từ 35% xuống 18%

DIAGNOSTIC:

1. Check Payout changes
   ╰→ Payout bump cho 3 top affiliates (+$2/lead)

2. Check Revenue from Advertiser
   ╰→ Stable, chưa thay đổi

3. Calculate impact
   ╰→ Payout tăng $2 × 500 approved leads = $1,000/day
   ╰→ Margin mất $1,000/day = $30,000/month

ROOT CAUSE: Payout bump không được offset bởi revenue increase

ACTION:
├── Negotiate higher revenue từ advertiser (leverage: volume tăng 20%)
├── Nếu advertiser không tăng → review payout bump
├── Set rule: Payout bump phải approved bởi Ops (bạn)
│   trước khi AM execute
└── Monitor margin daily cho đến khi resolve
```

### Scenario 4: Offer mới performance kém

```
TÌNH HUỐNG:
Offer mới "HairMax" Brazil, chạy 10 ngày:
- Leads: 80/day (cap: 100)
- AR: 22% (benchmark BR: 30-40%)
- Trash: 18%
- CR: 4% (thấp)

ANALYSIS:

1. CR thấp (4%)
   ╰→ Landing page có vấn đề hoặc traffic mismatch
   ╰→ Check: LP có Portuguese? → CÓ ✓
   ╰→ Check: LP design/copy tốt? → Trung bình, cần test alternatives

2. AR thấp (22%)
   ╰→ Check confirm rate at call center: 55% → OK
   ╰→ Check delivery rate: 40% → THẤP
   ╰→ Check delivery time: trung bình 18 ngày → QUÁ LÂU
   ╰→ ROOT CAUSE: Delivery time dài → khách đổi ý / quên

3. Trash 18% → acceptable

DECISION MATRIX:
├── CR fixable? → Có (test LP mới) → Worth trying
├── AR fixable? → Khó (delivery time là structural issue)
├── 10 ngày data đủ? → Cho AR thì chưa (delivery cycle 18 ngày)
│   → Leads ngày 1-3 mới biết AR thực

DECISION: Tiếp tục test thêm 7 ngày với LP mới,
          nhưng set max loss threshold $X.
          Nếu AR < 28% sau 20 ngày → KILL
```

### Scenario 5: Phát hiện Fraud

```
TÌNH HUỐNG:
Affiliate A010, tuần trước: 30 leads/day, AR 40%
Tuần này: 200 leads/day, AR 12%

RED FLAGS:
├── Volume spike 6x trong 1 tuần → bất thường
├── AR crash → lead quality rất thấp
├── Check lead data:
│   ├── Nhiều SĐT invalid
│   ├── Tên lặp lại patterns
│   ├── IP address clustered (cùng 1 khu vực nhỏ)
│   └── Submit time pattern: leads đến đều đặn mỗi 30 giây → BOT

DIAGNOSIS: Affiliate đang dùng bot/fake leads

ACTION:
├── NGAY LẬP TỨC: Pause affiliate (cap = 0)
├── Không trả tiền cho leads gian lận (hold payment)
├── Check các offer khác A010 đang chạy → cũng pause
├── Document evidence
├── Quyết định: cảnh cáo hay ban permanent
└── Review anti-fraud rules: thêm rule detect bot pattern
```

## 7.3 Phân tích chuyên sâu

### Cohort Analysis

```
Phân tích theo "đợt" lead (cohort = nhóm leads cùng ngày/tuần)

Ví dụ: Approval Rate by Lead Date (cho offer có delivery cycle 14 ngày)

Lead Date    │ Leads │ Day 7 AR │ Day 14 AR │ Day 21 AR │ Final AR
─────────────┼───────┼──────────┼───────────┼───────────┼─────────
Mar 1-7      │ 700   │ 15%      │ 32%       │ 38%       │ 40%
Mar 8-14     │ 750   │ 12%      │ 28%       │ 35%       │ 37%
Mar 15-21    │ 800   │ 10%      │ 25%       │ ???       │ ???
Mar 22-28    │ 900   │ 8%       │ ???       │ ???       │ ???

INSIGHT:
- Day 7 AR giảm dần: 15% → 12% → 10% → 8%
- Final AR cũng đang giảm: 40% → 37% → ???
- TREND: Quality đang deteriorate
- ACTION: Investigate ngay, đừng đợi final AR confirm
```

### Funnel Analysis

```
Full funnel breakdown cho 1 offer/GEO:

Impressions:    100,000     (100%)
    ↓ CTR: 2%
Clicks:         2,000       (2.0%)
    ↓ CR: 10%
Leads:          200         (0.2%)
    ↓ Contact Rate: 85%
Contacted:      170         (0.17%)
    ↓ Confirm Rate: 60%
Confirmed:      102         (0.10%)
    ↓ Ship Rate: 95%
Shipped:        97          (0.097%)
    ↓ Delivery Rate: 75%
Approved:       73          (0.073%)

OVERALL: 100,000 impressions → 73 approved = 0.073%

ĐÂU LÀ BOTTLENECK?
├── CTR 2% → OK cho nutra
├── CR 10% → Good
├── Contact Rate 85% → OK (15% unreachable)
├── Confirm Rate 60% → OK
├── Delivery Rate 75% → ← BOTTLENECK (25% không nhận hàng)

→ Focus: Tại sao 25% không nhận? Address sai? Giao chậm? Đổi ý?
```

### Trend Analysis

```
Weekly AR Trend — Offer "SlimFit" Russia

Week  │ AR    │ Trend │ ∆     │ Signal
──────┼───────┼───────┼───────┼────────────────
W1    │ 45%   │       │       │
W2    │ 43%   │ ↓     │ -2pp  │ Normal fluctuation
W3    │ 44%   │ ↑     │ +1pp  │ Normal fluctuation
W4    │ 42%   │ ↓     │ -2pp  │ Normal fluctuation
W5    │ 38%   │ ↓     │ -4pp  │ ⚠️ Watch closely
W6    │ 35%   │ ↓     │ -3pp  │ ⚠️ Declining trend
W7    │ 33%   │ ↓     │ -2pp  │ 🔴 ACTION NEEDED
W8    │ 30%   │ ↓     │ -3pp  │ 🔴 CRITICAL

Rule of thumb:
- 1-2pp fluctuation week-over-week = normal
- 3+ pp drop = investigate
- 3 consecutive weeks declining = ACTION required
- Below GEO benchmark = CRITICAL
```

## 7.4 KPI Targets — Bao nhiêu là "tốt"?

### Targets by GEO (Benchmark)

```
         │ AR     │ Trash  │ CR     │ Margin │ ROI
─────────┼────────┼────────┼────────┼────────┼───────
CIS      │ >40%   │ <15%   │ >8%    │ >25%   │ >40%
Asia     │ >30%   │ <18%   │ >6%    │ >20%   │ >30%
Latam    │ >30%   │ <15%   │ >5%    │ >25%   │ >35%

"Tốt":   Top 25% of offers đạt được
"OK":     Đạt benchmark
"Kém":    Dưới benchmark > 5pp
"Critical": Dưới benchmark > 10pp
```

### Traffic Light System

```
Dùng hệ thống đèn giao thông để nhanh chóng đánh giá:

🟢 GREEN (Healthy):
├── AR ≥ benchmark
├── Trash ≤ target
├── Volume ≥ 80% cap
├── Margin ≥ target
└── Trend: stable hoặc up

🟡 YELLOW (Watch):
├── AR 5-10pp dưới benchmark
├── Trash 5-10pp trên target
├── Volume 50-80% cap
├── Margin 10-20%
└── Trend: slight decline

🔴 RED (Action Required):
├── AR > 10pp dưới benchmark
├── Trash > 10pp trên target
├── Volume < 50% cap
├── Margin < 10%
└── Trend: declining > 2 weeks

⚫ BLACK (Kill):
├── AR < 20%
├── Trash > 35%
├── Volume near 0
├── Negative margin
└── No recovery plan viable
```

## 7.5 Financial Analysis cho MKT Ops

### P&L Statement mẫu (Monthly)

```
PROFIT & LOSS — MARCH 2026
════════════════════════════════════

                        Actual      Budget      Var %
REVENUE
├── CIS Revenue         $85,000     $80,000     +6.3%
├── Asia Revenue        $42,000     $45,000     -6.7%
├── Latam Revenue       $28,000     $25,000     +12.0%
├── Total Revenue       $155,000    $150,000    +3.3%

COST OF REVENUE
├── Affiliate Payouts   ($108,500)  ($105,000)  +3.3%
├── Total COGS          ($108,500)  ($105,000)  +3.3%

GROSS PROFIT            $46,500     $45,000     +3.3%
Gross Margin            30.0%       30.0%       —

OPERATING EXPENSES
├── Platform/Tech       ($5,000)    ($5,000)    0%
├── Team Salaries       ($15,000)   ($15,000)   0%
├── Other OpEx          ($3,000)    ($3,000)    0%
├── Total OpEx          ($23,000)   ($23,000)   0%

NET PROFIT              $23,500     $22,000     +6.8%
Net Margin              15.2%       14.7%       —
```

### Revenue Waterfall (Tháng này vs tháng trước)

```
Last Month Revenue:                     $142,000
+ New offers launched:                  + $8,000
+ Existing offers volume growth:        + $12,000
+ Payout optimization (margin improve): + $3,000
- Offers paused/killed:                 - $6,000
- AR decline on existing:               - $4,000
─────────────────────────────────────────────────
This Month Revenue:                     $155,000
Change:                                 + $13,000 (+9.2%)
```

## 7.6 Forecast — Dự báo

### Simple Forecast Method

```
NEXT MONTH FORECAST:

For each Offer/GEO combo:

Current daily leads × Expected days × Adjustment factor = Forecasted leads

Adjustment factors:
├── Scaling offer:    1.1 - 1.3 (expect growth)
├── Stable offer:     0.95 - 1.05 (small variance)
├── Declining offer:  0.7 - 0.9 (expect drop)
├── New offer:        High uncertainty (wide range)
└── Seasonal:         Historical data from same period last year

Example:
SlimFit RU: 200 leads/day × 30 days × 1.0 (stable) = 6,000 leads
AR expected: 42%
Approved: 2,520
Revenue: 2,520 × $14 = $35,280
Payout: 2,520 × $10 = $25,200
Margin: $10,080

(Repeat for each offer/GEO, sum up)
```

## 7.7 Presentation Tips — Trình bày số liệu cho CMO/Board

```
DO:
├── Lead with the CONCLUSION, then data
│   "Revenue tăng 9% nhờ scale thành công 3 offers mới tại Latam"
│   NOT "Offer A tăng 5%, Offer B tăng 3%, ..."
│
├── Use traffic light colors (green/yellow/red)
├── Show trends, not just snapshots
├── Always include ACTION ITEMS
├── Compare actual vs plan/target
└── Highlight risks AND opportunities

DON'T:
├── Show raw data without insight
├── Use too many decimals ($8,451.37 → $8,500)
├── Present problems without solutions
├── Bury bad news — call it out early
└── Use jargon with non-marketing stakeholders
```
