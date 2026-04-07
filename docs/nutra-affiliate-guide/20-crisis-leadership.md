# Chương 20: Crisis Management, Conflict Resolution & Leadership

## 20.1 Crisis Management Framework

### Phân loại Crisis theo mức độ

```
CRISIS SEVERITY LEVELS:
═══════════════════════

LEVEL 1 — MINOR (Bạn tự handle)
├── 1 offer AR drop < 10pp
├── 1 affiliate quality issue
├── Minor tracking glitch (< 1 hour)
├── Stock low (not out) on 1 offer
├── Impact: < $2K/day revenue
└── Response time: within same day

LEVEL 2 — MODERATE (Bạn + CMO)
├── Multiple offers affected
├── Top affiliate threatens to leave
├── Tracking down 1-4 hours
├── OOS on key offer
├── Impact: $2K-10K/day revenue
└── Response time: within 2 hours

LEVEL 3 — SEVERE (CMO + C-suite)
├── Platform-wide tracking failure
├── Top 3 affiliates issue simultaneously
├── Advertiser payment default > $20K
├── Compliance/legal threat
├── Impact: > $10K/day revenue
└── Response time: within 1 hour

LEVEL 4 — EXISTENTIAL (All hands + Legal)
├── Regulatory action against company
├── Payment processor ban
├── Mass affiliate exodus
├── Major fraud discovered (internal)
├── Data breach
├── Impact: threatens business continuity
└── Response time: IMMEDIATE
```

### Crisis Response Protocol — Step by Step

```
THE OODA LOOP (Military decision framework, adapt for business):

OBSERVE → ORIENT → DECIDE → ACT → (repeat)

OBSERVE (Minutes 0-15):
├── What happened? (symptoms, not causes yet)
├── What's the scope? (1 offer? 1 GEO? all?)
├── What's the current impact? (leads, revenue per hour)
├── Who's affected? (affiliates, advertisers, internal)
└── Is it getting worse or stable?

ORIENT (Minutes 15-30):
├── What could be causing this? (top 3 hypotheses)
├── Have we seen this before? (check incident history)
├── What information do we need to confirm?
├── Who do we need to involve?
└── What's the worst case if we don't act for 1 hour?

DECIDE (Minutes 30-45):
├── Choose immediate action (contain, not fix yet)
├── Choose communication plan (who to tell, what to say)
├── Assign roles (who investigates, who communicates)
├── Set review checkpoint (30 min or 1 hour)
└── Document decision and reasoning

ACT (Minutes 45+):
├── Execute containment (pause, cap reduce, redirect)
├── Send communications (affiliates, internal, advertiser)
├── Begin root cause investigation
├── Monitor: is containment working?
└── Update stakeholders at checkpoints
```

### Crisis Communication Templates

```
TEMPLATE 1: INTERNAL ALERT (Slack/Email)

🔴 [CRISIS LEVEL {1/2/3}] — {Brief description}

WHAT: {What happened in 1-2 sentences}
WHEN: Started approximately {time}
IMPACT: {Revenue/leads/affiliates affected}
STATUS: {Investigating / Contained / Resolving}

ACTIONS TAKEN:
• {Action 1}
• {Action 2}

NEXT UPDATE: {Time}
LEAD: {Your name}

──────────────────────────────

TEMPLATE 2: AFFILIATE COMMUNICATION

Subject: Service Notice — {Issue type}

Hi team,

We're aware of {issue description} that started at approximately {time}.

Current status: {Our team is actively working on resolution}

What you should do:
• {Specific action: continue/pause/wait}

What we're doing:
• {Action being taken}

Expected resolution: {ETA if known, or "investigating"}

All {leads/conversions} during this period will be {credited/reconciled}.

We'll send the next update at {time}.

Apologies for the inconvenience.
— MKT Operations Team

──────────────────────────────

TEMPLATE 3: POST-INCIDENT REPORT

INCIDENT REPORT
Date: {date}
Duration: {start time} — {end time} ({total hours})
Severity: Level {1/2/3}
Lead: {name}

SUMMARY:
{1-2 sentences: what happened and total impact}

TIMELINE:
{time} — {event}
{time} — {event}
{time} — {event}
{time} — Resolved

ROOT CAUSE:
{What caused it and why}

IMPACT:
├── Revenue lost: ${amount}
├── Leads affected: {count}
├── Affiliates affected: {count}
└── Reconciliation: {done/pending}

WHAT WENT WELL:
├── {positive 1}
└── {positive 2}

WHAT COULD IMPROVE:
├── {improvement 1}
└── {improvement 2}

PREVENTION:
├── {Action 1} — Owner: {name} — Due: {date}
├── {Action 2} — Owner: {name} — Due: {date}
└── {Action 3} — Owner: {name} — Due: {date}
```

## 20.2 Conflict Resolution — Giữa các Teams

### Conflict phổ biến nhất

```
CONFLICT 1: AM Team vs Ops (BẠN) — Payout Disputes
═══════════════════════════════════════════════════

AM muốn: Tăng payout để giữ affiliate / recruit affiliate mới
Bạn muốn: Protect margin, chỉ tăng khi justified

TÌNH HUỐNG THỰC TẾ:
AM: "A01 sẽ rời nếu không tăng payout lên $12. Phải approve ngay!"
Bạn: "Margin sẽ giảm xuống 14%. Không sustainable."
AM: "Nếu mất A01, revenue drop $30K/tháng. Chọn đi!"

CÁCH XỬ LÝ:

❌ SAI: 
├── "Không, policy là margin > 25%." (rigid, không collaborative)
├── "OK tăng đi." (cave in, lose margin long-term)
└── Escalate ngay lên CMO (looks like you can't handle)

✅ ĐÚNG:
1. Acknowledge urgency: "Tôi hiểu A01 quan trọng. Cùng giải quyết."
2. Get data: "Cho tôi 2 giờ check market rates và calculate options."
3. Present options WITH DATA:
   "A01 đang làm $56K/tháng cho chúng ta. Margin $20K/tháng.
   
   Option A: Tăng lên $11 (không phải $12) + Net-7 payment + VIP support
   → Margin giảm $6K/tháng nhưng còn $14K = 25% OK
   
   Option B: Tăng lên $11.50 BUT tie to performance: AR ≥ 43%, volume ≥ 400/day
   → Nếu đạt: margin vẫn OK vì volume tăng offset payout increase
   
   Option C: Match $12 nhưng chỉ cho 30 ngày trial
   → Review sau 30 ngày. Nếu margin < 20% → revert"
   
4. Seek agreement: "Tôi recommend Option B. Bạn thấy sao?"
5. If disagreement continues → escalate WITH both options to CMO

KEY PRINCIPLE:
Never say "No" without "But here's what we CAN do"
AM team is not your enemy — they want revenue too.
```

```
CONFLICT 2: AR Team vs Ops (BẠN) — Offer Quality
═════════════════════════════════════════════════

AR team muốn: Launch offer nhanh (KPI họ = number of new offers)
Bạn muốn: Quality gate — chỉ launch offer pass test criteria

TÌNH HUỐNG:
AR: "Advertiser mới có 5 offers, cần launch tuần này."
Bạn: "Advertiser này chưa verified. Chúng ta chưa biết AR sẽ ra sao."
AR: "Nếu chờ, competitor sẽ grab exclusive trước."

CÁCH XỬ LÝ:

1. Find the YES inside the NO:
   "OK, launch được — NHƯNG với safeguards:
   ├── Cap test: 30 leads/day (không phải 200)
   ├── Duration: 10 ngày test
   ├── Max loss accepted: $500
   ├── Chỉ dùng 1-2 trusted affiliates (không blast)
   └── AR team phải provide: advertiser references, payment proof"

2. Create a shared framework:
   "Để lần sau không phải debate mỗi lần, cùng agree:
   ├── New advertiser → mandatory test phase (SOP #2)
   ├── Existing advertiser → fast-track OK
   └── Risk level determines cap & duration"

3. Document the agreement → becomes SOP
```

```
CONFLICT 3: Finance vs Ops (BẠN) — Cash Flow
════════════════════════════════════════════

Finance muốn: Hold affiliate payments longer (improve cash flow)
Bạn muốn: Pay on time (keep affiliates happy)

TÌNH HUỐNG:
Finance: "Chúng ta cần chuyển từ Net-7 sang Net-15 cho tất cả affiliates."
Bạn: "Top affiliates sẽ rời. Họ cần cash flow để mua traffic."

CÁCH XỬ LÝ:

1. Quantify the risk:
   "Nếu chuyển Net-15:
   ├── Estimated 3-5 top affiliates sẽ reduce volume hoặc chuyển network
   ├── Revenue impact: -$40K-80K/tháng
   ├── Cash saved: ~$15K (delay 1 week of payments)
   └── Net impact: NEGATIVE"

2. Propose compromise:
   "Tier A (top 5): keep Net-7 (revenue justifies)
    Tier B (mid 13): move to Net-10 (from Net-7)
    Tier C (small 16): move to Net-15 (they have less leverage)
    
    Cash flow improvement: ~$8K
    Revenue risk: minimal (Tier C contributes only 8%)"

3. Set SLA with Finance:
   "Advertiser payments overdue > 7 days → reduce affiliate volume
    (không phải delay affiliate payment)"
```

```
CONFLICT 4: Media Buying vs Ops (BẠN) — Quality vs Volume
══════════════════════════════════════════════════════════

Media buyers muốn: Scale volume (KPI = leads)
Bạn muốn: Quality (AR > threshold)

TÌNH HUỐNG:
Media: "Tôi tìm được source mới, có thể tăng volume 3x. CPL rất rẻ."
Bạn: "Push traffic? Trash rate thường 25%+."
Media: "Nhưng ROI vẫn positive vì CPL thấp."

CÁCH XỬ LÝ:

1. Don't block — CREATE GUARDRAILS:
   "OK test, nhưng:
   ├── Separate tracking (sub ID riêng cho push traffic)
   ├── Cap: 50 leads/day max cho test
   ├── Auto-pause nếu trash > 25% trong 48h
   ├── Evaluate after 7 days with REAL AR (not projected)
   └── Media buyer KPI should include quality metric, not just volume"

2. Propose KPI adjustment (long-term fix):
   "Media buyer KPI hiện tại: Leads generated
    Proposed KPI: Approved leads × margin
    → This aligns incentives. They'll self-optimize for quality."
```

## 20.3 Handling Difficult Conversations

### Framework: COIN (Context, Observation, Impact, Next steps)

```
EXAMPLE: Warning an underperforming affiliate

CONTEXT:
"A12, chúng tôi rất appreciate partnership 2 tháng qua."

OBSERVATION:
"Tôi thấy trong 2 tuần gần đây, trash rate tăng từ 12% lên 22%, 
và AR giảm từ 35% xuống 28%."

IMPACT:
"Ở mức này, offer không profitable cho cả 2 bên. 
Advertiser cũng đã flag quality concern."

NEXT STEPS:
"Chúng tôi cần trash rate dưới 18% trong 7 ngày tới.
Tôi suggest:
- Review lại traffic source hiện tại
- Tạm dừng sources có trash cao
- Chúng tôi sẽ giảm cap xuống 80 leads/day trong khi optimize

Nếu improve → chúng tôi sẽ tăng cap lại và discuss payout bump.
Nếu không improve sau 7 ngày → chúng tôi sẽ phải pause temporarily."
```

### Framework: Delivering Bad News to CMO/Board

```
STRUCTURE: Lead with the impact, then explain

SAI: 
"Tuần này Brazil AR giảm vì advertiser đổi courier, lead quality 
cũng giảm, và tôi nghĩ có thể do mùa carnival..."
→ CMO: "So what? How bad?"

ĐÚNG:
"Brazil sẽ miss target $15K tháng này (-26%). Đây là tuần thứ 3 
AR liên tục giảm, hiện ở 25%.

Root cause: Advertiser đổi courier → delivery time tăng gấp đôi.

Tôi đã:
1. Split offer São Paulo / Regions (old courier for SP)
2. Reduced volume 40% to limit losses
3. Sourcing alternative advertiser

Recovery plan: 
- SP segment should recover within 2 weeks
- Alternative advertiser test starts next week
- Forecast: -$10K this month, recovery by month 2"
```

## 20.4 Team Leadership for MKT Ops

### 1-on-1 Meeting Framework

```
1:1 WITH DIRECT REPORTS (Weekly, 30 min)
════════════════════════════════════════

STRUCTURE:
├── 5 min: THEM first — What's on your mind?
├── 10 min: THEIR wins + challenges this week
├── 10 min: YOUR feedback + priorities for next week
└── 5 min: Growth/development check-in

QUESTIONS THAT WORK:
├── "What's blocking you right now?"
├── "What's one thing we should stop doing?"
├── "If you had my authority for a day, what would you change?"
├── "What should I know about that I probably don't?"
└── "How can I help you do your best work?"

QUESTIONS TO AVOID:
├── "Is everything OK?" (too vague, gets "yes")
├── "Why did that happen?" (sounds accusatory)
└── "Can you just..." (minimizing their workload)
```

### Building Data-Driven Culture

```
HOW TO BUILD ACCOUNTABILITY:

1. VISIBILITY — Make metrics PUBLIC
   ├── Team dashboard visible to everyone
   ├── Weekly metrics review in team meeting
   ├── Personal KPIs visible to individuals
   └── "What gets measured gets managed"

2. OWNERSHIP — Assign CLEAR owners
   ├── Every KPI has ONE owner
   ├── Every action item has ONE owner + deadline
   ├── "Nếu không có tên người chịu trách nhiệm → sẽ không ai làm"
   └── Review ownership in weekly meeting

3. RITUALS — Make it a HABIT
   ├── Daily standup: 15 min, same time, every day
   ├── Weekly review: numbers first, stories second
   ├── Monthly retro: what worked, what didn't, what to change
   └── Quarterly goals: OKR or similar framework

4. PSYCHOLOGICAL SAFETY — Make it OK to FLAG PROBLEMS
   ├── Celebrate people who find problems EARLY
   ├── Never shoot the messenger
   ├── "Bad news early is good news; bad news late is bad news"
   └── Punish hiding problems, not having problems
```

### Hiring for your PMO team

```
ROLES YOU'LL NEED:

PERFORMANCE ANALYST (1-2 people)
├── Skills: SQL, Excel/Sheets, data viz, attention to detail
├── KPI: Report accuracy, timeliness, anomaly detection speed
├── Interview question: "Here's a dataset. Tell me what's wrong."
├── Red flag: can't explain a metric in plain language
└── Salary range: $1,000-2,500/month (Vietnam/SEA market)

OPERATIONS COORDINATOR (1 person)
├── Skills: Communication, organization, process-driven
├── KPI: SLA tracking, meeting facilitation, documentation
├── Interview question: "Walk me through how you'd handle [crisis scenario]"
├── Red flag: can't prioritize (everything is "urgent")
└── Salary range: $800-1,500/month

QUALITY / FRAUD ANALYST (1 person)
├── Skills: Pattern recognition, SQL, skeptical mindset
├── KPI: Fraud detection rate, false positive rate
├── Interview question: "Here's an affiliate's data. Is it legit?"
├── Red flag: too trusting or too paranoid
└── Salary range: $1,000-2,000/month
```

## 20.5 Tài liệu tham khảo

### Leadership Books (Ưu tiên đọc)
- **"The First 90 Days"** — Michael Watkins — Onboarding vào vị trí mới
- **"High Output Management"** — Andy Grove — Operations management bible
- **"The Manager's Path"** — Camille Fournier — From IC to manager
- **"Radical Candor"** — Kim Scott — Feedback culture
- **"Turn the Ship Around"** — David Marquet — Leadership từ intent, không command

### Crisis Management
- **"The Hard Thing About Hard Things"** — Ben Horowitz — Crisis leadership
- PagerDuty Incident Response Guide — https://response.pagerduty.com (free, excellent)
- Atlassian Incident Management Guide — https://www.atlassian.com/incident-management

### Conflict Resolution
- **"Crucial Conversations"** — Kerry Patterson — Handling difficult talks
- **"Getting to Yes"** — Roger Fisher — Win-win negotiation
- Harvard Program on Negotiation — https://www.pon.harvard.edu/daily/ (free articles)
