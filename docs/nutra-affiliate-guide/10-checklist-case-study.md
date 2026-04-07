# Chương 10: Checklist thực hành & Case Studies

## 10.1 Master Checklist — Những gì phải biết trước khi bắt đầu

### A. Kiến thức ngành (Phải hiểu rõ)

```
□ Nutra COD flow hoạt động như thế nào (lead → call → ship → deliver → approve)
□ Sự khác biệt giữa COD vs SS (Straight Sale) vs Trial
□ Các trạng thái của lead: trash, reject, hold, confirmed, shipped, approved, returned
□ Unit economics: CPL, CPA, EPC, EPL, AR, ROI, margin
□ Cash flow cycle (30-45 ngày từ spend đến receive)
□ Vòng đời offer: test → scale → stable → decline → kill
□ Vai trò từng bên: advertiser, network, affiliate, call center, warehouse
```

### B. Platform & Tools (Phải biết dùng)

```
□ AffScale: navigation, offer creation, reporting, affiliate management
□ Dashboard: đọc overview, drill down by GEO/offer/affiliate
□ Tracking: hiểu click → postback → conversion flow
□ Excel/Sheets: pivot tables, formulas cho analysis
□ Communication tools: Slack/Telegram cho team coordination
```

### C. GEO Knowledge (Phải nắm benchmark)

```
□ CIS: RU benchmark metrics, KZ, UA đặc điểm
□ Asia: TH, VN, PH, ID benchmark metrics và challenges
□ Latam: BR, MX, CO benchmark metrics và delivery issues
□ Biết GEO nào phù hợp offer category nào
□ Biết traffic source nào phổ biến ở GEO nào
```

### D. Operational Skills (Phải làm được)

```
□ Thực hiện daily performance review trong 30 phút
□ Viết daily/weekly/monthly report
□ Đánh giá offer mới (Offer Scorecard)
□ Phát hiện anomaly từ dashboard
□ Root cause analysis khi metrics giảm
□ Escalation đúng format và đúng người
□ Cap allocation decision
□ Payout negotiation basics
```

## 10.2 Case Studies

### Case Study 1: "Offer weight loss mới tại Russia — Launch thành công"

```
BACKGROUND:
- Advertiser giới thiệu offer "KetoBurn" cho Russia
- Payout: $12/approved, Revenue: $17/approved
- Cap: 100 leads/day test
- Có 3 landing pages sẵn

NGÀY 1-3: SETUP & LAUNCH
├── Setup offer trên AffScale
├── Test tracking → OK
├── Assign cho 2 trusted affiliates (A001 và A002)
├── A001 chạy Facebook, A002 chạy Native (MGID)

NGÀY 4-7: FIRST DATA
├── Total leads: 280 (40/day average)
├── A001 (FB): 180 leads, trash 8%, CR 12%
├── A002 (Native): 100 leads, trash 15%, CR 6%
├── Call center confirm rate: 58%
├── AR chưa có (delivery cycle 10-14 ngày)

PHÂN TÍCH:
├── Lead quality: ✅ Trash rate acceptable cả 2
├── Volume: ⚠️ Chưa fill cap (40/100)
├── CR: A001 tốt hơn A002 đáng kể
└── Confirm rate: ✅ 58% là tốt cho RU

NGÀY 8-14: PRELIMINARY RESULTS
├── Day 1-3 leads bắt đầu có delivery results
├── AR (preliminary): 41% → ✅ Trên benchmark RU (40%)
├── Return rate: 12% → OK
├── A001 AR: 46%, A002 AR: 33%

QUYẾT ĐỊNH: SCALE
├── Tăng cap: 100 → 200 → 300
├── Onboard thêm 3 affiliates
├── Keep A001 on premium payout ($13)
├── A002: suggest focus FB thay vì native cho offer này
├── Monitor AR weekly

NGÀY 15-30: SCALING
├── Volume reached 250 leads/day
├── AR stabilized at 42%
├── 5 affiliates running
├── Monthly revenue: ~$17,850
├── Monthly margin: ~$5,250
├── Added to "Key Offers" portfolio

LESSONS LEARNED:
├── FB traffic > Native cho weight loss RU (cho offer này)
├── 14 ngày test là đủ cho RU (delivery cycle cho phép)
├── Confirm rate 58% là good indicator cho high AR
└── Gradual scaling (30%/week) giữ AR stable
```

### Case Study 2: "AR crash ở Brazil — Diagnosis và Recovery"

```
BACKGROUND:
- Offer "MaxPotency" Brazil đang chạy 2 tháng
- Stable: 150 leads/day, AR 34%, margin $600/day
- Tuần này: AR crash xuống 18%

NGÀY 1 (DETECTION):
Dashboard sáng thứ Hai hiện:
├── AR 7-day average: 18% (was 34%)
├── Volume: 160 leads/day (stable)
├── Trash: 14% (stable)
└── ⚠️ Alert triggered

NGÀY 1 (INVESTIGATION):

Step 1: Break down by affiliate
├── A003: 80 leads/day, AR 20% (was 35%) → GIẢM
├── A005: 50 leads/day, AR 15% (was 32%) → GIẢM
├── A008: 30 leads/day, AR 18% (was 34%) → GIẢM
└── Observation: TẤT CẢ affiliates đều giảm → KHÔNG PHẢI traffic issue

Step 2: Check call center
├── Confirm rate: 55% → stable (không đổi)
├── Time-to-call: 12 phút → OK
└── Observation: Call center KHÔNG phải vấn đề

Step 3: Check delivery
├── Delivery rate: 48% (was 72%) → ĐÂY LÀ VẤN ĐỀ
├── Average delivery time: 22 ngày (was 14 ngày)
├── Return rate: 35% (was 15%)
└── ROOT CAUSE: Delivery time tăng gấp đôi → khách không nhận

Step 4: Check with advertiser
├── Advertiser confirm: đổi courier service tuần trước
├── New courier rẻ hơn nhưng chậm hơn nhiều
└── Đặc biệt chậm ở regions ngoài São Paulo

NGÀY 1 (ACTION):
├── Escalate to CMO: revenue impact ~$800/day
├── AR team contact advertiser: yêu cầu switch back courier
├── Temporary: giảm cap xuống 80 leads/day
├── Focus leads ở São Paulo/Rio (delivery nhanh hơn)
└── Inform affiliates: "temporary issue, adjusting"

NGÀY 2-5 (RESOLUTION):
├── Advertiser đồng ý dùng courier cũ cho São Paulo area
├── Vẫn dùng courier mới cho regions (rẻ hơn, chấp nhận AR thấp hơn)
├── AR bắt đầu recover cho São Paulo leads

NGÀY 6-14 (RECOVERY):
├── São Paulo leads AR: 38% (better than before!)
├── Regional leads AR: 22% (still low)
├── Blended AR: 30% (recovering)
├── Volume back to 140 leads/day

FINAL OUTCOME:
├── Split offer thành 2: "MaxPotency BR-SP" và "MaxPotency BR-Regions"
├── SP: higher payout, guaranteed courier
├── Regions: lower payout, different expectations
├── Total margin recovered to ~$500/day
└── New SOP: Advertiser phải notify trước khi thay đổi logistics

LESSONS:
├── Delivery changes = massive AR impact (đặc biệt ở Brazil)
├── Root cause KHÔNG phải lúc nào cũng ở phía traffic
├── Cross-checking ALL dimensions tìm ra vấn đề
├── SLA với advertiser về logistics changes = cần thiết
└── Sub-GEO analysis (city-level) có thể unlock value
```

### Case Study 3: "Phát hiện và xử lý Fraud"

```
BACKGROUND:
- Affiliate A015 mới join 3 tuần
- Tuần 1-2: 30 leads/day, trash 12%, AR 38% → good
- Tuần 3: 150 leads/day, trash 8%, waiting AR...

DETECTION:
├── Volume 5x spike bắt thường
├── NHƯNG trash rate giảm (8%) → "tốt quá" cũng suspicious
├── Deep dive vào lead data...

INVESTIGATION:

1. Lead timestamp analysis:
   ├── 150 leads trong 10 giờ = 15 leads/hour
   ├── NHƯNG: leads đến exactly mỗi 4 phút
   └── 🔴 Pattern quá đều → likely automated

2. Phone number analysis:
   ├── Tất cả SĐT đều valid format (passed validation)
   ├── NHƯNG: 30% SĐT thuộc cùng 1 operator, same prefix
   └── 🔴 Clustered phone numbers → database injection

3. IP analysis:
   ├── 60% leads từ cùng 3 IP addresses
   └── 🔴 Concentrated IPs → not real diverse traffic

4. Call center feedback (khi bắt đầu gọi):
   ├── 70% SĐT → "không biết sản phẩm gì", "không đặt hàng"
   ├── 20% SĐT → không nghe máy
   ├── 10% SĐT → invalid (dù passed validation)
   └── Confirm rate: 5% (vs normal 55%)

DIAGNOSIS: 
A015 đang inject leads từ phone number database.
Tuần 1-2 chạy legit để build trust, tuần 3 switch sang fraud.

ACTION:
├── Day 0: Pause A015 immediately (cap = 0)
├── Day 0: Hold all pending payments ($1,200)
├── Day 1: Document evidence (timestamps, IPs, call center report)
├── Day 1: Notify A015: "Account suspended pending investigation"
├── Day 2: Calculate losses:
│   ├── 150 leads × 3 days = 450 fake leads
│   ├── If paid at $8/approved: potential fraud $0 (none approved)
│   ├── BUT call center cost wasted: ~$200
│   └── Opportunity cost: cap used for fake leads
├── Day 3: Decision: Ban permanent
├── Day 3: Add to blacklist (email, payment info, IP addresses)
└── Day 5: Post-mortem & rule update

NEW RULES IMPLEMENTED:
├── Auto-flag when volume increases > 3x in 24 hours
├── Auto-flag when lead interval is too regular (< 5% variance)
├── Max leads per IP per day: 5
├── Phone number cluster detection (> 20% same prefix)
└── Mandatory 14-day probation for new affiliates (low cap)

LESSONS:
├── "Good metrics" (low trash) can be faked
├── Volume spike from new affiliate = always investigate
├── Automated detection rules save time and money
├── Trust is built over time, not given upfront
└── Document everything for legal protection
```

### Case Study 4: "Mở thị trường mới — Vietnam"

```
BACKGROUND:
- Network chưa có presence ở Vietnam
- CMO muốn test VN do CPL rẻ và market growing
- Bạn được assign lead initiative

PHASE 1: MARKET RESEARCH (Week 1-2)
├── CPL benchmark VN: $0.3 - $1.5
├── AR benchmark: 25-45%
├── Popular categories: weight loss, beauty, male health
├── Traffic: Facebook dominant, TikTok growing fast
├── Delivery: GHN, Viettel Post, J&T → 2-5 days major cities
├── Call center: Vietnamese speaking required, cost ~$300/month/agent
├── Competitor analysis: networks active in VN: Dr.Cash, Everad, local networks

PHASE 2: PARTNERSHIP SETUP (Week 3-4)
├── Find advertiser with VN offers
├── Selected: 2 advertisers
│   ├── Adv A: 3 weight loss offers, has VN call center
│   └── Adv B: 2 beauty offers, has VN warehouse
├── Negotiate terms:
│   ├── Adv A: $6/approved, cap 50/day
│   └── Adv B: $5/approved, cap 30/day
├── Set payout to affiliates: $4/approved (margin ~$1.5-2)

PHASE 3: SOFT LAUNCH (Week 5-6)
├── Launch 5 offers on AffScale
├── Recruit VN-focused affiliates (3 found)
├── Results after 2 weeks:
│   ├── Offer VN-001 (weight loss): 40 leads/day, AR 32%, trash 15% → ✅
│   ├── Offer VN-002 (weight loss): 25 leads/day, AR 28%, trash 20% → ⚠️
│   ├── Offer VN-003 (weight loss): 15 leads/day, AR 22%, trash 25% → 🔴
│   ├── Offer VN-004 (beauty): 30 leads/day, AR 35%, trash 12% → ✅
│   └── Offer VN-005 (beauty): 10 leads/day, AR 18%, trash 30% → 🔴

PHASE 4: DECISION
├── Scale: VN-001, VN-004 (proven)
├── Optimize: VN-002 (potential, needs LP improvement)
├── Kill: VN-003, VN-005 (below threshold)
├── Recruit more affiliates
├── Cap increase for proven offers

MONTH 3 RESULTS:
├── VN contributing 5% of total network revenue
├── 3 offers active, 150 leads/day total
├── Average AR: 33%
├── Monthly margin: ~$2,700
├── Growing 15% month-over-month
├── Target: 10% of revenue within 6 months

LESSONS:
├── Start small: 5 offers, 3 affiliates → validate then scale
├── Beauty performs better than expected in VN
├── TikTok affiliates delivery better CR than Facebook in VN
├── Delivery is fast (VN advantage over Brazil/Indonesia)
├── Call center quality varies hugely → test 2-3 before committing
└── Local language LP is NON-NEGOTIABLE
```

## 10.3 Quick Reference Card (In ra để bàn)

```
╔══════════════════════════════════════════════════════════╗
║              MKT OPS MANAGER — QUICK REFERENCE           ║
╠══════════════════════════════════════════════════════════╣
║                                                          ║
║  DAILY WORKFLOW:                                         ║
║  09:00 Dashboard review → 09:30 Standup → Actions        ║
║                                                          ║
║  KEY METRICS & THRESHOLDS:                               ║
║  ┌────────┬────────┬────────┬────────┐                   ║
║  │        │ CIS    │ Asia   │ Latam  │                   ║
║  ├────────┼────────┼────────┼────────┤                   ║
║  │ AR     │ >40%   │ >30%   │ >30%   │                   ║
║  │ Trash  │ <15%   │ <18%   │ <15%   │                   ║
║  │ Margin │ >25%   │ >20%   │ >25%   │                   ║
║  └────────┴────────┴────────┴────────┘                   ║
║                                                          ║
║  TRAFFIC LIGHT:                                          ║
║  🟢 At/above benchmark → Maintain                        ║
║  🟡 5-10pp below → Watch & Investigate                   ║
║  🔴 >10pp below → Action Required NOW                    ║
║  ⚫ Unrecoverable → Kill                                 ║
║                                                          ║
║  ESCALATION:                                             ║
║  >$1K/day impact → You handle                            ║
║  >$5K/day impact → CMO (2h)                              ║
║  >$20K/day impact → CMO+COO (1h)                         ║
║  Legal issue → Immediate                                 ║
║                                                          ║
║  ROOT CAUSE DRILL:                                       ║
║  AR drop? → By GEO → By Offer → By Affiliate →           ║
║  By Traffic Source → By Sub-GEO → ROOT CAUSE              ║
║                                                          ║
║  FORMULAS:                                               ║
║  EPL = Revenue / Leads                                   ║
║  ROI = (Revenue - Cost) / Cost × 100%                    ║
║  Margin = Revenue - Payout                               ║
║  Effective AR = Approved / (Leads - Trash)               ║
║                                                          ║
╚══════════════════════════════════════════════════════════╝
```

## 10.4 Tài liệu & nguồn tham khảo thêm

### Đọc thêm (theo priority)

```
MUST READ (Tuần 1-2):
├── AffScale documentation (toàn bộ)
├── Blog posts: "How COD Nutra Works" (search trên STM Forum)
├── YouTube: "Affiliate Marketing Nutra Tutorial" (có nhiều)
└── Sách: "The First 90 Days" — Michael Watkins

SHOULD READ (Tháng 1):
├── STM Forum — Nutra section (case studies thực tế)
├── AffLIFT Forum — Nutra discussions
├── Sách: "High Output Management" — Andy Grove
├── Sách: "Lean Analytics" — Alistair Croll
└── Sách: "Measure What Matters" — John Doerr (OKR)

NICE TO HAVE (Tháng 2-3):
├── Blog: CharlesNgo.com (affiliate marketing insights)
├── Spy tools: browse AdSpy/Anstrex để hiểu creative landscape
├── YouTube channels: iAmAttila, Matuloo (affiliate marketing)
└── Podcast: Affiliate Buzz, The Affiliate Marketing Podcast
```

### Communities

```
├── STM Forum (trả phí, chất lượng cao nhất)
├── AffLIFT (trả phí, tốt cho beginners)
├── AffiliateFix (miễn phí)
├── Reddit: r/affiliatemarketing
├── Telegram groups: search "[nutra affiliate]" groups
└── LinkedIn: connect với người trong ngành
```

### Conferences & Events

```
├── Affiliate World (Barcelona, Bangkok) — lớn nhất
├── TES Affiliate Conferences
├── MAC Affiliate Conference
├── PI LIVE
└── Local meetups trong city của bạn
```
