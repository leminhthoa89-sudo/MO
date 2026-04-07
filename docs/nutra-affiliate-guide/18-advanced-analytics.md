# Chương 18: Advanced Analytics, Forecasting & Dashboard Examples

## 18.1 Cohort Analysis chuyên sâu

### Lead Cohort — AR maturation curve

```
VÍ DỤ THỰC TẾ: Offer KetoBurn Russia
Mỗi row = 1 "đợt" leads (cohort theo tuần vào)
Columns = AR tích lũy theo thời gian sau khi lead vào

APPROVAL RATE MATURATION TABLE
══════════════════════════════════════════════════════════════════
Cohort     │Leads│Day3 │Day7 │Day14│Day21│Day30│Final│Trend
(lead week)│     │  AR │  AR │  AR │  AR │  AR │  AR │
───────────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼──────
Mar 3-9    │ 980 │ 8.2%│22.4%│36.8%│41.2%│43.5%│44.1%│ —
Mar 10-16  │1,050│ 7.8%│21.1%│35.2%│40.0%│42.8%│43.5%│ ↓-0.6
Mar 17-23  │1,120│ 7.5%│20.5%│33.8%│38.5%│41.0%│ ??? │ ↓-1.4
Mar 24-30  │1,200│ 6.9%│19.2%│32.1%│ ??? │ ??? │ ??? │ ↓-1.7
Mar 31-Apr6│1,350│ 6.1%│17.8%│ ??? │ ??? │ ??? │ ??? │ ↓-1.4
Apr 7-13   │1,400│ 5.5%│ ??? │ ??? │ ??? │ ??? │ ??? │ ↓-2.3
───────────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴──────

CÁCH ĐỌC:
• Day3 AR đang giảm mỗi tuần: 8.2% → 5.5%
• Đây là EARLY WARNING: final AR cũng sẽ giảm tương ứng
• Pattern: Day3 thường = 18-20% of Final AR
  → Day3 = 5.5% → Final AR estimated ≈ 28-30%
  → SO VỚI target 40%+ → ĐANG CÓ VẤN ĐỀ LỚN

ACTION:
• Đừng đợi Final AR confirm (30 ngày nữa mới biết!)
• Day3 / Day7 là leading indicators → act NOW
• Investigate root cause (traffic quality? call center?)
```

### Revenue Cohort — LTV Tracking

```
CUSTOMER LTV TABLE (nếu có rebill/repeat purchase)
══════════════════════════════════════════════════════════════
First       │ Cust │Month1│Month2│Month3│Month4│Month5│Month6
Purchase    │ Count│  Rev │  Rev │  Rev │  Rev │  Rev │  Rev
────────────┼──────┼──────┼──────┼──────┼──────┼──────┼──────
Jan 2026    │  850 │$34.0K│$8.5K │$5.1K │$3.4K │$2.2K │$1.7K
Feb 2026    │  920 │$36.8K│$9.2K │$5.5K │$3.7K │$2.4K │ ???
Mar 2026    │1,050 │$42.0K│$10.5K│$6.3K │ ???  │ ???  │ ???
Apr 2026    │1,150 │$46.0K│ ???  │ ???  │ ???  │ ???  │ ???
────────────┴──────┴──────┴──────┴──────┴──────┴──────┴──────

INSIGHT:
• Month 2 revenue ≈ 25% of Month 1 (repeat purchase rate)
• Month 3 ≈ 15% of Month 1 (declining but still significant)
• 6-month LTV ≈ $65 per customer (vs CAC ~$25)
• LTV:CAC ratio = 2.6:1 → healthy

TẠI SAO QUAN TRỌNG:
Advertiser thường chỉ pay CPA cho first purchase.
Nhưng nếu bạn biết LTV cao → negotiate higher payout:
"Khách hàng chúng tôi gửi có LTV $65, cao hơn 20% average.
Chúng tôi xứng đáng payout tốt hơn."
```

## 18.2 Funnel Analysis — Nhiều ví dụ

### Full funnel theo GEO

```
FUNNEL COMPARISON: RUSSIA vs BRAZIL vs THAILAND
═══════════════════════════════════════════════════════════════

                    RUSSIA          BRAZIL          THAILAND
                    ──────          ──────          ────────
Impressions         500,000         300,000         400,000
    CTR             1.8%            2.2%            2.5%
Clicks              9,000           6,600           10,000
    CR              11.0%           7.5%            8.0%
Leads               990             495             800
    Contact Rate    88%             82%             85%
Contacted           871             406             680
    Confirm Rate    60%             55%             52%
Confirmed           523             223             354
    Ship Rate       96%             90%             93%
Shipped             502             201             329
    Delivery Rate   78%             62%             72%
Approved            392             125             237
    
OVERALL AR          39.6%           25.3%           29.6%
    
BOTTLENECK          Delivery (78%)  Delivery (62%)  Confirm (52%)
                    Vùng xa chậm    Logistics BR    CC quality TH
                    
ACTION              Focus metro     Local warehouse Retrain CC
                    areas           + better courier agents
```

### Funnel by Traffic Source (cùng 1 offer)

```
OFFER: KetoBurn Russia — FUNNEL BY TRAFFIC SOURCE
═══════════════════════════════════════════════════════════════

                    FACEBOOK        NATIVE (MGID)   PUSH
                    ────────        ─────────────    ────
Clicks              5,000           3,000            8,000
    CR              12.5%           7.0%             3.5%
Leads               625             210              280
    Trash Rate      8.0%            14.0%            28.0%
Clean Leads         575             181              202
    Confirm Rate    62%             58%              42%
Confirmed           357             105              85
    Approve Rate    78%             75%              65%
Approved            278             79               55

OVERALL AR          44.5%           37.6%            19.6%
CPL                 $4.00           $5.50            $1.20
CPA (per approved)  $8.99           $14.62           $6.11
Payout              $10.00          $10.00           $10.00
ROI                 +11.2%          -31.6%           +63.6%

INSIGHT:
• Facebook: best quality (AR 44.5%) but highest CPL
• Push: lowest CPL nhưng trash 28% → AR thấp → NHƯNG ROI cao nhất!
• Native: worst of both worlds cho offer này → CONSIDER PAUSE
• Push ROI cao NHƯNG volume thấp và trash rate borderline

DECISION:
├── Facebook: maintain, try to lower CPL
├── Native: pause cho offer này, redirect budget
├── Push: keep NHƯNG set trash threshold 25% auto-pause
└── Test TikTok as alternative
```

## 18.3 Dashboard Examples — Chi tiết

### Dashboard 1: CEO/CMO Executive Overview

```
╔═══════════════════════════════════════════════════════════════╗
║           EXECUTIVE DASHBOARD — APRIL 2026                    ║
╠═══════════════════════════════════════════════════════════════╣
║                                                               ║
║  ┌─── REVENUE ──────┐  ┌─── MARGIN ───────┐  ┌─── ROI ──┐  ║
║  │    $298,500       │  │    $105,475      │  │   54.6%   │  ║
║  │    ↑ +8.5% MoM   │  │    ↑ +9.6% MoM  │  │   ↑ +1.2  │  ║
║  │    vs $310K target│  │    vs $108K tgt  │  │   pp MoM  │  ║
║  │    96.3% achieved │  │    97.2% achieved│  │           │  ║
║  └──────────────────┘  └──────────────────┘  └───────────┘  ║
║                                                               ║
║  ┌─── VOLUME ───────┐  ┌─── QUALITY ──────┐  ┌── ALERTS ─┐  ║
║  │  Leads: 58,400   │  │  AR: 38.5%       │  │  🔴 2     │  ║
║  │  Approved: 22,480│  │  Trash: 12.9%    │  │  🟡 3     │  ║
║  │  ↑ +7.7% MoM    │  │  Both within     │  │  🟢 12    │  ║
║  │                  │  │  thresholds ✅   │  │           │  ║
║  └──────────────────┘  └──────────────────┘  └───────────┘  ║
║                                                               ║
║  REVENUE TREND (Daily, last 30 days)                         ║
║  $15K ┤                                                      ║
║       │        ╭─╮   ╭──╮  ╭─╮                              ║
║  $12K ┤   ╭──╮│ │╭─╮│  ╰──╯ ╰╮  ╭──╮  ╭─╮                ║
║       │╭──╯  ╰╯ ╰╯ ╰╯       ╰──╯  ╰──╯ ╰──╮              ║
║  $9K  ┤╯                                     ╰──            ║
║       │                                                      ║
║  $6K  ┤                                                      ║
║       └──────────────────────────────────────────────        ║
║        Mar 7    Mar 14   Mar 21   Mar 28   Apr 4             ║
║                                                               ║
║  REVENUE BY GEO (Pie chart)          TOP ISSUES:             ║
║  ┌──────────────────────┐    ┌─────────────────────────┐     ║
║  │  RU  ████████  36.3% │    │ 🔴 Brazil AR 25% (3wk↓)│     ║
║  │  KZ  ████      12.5% │    │ 🔴 Indonesia AR 21%    │     ║
║  │  UA  ████      12.7% │    │ 🟡 TH delivery delay   │     ║
║  │  TH  ██         6.0% │    │ 🟡 VN trash rate 18%   │     ║
║  │  BR  ██         5.2% │    │ 🟡 A10 probation       │     ║
║  │  Other ██████  27.3% │    └─────────────────────────┘     ║
║  └──────────────────────┘                                    ║
╚═══════════════════════════════════════════════════════════════╝
```

### Dashboard 2: GEO Deep Dive — Russia

```
╔═══════════════════════════════════════════════════════════════╗
║           GEO DASHBOARD: RUSSIA (RU) — April 2026            ║
╠═══════════════════════════════════════════════════════════════╣
║                                                               ║
║  Revenue: $108,360 │ Leads: 16,800 │ AR: 43.0% │ Margin: 40%║
║  ↑ +6.2% MoM      │ ↑ +5.8% MoM   │ → stable  │ → stable   ║
║                                                               ║
║  OFFERS IN RUSSIA                                            ║
║  ┌────────────┬──────┬──────┬──────┬───────┬───────┬───────┐ ║
║  │ Offer      │Leads │Apprd │  AR  │Trash% │Margin │Status │ ║
║  ├────────────┼──────┼──────┼──────┼───────┼───────┼───────┤ ║
║  │ KetoBurn   │6,200 │2,852 │46.0% │ 8.0%  │$11.4K │  🟢  │ ║
║  │ JointFlex  │4,650 │2,046 │44.0% │10.5%  │ $8.2K │  🟢  │ ║
║  │ ParaClean  │3,700 │1,554 │42.0% │13.0%  │ $6.2K │  🟢  │ ║
║  │ ManPower RU│1,500 │  630 │42.0% │11.0%  │ $2.5K │  🟢  │ ║
║  │ DiabetCtrl │  750 │  278 │37.0% │15.0%  │ $1.1K │  🟡  │ ║
║  └────────────┴──────┴──────┴──────┴───────┴───────┴───────┘ ║
║                                                               ║
║  AR TREND — 12 WEEKS                                         ║
║  50% ┤                                                       ║
║      │  ●──●──●──●                                           ║
║  45% ┤           ╲●──●──●──●──●──●                          ║
║      │                              ╲●──●                    ║
║  40% ┤                                                       ║
║      │── ── ── ── ── ── ── ── ── ── ── ── target (40%)      ║
║  35% ┤                                                       ║
║      └─W3──W4──W5──W6──W7──W8──W9─W10─W11─W12─W13─W14─     ║
║                                                               ║
║  TOP AFFILIATES (Russia)                                     ║
║  ┌──────────────┬──────┬──────┬──────┬────────┬───────────┐  ║
║  │ Affiliate    │Leads │  AR  │Trash │Payout  │7d Trend   │  ║
║  ├──────────────┼──────┼──────┼──────┼────────┼───────────┤  ║
║  │ MediaPro A01 │4,200 │47.2% │ 7.5% │ $17.8K │ ↑ +6%    │  ║
║  │ ClickMax A02 │3,500 │44.0% │ 9.0% │ $13.9K │ → +1%    │  ║
║  │ RU-Dgtl  A09 │2,800 │45.5% │ 8.5% │ $11.5K │ → +2%    │  ║
║  │ TrafKing A03 │2,100 │38.0% │14.0% │ $ 7.2K │ ↓ -5%    │  ║
║  │ Others (8)   │4,200 │40.2% │13.5% │ $15.2K │ → +1%    │  ║
║  └──────────────┴──────┴──────┴──────┴────────┴───────────┘  ║
║                                                               ║
║  ⚠️ A03 declining 3 weeks — AM scheduled check-in Monday    ║
║                                                               ║
║  SEASONAL NOTE: Pre-summer weight loss season starting.      ║
║  Expect KetoBurn volume +20-30% in May-June.                ║
║  → Action: Confirm call center capacity with advertiser.     ║
╚═══════════════════════════════════════════════════════════════╝
```

### Dashboard 3: Offer Performance Card

```
╔═══════════════════════════════════════════════════════════════╗
║  OFFER CARD: KetoBurn — Russia (RU)                          ║
║  Category: Weight Loss │ Advertiser: NutraHealth LLC         ║
║  Active since: Jan 15 │ Status: 🟢 KEY OFFER               ║
╠═══════════════════════════════════════════════════════════════╣
║                                                               ║
║  KEY METRICS (MTD April)                                     ║
║  ┌──────────┬──────────┬──────────┬──────────┬──────────┐    ║
║  │  Leads   │ Approved │    AR    │   Rev    │  Margin  │    ║
║  │  6,200   │  2,852   │  46.0%   │ $42.8K   │ $11.4K  │    ║
║  │  +5.8%↑  │  +7.1%↑  │ +0.5pp↑  │  +8.2%↑  │ +9.6%↑ │    ║
║  └──────────┴──────────┴──────────┴──────────┴──────────┘    ║
║                                                               ║
║  DAILY TREND (last 14 days)                                  ║
║                                                               ║
║  Leads/day    AR%                                            ║
║  250│    ╭─╮          50%│                                   ║
║     │  ╭─╯ ╰╮╭─╮        │ ●──●──●──●                       ║
║  200│──╯     ╰╯ ╰──  45%│              ●──●──●──●           ║
║     │                    │                        ●──●       ║
║  150│                 40%│                                   ║
║     └──────────────      └──────────────                     ║
║      Mar24    Apr4        Mar24    Apr4                       ║
║                                                               ║
║  UNIT ECONOMICS                                              ║
║  ┌─────────────────────────────────────────────────────┐     ║
║  │ Revenue/approved:  $15.00                           │     ║
║  │ Payout/approved:   $10.50 (A01 gets $11)           │     ║
║  │ Margin/approved:   $ 4.50 (30.0%)                  │     ║
║  │ Daily approved:    ~204                             │     ║
║  │ Daily margin:      ~$918                            │     ║
║  │ Monthly margin:    ~$27,540 (projected)            │     ║
║  │ Cap:               250/day (82% utilized)          │     ║
║  │ Cap headroom:      46 leads/day available          │     ║
║  └─────────────────────────────────────────────────────┘     ║
║                                                               ║
║  BREAKDOWN BY AFFILIATE                                      ║
║  ┌────────────┬─────┬──────┬──────┬────────────────────────┐ ║
║  │ Affiliate  │Leads│  AR  │Trash │ AR vs Offer Average    │ ║
║  ├────────────┼─────┼──────┼──────┼────────────────────────┤ ║
║  │ A01        │2,400│48.5% │ 6.0% │ ████████████████▓ +2.5│ ║
║  │ A02        │1,800│46.0% │ 8.5% │ ███████████████▓  0.0 │ ║
║  │ A09        │1,200│45.0% │ 9.0% │ ██████████████▓  -1.0 │ ║
║  │ A03        │  600│38.0% │14.0% │ ██████████▓      -8.0 │ ║
║  │ A05        │  200│42.0% │12.0% │ ████████████▓    -4.0 │ ║
║  └────────────┴─────┴──────┴──────┴────────────────────────┘ ║
║                                                               ║
║  ⚠️ A03 AR 8pp below average — investigate traffic source   ║
║                                                               ║
║  FUNNEL BREAKDOWN                                            ║
║  Clicks      │████████████████████████████████████│ 56,000   ║
║  → CR 11.1%                                                  ║
║  Leads       │██████████████████                  │  6,200   ║
║  → Trash 8%                                                  ║
║  Clean       │█████████████████                   │  5,704   ║
║  → Confirm 62%                                               ║
║  Confirmed   │██████████                          │  3,536   ║
║  → Deliver 80.7%                                             ║
║  Approved    │████████                            │  2,852   ║
║                                                               ║
║  BOTTLENECK: Delivery rate (80.7%)                           ║
║  → 19.3% confirmed but not delivered                         ║
║  → Investigate: delivery time by region?                     ║
╚═══════════════════════════════════════════════════════════════╝
```

### Dashboard 4: Affiliate Risk Monitor

```
╔═══════════════════════════════════════════════════════════════╗
║           AFFILIATE RISK MONITOR — April 5, 2026             ║
╠═══════════════════════════════════════════════════════════════╣
║                                                               ║
║  CONCENTRATION RISK                                          ║
║  ┌─────────────────────────────────────────────────────────┐ ║
║  │ Top 1 (A01):  18.8% of revenue  [████████░░] ⚠️<20%   │ ║
║  │ Top 3:        47.2% of revenue  [█████████░] ⚠️<50%   │ ║
║  │ Top 5:        63.1% of revenue  [████████████] 🔴>60% │ ║
║  │ Top 10:       81.4% of revenue  [████████████████] !!  │ ║
║  └─────────────────────────────────────────────────────────┘ ║
║  → ACTION: Recruit 5+ new Tier B affiliates to reduce       ║
║    concentration below 55% for top 5                         ║
║                                                               ║
║  QUALITY HEATMAP                                             ║
║  ┌────────────┬───────────────────────────────────┬────────┐ ║
║  │ Affiliate  │ Trash Rate (30d rolling)          │ Trend  │ ║
║  ├────────────┼───────────────────────────────────┼────────┤ ║
║  │ A01        │ ██░░░░░░░░░░░░░░░░░░  7.5%       │ →      │ ║
║  │ A02        │ ████░░░░░░░░░░░░░░░░  9.0%       │ →      │ ║
║  │ A09        │ ████░░░░░░░░░░░░░░░░  8.5%       │ →      │ ║
║  │ A04        │ ██████░░░░░░░░░░░░░░ 12.1%       │ ↑      │ ║
║  │ A03        │ ████████░░░░░░░░░░░░ 14.3%       │ ↑ ⚠️   │ ║
║  │ A05        │ █████████░░░░░░░░░░░ 15.5%       │ →      │ ║
║  │ A07        │ ████████░░░░░░░░░░░░ 16.0%       │ →      │ ║
║  │ A06        │ ███████████░░░░░░░░░ 18.3%       │ ↑ ⚠️   │ ║
║  │ A08        │ ██████░░░░░░░░░░░░░░ 12.3%       │ ↓      │ ║
║  │ A10        │ █████████████░░░░░░░ 23.6%       │ ↑ 🔴   │ ║
║  ├────────────┼───────────────────────────────────┼────────┤ ║
║  │            │ ░░░░░░░░░░|░░░░░░░░░|░░░░░░░░░░ │        │ ║
║  │            │ 0%       15%       25%      40%  │        │ ║
║  │            │  🟢 OK    │🟡 Watch │🔴 Action   │        │ ║
║  └────────────┴───────────────────────────────────┴────────┘ ║
║                                                               ║
║  FRAUD ALERTS (Last 7 days)                                  ║
║  ┌─────────────────────────────────────────────────────────┐ ║
║  │ 🔴 A10: Trash 23.6%, trending up. Probation week 2.    │ ║
║  │    → Decision needed by Apr 9                           │ ║
║  │ ⚠️ A06: Trash 18.3%, volume up 15%. Quality declining.  │ ║
║  │    → Warning issued Apr 4                               │ ║
║  │ ⚠️ A03: AR declining 3 weeks. Possible source change.   │ ║
║  │    → AM check-in scheduled Apr 7                        │ ║
║  │ ℹ️ A11: New affiliate, week 1. 45 leads/day. Monitoring.│ ║
║  └─────────────────────────────────────────────────────────┘ ║
╚═══════════════════════════════════════════════════════════════╝
```

### Dashboard 5: Financial Overview

```
╔═══════════════════════════════════════════════════════════════╗
║           FINANCIAL DASHBOARD — March 2026 (Closed)          ║
╠═══════════════════════════════════════════════════════════════╣
║                                                               ║
║  P&L SUMMARY                                                 ║
║  ┌────────────────────┬──────────┬──────────┬───────────────┐║
║  │                    │  Actual  │  Budget  │  Var          │║
║  ├────────────────────┼──────────┼──────────┼───────────────┤║
║  │ Revenue            │ $298,500 │ $310,000 │ -$11,500 -3.7%│║
║  │ ├── CIS            │ $170,150 │ $170,000 │    +$150 +0.1%│║
║  │ ├── Asia           │  $78,200 │  $82,000 │  -$3,800 -4.6%│║
║  │ └── Latam          │  $50,150 │  $58,000 │  -$7,850-13.5%│║
║  │                    │          │          │               │║
║  │ Payout             │($193,025)│($201,500)│  +$8,475 -4.2%│║
║  │ Gross Margin       │ $105,475 │ $108,500 │  -$3,025 -2.8%│║
║  │ Gross Margin %     │   35.3%  │   35.0%  │  +0.3pp       │║
║  │                    │          │          │               │║
║  │ OpEx               │ ($48,000)│ ($48,000)│     $0    0.0%│║
║  │ Net Profit         │  $57,475 │  $60,500 │  -$3,025 -5.0%│║
║  │ Net Margin %       │   19.3%  │   19.5%  │  -0.2pp       │║
║  └────────────────────┴──────────┴──────────┴───────────────┘║
║                                                               ║
║  REVENUE WATERFALL (Feb → Mar)                               ║
║  ┌─────────────────────────────────────────────────────────┐ ║
║  │ Feb Revenue         ████████████████████████ $275,000    │ ║
║  │ + New offers        ███                     +$12,500     │ ║
║  │ + Volume growth     █████                   +$18,200     │ ║
║  │ + Margin optimize   █                       + $3,100     │ ║
║  │ - Offers paused     ██                      - $6,200     │ ║
║  │ - AR decline        █                       - $4,100     │ ║
║  │ = Mar Revenue       █████████████████████████ $298,500   │ ║
║  └─────────────────────────────────────────────────────────┘ ║
║                                                               ║
║  CASH FLOW STATUS                                            ║
║  ┌─────────────────────────────────────────────────────────┐ ║
║  │ Cash available:           $52,000                       │ ║
║  │ Receivables (due ≤7d):    $45,200  ← NutraHealth       │ ║
║  │ Receivables (due ≤30d):   $68,500                       │ ║
║  │ Payables (next run):     ($38,400) ← Apr 7 payment     │ ║
║  │ Net position:             $127,300  ✅ Healthy          │ ║
║  │                                                         │ ║
║  │ ⚠️ BrazilNutra: $12,800 overdue 3 days                 │ ║
║  │ → AR team following up. Volume reduced as precaution.   │ ║
║  └─────────────────────────────────────────────────────────┘ ║
║                                                               ║
║  MARGIN BY GEO                                               ║
║  ┌──────┬──────────┬────────┬────────┬─────────┬───────────┐║
║  │ GEO  │ Revenue  │ Payout │ Margin │Margin % │ Target 35%│║
║  ├──────┼──────────┼────────┼────────┼─────────┼───────────┤║
║  │ RU   │ $108,360 │ $64,320│ $44,040│  40.6%  │ ████ ✅   │║
║  │ KZ   │  $37,184 │ $23,520│ $13,664│  36.7%  │ ███ ✅    │║
║  │ UA   │  $37,800 │ $23,400│ $14,400│  38.1%  │ ████ ✅   │║
║  │ TH   │  $17,952 │ $11,200│  $6,752│  37.6%  │ ███ ✅    │║
║  │ VN   │  $11,564 │  $8,200│  $3,364│  29.1%  │ ██ ⚠️    │║
║  │ PH   │  $10,800 │  $6,750│  $4,050│  37.5%  │ ███ ✅    │║
║  │ BR   │  $15,600 │ $10,800│  $4,800│  30.8%  │ ██ ⚠️    │║
║  │ MX   │  $11,484 │  $7,420│  $4,064│  35.4%  │ ███ ✅    │║
║  │ ID   │   $1,323 │   $880 │   $443 │  33.5%  │ ██ ⚠️    │║
║  └──────┴──────────┴────────┴────────┴─────────┴───────────┘║
║                                                               ║
║  ⚠️ VN margin 29.1% — below target. Payout too high vs rev. ║
║  ⚠️ BR margin 30.8% — declining with AR. Review payout.     ║
╚═══════════════════════════════════════════════════════════════╝
```

## 18.4 Forecasting

### Simple Forecast Model (Google Sheets)

```
MONTHLY REVENUE FORECAST — April 2026
══════════════════════════════════════════════════════════════════

For each active offer:

Offer      │GEO│Current │Adj   │Forecast│Est AR│Est    │Est
           │   │Leads/d │Factor│Leads/d │      │Appr/d │Rev/month
───────────┼───┼────────┼──────┼────────┼──────┼───────┼─────────
KetoBurn   │RU │  200   │ 1.15 │  230   │ 45%  │  104  │ $46,620
JointFlex  │RU │  150   │ 1.00 │  150   │ 44%  │   66  │ $29,700
ParaClean  │RU │  120   │ 0.95 │  114   │ 42%  │   48  │ $21,528
ManPower+  │KZ │  140   │ 1.20 │  168   │ 55%  │   92  │ $27,720
SlimFit    │UA │  130   │ 1.05 │  137   │ 42%  │   57  │ $17,271
SkinGlow   │TH │  110   │ 0.90 │   99   │ 33%  │   33  │ $ 7,821
SlimViet   │VN │  120   │ 1.10 │  132   │ 30%  │   40  │ $ 8,316
MaxPotency │BR │  100   │ 0.80 │   80   │ 27%  │   22  │ $ 8,424
HairMax    │MX │   65   │ 1.15 │   75   │ 37%  │   28  │ $ 9,135
Others     │Mix│  250   │ 1.00 │  250   │ 35%  │   88  │ $35,024
───────────┴───┴────────┴──────┴────────┴──────┴───────┴─────────
TOTAL FORECAST:                                         $211,559
+ New offers (test):                                    + $8,000
+ Seasonal uplift (Apr-May weight loss CIS):            +$15,000
───────────────────────────────────────────────────────────────
FORECAST RANGE: $315,000 (base) — $340,000 (optimistic)
vs Target $380,000: gap $40K-65K → NEED aggressive scaling

ADJUSTMENT FACTORS:
├── 1.15 = Scaling (adding affiliates, increasing cap)
├── 1.00 = Stable (no changes planned)
├── 0.95 = Slight decline expected
├── 0.80 = Known issues (BR delivery problem)
└── Seasonal: CIS weight loss peak April-June
```

## 18.5 Tài liệu tham khảo

### Analytics
- **"Lean Analytics"** — Alistair Croll & Benjamin Yoskovitz
- **Google Analytics Academy** — https://analytics.google.com/analytics/academy/
- Coursera: **"Business Metrics for Data-Driven Companies"** — Duke University

### Forecasting
- **"Forecasting: Principles and Practice"** — Rob Hyndman (FREE online: https://otexts.com/fpp3/)
- Excel Forecasting Functions — https://support.microsoft.com/en-us/office/forecast-functions

### Data Visualization
- **"Storytelling with Data"** — Cole Nussbaumer Knaflic
- **Data Visualization Catalogue** — https://datavizcatalogue.com
- **From Data to Viz** — https://www.data-to-viz.com — Decision tree for chart types
