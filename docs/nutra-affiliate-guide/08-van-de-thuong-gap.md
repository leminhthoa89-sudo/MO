# Chương 8: Các vấn đề thường gặp & Cách xử lý

## 8.1 Top 15 vấn đề thường gặp nhất

### VẤN ĐỀ 1: Approval Rate giảm

**Mức độ nghiêm trọng:** 🔴 Critical
**Tần suất:** Rất thường xuyên

**Nguyên nhân có thể:**

```
AR GIẢM
├── TRAFFIC QUALITY (50% cases)
│   ├── Affiliate mới chất lượng thấp
│   ├── Affiliate đổi traffic source (FB → push/pop)
│   ├── Bot/fraud traffic
│   └── Audience saturation → clicks từ unqualified users
│
├── CALL CENTER (25% cases)
│   ├── Call center quá tải → gọi chậm → lead nguội
│   ├── Agents mới chưa trained tốt
│   ├── Script không phù hợp sản phẩm/GEO
│   └── Working hours mismatch với lead timezone
│
├── DELIVERY / LOGISTICS (15% cases)
│   ├── Delivery time tăng → khách quên/đổi ý
│   ├── Address errors → không giao được
│   ├── Courier issues (đình công, thiên tai)
│   └── Remote areas mở rộng → delivery rate thấp
│
└── ADVERTISER SIDE (10% cases)
    ├── Product quality issue → returns tăng
    ├── Shaving (cắt conversions)
    ├── Đổi call center
    └── Pricing change → khách shock khi nhận
```

**Xử lý:**
```
Step 1: IDENTIFY scope
├── Giảm ở tất cả hay chỉ 1 offer/GEO/affiliate?
└── Bắt đầu giảm từ khi nào? Correlate với event nào?

Step 2: DRILL DOWN
├── Nếu specific affiliate → check traffic source, sub IDs
├── Nếu across all affiliates → call center hoặc advertiser issue
└── Nếu specific GEO → check logistics, seasonal factor

Step 3: ACTION
├── Traffic issue → pause bad affiliates, tighten caps
├── Call center → escalate to advertiser, request SLA
├── Delivery → escalate to advertiser, suggest local warehouse
└── Shaving → confront advertiser with data, negotiate

Step 4: MONITOR recovery
├── Set 48-hour check-in
└── If no improvement → escalate to CMO
```

---

### VẤN ĐỀ 2: Out of Stock (OOS)

**Mức độ nghiêm trọng:** 🔴 Critical
**Impact:** Leads tiếp tục vào nhưng không ship được → waste money

```
TÌNH HUỐNG THỰC TẾ:

Day 1: Advertiser thông báo OOS cho offer SlimFit RU
        Stock hiện tại: 0 units
        Restock ETA: 7-10 ngày

Affiliates vẫn đang chạy ads, chi $2,000/ngày
→ $14,000 - $20,000 wasted nếu không action ngay

ACTION CHECKLIST:
□ NGAY LẬP TỨC (trong 30 phút):
  ├── Pause offer trên AffScale (hoặc set cap = 0)
  ├── Notify tất cả affiliates đang chạy offer
  ├── AM team thông báo qua Telegram/Skype
  └── Update dashboard status → OOS

□ TRONG 2 GIỜ:
  ├── Confirm restock date từ advertiser
  ├── Identify alternative offers cho affiliates
  ├── Reallocate traffic nếu có offer tương tự
  └── Estimate revenue loss

□ DAILY until resolved:
  ├── Follow up restock status
  ├── Keep affiliates updated
  └── Log total loss

□ POST-MORTEM:
  ├── Tại sao OOS? Forecast sai? Volume spike?
  ├── Implement stock alert (warning khi < 3 ngày stock)
  └── SLA với advertiser: restock time commitment
```

---

### VẤN ĐỀ 3: Affiliate Fraud / Lead rác

**Mức độ nghiêm trọng:** 🔴 Critical
**Tần suất:** Thường xuyên

```
TYPES OF FRAUD:

1. BOT TRAFFIC
   ├── Dấu hiệu: leads vào đều đặn (mỗi 30s), cùng pattern
   ├── SĐT random/invalid
   ├── IP clustered
   └── Trash rate > 40%

2. INCENTIVIZED TRAFFIC
   ├── Affiliate hứa "quà miễn phí" để lấy lead
   ├── Leads đúng SĐT nhưng không có intent mua
   └── Confirm rate thấp, AR rất thấp

3. DUPLICATE LEADS
   ├── Cùng 1 lead gửi nhiều lần
   ├── Cùng SĐT với thay đổi nhỏ
   └── Detect qua dedup rules

4. LEAD INJECTION
   ├── Affiliate inject leads từ database cũ
   ├── Leads có thể "real" nhưng không phải từ ads
   └── Detect: check source IP, timestamp patterns

PREVENTION:
├── Automated rules: auto-pause khi trash > X%
├── Dedup rules: reject duplicate phone numbers
├── IP analysis: flag clustered IPs
├── Time analysis: flag regular interval submissions
├── Manual review: audit random sample leads weekly
└── Blacklist: maintain list of known fraudulent affiliates
```

---

### VẤN ĐỀ 4: Tracking Issues / Postback Failure

**Mức độ nghiêm trọng:** 🔴 Critical (mất data = mất tiền)

```
SYMPTOMS:
├── Affiliate thấy conversions trên tracker nhưng AffScale không ghi nhận
├── Số leads trên AffScale ≠ số trên CRM advertiser
├── Affiliate complain "tôi có 100 leads nhưng chỉ thấy 70"
└── Revenue dashboard hiển thị $0 cho offer đang active

COMMON CAUSES:
├── Postback URL sai (typo, wrong parameter)
├── Server timeout (postback không gửi được)
├── Click ID mismatch (lost in redirect chain)
├── SSL/firewall blocking
├── API changes từ 1 bên
└── Duplicate postback (tính 2 lần)

DIAGNOSTIC:
1. Check postback logs trên AffScale
2. Cross-check lead count: AffScale vs Advertiser CRM
3. Test postback manually (fire test postback)
4. Check error logs

ACTION:
├── Fix postback URL/parameters
├── Reconcile data manually (cho period bị miss)
├── Credit affiliate cho lost conversions
├── Set up monitoring alert cho postback failure
└── Document & prevent recurrence
```

---

### VẤN ĐỀ 5: Advertiser giảm Payout / thay đổi Terms

```
TÌNH HUỐNG:
Advertiser thông báo giảm payout từ $14 → $11 / approved lead
Effective ngay lập tức

IMPACT:
├── Current payout to affiliate: $10
├── New margin: $11 - $10 = $1 (was $4)
├── Margin drop: 75%
└── Ở volume 200 approved/day: $200/day margin (was $800)

ACTION PLAN:

Option A: Absorb & Negotiate
├── Accept temporarily
├── Negotiate volume commitment → better payout
├── Present data: "Nếu giữ $13 payout, chúng tôi cam kết 300 approved/day"
└── Leverage: threaten to reduce volume / switch advertiser

Option B: Pass through to Affiliate
├── Giảm affiliate payout tương ứng ($10 → $7)
├── Risk: affiliate chuyển network khác
├── Communicate transparently: "advertiser giảm, chúng tôi giảm ít hơn"
└── Keep margin reasonable ($11 - $7 = $4)

Option C: Find Alternative
├── Source cùng product từ advertiser khác
├── Test alternative offers để thay thế
└── Gradual migration

DECISION: Usually combination of A + B
├── Negotiate with advertiser (try to get $12)
├── Reduce affiliate payout slightly ($10 → $8.5)
├── New margin: $12 - $8.5 = $3.50 (was $4, acceptable)
└── If negotiation fails: lean harder on B or C
```

---

### VẤN ĐỀ 6: Top Affiliate rời đi

```
IMPACT:
├── Revenue drop immediate
├── Cap under-utilized
├── Advertiser unhappy (less volume)
└── Hard to replace quickly

PREVENTION:
├── Regular check-ins with top affiliates
├── Competitive payouts + volume bumps
├── Exclusive offers
├── Fast payment terms
├── Priority support
└── Early warning: volume decline = possible churn signal

WHEN IT HAPPENS:
├── Immediately: reallocate cap
├── Short-term: recruit replacement, bump payouts for existing
├── Long-term: reduce concentration (no affiliate > 20-25% total)
└── Post-mortem: WHY did they leave? Fix for future
```

---

### VẤN ĐỀ 7: Call Center quá tải

```
SYMPTOMS:
├── Time-to-call tăng (> 30 phút)
├── Contact rate giảm (leads not reached)
├── Confirm rate giảm (leads nguội khi gọi)
├── Hold rate tăng (chưa kịp gọi)
└── AR giảm overall

CAUSES:
├── Volume spike mà không báo trước
├── Call center understaffed
├── Holiday/weekend (ít agents)
└── Multi-offer routing không optimal

ACTION:
├── Coordinate volume với call center capacity
├── Set cap based on call center bandwidth (not just stock)
├── SLA: time-to-call < 15 minutes
├── Escalate to advertiser nếu AR impact > 5pp
└── Consider spreading leads across time zones
```

---

### VẤN ĐỀ 8: Landing Page bị block / Facebook ban

```
IMPACT:
├── Affiliate không chạy được → volume = 0
├── Nếu nhiều affiliates bị cùng lúc → massive drop

WHY IT HAPPENS:
├── Facebook cloaking detection improved
├── Landing page vi phạm policies
├── Competitor report
└── Platform periodic sweeps

WHAT YOU CAN DO (as Ops Manager):
├── Không trực tiếp fix (đó là việc affiliate)
├── NHƯNG: cung cấp compliant LP alternatives
├── Diversify traffic sources (không only Facebook)
├── Monitor which LP versions ít bị ban hơn
├── Track "account survival rate" by LP type
└── Have backup plan: alternative traffic sources ready
```

---

### VẤN ĐỀ 9: Currency fluctuation

```
TÌNH HUỐNG:
- Advertiser trả USD
- Nhưng products bán ở Russia (RUB), Brazil (BRL)
- Khi RUB mất giá: khách trả ít hơn → advertiser revenue giảm → payout giảm

IMPACT:
├── Sudden payout changes
├── Margin squeeze
├── Advertiser may pause offers in affected GEO

MITIGATION:
├── Track major currency pairs (USD/RUB, USD/BRL, USD/THB)
├── When currency drops > 5%: proactively reach out to advertiser
├── Include currency risk in forecasts
├── Negotiate payout in local currency or with adjustment clause
└── Diversify GEO portfolio to hedge
```

---

### VẤN ĐỀ 10: Team internal conflict

```
COMMON CONFLICTS:

1. AM team raise payout quá cao → margin giảm
   ╰→ Solution: Payout approval workflow, bạn sign off

2. Media buyers muốn scale nhưng quality giảm
   ╰→ Solution: KPI tied to both volume AND quality

3. AR team promise volume cho advertiser nhưng không đạt
   ╰→ Solution: Forecast review meeting, bạn validate

4. Finance hold affiliate payment quá lâu → affiliate complain
   ╰→ Solution: SLA payment timeline, escalation path

5. Tech delay dashboard features → bạn không có data kịp thời
   ╰→ Solution: Priority list, regular tech sync meeting

AS OPS MANAGER:
├── Bạn là neutral referee
├── Dùng DATA để resolve conflict (không dùng opinion)
├── Set clear SLAs and accountability
└── Escalate to CMO khi cannot resolve
```

---

### VẤN ĐỀ 11-15 (Quick Reference)

```
#11: SEASONAL DIPS
├── Problem: Q1 thường chậm, pre-summer tăng
├── Action: Budget adjustment, offer rotation theo season
└── Prep: Plan 2 tháng trước mùa peak

#12: COMPLIANCE / LEGAL ISSUES  
├── Problem: Quảng cáo bị cơ quan quản lý flag
├── Action: Audit LP/creatives, remove claims vi phạm
└── Prevention: Compliance review trước launch

#13: ADVERTISER PAYMENT DELAY
├── Problem: Advertiser trả chậm → cash flow crunch
├── Action: Payment reminders, escalation, hold volume
└── Prevention: Credit check advertiser mới, diversify

#14: DATA DISCREPANCY
├── Problem: Số liệu AffScale ≠ Advertiser CRM ≠ Finance
├── Action: Weekly reconciliation, identify source of truth
└── Prevention: Automated reconciliation, clear data definitions

#15: SCALING TOO FAST
├── Problem: Volume tăng 3x nhưng AR crash
├── Action: Gradual scaling (max +30% per week)
└── Prevention: Scaling SOP, quality checkpoints
```

## 8.2 Escalation Matrix

```
WHO HANDLES WHAT:

Level 1 — YOU (MKT Ops Manager):
├── Daily monitoring & reporting
├── Offer pause/resume decisions
├── Cap allocation
├── Affiliate quality warnings
├── SLA tracking
└── Cross-team coordination

Level 2 — CMO:
├── Strategic offer decisions
├── Major payout changes
├── Budget reallocation > $X
├── Advertiser relationship issues
└── Team restructuring

Level 3 — COO/CEO:
├── Financial exposure > $X
├── Legal/compliance issues
├── Major advertiser disputes
├── Business model changes
└── Market entry/exit decisions

ESCALATION TRIGGER:
├── Revenue impact > $5,000/day → CMO within 2 hours
├── Revenue impact > $20,000/day → COO within 1 hour
├── Legal issue → CMO + Legal immediately
├── Fraud > $10,000 → CMO + Finance immediately
└── All escalations: include data + impact + recommendation
```

## 8.3 Crisis Management Playbook

```
CRISIS SCENARIO: Major tracking failure — 0 conversions recording for 6 hours

HOUR 0 (DETECTION):
├── Alert detected: 0 conversions since 6AM
├── Quick check: AffScale platform status → DOWN / DEGRADED
└── Activate crisis mode

HOUR 0-1 (ASSESS):
├── Scope: ALL offers or specific?
├── Duration: When did it start? (check last valid conversion)
├── Impact estimate: Leads still flowing? How many untracked?
├── Notify: CMO + Tech lead + AM team lead
└── Document: Start incident log

HOUR 1-2 (CONTAIN):
├── If platform-wide: Contact AffScale support / tech team
├── If specific offer: Check postback configuration
├── Decide: Pause affected offers? (prevent further data loss)
├── Alternative: Manual tracking (spreadsheet) temporarily
└── Communicate: Update to affiliates "aware of issue, working on fix"

HOUR 2-4 (RESOLVE):
├── Fix identified and implemented
├── Verify: Test conversions flowing again
├── Reconcile: Count missed conversions, cross-check with advertiser CRM
└── Backfill: Credit affiliates for missed conversions

HOUR 4-24 (RECOVER):
├── Full reconciliation complete
├── All affiliates credited correctly
├── Advertiser notified of discrepancy
├── Dashboard data corrected
└── Communication: "Issue resolved" to all stakeholders

POST-INCIDENT (48h):
├── Root cause analysis document
├── Prevention measures identified
├── Monitoring improvements deployed
├── Lessons learned shared with team
└── Update SOP/playbook
```
