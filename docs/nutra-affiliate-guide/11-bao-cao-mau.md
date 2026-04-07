# Chương 11: Báo cáo mẫu — Tập đọc số thực tế

## 11.1 DAILY REPORT MẪU

```
══════════════════════════════════════════════════════════════════
                DAILY PERFORMANCE REPORT
                Date: Wednesday, April 2, 2026
                Prepared by: MKT Operations
══════════════════════════════════════════════════════════════════

1. HEADLINE METRICS
───────────────────────────────────────────────────────────────
                    Today      Yesterday   WoW         MTD
Clicks              28,450     27,100      +8.2%       56,300
Leads               2,185      2,040       +5.1%       4,280
Approved             836        802        +2.8%       1,650
Trash                287        245        +12.5%      540
Approval Rate       38.3%      39.3%      -1.0pp      38.6%
Trash Rate          13.1%      12.0%      +0.8pp      12.6%
Revenue            $11,704    $11,228      +1.5%      $23,100
Payout              $7,524     $7,218      +2.1%      $14,850
Margin              $4,180     $4,010      +4.2%       $8,250
Margin Rate         35.7%      35.7%       0.0pp      35.7%
Avg Payout/Appr     $9.00      $9.00       —           —
Avg Revenue/Appr   $14.00     $14.00       —           —
───────────────────────────────────────────────────────────────

2. PERFORMANCE BY GEO
───────────────────────────────────────────────────────────────
GEO   │Leads│Appr│ AR   │Trash│Trash%│ Rev    │Payout │Margin │ROI
──────┼─────┼────┼──────┼─────┼──────┼────────┼───────┼───────┼─────
RU    │ 620 │ 267│43.1% │  68 │11.0% │ $4,005 │$2,403 │$1,602 │66.7%
KZ    │ 310 │ 174│56.1% │  28 │ 9.0% │ $1,914 │$1,218 │ $696  │57.1%
UA    │ 280 │ 117│41.8% │  36 │12.9% │ $1,521 │ $936  │ $585  │62.5%
TH    │ 250 │  85│34.0% │  33 │13.2% │ $  680 │ $425  │ $255  │60.0%
VN    │ 220 │  62│28.2% │  40 │18.2% │ $  434 │ $310  │ $124  │40.0%
PH    │ 165 │  50│30.3% │  25 │15.2% │ $  400 │ $250  │ $150  │60.0%
BR    │ 180 │  45│25.0% │  30 │16.7% │ $  540 │ $360  │ $180  │50.0%
MX    │ 110 │  40│36.4% │  18 │16.4% │ $  440 │ $280  │ $160  │57.1%
ID    │  50 │  11│22.0% │   9 │18.0% │ $   77 │ $ 55  │ $  22 │40.0%
──────┼─────┼────┼──────┼─────┼──────┼────────┼───────┼───────┼─────
TOTAL │2,185│ 851│38.9% │ 287 │13.1% │$10,011 │$6,237 │$3,774 │60.5%
───────────────────────────────────────────────────────────────

⚠️ LƯU Ý: Approved count (851) ≠ Headline (836) vì headline dùng 
   data reconciled từ advertiser, bảng GEO dùng AffScale raw data.
   Discrepancy: 1.8% — within acceptable range (<3%).

3. TOP 15 OFFERS
───────────────────────────────────────────────────────────────
#  │ Offer              │GEO│Leads│Appr│ AR   │Trash%│Margin│Status
───┼────────────────────┼───┼─────┼────┼──────┼──────┼──────┼──────
1  │ KetoBurn           │RU │ 200 │  92│46.0% │ 8.0% │ $552 │ 🟢
2  │ JointFlex Pro      │RU │ 150 │  68│45.3% │10.0% │ $340 │ 🟢
3  │ ManPower Plus      │KZ │ 140 │  81│57.9% │ 7.1% │ $324 │ 🟢
4  │ SlimFit Ultra      │UA │ 130 │  55│42.3% │12.3% │ $275 │ 🟢
5  │ ParaClean          │RU │ 120 │  50│41.7% │14.2% │ $200 │ 🟢
6  │ ManPower Plus      │UA │  90 │  38│42.2% │11.1% │ $190 │ 🟢
7  │ SkinGlow Thai      │TH │ 110 │  42│38.2% │11.8% │ $168 │ 🟢
8  │ SlimFit Thai       │TH │  85 │  28│32.9% │15.3% │ $112 │ 🟡
9  │ MaxPotency         │BR │ 100 │  27│27.0% │15.0% │ $108 │ 🟡
10 │ ManPower Plus      │KZ │  80 │  46│57.5% │ 8.8% │ $ 92 │ 🟢
11 │ HairMax            │MX │  65 │  25│38.5% │13.8% │ $ 75 │ 🟢
12 │ SlimViet           │VN │ 120 │  35│29.2% │17.5% │ $ 70 │ 🟡
13 │ BeautyPH           │PH │  80 │  28│35.0% │13.8% │ $ 56 │ 🟢
14 │ KetoMax            │BR │  50 │  10│20.0% │20.0% │ $ 40 │ 🔴
15 │ GlowSkin ID        │ID │  35 │   7│20.0% │20.0% │ $ 14 │ 🔴
───────────────────────────────────────────────────────────────
🟢 Healthy (8)  🟡 Watch (3)  🔴 Critical (2)

4. TOP 10 AFFILIATES
───────────────────────────────────────────────────────────────
#  │ Affiliate      │Leads│Appr│ AR   │Trash%│Payout  │7d Trend
───┼────────────────┼─────┼────┼──────┼──────┼────────┼────────
1  │ MediaPro (A01) │ 420 │ 185│44.0% │ 9.5% │ $1,665 │ ↑ +8%
2  │ ClickMax (A02) │ 350 │ 144│41.1% │11.4% │ $1,296 │ → +1%
3  │ TrafficKing(A03│ 280 │ 106│37.9% │14.3% │ $  848 │ ↓ -6%
4  │ NutraBoss (A04)│ 240 │  98│40.8% │12.1% │ $  784 │ ↑ +4%
5  │ AdScale (A05)  │ 200 │  72│36.0% │15.5% │ $  576 │ → +2%
6  │ VietAds (A06)  │ 180 │  52│28.9% │18.3% │ $  364 │ ↑ +15%
7  │ LatamPro (A07) │ 150 │  50│33.3% │16.0% │ $  400 │ → +1%
8  │ ThaiMedia (A08)│ 130 │  48│36.9% │12.3% │ $  336 │ ↓ -3%
9  │ RU-Digital(A09)│ 110 │  49│44.5% │10.9% │ $  441 │ → 0%
10 │ NewBuyer (A10) │  55 │  14│25.5% │23.6% │ $   98 │ 🆕 Week2
───────────────────────────────────────────────────────────────

5. ALERTS & ISSUES
───────────────────────────────────────────────────────────────
🔴 CRITICAL:
• Offer KetoMax BR: AR 20.0%, dưới threshold 30%. 
  → Đã 5 ngày liên tiếp dưới 25%. RECOMMEND: Pause.
• Affiliate A10 (NewBuyer): Trash rate 23.6%, tăng từ 18% hôm qua.
  → Monitor thêm 24h, nếu > 25% → auto-pause.

⚠️ WARNING:
• VN trash rate 18.2% (threshold 18%). Sát ngưỡng.
  → Chủ yếu từ A06 (VietAds) trash 18.3%. Đã gửi warning.
• Offer SlimFit Thai: AR giảm 3pp WoW (36% → 33%).
  → Check: delivery time TH tăng từ 3 → 5 ngày tuần này.
• A03 (TrafficKing): Volume giảm 6% WoW.
  → AM team check: có chuyển volume sang network khác?

ℹ️ INFO:
• KZ performance đang peak — xem xét tăng cap ManPower Plus.
• A06 (VietAds) volume tăng 15% — quality cần monitor chặt.
• 2 offers mới đang trong test period (chưa đủ data report).

6. ACTION ITEMS
───────────────────────────────────────────────────────────────
Priority │ Action                              │ Owner    │ Due
─────────┼─────────────────────────────────────┼──────────┼────────
🔴 HIGH  │ Pause KetoMax BR                    │ Ops (You)│ Today
🔴 HIGH  │ Monitor A10 trash rate              │ AM Team  │ Tmrw
⚠️ MED   │ Investigate TH delivery delay       │ AR Team  │ Tmrw
⚠️ MED   │ Check A03 volume decline            │ AM Team  │ Tmrw
⚠️ MED   │ VN quality review (A06 focus)       │ Ops (You)│ Fri
🟢 LOW   │ Propose KZ cap increase             │ Ops (You)│ Fri
───────────────────────────────────────────────────────────────

══════════════════════════════════════════════════════════════════
```

---

## 11.2 WEEKLY REPORT MẪU

```
══════════════════════════════════════════════════════════════════
                   WEEKLY PERFORMANCE REPORT
                   Week 14 (Mar 30 — Apr 5, 2026)
                   Prepared by: MKT Operations
══════════════════════════════════════════════════════════════════

EXECUTIVE SUMMARY
─────────────────
• Revenue đạt $78,200 (+6.5% vs W13), vượt target $75,000.
• CIS tiếp tục là engine chính (58% revenue), KZ outperform.
• Brazil underperform: AR giảm liên tục 3 tuần, KetoMax BR paused.
• 1 offer mới (VeinClear UA) passed test, approved for scaling.
• 1 affiliate mới (A10 NewBuyer) đang trong probation, chất lượng 
  chưa đạt.

1. WEEK PERFORMANCE vs TARGET
───────────────────────────────────────────────────────────────
                 W14 Actual  W14 Target   Var%    W13 Actual  WoW%
Leads            15,120      14,500       +4.3%   14,350      +5.4%
Approved          5,810       5,800       +0.2%    5,520      +5.3%
AR               38.4%       40.0%       -1.6pp   38.5%      -0.1pp
Trash Rate       12.8%       <15%         ✅      12.5%      +0.3pp
Revenue         $78,200     $75,000       +4.3%  $73,400      +6.5%
Payout          $50,490     $48,500       +4.1%  $47,200      +7.0%
Margin          $27,710     $26,500       +4.6%  $26,200      +5.8%
Margin Rate      35.4%       35.3%       +0.1pp   35.7%      -0.3pp
───────────────────────────────────────────────────────────────

2. GEO BREAKDOWN (WEEKLY)
───────────────────────────────────────────────────────────────
GEO  │ Leads│ Appr│  AR  │Rev     │Margin  │Margin%│WoW Rev │Status
─────┼──────┼─────┼──────┼────────┼────────┼───────┼────────┼──────
RU   │4,250 │1,828│43.0% │$27,420 │$10,968 │40.0%  │ +5.2%  │ 🟢
KZ   │2,150 │1,199│55.8% │$13,189 │ $4,796 │36.4%  │+10.5%  │ 🟢
UA   │1,950 │  819│42.0% │$10,647 │ $4,095 │38.5%  │ +8.2%  │ 🟢
TH   │1,720 │  576│33.5% │ $4,608 │ $1,728 │37.5%  │ -2.1%  │ 🟡
VN   │1,530 │  428│28.0% │ $2,996 │ $  856 │28.6%  │ +4.8%  │ 🟡
PH   │1,140 │  342│30.0% │ $2,736 │ $1,026 │37.5%  │ +3.0%  │ 🟢
BR   │1,230 │  314│25.5% │ $3,768 │ $1,256 │33.3%  │ -8.4%  │ 🔴
MX   │  750 │  270│36.0% │ $2,970 │ $1,080 │36.4%  │ +5.7%  │ 🟢
ID   │  400 │   84│21.0% │ $  588 │ $  168 │28.6%  │ +2.0%  │ 🔴
─────┼──────┼─────┼──────┼────────┼────────┼───────┼────────┼──────
TOTAL│15,120│5,860│38.8% │$68,922*│$25,973 │37.7%  │ +6.5%  │
───────────────────────────────────────────────────────────────
* Revenue theo AffScale raw data. Reconciled revenue = $78,200 
  (bao gồm adjustment từ tuần trước)

GEO ANALYSIS:
• 🟢 KZ: Best performer. AR 55.8%, WoW +10.5%. ManPower Plus driving 
  growth. RECOMMEND: Increase cap from 350 to 500/day.
• 🟢 UA: Solid recovery. VeinClear UA passed test, contributing.
• 🟡 TH: Revenue giảm nhẹ -2.1%. SlimFit Thai AR declining (33%).
  Root cause: delivery partner delay. AR team following up.
• 🟡 VN: AR 28% — below benchmark (30%). Trash rate 18% sát threshold.
  A06 (VietAds) cần quality review.
• 🔴 BR: AR 25.5%, 3 tuần liên tiếp giảm (W12: 32%, W13: 28%, W14: 25.5%).
  KetoMax BR paused (W14 Day 3). MaxPotency BR cần review urgent.
• 🔴 ID: AR 21%. Volume quá thấp để kết luận. Tiếp tục test thêm 2 tuần.

3. OFFER PORTFOLIO SNAPSHOT
───────────────────────────────────────────────────────────────
Status    │ Count │ % Revenue │ Notes
──────────┼───────┼───────────┼────────────────────────────────
🟢 Key    │   8   │   72%     │ Stable, driving revenue
🟡 Watch  │   4   │   18%     │ Need optimization
🔴 Critical│  2   │    4%     │ 1 paused, 1 under review
🆕 Test   │   3   │    6%     │ VeinClear UA passed → scaling
──────────┼───────┼───────────┼
Total     │  17   │  100%     │

Changes this week:
• PAUSED: KetoMax BR (AR 20%, 5 days below threshold)
• PASSED TEST: VeinClear UA → moving to Scale phase
• NEW TEST: DiabetControl RU, SkinWhite TH (launched W14 Day 5)

4. AFFILIATE BASE
───────────────────────────────────────────────────────────────
                    W14       W13       Change
Active Affiliates   32        31        +1 (A10 NewBuyer onboarded)
Tier A (top)         5         5         0
Tier B (mid)        12        12         0
Tier C (small/new)  15        14        +1

Concentration Risk:
• Top 3 affiliates = 49% of total leads (target: <50%) ⚠️ borderline
• A01 alone = 19.4% (target: <20%) ⚠️ borderline

AFFILIATE ISSUES:
• A10 (NewBuyer): Probation week 2. Trash 23.6%. Warning issued.
  If no improvement by W15 → reduce cap or pause.
• A03 (TrafficKing): Volume declining 3 weeks in a row.
  AM check-in scheduled for Monday.

5. FINANCIAL SUMMARY
───────────────────────────────────────────────────────────────
                        W14         MTD (Apr 1-5)   Full Month Target
Revenue                $78,200     $78,200          $310,000
Payout                ($50,490)   ($50,490)         ($200,000)
Gross Margin           $27,710     $27,710          $110,000
Margin Rate             35.4%       35.4%            35.5%

Outstanding Receivables (from Advertisers):
• NutraHealth LLC:    $45,200 (due Apr 10) — on track
• BrazilNutra:        $12,800 (due Apr 5)  — ⚠️ 1 day overdue
• AsiaOffer Corp:      $8,500 (due Apr 15) — on track

Outstanding Payables (to Affiliates):
• Next payment run: Apr 7 (Monday)
• Total scheduled: $38,400
• Cash available: $52,000 ✅

6. NEXT WEEK PRIORITIES
───────────────────────────────────────────────────────────────
□ Urgent: Brazil review — decide MaxPotency BR: optimize or pause
□ Urgent: A10 quality decision by Wednesday
□ Important: KZ cap increase proposal → get advertiser confirmation
□ Important: TH delivery issue follow-up
□ Important: VN quality audit (A06 focus)
□ Standard: Launch 2 new test offers (DiabetControl RU, SkinWhite TH)
□ Standard: Monthly report prep (April full month)

══════════════════════════════════════════════════════════════════
```

---

## 11.3 MONTHLY REPORT MẪU (March 2026)

```
══════════════════════════════════════════════════════════════════
               MONTHLY PERFORMANCE REPORT — MARCH 2026
               Prepared by: MKT Operations
══════════════════════════════════════════════════════════════════

EXECUTIVE SUMMARY
─────────────────
March closed at $298,500 revenue (96.3% of $310K target), with 
margin $105,400 (34.0%). CIS contributed 57% of revenue and 
continues to be the growth engine. Latam underperformed due to 
Brazil AR decline (now under remediation). 3 new offers launched, 
2 passed test, 1 killed. Net affiliate base grew by 4.

1. P&L OVERVIEW
───────────────────────────────────────────────────────────────
                    Mar-26     Feb-26    MoM%     Mar Target   Var%
Revenue            $298,500   $275,000   +8.5%    $310,000    -3.7%
├── CIS            $170,150   $158,000   +7.7%    $170,000    +0.1%
├── Asia            $78,200    $72,000   +8.6%     $82,000    -4.6%
└── Latam           $50,150    $45,000  +11.4%     $58,000   -13.5%

Payout            ($193,025)  ($178,750)  +8.0%  ($201,500)   -4.2%
Gross Margin       $105,475    $96,250   +9.6%   $108,500    -2.8%
Gross Margin %       35.3%      35.0%   +0.3pp     35.0%    +0.3pp

OpEx               ($48,000)  ($47,500)  +1.1%   ($48,000)    0.0%
├── Team salaries   ($32,000)  ($32,000)    —     ($32,000)     —
├── Platform/Tech    ($8,500)   ($8,500)    —      ($8,500)     —
├── Other            ($7,500)   ($7,000)  +7.1%    ($7,500)     —

Net Profit          $57,475    $48,750  +17.9%    $60,500    -5.0%
Net Margin %         19.3%      17.7%   +1.6pp     19.5%    -0.2pp
───────────────────────────────────────────────────────────────

2. VOLUME & QUALITY
───────────────────────────────────────────────────────────────
                    Mar-26     Feb-26    MoM%     Target
Total Leads        58,400      54,200    +7.7%    60,000
Total Approved     22,480      20,900    +7.6%    23,500
Overall AR          38.5%       38.6%   -0.1pp    39.2%
Trash Rate          12.9%       12.2%   +0.7pp    <15.0%
Avg CPL (network)    $3.31       $3.30     —        —
Avg EPL              $5.11       $5.07   +0.8%      —
Avg Payout/Appr      $8.59       $8.55   +0.5%      —
Avg Revenue/Appr    $13.28      $13.16   +0.9%      —
───────────────────────────────────────────────────────────────

3. GEO DEEP DIVE
───────────────────────────────────────────────────────────────

RUSSIA 🟢
    Leads: 16,800 | Approved: 7,224 | AR: 43.0% | Rev: $108,360
    MoM: +6.2% revenue | Status: Strong, stable
    Key offers: KetoBurn (star), JointFlex (stable), ParaClean (stable)
    Notes: Pre-summer season starting, expect weight loss spike Apr-May

KAZAKHSTAN 🟢
    Leads: 8,300 | Approved: 4,648 | AR: 56.0% | Rev: $37,184
    MoM: +12.8% revenue | Status: Best performing, scaling
    Key offers: ManPower Plus (star, scaling)
    Notes: Approval rate consistently highest. Cap increase approved.

UKRAINE 🟢
    Leads: 7,500 | Approved: 3,150 | AR: 42.0% | Rev: $37,800
    MoM: +9.1% revenue | Status: Growing
    Key offers: SlimFit Ultra, ManPower Plus, VeinClear (new)
    Notes: VeinClear passed test, contributing to growth

THAILAND 🟡
    Leads: 6,800 | Approved: 2,244 | AR: 33.0% | Rev: $17,952
    MoM: +2.3% revenue | Status: Flat, AR concern
    Key offers: SkinGlow Thai (stable), SlimFit Thai (declining)
    Notes: Delivery delay impacting AR. AR team negotiating with advertiser.

VIETNAM 🟡
    Leads: 5,900 | Approved: 1,652 | AR: 28.0% | Rev: $11,564
    MoM: +8.9% revenue | Status: Growing but quality issues
    Key offers: SlimViet (main)
    Notes: Volume growing but trash rate creeping up (18%). Quality 
    audit needed. TikTok traffic growing fast but unproven quality.

PHILIPPINES 🟢
    Leads: 4,500 | Approved: 1,350 | AR: 30.0% | Rev: $10,800
    MoM: +7.5% revenue | Status: Stable
    Key offers: BeautyPH (stable)

BRAZIL 🔴
    Leads: 4,800 | Approved: 1,200 | AR: 25.0% | Rev: $15,600
    MoM: -5.5% revenue | Status: Declining
    Key offers: MaxPotency (declining), KetoMax (PAUSED)
    Notes: AR declined from 32% (Jan) → 28% (Feb) → 25% (Mar).
    Root causes: delivery time increase + courier change.
    Action: MaxPotency under optimization, split São Paulo / regions.

MEXICO 🟢
    Leads: 2,900 | Approved: 1,044 | AR: 36.0% | Rev: $11,484
    MoM: +14.2% revenue | Status: Growing nicely
    Key offers: HairMax (scaling)

INDONESIA 🔴
    Leads: 900 | Approved: 189 | AR: 21.0% | Rev: $1,323
    MoM: +5.0% revenue | Status: Testing, low volume
    Notes: AR below benchmark. Structural issues (delivery logistics).
    Decision: Continue testing 1 more month, then decide.

4. OFFER PORTFOLIO — END OF MONTH STATUS
───────────────────────────────────────────────────────────────
                 Count    Revenue    % Rev    Avg AR    Avg Margin%
Key (stable)       8     $214,920    72.0%    42.8%      36.5%
Growing            3      $52,290    17.5%    38.0%      34.0%
Watch              2      $18,660     6.3%    29.5%      30.2%
Test               2       $8,940     3.0%    27.0%      28.0%
Paused             2       $3,690     1.2%    20.0%        —
─────────────────────────────────────────────────────────────
Total             17     $298,500   100.0%    38.5%      35.3%

Offer Movements in March:
• Launched: VeinClear UA, DiabetControl RU, SkinWhite TH
• Passed test → Scale: VeinClear UA
• Paused: KetoMax BR (AR 20%), GlowSkin ID temporarily
• Killed: none (GlowSkin ID on pause, pending decision)

5. AFFILIATE BASE
───────────────────────────────────────────────────────────────
                    Mar-26   Feb-26    Change
Total registered      78       72       +6
Active (≥1 lead)      34       30       +4
Tier A                 5        5        0
Tier B                13       12       +1
Tier C                16       13       +3

Churn: 0 (no Tier A/B lost)
New Tier B: A09 (RU-Digital) promoted from Tier C

Concentration Risk:
• Top affiliate (A01): 18.8% of revenue → OK (<20%)
• Top 3 affiliates: 47.2% of revenue → OK (<50%)
• Top 5 affiliates: 63.1% of revenue → ⚠️ monitor (<65%)

6. OPERATIONAL METRICS
───────────────────────────────────────────────────────────────
Daily Report On-Time:           30/31 (96.8%) — 1 day late (Mar 17, tech issue)
Escalations Raised:             4
Escalations Resolved <24h:      3 (75%)
Escalation Open:                1 (Brazil AR — ongoing)
Offers Launched on Schedule:    3/3 (100%)
SLA Violations:                 2 (BrazilNutra payment 3d late, TH delivery SLA)
Data Reconciliation Variance:   1.8% avg (target <3%) ✅

7. APRIL FORECAST & PLAN
───────────────────────────────────────────────────────────────
Revenue Forecast:     $315,000 - $330,000
├── CIS:              $180,000 (KZ scaling, RU pre-summer boost)
├── Asia:              $82,000 (TH recovery, VN quality improvement)
└── Latam:             $53,000 - $68,000 (BR uncertainty, MX growth)

Key Initiatives April:
1. Brazil turnaround: MaxPotency split (SP / Regions), new offer test
2. KZ scaling: Cap increase, recruit more affiliates for KZ
3. VN quality: Audit + new anti-fraud rules
4. Pre-summer push: Weight loss offers CIS (Apr-May peak)
5. New GEO evaluation: Exploring Peru and Colombia for Q2 entry

Risks:
• Brazil AR may not recover → $10K-15K monthly revenue at risk
• A01 concentration (18.8%) → if they churn, significant impact
• TH delivery SLA not met → AR could decline further
• Currency: BRL weakening → advertiser may cut payout

══════════════════════════════════════════════════════════════════
```

---

## 11.4 RECONCILIATION REPORT MẪU

```
══════════════════════════════════════════════════════════════════
              WEEKLY RECONCILIATION — W14 (Mar 30 - Apr 5)
══════════════════════════════════════════════════════════════════

PURPOSE: Cross-check AffScale data vs Advertiser CRM data

ADVERTISER: NutraHealth LLC (RU + KZ offers)
───────────────────────────────────────────────────────────────
Offer        │AffScale Appr│Adv CRM Appr│ Diff │ Diff%│ Status
─────────────┼─────────────┼────────────┼──────┼──────┼───────
KetoBurn RU  │    640       │    628     │  -12 │-1.9% │ ✅ OK
JointFlex RU │    476       │    470     │   -6 │-1.3% │ ✅ OK
ManPower KZ  │    560       │    548     │  -12 │-2.1% │ ✅ OK
ParaClean RU │    350       │    320     │  -30 │-8.6% │ 🔴 FLAG
─────────────┼─────────────┼────────────┼──────┼──────┼───────
Total        │   2,026      │   1,966    │  -60 │-3.0% │ ⚠️

⚠️ ParaClean RU: 8.6% discrepancy. Possible shaving or tracking issue.
   ACTION: Request detailed lead-level report from advertiser.
   Compare click_ids to identify which 30 leads are missing.

ADVERTISER: BrazilNutra (BR offers)
───────────────────────────────────────────────────────────────
Offer        │AffScale Appr│Adv CRM Appr│ Diff │ Diff%│ Status
─────────────┼─────────────┼────────────┼──────┼──────┼───────
MaxPotency BR│    189       │    185     │   -4 │-2.1% │ ✅ OK
KetoMax BR   │     70       │     65     │   -5 │-7.1% │ 🟡
─────────────┼─────────────┼────────────┼──────┼──────┼───────
Total        │    259       │    250     │   -9 │-3.5% │ ⚠️

KetoMax BR: 7.1% diff nhưng volume thấp (5 leads chênh lệch).
Small sample = high % variance. Monitor next week.

FINANCIAL RECONCILIATION:
───────────────────────────────────────────────────────────────
                    AffScale    Finance     Diff      Status
Revenue (invoice)   $78,200     $78,200     $0        ✅
Payout (scheduled)  $50,490     $50,490     $0        ✅
Payment received    $65,400     $65,400     $0        ✅
Payment outstanding $45,200     $45,200     $0        ✅

══════════════════════════════════════════════════════════════════
```

---

## 11.5 OFFER SCORECARD MẪU (Filled)

```
══════════════════════════════════════════════════════════════════
                    OFFER SCORECARD
══════════════════════════════════════════════════════════════════
Offer: KetoBurn              GEO: Russia (RU)
Date: April 5, 2026          Status: Key Offer (Scaling)
Category: Weight Loss         Advertiser: NutraHealth LLC
Active since: January 15, 2026 (11 weeks)

1. VOLUME                                          Score: 8/10
   Current leads/day: 200 (avg W14)
   Cap: 250/day (80% utilized)
   Peak: 220/day (W12)
   Trend: ↑ Gradually increasing
   Notes: Room to grow to cap. Recruit 1 more affiliate.

2. APPROVAL RATE                                   Score: 9/10
   Current AR: 46.0% (W14 avg)
   GEO benchmark: 40%
   Best: 48.5% (W10)
   Worst: 42.0% (W8)
   Trend: → Stable
   Notes: Consistently above benchmark. Top performer.

3. MARGIN                                          Score: 7/10
   Revenue/approved: $15.00
   Payout/approved: $10.50 (A01 gets $11, others $10)
   Margin/approved: $4.50 (30.0%)
   Daily margin: ~$414
   Monthly margin: ~$12,420
   Notes: Healthy margin. Payout bumps for A01 justified by volume.

4. STABILITY                                       Score: 8/10
   Active since: 11 weeks
   Volume fluctuation: Low (±10%)
   AR fluctuation: Low (±3pp)
   Advertiser reliability: High (NutraHealth is long-term partner)
   Notes: Very stable offer, no surprises.

5. QUALITY (Trash Rate)                            Score: 8/10
   Current trash: 8.0%
   Target: <15%
   Notes: Well below threshold. Affiliates send quality traffic.

6. SCALABILITY                                     Score: 7/10
   Cap headroom: 50 leads/day (can request increase)
   Affiliates running: 4
   Potential affiliates: 2-3 more identified
   Traffic source diversity: FB (60%), Native (30%), Push (10%)
   Notes: Can scale to 350-400 with more affiliates + cap increase.

7. COMPETITION                                     Score: 6/10
   Other networks: Yes (Everad, Dr.Cash have similar offers)
   Payout competitive: Yes (market rate $9-11)
   Notes: Competitive landscape, but our AR advantage is differentiator.

8. STRATEGIC VALUE                                 Score: 7/10
   Category importance: High (weight loss = #1 category)
   Pre-summer season coming: Expect volume boost Apr-May
   Advertiser relationship: Strong
   Notes: Flagship RU offer. Good for recruitment pitch.

═══════════════════════════════════════════════════════════════
TOTAL SCORE: 60/80 (75%) — STRONG PERFORMER
ACTION: SCALE — increase cap, add affiliates, prepare for summer
═══════════════════════════════════════════════════════════════
```
