# Chương 9: SOP & Framework vận hành

## 9.1 Framework tổng thể — Performance Marketing Operations

```
                    MKT OPS FRAMEWORK
                    ═══════════════════
                    
┌─────────────────────────────────────────────────┐
│                 STRATEGIC LAYER                   │
│  Monthly/Quarterly planning, GEO strategy,       │
│  Portfolio management, Budget allocation          │
└────────────────────────┬────────────────────────┘
                         │
┌────────────────────────▼────────────────────────┐
│               OPERATIONAL LAYER                   │
│  Daily monitoring, Offer management,             │
│  Affiliate management, Cap allocation            │
└────────────────────────┬────────────────────────┘
                         │
┌────────────────────────▼────────────────────────┐
│                DATA & ANALYTICS LAYER             │
│  Tracking, Dashboard, Reporting,                 │
│  Forecasting, Root cause analysis                │
└────────────────────────┬────────────────────────┘
                         │
┌────────────────────────▼────────────────────────┐
│              PROCESS & GOVERNANCE LAYER           │
│  SOPs, SLAs, Escalation, Quality control,        │
│  Compliance, Documentation                       │
└─────────────────────────────────────────────────┘
```

## 9.2 SOP Template

Mỗi SOP cần có:

```
SOP TEMPLATE
═════════════

Title:          [Tên quy trình]
Version:        1.0
Owner:          [Ai chịu trách nhiệm]
Last Updated:   [Date]
Frequency:      [Daily/Weekly/As needed]

PURPOSE:
Tại sao SOP này tồn tại, mục đích gì

SCOPE:
Áp dụng cho ai, khi nào

TRIGGER:
Điều gì kích hoạt quy trình này

STEPS:
1. Step 1
2. Step 2
3. ...

DECISION POINTS:
Nếu X → làm A
Nếu Y → làm B

ESCALATION:
Khi nào escalate, cho ai

OUTPUT/DELIVERABLE:
Kết quả cuối cùng là gì

METRICS:
Đo lường hiệu quả SOP bằng gì
```

## 9.3 Các SOP cốt lõi

### SOP 1: Daily Performance Review

```
SOP: DAILY PERFORMANCE REVIEW
════════════════════════════════
Owner: MKT Ops Manager
Frequency: Daily, 9:00 - 9:30 AM
Trigger: Every working day

STEPS:

09:00 — Open Overview Dashboard
├── 1. Record headline numbers: leads, approved, AR, revenue, margin
├── 2. Compare vs yesterday & vs same day last week
└── 3. Note any anomalies (>10% deviation)

09:10 — Drill Down by GEO
├── 4. Review each active GEO performance
├── 5. Flag any GEO with AR < threshold
└── 6. Check cap utilization per GEO

09:15 — Review Offers
├── 7. Top 10 offers by volume — any issues?
├── 8. Any offer in 🔴 RED status?
├── 9. Check OOS alerts
└── 10. New offers in test — results so far?

09:20 — Review Affiliates
├── 11. Top 10 affiliates — stable?
├── 12. Any new affiliate with trash > 25%?
├── 13. Any affiliate volume anomaly?
└── 14. Pending affiliate approvals?

09:25 — Financials
├── 15. Yesterday's margin
├── 16. Any payment issues?
└── 17. Month-to-date vs budget

09:30 — Action & Report
├── 18. List action items with priority & owner
├── 19. Draft daily report
├── 20. Send to CMO + team leads
└── 21. Create tasks for action items

OUTPUT: Daily report email/Slack message
TIME: Max 30 minutes
```

### SOP 2: New Offer Launch

```
SOP: NEW OFFER LAUNCH
═════════════════════
Owner: MKT Ops Manager + AR Team
Frequency: As needed
Trigger: New offer received from advertiser

PRE-LAUNCH (Day -3 to -1):

□ 1. Receive offer details from AR team
      ├── Product name, category
      ├── GEO, payout, cap
      ├── Landing pages
      ├── Traffic restrictions
      └── Call center confirmation

□ 2. Evaluate offer (Offer Scorecard)
      ├── Compare payout vs market
      ├── Check advertiser track record
      ├── Assess GEO fit
      └── Calculate expected margin

□ 3. DECISION: Launch / Reject
      ├── If Reject → communicate to AR team with reason
      └── If Launch → continue

□ 4. Setup on AffScale
      ├── Create offer
      ├── Configure tracking/postback
      ├── Set test cap (20-50 leads/day)
      ├── Assign landing pages
      └── Set traffic restrictions

□ 5. Test tracking
      ├── Generate test click
      ├── Submit test lead
      ├── Verify postback fires correctly
      ├── Verify lead appears in advertiser CRM
      └── If fail → fix before launch

LAUNCH (Day 0):

□ 6. Select test affiliates (1-3 trusted)
□ 7. Brief affiliates: payout, restrictions, expectations
□ 8. Activate offer
□ 9. Monitor first 10 leads within 2 hours
      ├── Leads flowing? → continue
      └── No leads? → check tracking

TEST PERIOD (Day 1-14):

□ 10. Daily check: leads, trash rate, CR
□ 11. Day 3: First quality assessment
       ├── Trash rate acceptable? (< 20%)
       └── Lead volume meeting expectations?
□ 12. Day 7: Mid-test review
       ├── If data sufficient → preliminary AR
       ├── Confirm rate from call center?
       └── Any red flags?
□ 13. Day 14: Final test decision

DECISION:
├── AR > threshold AND trash < 20% AND margin > 20%
│   → SCALE (increase cap, add affiliates)
├── AR borderline OR needs optimization
│   → EXTEND test 7 more days
└── AR < threshold OR trash > 30% OR margin negative
    → KILL (pause offer, notify stakeholders)

POST-LAUNCH (if scaling):
□ 14. Gradual cap increase (Week 1: 100, Week 2: 200, etc.)
□ 15. Onboard additional affiliates
□ 16. Monitor AR as volume increases
□ 17. Set up automated alerts
□ 18. Add to regular reporting
```

### SOP 3: Affiliate Onboarding & Quality Management

```
SOP: AFFILIATE MANAGEMENT
══════════════════════════
Owner: AM Team + MKT Ops oversight

NEW AFFILIATE ONBOARDING:

□ 1. Application review
      ├── Traffic source experience
      ├── GEO experience
      ├── Past performance (request stats from other networks)
      └── Fraud risk assessment

□ 2. Approval decision
      ├── Approved → continue
      ├── Rejected → notify with reason
      └── Conditional → limited offers/cap

□ 3. Initial setup
      ├── Account created on AffScale
      ├── Test cap: 20-50 leads/day
      ├── Standard payout (no bumps yet)
      ├── Payment terms: Net-30 (first month)
      └── Limited to 1-2 proven offers

□ 4. First week monitoring
      ├── Daily check: trash rate, volume pattern
      ├── If trash > 25% → warning
      ├── If trash > 35% → pause
      └── If clean → consider expanding access

ONGOING QUALITY MANAGEMENT:

Monthly Affiliate Review:
├── Tier A (top 10% by volume + quality): VIP treatment
├── Tier B (middle): standard review
├── Tier C (bottom): improvement needed or cut
└── Auto-rules:
    ├── Trash > 25% for 3 consecutive days → auto-warning
    ├── Trash > 35% for 2 consecutive days → auto-pause
    ├── AR < 20% for 7 days → cap reduction
    └── 0 volume for 14 days → inactive status
```

### SOP 4: Offer Pause / Kill

```
SOP: OFFER PAUSE / KILL
════════════════════════
Owner: MKT Ops Manager
Trigger: Offer performance below threshold

PAUSE CRITERIA (any one):
├── AR < 20% for 7+ days (with sufficient data)
├── Trash > 30% across all affiliates
├── Margin negative for 5+ days
├── Advertiser request
├── OOS > 5 days with no restock date
├── Compliance/legal issue
└── Tracking broken and unfixable

PAUSE PROCESS:

□ 1. Document reason for pause
□ 2. Set cap = 0 on AffScale (or deactivate offer)
□ 3. Notify all active affiliates (AM team sends message)
      "Offer [Name] paused effective immediately due to [reason].
       Please switch to [alternative offer]."
□ 4. Suggest alternative offers
□ 5. Notify advertiser (AR team)
□ 6. Update dashboard status
□ 7. Calculate final P&L for the offer
□ 8. Archive learnings

KILL (permanent) — additional steps:
□ 9. Remove from active offer list
□ 10. Final reconciliation with advertiser
□ 11. Final payment to affiliates
□ 12. Post-mortem document: what worked, what didn't, lessons
```

### SOP 5: Escalation

```
SOP: ESCALATION PROCESS
════════════════════════
Owner: MKT Ops Manager

WHEN TO ESCALATE:

Revenue impact estimated to exceed:
├── $1,000/day → YOU handle directly
├── $5,000/day → Escalate to CMO within 2 hours
├── $20,000/day → Escalate to CMO + COO within 1 hour
└── Any legal issue → Escalate to CMO + Legal IMMEDIATELY

ESCALATION FORMAT (Slack/Email):

Subject: [ESCALATION] [Level: Warning/Critical] — Brief description

IMPACT:
• Estimated revenue impact: $X/day
• Duration so far: X hours/days
• Affected: [offers/GEOs/affiliates]

ROOT CAUSE:
• What happened
• Why it happened (if known)

ACTIONS TAKEN:
• What has been done so far

RECOMMENDATION:
• What should be done next
• Decision needed from escalation target

TIMELINE:
• When decision is needed by
```

## 9.4 Meeting Cadence

```
MEETING SCHEDULE:
═════════════════

DAILY (15 min) — Morning Standup
├── Who: MKT Ops + AM team lead + AR team lead
├── When: 9:30 AM (after daily review)
├── Agenda:
│   ├── Yesterday's highlights/issues
│   ├── Today's priorities
│   └── Blockers
└── Output: Action items with owners

WEEKLY (60 min) — Performance Review
├── Who: MKT Ops + CMO + AM + AR + Finance
├── When: Monday 2:00 PM
├── Agenda:
│   ├── Week performance vs targets (15 min)
│   ├── GEO/Offer deep dive (20 min)
│   ├── Issues & escalations (15 min)
│   └── Next week priorities (10 min)
└── Output: Weekly report, action items

BI-WEEKLY (30 min) — Tech Sync
├── Who: MKT Ops + Tech lead
├── When: Every other Wednesday
├── Agenda:
│   ├── Dashboard/reporting requests
│   ├── Tracking issues
│   └── Feature requests priority
└── Output: Updated tech backlog

MONTHLY (90 min) — Business Review
├── Who: MKT Ops + CMO + CEO/COO + Finance
├── When: First week of month
├── Agenda:
│   ├── Monthly P&L (20 min)
│   ├── Portfolio review (30 min)
│   ├── Strategic initiatives (20 min)
│   └── Next month forecast & plan (20 min)
└── Output: Monthly report, strategic decisions

QUARTERLY (Half day) — Strategic Planning
├── Who: MKT Ops + CMO + C-suite
├── When: First 2 weeks of quarter
├── Agenda:
│   ├── Quarter review
│   ├── Market trends & opportunities
│   ├── GEO strategy
│   ├── Budget planning
│   └── Team development
└── Output: Quarterly plan, OKRs
```

## 9.5 KPI Framework

### Your Personal KPIs (as MKT Ops Manager)

```
FINANCIAL:
├── Total Revenue vs Target:      monthly
├── Total Margin vs Target:       monthly  
├── Margin Rate:                  ≥ 25%
└── Budget Variance:              ± 10%

OPERATIONAL:
├── Daily Report On-Time Rate:    100%
├── Offer Launch Success Rate:    > 60% (test → scale)
├── Escalation Resolution Time:   < 24 hours
├── SLA Compliance Rate:          > 90%
└── OOS Incidents/month:          < 3

GROWTH:
├── New Offers Launched/month:    target set quarterly
├── New GEOs Entered/quarter:     target set quarterly
├── Affiliate Base Growth:        net new active affiliates
└── Revenue Growth MoM:           target set quarterly

QUALITY:
├── Average AR across portfolio:  > GEO benchmarks
├── Average Trash Rate:           < 15%
├── Fraud Detection Rate:         % caught before payout
└── Data Accuracy:                < 2% discrepancy vs reconciled
```

### Team KPIs (PMO team you manage)

```
ANALYST/COORDINATOR KPIS:
├── Report accuracy: < 1% error rate
├── Report timeliness: on-time delivery
├── Dashboard uptime: > 99%
├── Issue detection time: < 2 hours from anomaly
├── Reconciliation completion: weekly on time
└── Documentation currency: SOPs updated quarterly
```

## 9.6 Tools & Templates cần chuẩn bị

```
WEEK 1: Setup these tools/templates

□ Daily Report Template (Email/Slack)
□ Weekly Report Template (Slides or Doc)
□ Monthly Report Template (Slides)
□ Offer Scorecard Template (Spreadsheet)
□ Offer Tracker (all active offers, status, key metrics)
□ Affiliate Tier List (updated monthly)
□ Cap Allocation Sheet
□ Escalation Log
□ Meeting Agenda Templates (daily/weekly/monthly)
□ SOP Document Repository (Google Drive / Notion / Confluence)

WEEK 2: Setup these dashboards/automations

□ Overview Dashboard (if not existing → request from tech)
□ GEO Dashboard
□ Offer Dashboard
□ Affiliate Dashboard
□ Alert System (Slack notifications for thresholds)
□ Automated daily metrics email
□ Reconciliation tracking sheet
```

## 9.7 First 30-60-90 Day Plan

```
FIRST 30 DAYS — LEARN & ASSESS
═══════════════════════════════
Week 1:
├── Meet every team lead 1:1
├── Get AffScale access, explore platform
├── Understand current offer portfolio
├── Review existing reports/dashboards
├── Identify data sources and flows
└── Read all existing documentation

Week 2:
├── Shadow daily operations
├── Understand current pain points from each team
├── Map current processes (written or unwritten)
├── Start attending all meetings
├── First draft of current state assessment
└── Identify quick wins

Week 3:
├── Take over daily reporting
├── Start daily performance reviews independently
├── Identify gaps in data/reporting
├── Draft initial SOPs for critical processes
└── Present "Current State" to CMO

Week 4:
├── First weekly report independently
├── Propose priority SOPs and KPIs
├── Quick wins implemented
├── First escalation handled
└── 30-day review with CMO

DAYS 31-60 — BUILD & IMPLEMENT
═══════════════════════════════
├── Implement core SOPs (daily review, offer launch, escalation)
├── Setup alert system
├── Establish meeting cadence
├── First monthly report to Board
├── Request dashboard improvements from Tech
├── Train team on new SOPs
├── First offer launch you manage end-to-end
└── 60-day review

DAYS 61-90 — OPTIMIZE & SCALE
═══════════════════════════════
├── Refine SOPs based on feedback
├── Implement advanced analytics (cohort, funnel)
├── Propose strategic initiatives (new GEO, new category)
├── Build forecasting model
├── Full KPI framework operational
├── Team development plans
├── Quarterly planning participation
└── 90-day review with CEO/CMO
```
