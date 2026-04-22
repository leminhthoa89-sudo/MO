# Marketing Operations Manager — Scope of Work

> Tài liệu chính thức về vai trò, phạm vi trách nhiệm, quy tắc phối hợp và workflow vận hành cho **Marketing Operations Manager** — trung tâm điều phối và ra quyết định giữa AM/Pub, GEO (Region Ops), Finance và Product.

---

## I. ROLE & POSITIONING

### 1.1. Định nghĩa

**Marketing Operations Manager** = người **quản lý vận hành + ra quyết định** ở giao điểm của **4 trục**:

```
              ┌──────────────┐
              │   AM / PUB   │
              └──────┬───────┘
                     │
┌────────────┐   ┌───┴────────────┐   ┌──────────┐
│     GEO    │───│  MKT Ops Mgr   │───│ PRODUCT  │
│ (Region Ops)│  └───┬────────────┘   └──────────┘
└────────────┘      │
                    │
              ┌─────┴──────┐
              │  FINANCE   │
              └────────────┘
```

*Note: Region Ops = người phụ trách GEO side — gộp chung với GEO trong tài liệu này.*

Không phải người chuyển tin. Không phải người nhập số. Là người:
- **THIẾT KẾ** SOP, workflow, quy trình phối hợp
- **RA QUYẾT ĐỊNH** về product pipeline, cap, lead allocation, deal lifecycle
- **CHỊU TRÁCH NHIỆM** cho P&L portfolio offers và partner health
- **LEAD** team MKT Ops Executives và cross-team alignment

### 1.2. Manager vs Ops Executive — Ranh giới rõ ràng

| Hạng mục | Ops Exec làm (MKT Ops Executive) | **Manager làm** |
|---|---|---|
| Stock check daily | Execute | **Thiết kế rule, threshold, escalation ladder** |
| Báo cáo | Tạo report theo template | **Thiết kế template, approve final, present up** |
| Cap lead | Đề xuất với data | **APPROVE** hoặc **REJECT** |
| Incident | Execute theo runbook | **Thiết kế runbook, lead post-mortem** |
| Partner sync | Tham dự meeting | **Chủ trì meeting, đàm phán** |
| Product launch | Thực thi checklist | **Quyết định Go / No-Go** |
| Lead plan | Draft weekly | **APPROVE** trước thứ 2 |
| Partner tier | Tính số liệu | **Quyết định upgrade/downgrade** |

> **Nguyên tắc vàng:** *Manager không làm việc của Ops Exec. Manager xây hệ thống để Ops Exec làm việc hiệu quả và chỉ can thiệp khi có exception.*

### 1.3. Triết lý cốt lõi

> *"MKT Ops Manager tồn tại để các team khác không phải tự đi tìm vấn đề, không phải tự định nghĩa SOP, không phải tự align lẫn nhau. Manager là người xây hệ thống chạy tự động ở tầng Ops Executive — và là người ra quyết định cuối cùng khi có exception."*

---

## II. 8 CORE RESPONSIBILITIES

### 1️⃣ PRODUCT PIPELINE MANAGEMENT

> *Base on information between AM and GEOs, propose product list and follow product pipeline.*

#### 🎯 MANAGER OWNS (không delegate)
- **Quyết định cuối cùng** product list sẽ launch mỗi quý
- **Phê duyệt** product roadmap sau khi align với AM + GEO
- **Đàm phán** với GEO về exclusivity, timing, volume commitment
- **Kill / pause** sản phẩm không đạt KPI sau phase test
- **Present** product pipeline lên Leadership hàng tháng

#### Team executes
- Gather intel từ AM (Pub demand) + GEO (offer availability, payout)
- Maintain product tracker: proposed → testing → live → paused → killed
- Weekly pipeline update cho Manager

#### Workflow — Monthly Product Review (Thứ 2 đầu tháng)
```
1. Ops Exec compile offers AM đang hỏi + offers GEO đang push
2. Ops Exec scorecard mỗi offer: expected CR, payout, margin, risk, compliance
3. MANAGER decide: Go / No-Go / Test phase
4. MANAGER align với AM + GEO về launch timeline
5. Ops Exec execute launch workflow (WF-4)
```

#### Rules
- Không launch offer không có **scorecard Manager đã duyệt**
- Max **3 offers** trong "testing" phase cùng lúc
- Test phase **max 2 tuần** → Manager decide keep hay kill
- Mọi product decision phải ghi vào Product Decision Log

#### KPI Manager
- ≥60% offer launched đạt break-even trong tháng đầu
- Zero offer launch mà không qua Monthly Product Review
- Product pipeline có ≥5 candidate offers active mọi lúc

---

### 2️⃣ CROSS-DEPARTMENT STANDARDIZATION

> *Standardize cross-department communication / workflow / SOP / reports across AM, GEOs (Region Ops), FN.*

#### 🎯 MANAGER OWNS
- **THIẾT KẾ** toàn bộ SOP cho các quy trình cross-team
- **OWN** SOP library — version control, review quarterly
- **ENFORCE** compliance — ai không follow SOP phải giải trình
- **LEAD** cross-team alignment meetings (weekly + monthly)
- **ESCALATION POINT** cho mọi cross-team conflict

#### SOP Library Manager phải own
| Mã | Nội dung |
|---|---|
| **SOP-01** | AM ↔ Ops daily sync (stock, cap, performance) |
| **SOP-02** | GEO ↔ Ops weekly sync (stock forecast, restock, disputes) |
| **SOP-03** | Finance ↔ Ops reconciliation (weekly + monthly close) |
| **SOP-04** | Compliance check workflow (new market, new offer) — owned by GEO/Region Ops |
| **SOP-05** | Product ↔ Ops tech integration (tracking, postback, pixel) |
| **SOP-06** | LDP ↔ Sales ↔ Ops alignment (weekly audit) |
| **SOP-07** | Incident escalation ladder |
| **SOP-08** | Partner P&L reporting |

#### Rules
- SOP review mỗi quý — Manager approve changes, không delegate
- Mọi escalation cross-team → **Manager trong vòng 2h**
- Không có quy trình ngầm / off-record — mọi thứ phải có SOP
- Team compliance ≥95% với SOP — measure qua audit

#### KPI Manager
- 100% quy trình cross-team có SOP documented
- Cross-team incident resolution time <24h
- Team compliance rate với SOP ≥95%
- Quarterly SOP audit hoàn thành đúng hạn

---

### 3️⃣ LEAD COST & VOLUME CONTROL

> *Control lead cost **and lead volume** across GEOs / Categories / Pubs / Deals.*

**Hai trục ngang nhau** — vừa quản **cost** (không để CPL vượt target), vừa quản **volume** (đủ lead để deliver commitment, không dư thành burnout).

#### 🎯 MANAGER OWNS
- **SET** target cost & volume theo quý (baseline ngân sách)
- **APPROVE** bất kỳ thay đổi CPL nào vượt target
- **NEGOTIATE** với AM khi cost lệch target
- **DECIDE** pub/GEO nào scale, pub/GEO nào cut
- **OWN** lead volume plan — đảm bảo đủ volume theo commitment, không để pub idle hoặc GEO overflow

#### Team executes
- Daily tracking: CPL & volume theo GEO / Category / Pub / Deal
- Weekly variance report
- Flag outliers cho Manager **ngay khi vượt target** (không đợi 3 ngày)

#### Manager Dashboard (track daily)
| Metric | Target | Threshold alert |
|---|---|---|
| **Avg CPL** theo GEO | Set per quarter | **>target +5% → alert ngay** |
| **Daily lead volume** | Set per quarter | ±15% → alert |
| Cost per approved lead | GEO baseline | +10% |
| Rejection rate | <5% | >8% |
| Volume fulfillment rate | ≥95% commitment | <90% → alert |

#### Rules (Cost)
- **CPL > target (bất kỳ mức nào) → Ops Exec alert Manager NGAY**, không đợi 3 ngày
- CPL > target +5% → **Manager phải action trong 24h** (cap down, renegotiate, hoặc pause)
- Không có quyết định đổi CPL qua DM riêng — tất cả qua ticket/group chính thức
- Mọi "special deal" CPL phải có Manager sign-off bằng văn bản

#### Rules (Volume)
- Daily volume > target **+15%** → alert ngay (risk overburn budget / GEO overflow)
- Daily volume < target **-15%** → alert ngay (risk under-deliver commitment với AM/Pub)
- Volume fulfillment rate < 90% tuần → Manager review với AM + GEO, rebalance pipeline
- Volume spike cuối tuần do Pub scale → bắt buộc báo trước 24h (theo SOP-01)

#### KPI Manager
- CPL variance vs target **<5%** weekly (thay vì 15% quarterly — tight control)
- Volume delivery **≥95%** of committed volume
- Zero "ad-hoc" CPL change without Manager approval
- Zero case overburn budget do không control volume kịp

---

### 4️⃣ CAP MANAGEMENT (INCREASE / DECREASE BASED ON DEAL PERFORMANCE)

> *Increase / down cap based on deal performance.*

#### 🎯 MANAGER OWNS
- **APPROVE** mọi quyết định cap up/down **>20%** daily volume
- **SET** performance thresholds trigger cap change
- **MEDIATE** khi AM muốn scale nhưng Ops/GEO báo rủi ro
- **RESOLVE** conflict giữa Pub (muốn scale) vs GEO (lo capacity)

#### Cap Change Decision Matrix
| Situation | Action | Decision owner |
|---|---|---|
| AR% drop >20% trong 3 ngày | Cap down 30% | Ops Exec propose, **Manager approve** |
| Stock <10 ngày | Cap down 50% | Ops Exec execute ngay, notify Manager |
| CR ↑ >30% ổn định 5 ngày | Cap up 20% | Ops Exec propose, **Manager approve** |
| GEO SOS | Cap down 70% | Ops Exec execute ngay, notify Manager |
| Pub request scale >50% | Cap up theo thỏa thuận | **Manager decide** (cần align GEO trước) |
| Pub request scale 20–50% | Cap up | **Manager approve** |
| Pub request scale <20% | Cap up | Ops Exec execute, notify Manager |

#### Rules
- Mọi cap change phải có **số liệu backing + thời gian review**
- Cap up **>50%** bắt buộc align trước với GEO (capacity confirm)
- Cap down khẩn cấp: Ops Exec execute trước, Manager notified trong 1h
- Weekly cap review meeting (Manager chủ trì)

#### KPI Manager
- **Zero stock-out** do cap không đúng lúc
- **Zero Pub complaint** về "sudden cap" không explain được
- Cap decision turnaround **<4h** trong giờ hành chính

---

### 5️⃣ LEAD PLAN — CHECK & BALANCE

> *Check and balance lead plan across offers, GEOs, and pubs.*

#### 🎯 MANAGER OWNS
- **APPROVE** weekly lead plan trước **thứ 2 mỗi tuần**
- **REBALANCE** khi forecast lệch thực tế **>20%**
- **OWN** capacity allocation strategy (offer nào được bao nhiêu % volume)
- **PRIORITIZE** khi capacity không đủ (Pub A hay Pub B ưu tiên?)

#### Team executes
- Draft weekly lead plan (Thứ 6 cho tuần sau)
- Daily actual vs plan variance tracking
- Propose rebalance khi cần

#### Weekly Lead Plan Template
```
| Offer | GEO | Pub | Mon | Tue | Wed | Thu | Fri | Sat | Sun | Total |
|-------|-----|-----|-----|-----|-----|-----|-----|-----|-----|-------|
```

#### Rules
- Lead plan approved = **binding**. Change giữa tuần cần Manager approve + reason
- Weekly variance review **thứ 6 hàng tuần** — Manager chủ trì
- Monthly capacity review: điều chỉnh baseline dựa trên 3-month rolling
- Lead plan vs actual gap >30% tuần → mandatory root cause analysis

#### KPI Manager
- Weekly plan vs actual variance **<15%**
- **Zero "blind week"** (tuần không có plan)
- Rebalance decision turnaround **<6h**

---

### 6️⃣ DEAL PERFORMANCE MONITORING & OPTIMIZATION (END-TO-END)

> *Monitor and optimize deal performance from create deal until deal success / fail.*

#### 🎯 MANAGER OWNS
- **OWN deal P&L** — mỗi deal = mini-business, Manager chịu trách nhiệm
- **DECIDE** khi nào kill deal (lose money 2 tuần liên tiếp)
- **APPROVE** optimization experiments (creative, price, GEO, cap)
- **LEAD** deal review meetings (weekly + ad-hoc khi deal fail)

#### Deal Lifecycle (Manager tracks từng stage)
```
1. CREATE   → Deal onboarding, terms align với GEO + AM
2. LAUNCH   → First 7 days performance watch (daily review)
3. SCALE    → Scale decisions, cap management
4. MAINTAIN → Steady state monitoring (weekly)
5. DECLINE  → Optimization attempts hoặc exit plan
6. KILL/WIN → Post-mortem / case study
```

#### Team executes
- Daily deal performance dashboard
- Flag declining deals
- Execute optimization experiments per Manager direction

#### Rules
- Mọi deal có **scorecard Manager approved** trước launch
- Weekly deal review: Manager present **top 5 winners + bottom 5 losers**
- Deal lỗ 2 tuần liên tục → **mandatory review**, Manager decide kill/optimize
- Post-mortem cho mọi deal killed → doc hóa lesson learned vào library

#### KPI Manager
- Deal profitability rate **≥70%** (deal có lãi / tổng deal live)
- Avg deal lifespan **≥3 tháng**
- Optimization hit rate **≥40%** (experiment thành công)

---

### 7️⃣ PARTNER PERFORMANCE ANALYSIS (PROFIT AFTER CIT — FN VIEW)

> *Analyze partner performance by Profit after CIT, from Finance view.*

#### 🎯 MANAGER OWNS
- **OWN partner P&L** theo góc nhìn Finance (profit after corporate income tax)
- **TIER partners** — S/A/B/C tier dựa trên profit contribution
- **DECIDE** upgrade / downgrade / terminate partner
- **NEGOTIATE** terms với partner tier S (rate, exclusivity, priority)
- **REPORT** partner performance lên Leadership hàng tháng

#### Partner Tier Framework
| Tier | Profit after CIT/tháng | Treatment |
|---|---|---|
| **S** | >$50k | Priority allocation, exclusive deals, monthly review với Manager |
| **A** | $20k–$50k | Stable allocation, quarterly review |
| **B** | $5k–$20k | Standard, semi-annual review |
| **C** | <$5k | Probation, 2 quarter để climb hoặc drop |

#### Team executes
- Monthly P&L calculation per partner (với Finance)
- Partner scorecard preparation
- Data support cho Manager meetings

#### Rules
- Monthly partner P&L review với Finance — **cùng Manager**, không delegate
- Partner tier change cần:
  1. **2 quarter data** backing
  2. **Finance sign-off**
  3. **AM agreement**
- Không có "gut feeling" partner decision — tất cả từ Profit after CIT
- Partner S tier có direct line với Manager — không qua Ops Exec

#### KPI Manager
- Top 10 partners contribute **≥70%** profit (Pareto healthy)
- Partner churn rate **<15%/quarter** (tier A/S)
- Partner P&L report on-time mỗi tháng (ngày 5)

---

### 8️⃣ LDP CONTENT ALIGNMENT (PRICE, PRODUCT) WITH SALES PERFORMANCE

> *Align content on LDP (price, product info, etc.) with performance of sale.*

#### 🎯 MANAGER OWNS
- **APPROVE** mọi LDP content change: price, claims, product details
- **LEAD** alignment giữa Landing team, Sales, và Ops
- **DECIDE** khi nào update LDP dựa trên sales feedback (AR thấp? Sales complaint về lead quality?)
- **ENSURE** LDP không "sell what we don't have" — stock alignment là P0

#### Team executes
- Weekly LDP audit: check price, claims, stock status
- Log sales feedback về lead expectation vs reality
- Coordinate với Landing team on changes

#### Weekly LDP Audit Checklist
- [ ] Price trên LDP = price Sales quote cho customer
- [ ] Product info (dosage, ingredient, shipping) = actual
- [ ] Stock status (in stock / limited / pre-order) = reality
- [ ] Promotional claims → Reg. Ops đã approve
- [ ] A/B test results reviewed
- [ ] CTA/form flow chạy đúng

#### Rules
- LDP change impact **price / product / claims** → cần **Manager + Sales + Reg. Ops** approval
- Mismatch giữa LDP và sales script → **P0 fix trong 24h**
- Weekly LDP audit mandatory — Manager review report mỗi thứ 2
- LDP change mà không qua Ops Manager → warning, lặp lại → escalate lên VP

#### KPI Manager
- **Zero "LDP–sales mismatch"** incident/tháng
- AR% improvement sau mỗi LDP optimization cycle
- Sales team satisfaction với LDP accuracy **≥90%**

---

## III. 🎯 MANAGER-SPECIFIC RESPONSIBILITIES (ngoài 8 core)

Đây là phần **KHÔNG DELEGATE được** — chỉ Manager mới có thẩm quyền và trách nhiệm:

### 3.1. People Management
- Hire & onboard MKT Ops Executives
- **Weekly 1-on-1** với mỗi direct report
- **Quarterly performance review**
- Career development plan cho từng Ops Exec
- Conflict resolution trong team
- Terminate underperformer (sau 2 quarter probation)

### 3.2. Strategic Planning
- **Quarterly OKR** planning cho Ops team
- **Annual budget** proposal cho Leadership
- **Hiring plan** — khi nào mở thêm head count
- Tool/system investment decisions (dashboard, automation, tracker)

### 3.3. Cross-Functional Leadership
- Represent Ops ở **Leadership meetings**
- Own Ops-related OKR commitment với **CEO/COO**
- Build bridge giữa các department head: AM Head, GEO Head (Region Ops), FN Head, Product Head

### 3.4. Escalation & Crisis Management
- **Primary escalation point** cho mọi Ops incident P0/P1
- Lead **post-mortem** cho major incidents
- Crisis communication với partners/leadership khi có sự cố

### 3.5. P&L Ownership (ULTIMATE accountability)
- **Deal P&L** (Resp. #6)
- **Partner P&L** (Resp. #7)
- **Cost efficiency** (Resp. #3)
- **Monthly P&L review** với Finance + Leadership

### 3.6. SOP & System Design
- Design **new SOP** khi có gap
- **Quarterly SOP audit** & update
- **Automation roadmap** — work với Product để auto hóa manual tasks

### 3.7. Reporting Up
- **Weekly report → COO:** top wins, top losses, risks
- **Monthly business review → Leadership:** full P&L, partner health, capacity plan
- **Quarterly strategic review → CEO:** big bets, roadmap

---

## IV. STAKEHOLDER RULES OF ENGAGEMENT

### 4.1. Với AM / PUB
**Họ cần:** quyết định nhanh + số liệu tin cậy + đề xuất rõ ràng.

**Rules:**
1. Mọi alert gửi AM phải kèm **recommendation** (không chỉ data)
2. Format báo stock 4 trường: `GEO | Remaining | Pace | ETA out | Proposal`
3. **SLA response:** ≤2h in-hours, ≤6h out-of-hours
4. AM/Pub scale lead **>20%** → ping Ops + GEO **trước 24h**, không ngoại lệ
5. Daily sync 15 phút đầu ngày, weekly review 1h cuối tuần
6. **Manager** là escalation point cho cost dispute, cap conflict, partner issue

### 4.2. Với GEO
**Họ cần:** pace ổn định, forecast chính xác, không bị dump lead đột ngột.

**Rules:**
1. Ops phải phát hiện bất thường **TRƯỚC GEO**. Nếu GEO SOS trước → **Ops fail**
2. Stock <15 ngày → chuyển weekly alert sang **daily alert**
3. GEO alert "còn X ngày" = baseline, Ops tự recalculate mỗi ngày
4. Không push lead vượt capacity đã align
5. **Manager** chủ trì weekly GEO meeting — không delegate khi discuss capacity/payout

### 4.3. Với FINANCE
**Họ cần:** số sạch, đối soát đúng hạn, không sửa ngang.

**Rules:**
1. Weekly reconciliation thứ 2: lead delivered vs approved vs paid
2. Monthly invoice trước **ngày 5**, kèm breakdown offer–GEO
3. Retroactive edit → **log + lý do + Manager approval**
4. GEO dispute → Ops giải quyết trước, không đẩy Finance
5. Cash flow forecast weekly
6. **Manager** present monthly P&L với Finance Head

### 4.4. Với PRODUCT
**Họ cần:** bug report rõ ràng, priority hợp lý, không spam ticket.

**Rules:**
1. Tech issue escalation: screenshot + timestamp + offer/GEO + lead impacted + priority (P0/P1/P2)
2. Onboard offer mới — Ops test tracking trước khi live
3. Weekly tech sync 30 phút review tracking health, pixel fire rate, postback
4. Ngoài giờ chỉ ping P0 (revenue blocker >$1k/h)
5. **Manager** own automation roadmap với Product Head

---

## V. META-RULES (xuyên suốt mọi responsibility)

1. **Proactive > Reactive.** Ops phải thấy vấn đề trước khi nổ. Ngoại bộ phát hiện trước → **Ops fail**.

2. **Data + Recommendation, never data alone.** Không báo con số trần trụi. Luôn kèm: so sánh / nguyên nhân / đề xuất.

3. **Rule 20%.** Bất kỳ metric nào lệch >20% so với baseline → alert ngay, không đợi threshold hết hàng.

4. **Rule 24h.** Mọi quyết định scale >20% phải báo trước 24h. Ngoại lệ duy nhất: P0 emergency.

5. **Single Source of Truth.** Chỉ 1 dashboard chính thức, 1 nơi lưu quyết định. Không quyết định qua DM riêng.

6. **No silent failure.** Làm sai không sao — **im lặng khi làm sai** mới không chấp nhận được.

7. **Action-first, apology-later.** Khi thấy bất thường rõ ràng, ra quyết định tạm rồi báo cáo. Không đứng im chờ lệnh.

8. **Log everything.** Mọi quyết định lớn → decision log: ai quyết / lý do / số liệu căn cứ.

9. **Manager doesn't do Ops Exec work.** Manager caught doing Ops Exec work = team đang thiếu người hoặc Manager không trust team.

10. **Escalate, don't absorb.** Manager gặp vấn đề vượt thẩm quyền → escalate Leadership, đừng ôm một mình.

---

## VI. REPORTING CADENCE

### IC → Manager
| Tần suất | Report | Format |
|---|---|---|
| Daily (9h) | Stock + pace + red flags | Dashboard digest |
| Weekly (T6) | Variance, deal performance, cost review | Weekly ops report |
| Ad-hoc | Red flag alert | Group chat + ticket |

### Manager → Leadership
| Tần suất | Report | Audience |
|---|---|---|
| **Weekly (T2)** | Top wins, top losses, risks, need decisions | COO |
| **Monthly (ngày 5)** | Full P&L, partner health, capacity plan, OKR progress | Leadership team |
| **Quarterly** | Strategic review, big bets, hiring, tooling | CEO |

### Manager ↔ Stakeholders
| Tần suất | Meeting | Ai chủ trì |
|---|---|---|
| Daily 15ph | Ops team stand-up | Manager |
| Weekly 1h | AM sync | Manager |
| Weekly 1h | GEO sync | Manager |
| Weekly 30ph | Product tech review | Product |
| Bi-weekly 1h | Finance reconciliation | Finance |
| Monthly 1h | Reg. Ops compliance | Reg. Ops |
| Monthly 2h | Partner P&L review | Manager |

---

## VII. KPIs FOR MKT OPS MANAGER

### A. Operational KPIs (8 core responsibilities)
| # | KPI | Target |
|---|---|---|
| 1 | Offer break-even rate trong tháng đầu | ≥60% |
| 2 | SOP compliance rate | ≥95% |
| 3 | CPL variance vs target | <15% quarterly |
| 4 | Stock-out incidents do cap sai | **0** |
| 5 | Lead plan variance vs actual | <15% weekly |
| 6 | Deal profitability rate | ≥70% |
| 7 | Top 10 partners % profit contribution | ≥70% |
| 8 | LDP-Sales mismatch incidents | **0**/tháng |

### B. Manager-level KPIs (beyond 8 core)
| KPI | Target |
|---|---|
| Team retention (IC tier A) | ≥90% annually |
| Cross-team NPS (AM, GEO, FN, Reg, Product survey) | ≥8/10 |
| Incident post-mortem completion | 100% P0/P1 within 48h |
| OKR hit rate | ≥70% quarterly |
| Budget variance | <10% annually |

---

## VIII. CASE STUDY — Stock-out Incident (bài học Manager)

### Timeline thực tế
| Ngày | Sự kiện | Lỗi hệ thống |
|---|---|---|
| 13/4 | Stock còn 23 ngày | — |
| 16/4 | Stock rớt 13 ngày (mất 10 ngày trong 3 ngày) | ❌ Không có rule "20% deviation → alert" |
| 18–19/4 | Pub scale lead cuối tuần không báo | ❌ SOP không ràng buộc Pub báo trước scale |
| 20/4 | GEO SOS cap xuống 20 | ❌ Ops reactive, chờ GEO SOS mới action |
| 22/4 | Hết hàng | — |

### Root cause từ góc nhìn Manager
Đây **không phải lỗi IC** — đây là **lỗi Manager** vì:

1. ❌ Manager không thiết kế **SOP-01** (AM↔Ops daily sync) đủ chặt → Pub scale không báo
2. ❌ Manager không thiết kế **threshold alert** (20% deviation) → IC không biết khi nào phải alert
3. ❌ Manager không huấn luyện IC về **proactive mindset** → IC chỉ react khi GEO SOS
4. ❌ Manager không có **weekly stock review** để catch pattern "23→13 trong 3 ngày"

### Manager action sau incident
1. **Design SOP-01 v2:** Pub scale >20% → báo Ops trước 24h (binding)
2. **Install Rule 20%:** mọi metric lệch 20% → Ops Exec alert trong 30 phút
3. **Weekly stock review:** Manager chủ trì, review trend không chỉ snapshot
4. **IC training:** proactive escalation workshop, review real case
5. **Automation:** work với Product build auto-alert khi stock pace tăng bất thường

### Bài học
> *Manager chịu trách nhiệm cho vấn đề hệ thống, không đổ lỗi cho IC. Mỗi incident = cơ hội nâng cấp hệ thống, không phải cơ hội khiển trách.*

---

## IX. TÀI LIỆU LIÊN QUAN

- Nutra Affiliate Operations Guide (20 chapters) — operational deep-dive
- MKT Ops Daily Tracking System (6 CSV templates + HTML tool)
- SOP Library (SOP-01 → SOP-08) — referenced in Section II.2

---

*Document owner: Marketing Operations Manager*
*Review cadence: Quarterly, hoặc sau mỗi P0/P1 incident*
*Version: 2.0 — full rewrite aligned với 8 official responsibilities*
