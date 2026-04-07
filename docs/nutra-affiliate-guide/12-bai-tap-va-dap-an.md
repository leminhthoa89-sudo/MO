# Chương 12: Bài tập thực hành & Đáp án

> **Cách dùng:** Đọc đề bài, tự trả lời TRƯỚC, rồi mới xem đáp án.
> Mỗi bài tập mô phỏng tình huống thực tế bạn sẽ gặp hàng ngày.

---

## BÀI TẬP 1: Đọc Dashboard cơ bản

### Đề bài:

Sáng thứ Hai, bạn mở dashboard và thấy số liệu ngày Chủ Nhật:

```
                 Sunday     Saturday    Friday     Thu Avg(4w)
Leads            1,680      2,150       2,200      2,180
Approved           630        845         870        856
AR               37.5%      39.3%       39.5%      39.3%
Trash Rate       14.2%      12.5%       12.8%      12.6%
Revenue          $8,820    $11,830     $12,180    $11,984
Margin           $3,024     $4,178      $4,284     $4,227
Margin Rate      34.3%      35.3%       35.2%      35.3%
```

**Câu hỏi:**

1. Có vấn đề nghiêm trọng nào không?
2. Bạn có nên raise alert không?
3. Cần làm gì tiếp theo?

---

<details>
<summary><b>👉 CLICK ĐỂ XEM ĐÁP ÁN BÀI 1</b></summary>

### Đáp án:

**1. KHÔNG có vấn đề nghiêm trọng.**

Phân tích:
- Leads giảm 22% (1,680 vs 2,150) → NHƯNG đây là Chủ Nhật
- Trong nutra COD, **Chủ Nhật thường có volume thấp hơn 15-25%** vì:
  - Một số affiliates giảm budget cuối tuần
  - Facebook CPM thay đổi vào cuối tuần
  - Call center có thể có ít nhân sự hơn
- AR 37.5% giảm nhẹ so với weekday (39.3%) → bình thường cho weekend
- Trash rate 14.2% tăng nhẹ → vẫn dưới threshold 15%
- Margin rate 34.3% giảm nhẹ → acceptable

**2. KHÔNG cần raise alert** — đây là pattern weekend bình thường.

**3. Cần làm:**
- So sánh với **Chủ Nhật tuần trước** (không phải thứ 5-6-7):
  - Nếu Sunday W13 cũng ~1,680 → confirmed normal pattern
  - Nếu Sunday W13 là 2,000 → thì CÓ vấn đề
- Ghi note vào daily report: "Sunday dip consistent with weekly pattern"
- Không cần action nào thêm

**BÀI HỌC:** Luôn so sánh **cùng ngày tuần trước** (WoW), không so sánh với ngày trước đó. Weekend vs weekday không phải apple-to-apple.

</details>

---

## BÀI TẬP 2: Phát hiện vấn đề từ bảng GEO

### Đề bài:

Bảng performance tuần này:

```
GEO  │ Leads │ Appr │  AR   │ Trash%│ Rev     │ WoW Rev │ WoW AR
─────┼───────┼──────┼───────┼───────┼─────────┼─────────┼────────
RU   │ 4,100 │1,763 │ 43.0% │ 11.0% │ $26,445 │  +5.0%  │  0pp
KZ   │ 2,000 │1,080 │ 54.0% │  9.5% │ $10,800 │  +3.2%  │ -1.8pp
UA   │ 1,900 │  798 │ 42.0% │ 13.0% │ $10,374 │  +6.0%  │ +1.0pp
TH   │ 1,800 │  504 │ 28.0% │ 14.0% │ $ 4,032 │  -1.5%  │ -5.5pp
VN   │ 1,600 │  448 │ 28.0% │ 22.0% │ $ 3,136 │ +18.0%  │ -4.0pp
PH   │ 1,100 │  330 │ 30.0% │ 15.0% │ $ 2,640 │  +2.0%  │  0pp
BR   │ 1,300 │  273 │ 21.0% │ 16.0% │ $ 3,549 │ -12.0%  │ -4.0pp
MX   │   700 │  259 │ 37.0% │ 14.0% │ $ 2,849 │  +4.0%  │ +1.0pp
ID   │   450 │   81 │ 18.0% │ 20.0% │ $   567 │  +1.0%  │ -3.0pp
```

**Câu hỏi:**

1. Xếp hạng 3 GEO đáng lo ngại nhất theo thứ tự ưu tiên
2. Cho mỗi GEO đáng lo: xác định vấn đề chính và đề xuất action
3. GEO nào đang tốt nhất và tại sao?
4. VN revenue tăng 18% — đây là tin tốt hay xấu?

---

<details>
<summary><b>👉 CLICK ĐỂ XEM ĐÁP ÁN BÀI 2</b></summary>

### Đáp án:

**1. Top 3 đáng lo nhất:**

**#1: Thailand 🔴🔴🔴**
- AR 28%, giảm 5.5pp WoW → **giảm mạnh nhất**
- Benchmark TH: 30%+, hiện dưới benchmark
- Revenue giảm -1.5% dù volume có thể tăng
- ĐÂY LÀ VẤN ĐỀ CẤP BÁCH NHẤT vì drop 5.5pp trong 1 tuần là rất lớn

**#2: Brazil 🔴🔴**
- AR 21%, **thấp nhất trong bảng** (trừ ID đang test)
- Revenue giảm 12% WoW → **giảm revenue lớn nhất**
- AR giảm 4pp WoW, đang ở mức critical
- Trend: likely tiếp tục xấu nếu không intervention

**#3: Vietnam 🔴**
- Trash rate 22% → **VƯỢT threshold 18%**
- AR giảm 4pp WoW (32% → 28%)
- Revenue tăng 18% NHƯNG quality giảm → NGUY HIỂM

**2. Analysis & Actions:**

**Thailand:**
- Vấn đề: AR crash 5.5pp = gần chắc chắn có systemic issue
- Possible: delivery delay, call center issue, hoặc 1 affiliate lớn gửi bad traffic
- Action: 
  - Drill down by offer (offer nào giảm?)
  - Drill down by affiliate
  - Check call center response time
  - Escalate to AR team → check with advertiser

**Brazil:**
- Vấn đề: AR 21% = below critical threshold, revenue đang crash
- Action:
  - Review nên pause thêm offer nào (ngoài KetoMax đã pause)
  - Check MaxPotency split SP/Regions đã giúp chưa
  - Escalate to CMO nếu chưa có improvement plan

**Vietnam:**
- Vấn đề: Trash 22% là RED FLAG
- Action:
  - Identify affiliate(s) nào đang push trash cao
  - Likely A06 (VietAds) — volume tăng 18% + trash tăng = đang mua low-quality traffic
  - Issue formal warning to high-trash affiliates
  - Set auto-pause rule: trash > 25% → pause

**3. GEO tốt nhất: Russia 🟢**
- AR 43% — stable (0pp change WoW)
- Revenue +5% WoW — growing
- Trash 11% — healthy
- Lý do: mature market, proven offers, quality affiliates
- *Honorable mention: Ukraine* — AR tăng 1pp, revenue +6%, solid trajectory

**4. VN revenue +18% — ĐÂY LÀ TIN XẤU NGỤY TRANG TIN TỐT:**
- Revenue tăng vì VOLUME tăng (nhiều leads hơn)
- NHƯNG AR giảm 4pp VÀ trash tăng lên 22%
- Nghĩa là: affiliates đang đổ thêm traffic CHẤT LƯỢNG THẤP
- Nhiều lead hơn × approval rate thấp hơn = tạm thời revenue tăng
- NHƯNG NẾU TIẾP TỤC: advertiser sẽ complain, có thể giảm payout/cap
- Margin thực tế per lead đang giảm
- **Đây là trap phổ biến**: volume tăng che đậy quality giảm

**BÀI HỌC:** Revenue tăng KHÔNG phải lúc nào cũng tốt. Luôn check quality metrics (AR, trash) cùng lúc. "Vanity metrics" (leads, revenue) có thể misleading.

</details>

---

## BÀI TẬP 3: Affiliate Analysis

### Đề bài:

Bạn nhận được yêu cầu từ AM team: 3 affiliates dưới đây đều xin tăng payout thêm $1.50/approved. Hiện tại payout standard là $9/approved.

```
         │ Leads/day │ AR    │ Trash │ Active │ Offers  │ Current Payout
─────────┼───────────┼───────┼───────┼────────┼─────────┼───────────────
A11      │    320    │ 46.2% │  8.0% │ 8 months│ 4 offers│ $9.00
A12      │    180    │ 33.5% │ 18.5% │ 2 months│ 2 offers│ $9.00
A13      │     45    │ 51.0% │  5.0% │ 5 months│ 1 offer │ $9.00
```

Margin hiện tại: Revenue $14/approved, Payout $9/approved = $5 margin (35.7%).
Nếu tăng $1.50: Payout $10.50, Margin $3.50 (25.0%).

**Câu hỏi:**

1. Quyết định cho từng affiliate: Approve / Partial / Reject? Tại sao?
2. Nếu approve, với điều kiện gì?
3. Impact tài chính tổng nếu approve tất cả?

---

<details>
<summary><b>👉 CLICK ĐỂ XEM ĐÁP ÁN BÀI 3</b></summary>

### Đáp án:

**A11: APPROVE (với điều kiện)**
- Volume 320 leads/day = Tier A affiliate → high value
- AR 46.2% = TRÊN benchmark → quality tốt
- Trash 8% = xuất sắc
- 8 tháng active, 4 offers = invested in network → loyal
- **Rủi ro mất A11 lớn hơn rủi ro giảm margin**
- Điều kiện: Tăng $1.00 (không full $1.50), tie to volume commitment ≥350 leads/day
- Hoặc: Tăng full $1.50 nhưng chỉ cho leads có AR > 40%
- New margin: $14 - $10 = $4 (28.6%) — vẫn acceptable

**A12: REJECT (hoặc partial với điều kiện strict)**
- Volume 180 = mid-tier, không đủ leverage
- AR 33.5% = **DƯỚI benchmark** (40% cho CIS)
- Trash 18.5% = **sát threshold** 
- Chỉ 2 tháng = mới, chưa proven long-term
- **Tăng payout cho affiliate chất lượng thấp = bad precedent**
- Counter-offer: "Cải thiện AR lên 38%+ trong 4 tuần → sẽ xem xét bump $0.50"
- Hoặc: Hoàn toàn reject, explain lý do quality chưa đạt

**A13: REJECT (nhưng nurture)**
- AR 51% = xuất sắc, trash 5% = tốt nhất
- NHƯNG volume chỉ 45 leads/day = impact rất thấp
- Tăng $1.50 × 45 × 51% approved = $34.43/day thêm = ~$1,000/month
- Không significant impact nhưng cũng không significant cost
- Counter-offer: "Tăng volume lên 100+ leads/day → sẽ bump $1.00"
- Đây là cách incentivize A13 scale lên

**Tổng impact nếu approve ALL (worst case):**
```
A11: 320 leads × 46.2% AR × $1.50 = $221.76/day = $6,653/month
A12: 180 leads × 33.5% AR × $1.50 = $90.45/day  = $2,714/month
A13:  45 leads × 51.0% AR × $1.50 = $34.43/day   = $1,033/month

Total margin loss: $346.64/day = $10,399/month
```

$10,400/month margin loss là ĐÁNG KỂ → không nên approve tất cả.

**Recommended decision:**
```
A11: +$1.00 if volume ≥350/day    → Cost: ~$5,100/month, justified
A12: Reject, offer quality path    → Cost: $0
A13: +$0.50 if volume ≥100/day    → Cost: minimal until they scale
                                   
Net impact: ~$5,100/month (vs $10,400 if approve all)
```

**BÀI HỌC:** Payout decisions phải dựa trên 3 yếu tố: volume, quality, và retention risk. Không phải ai xin cũng cho. Data-driven negotiation.

</details>

---

## BÀI TẬP 4: Root Cause Analysis

### Đề bài:

Offer "SkinGlow Thai" (Thailand) performance 4 tuần gần nhất:

```
         │ Leads/day │  AR   │ Trash │ CR    │ Confirm Rate│ Delivery Rate
─────────┼───────────┼───────┼───────┼───────┼─────────────┼──────────────
Week 11  │    110    │ 38.2% │ 11.0% │ 9.5%  │   62.0%     │   72.0%
Week 12  │    125    │ 36.0% │ 12.5% │ 8.8%  │   60.0%     │   70.5%
Week 13  │    140    │ 31.5% │ 14.0% │ 7.5%  │   55.0%     │   68.0%
Week 14  │    160    │ 28.0% │ 16.5% │ 6.2%  │   50.0%     │   65.0%
```

Affiliate breakdown cho Week 14:

```
Affiliate │ Leads/day │  AR   │ Trash │ Traffic Source
──────────┼───────────┼───────┼───────┼──────────────
A08       │     70    │ 34.0% │ 10.0% │ Facebook
A14       │     50    │ 25.0% │ 18.0% │ TikTok
A15       │     40    │ 22.0% │ 24.0% │ Push notifications
```

**Câu hỏi:**

1. AR đang giảm — tìm TẤT CẢ nguyên nhân có thể từ data
2. Xếp hạng nguyên nhân theo likelihood
3. Action plan chi tiết (immediate, short-term, long-term)
4. Nếu chỉ được chọn 1 action duy nhất, chọn gì?

---

<details>
<summary><b>👉 CLICK ĐỂ XEM ĐÁP ÁN BÀI 4</b></summary>

### Đáp án:

**1. Tất cả nguyên nhân từ data:**

**A) Traffic quality degradation (CHÍNH)**
- Volume tăng 110 → 160 (+45%) nhưng AR giảm 38% → 28%
- Trash tăng 11% → 16.5%
- CR giảm 9.5% → 6.2% (landing page không convert tốt nữa)
- A15 (Push) trash 24% — RẤT CAO
- A14 (TikTok) AR 25%, trash 18% — below standard
- **Pattern: volume tăng vì thêm affiliates chất lượng thấp hơn**

**B) Call center degradation**
- Confirm rate giảm 62% → 50% (drop 12pp)
- Có thể call center CÙNG bị ảnh hưởng bởi trash (gọi leads rác mất thời gian)
- Hoặc call center quá tải vì volume tăng (110 → 160 leads)
- Hoặc call center quality giảm (agents mới?)

**C) Delivery degradation**
- Delivery rate giảm 72% → 65%
- Có thể delivery time tăng
- Hoặc address quality giảm (leads kém → address kém)

**D) Ad/LP fatigue**
- CR giảm 9.5% → 6.2% = landing page fatigue
- Cùng LP chạy lâu → audience đã thấy → ít convert

**E) Audience saturation (ít likely hơn cho TH)**
- Thailand 70M dân, khó saturate trong 4 tuần
- Nhưng nếu target narrow (women 35-50 Bangkok) → có thể

**2. Xếp hạng likelihood:**

```
#1 (80% likely): Traffic quality — thêm A14, A15 kéo average xuống
    Evidence: A08 (FB) vẫn AR 34%, trong khi A14 (TikTok) 25%, 
    A15 (Push) 22%. Gap rõ ràng theo affiliate.

#2 (60% likely): Call center overload — cascading effect từ #1
    Evidence: Confirm rate giảm đều. Volume tăng 45% nhưng call center 
    capacity có thể không tăng tương ứng. Trash leads waste agent time.

#3 (50% likely): LP fatigue — contributing factor
    Evidence: CR giảm đều từ 9.5% → 6.2% across 4 tuần.
    Đây là organic decline, không phải sudden → likely fatigue.

#4 (40% likely): Delivery issues — partly caused by #1
    Evidence: Delivery rate giảm nhẹ. Có thể do bad addresses từ 
    low-quality leads, không nhất thiết do logistics issue.
```

**LƯU Ý: Các nguyên nhân LIÊN QUAN VỚI NHAU:**
```
Bad traffic → Trash tăng → Call center waste time → Confirm giảm
Bad traffic → Bad addresses → Delivery giảm
Cả 2 → AR giảm

Nếu fix #1 (traffic quality), #2 và #4 có thể tự cải thiện.
```

**3. Action plan:**

**IMMEDIATE (Hôm nay):**
- Pause A15 (Push): Trash 24%, AR 22% = unacceptable
- Warning A14 (TikTok): "Giảm trash < 15% trong 5 ngày hoặc pause"
- Giảm tổng cap từ 160 → 100 leads/day (chỉ giữ A08 + giới hạn A14)
- Check call center: response time tăng chưa? Request data từ advertiser

**SHORT-TERM (Tuần này):**
- Request 2-3 LP mới từ advertiser (fix fatigue)
- A/B test LP mới vs cũ trên A08 traffic
- Review call center SLA: confirm rate 50% là dưới standard (60%+)
- Set quality threshold: affiliate nào AR < 28% sẽ bị reduced cap

**LONG-TERM (Tháng này):**
- Recruit 1-2 affiliates có kinh nghiệm TH trên Facebook (thay A15)
- Evaluate TikTok traffic specifically cho offer này (A14 nếu improve)
- Build auto-rules: trash > 20% → auto-reduce cap 50%
- Monthly LP rotation schedule

**4. NẾU CHỈ ĐƯỢC 1 ACTION:**

**→ Pause A15 và cap A14 xuống 20 leads/day.**

Lý do: 
- A08 (FB) vẫn AR 34% → offer CÒN healthy
- A14 + A15 đang kéo average xuống → loại bỏ noise
- Sau khi pause, expected AR sẽ recover về ~34% (A08 level)
- Từ đó mới biết các vấn đề khác (CC, delivery) có tồn tại riêng biệt không

**BÀI HỌC:** 
- Khi AR giảm cùng lúc volume tăng → 90% là traffic quality issue
- Luôn drill down by affiliate trước
- Fix traffic quality TRƯỚC, rồi mới evaluate các factor khác
- Đừng chỉ nhìn average — average che đậy variance giữa affiliates

</details>

---

## BÀI TẬP 5: Financial Decision Making

### Đề bài:

Advertiser đề xuất 2 offer mới cho bạn. Budget chỉ cho phép test 1 offer. Chọn offer nào?

```
OFFER A: "FlexJoint" — Russia
├── Category: Joint Pain
├── Revenue from Advertiser: $16/approved
├── Suggested Payout: $11/approved
├── Expected AR (based on similar): 40-45%
├── Expected leads if successful: 200-300/day
├── Test cap: 50/day
├── Advertiser: NutraHealth LLC (existing partner, reliable)
├── LP: 2 ready, proven in other networks
├── Competition: 3 other networks running it
└── Notes: Similar offer (JointFlex Pro) already in portfolio at AR 45%

OFFER B: "SlimTea" — Mexico
├── Category: Weight Loss (tea-based)
├── Revenue from Advertiser: $13/approved
├── Suggested Payout: $8/approved
├── Expected AR (based on similar): 32-38%
├── Expected leads if successful: 100-200/day
├── Test cap: 40/day
├── Advertiser: LatamNutra (new partner, no track record)
├── LP: 1 ready, untested
├── Competition: Exclusive (no other network has it)
└── Notes: Mexico is growing GEO, few weight loss offers available
```

**Câu hỏi:**

1. Phân tích ưu nhược điểm từng offer
2. Tính expected margin cho mỗi offer (pessimistic, realistic, optimistic)
3. Chọn offer nào? Justify bằng số liệu
4. Có rủi ro ẩn nào không?

---

<details>
<summary><b>👉 CLICK ĐỂ XEM ĐÁP ÁN BÀI 5</b></summary>

### Đáp án:

**1. Phân tích ưu nhược:**

```
OFFER A: FlexJoint RU
─────────────────────
✅ Ưu điểm:
├── Margin cao: $5/approved (31.3%)
├── AR expected cao (40-45%) → proven category RU
├── Advertiser reliable (existing partner)
├── LP proven → lower test risk
├── Scale potential lớn (200-300/day)
└── Russia = home GEO, hiểu rõ

❌ Nhược điểm:
├── 3 competitors đang chạy → không exclusive
├── Tương tự JointFlex Pro đang có → cannibalization risk
├── Payout $11 = market standard → affiliates có options
└── Revenue upside giới hạn (mature market)
```

```
OFFER B: SlimTea MX
────────────────────
✅ Ưu điểm:
├── EXCLUSIVE → no competition, differentiator
├── Mexico growing GEO, few WL offers → fills gap
├── Weight loss = largest category → high demand
├── Portfolio diversification (less CIS dependent)
└── If works → strong competitive moat

❌ Nhược điểm:
├── New advertiser (LatamNutra) → unknown reliability
├── LP untested → higher failure risk
├── Margin lower: $5/approved (38.5%) nhưng volume thấp hơn
├── AR uncertain (32-38% = wide range)
├── Mexico delivery can be unpredictable
└── Only 1 LP ready → no A/B testing possible
```

**2. Expected margin calculation:**

```
OFFER A: FlexJoint RU
                 Pessimistic  Realistic   Optimistic
AR:              40%          42%         45%
Leads/day:       200          250         300
Approved/day:    80           105         135
Margin/appr:     $5           $5          $5
Daily margin:    $400         $525        $675
Monthly margin:  $12,000      $15,750     $20,250
Test success %:  High (70%)   —           —

OFFER B: SlimTea MX
                 Pessimistic  Realistic   Optimistic
AR:              32%          35%         38%
Leads/day:       100          150         200
Approved/day:    32           52.5        76
Margin/appr:     $5           $5          $5
Daily margin:    $160         $262.50     $380
Monthly margin:  $4,800       $7,875      $11,400
Test success %:  Medium (50%) —           —
```

**3. Quyết định: CHỌN OFFER B (SlimTea MX)**

**Lý do (có thể gây tranh cãi — và đó là bài học):**

Nhiều người sẽ chọn A vì "safe bet" — higher expected margin, proven advertiser, lower risk. Và đó KHÔNG SAI.

Nhưng nếu phân tích STRATEGIC:

```
OFFER A advantages are MARGINAL:
├── Đã có JointFlex Pro RU (AR 45%) → rất giống
├── Cạnh tranh 3 networks → payout war likely → margin sẽ bị ép
├── Thêm 1 offer RU joint pain → incremental value thấp
└── Portfolio không đa dạng hơn

OFFER B advantages are STRATEGIC:
├── Exclusive → KHÔNG AI KHÁC CÓ → competitive moat
├── Fills MX gap (growing GEO, ít WL offer) → portfolio diversification
├── Weight loss = universal demand → scalable nếu works
├── Nếu thành công → có thể mở rộng sang CO, PE (Spanish Latam)
├── Giảm CIS dependency (hiện 57% revenue)
└── First-mover advantage tại MX cho offer này

RISK MITIGATION cho Offer B:
├── Request 2nd LP từ advertiser trước khi launch
├── Negotiate trial terms: "test 2 tuần, nếu AR < 30% → terminate"
├── Request advertiser references (other networks they work with)
├── Start with micro-cap (20 leads/day → 40 if promising)
├── Have backup plan: if test fails, approach advertiser for Offer A next month
└── Set strict loss limit: max $500 test budget
```

**NHƯNG** — nếu bạn chọn A, đó cũng là defensible:
- Lower risk, higher expected value
- Proven everything
- Safer for someone new in the role

**Quyết định cuối cùng phụ thuộc vào:**
- Portfolio hiện tại (nếu đã quá heavy CIS → B, nếu balanced → A)
- Risk appetite của CMO/Board
- Budget flexibility (nếu budget tight → A safer)

**4. Rủi ro ẩn:**

```
Offer A:
├── Cannibalization: FlexJoint sẽ "ăn" traffic của JointFlex Pro
│   → Total revenue có thể KHÔNG tăng $15K mà chỉ tăng $5K net
├── Advertiser leverage: NutraHealth sẽ biết bạn dependent → có thể 
│   giảm payout trong tương lai
└── Payout war: 3 competitors → affiliates sẽ đòi higher payouts

Offer B:
├── New advertiser risk: Có thể shave leads, trả tiền chậm, 
│   hoặc dừng offer bất ngờ
├── Exclusive trap: "Exclusive" có thể vì offer chưa proven ở MX
│   (advertiser không thể pitch network khác vì data xấu)
├── Single LP risk: Nếu LP fail, không có backup → test inconclusive
└── MX delivery risk: Courier issues có thể kill AR
```

**BÀI HỌC:** 
- Số liệu là nền tảng nhưng strategic thinking mới quyết định
- "Best expected value" ≠ "Best decision" khi xét portfolio
- Luôn tính cannibalization khi thêm offer cùng category/GEO
- Exclusive offers = gold nếu proven, = trap nếu unproven
- Không có đáp án "đúng duy nhất" — quan trọng là logic và data

</details>

---

## BÀI TẬP 6: Crisis Management

### Đề bài:

Thứ Năm, 2:30 PM. Bạn nhận Slack message từ AM team:

> "3 top affiliates (A01, A02, A04) vừa nhắn tin hỏi tại sao conversions 
> hiện tại = 0 trên dashboard của họ. Họ vẫn đang chạy ads bình thường. 
> A01 nói đã chi $800 từ sáng đến giờ mà không thấy conversion nào. 
> A02 cũng tương tự."

Bạn kiểm tra AffScale dashboard:
```
Today's data so far (2:30 PM):
                9AM-11AM    11AM-1PM    1PM-2:30PM
Clicks          5,200       5,100       0
Leads           410         395         0
Approved        (pending)   (pending)   0
```

**Câu hỏi:**

1. Đây có phải crisis không? Tại sao?
2. Viết 5 bước đầu tiên bạn sẽ làm NGAY (theo thứ tự thời gian)
3. Draft tin nhắn gửi cho affiliates
4. Draft tin nhắn escalation cho CMO
5. Sau khi fix xong, cần làm gì?

---

<details>
<summary><b>👉 CLICK ĐỂ XEM ĐÁP ÁN BÀI 6</b></summary>

### Đáp án:

**1. CÓ — đây là CRISIS LEVEL CRITICAL.**

Phân tích:
- 0 clicks từ 1PM → tracking system DOWN hoàn toàn
- Đây KHÔNG PHẢI affiliate issue (3 affiliates independent, cùng bị)
- Affiliates ĐANG CHI TIỀN mà không track được → MẤT TIỀN THẬT
- Estimated impact:
  - Average 5,150 clicks/2h → ~2,575 clicks bị miss mỗi giờ
  - ~200 leads/hour bị miss
  - Revenue miss: ~$200-300/hour
  - Affiliate trust damage: INCALCULABLE
- Mỗi phút delay = thêm tiền mất + thêm trust damage

**2. Năm bước đầu tiên:**

```
2:30 PM — MINUTE 0-5: CONFIRM & COMMUNICATE
├── Check AffScale status page: platform up hay down?
├── Check: chỉ tracking hay cả platform? (login vẫn OK?)
├── Quick check: toàn bộ offers hay chỉ specific?
└── Nhắn ngay cho AM team: "Confirmed tracking issue. Investigating. 
    Tell affiliates we're aware."

2:35 PM — MINUTE 5-10: ESCALATE TO TECH
├── Contact Tech team / AffScale support NGAY
├── Message: "URGENT: Tracking down since ~1PM. 0 clicks/leads 
    recording. All offers affected. Need immediate investigation."
├── If AffScale hosted: contact AffScale support hotline
├── If self-hosted: contact CTO/Tech lead directly (phone, not Slack)
└── Start incident log (Google Doc, time-stamped)

2:40 PM — MINUTE 10-15: NOTIFY STAKEHOLDERS
├── Message to CMO (see #4 below)
├── Message to AM team: "Send holding message to ALL active affiliates"
├── Message to AR team: "Notify advertisers of potential data gap"
└── Message to Finance: "FYI — tracking gap from ~1PM, reconciliation 
    will be needed"

2:45 PM — MINUTE 15-30: CONTAIN DAMAGE
├── DECISION: Should affiliates pause campaigns?
│   ├── If fix ETA < 1 hour → tell affiliates to continue, we'll reconcile
│   └── If fix ETA > 1 hour or unknown → RECOMMEND affiliates pause
│       (they're burning money with no tracking)
├── Start manual tracking: ask affiliates to screenshot their tracker data
└── Ask advertisers to export lead data from CRM for reconciliation later

3:00 PM — MINUTE 30+: MONITOR & UPDATE
├── Check every 15 minutes with Tech for status
├── Update stakeholders every 30 minutes
├── Keep incident log updated
└── When fix deployed → verify with test click → confirm data flowing
```

**3. Message cho affiliates:**

```
🔔 URGENT UPDATE — Tracking Issue

Hi team,

We've identified a tracking system issue starting approximately 1:00 PM 
today. You may notice 0 conversions in your dashboard during this period.

What's happening:
• Our tracking system stopped recording clicks/leads from ~1PM
• Your campaigns ARE still running and generating leads
• The leads ARE being received by advertisers (not lost)

What we're doing:
• Tech team is working on an emergency fix right now
• ETA for resolution: [X hours / investigating]

What you should do:
• [Option A if quick fix]: Continue running, we will reconcile ALL 
  missing conversions once tracking is restored
• [Option B if long fix]: We recommend pausing campaigns temporarily 
  to avoid untracked spend. We'll notify you when it's safe to resume.

We will credit every single missing conversion after reconciliation. 
No revenue will be lost on your end.

Next update: [time]

Sorry for the disruption. We're treating this as top priority.
— MKT Operations
```

**4. Escalation cho CMO:**

```
🔴 [ESCALATION — CRITICAL] Tracking System Down

IMPACT:
• Tracking down since ~1:00 PM (1.5 hours so far)
• ALL offers, ALL GEOs affected
• 0 clicks/leads recording
• Estimated miss: ~400 leads, ~$600 revenue per hour ongoing
• Top 3 affiliates already contacted us (A01, A02, A04)
• Affiliate trust at risk — they're spending without tracking

ROOT CAUSE:
• Under investigation by Tech team
• Likely: [platform issue / server issue / DNS issue]

ACTIONS TAKEN:
• Tech team alerted and working on fix
• All affiliates being notified
• Advertisers notified for reconciliation prep
• Manual tracking started
• Incident log opened

DECISION NEEDED:
• Approve recommendation to ask affiliates to pause if not fixed 
  within 30 minutes?
• Approve post-incident credit/goodwill for affected affiliates?

ESTIMATED FINANCIAL IMPACT:
• Revenue miss: ~$600-900 per hour
• If 4 hours total downtime: ~$2,400-3,600 revenue gap
• Reconciliation will recover most but not all (some leads may be 
  lost in the gap)
• Goodwill cost (payout bonus to affiliates): TBD

Next update: 30 minutes
```

**5. Sau khi fix xong:**

```
IMMEDIATE (Same day):
□ Verify: test click → lead → postback → all working
□ Confirm to all affiliates: "Tracking restored at [time]"
□ Tell affiliates to resume campaigns
□ Begin reconciliation: AffScale data vs Advertiser CRM data
□ Identify gap period: exactly which leads are missing

NEXT DAY:
□ Complete reconciliation
□ Credit affiliates for ALL missing conversions
□ Update advertisers on final numbers
□ Finance team adjust billing

WITHIN 48 HOURS:
□ Post-incident report:
│ ├── Timeline of events
│ ├── Root cause
│ ├── Total impact (financial + leads + duration)
│ ├── What went well in response
│ ├── What could be improved
│ └── Prevention measures
□ Implement prevention:
│ ├── Automated monitoring: alert if 0 clicks for > 15 minutes
│ ├── Redundancy: backup tracking system
│ └── Playbook update: document this scenario for future
□ Goodwill gesture for top affiliates (optional but recommended):
│ ├── Payout bonus for affected period
│ └── Personal message from AM: "sorry and thank you for patience"
□ Share learnings with team

IMPORTANT: This incident will be remembered.
How you HANDLE it matters more than the fact it happened.
Fast response + transparent communication + fair reconciliation = 
affiliates stay loyal even after a bad day.
```

**BÀI HỌC:**
- Speed of response > perfect response
- Communicate TRƯỚC khi bạn có full picture
- "We're aware and working on it" > silence
- Affiliates forgive technical issues. They DON'T forgive being ignored.
- Always have a reconciliation plan
- Post-incident: prevention > blame

</details>

---

## BÀI TẬP 7: Portfolio Strategy

### Đề bài:

Bạn đang chuẩn bị Monthly Business Review. Đây là portfolio hiện tại:

```
Revenue Breakdown (March 2026):
─────────────────────────────────────────
GEO    │ Revenue  │ %Total │ MoM Change │ AR   │ # Offers
───────┼──────────┼────────┼────────────┼──────┼─────────
RU     │ $108,360 │ 36.3%  │    +6.2%   │43.0% │    5
KZ     │  $37,184 │ 12.5%  │   +12.8%   │56.0% │    2
UA     │  $37,800 │ 12.7%  │    +9.1%   │42.0% │    3
TH     │  $17,952 │  6.0%  │    +2.3%   │33.0% │    2
VN     │  $11,564 │  3.9%  │    +8.9%   │28.0% │    1
PH     │  $10,800 │  3.6%  │    +7.5%   │30.0% │    1
BR     │  $15,600 │  5.2%  │    -5.5%   │25.0% │    2
MX     │  $11,484 │  3.8%  │   +14.2%   │36.0% │    1
ID     │   $1,323 │  0.4%  │    +5.0%   │21.0% │    1
Other* │  $46,433 │ 15.6%  │    +4.0%   │37.0% │    —
───────┼──────────┼────────┼────────────┼──────┼─────────
Total  │ $298,500 │100.0%  │    +8.5%   │38.5% │   18

*Other = smaller GEOs, test offers, misc
```

CMO hỏi bạn: **"Q2 revenue target là $380,000/tháng (+27% vs March). Đề xuất strategy để đạt target?"**

**Câu hỏi:**

1. Phân tích: target có realistic không?
2. Đề xuất revenue plan theo GEO cho tháng June (end of Q2)
3. Identify top 3 growth opportunities
4. Identify top 3 risks
5. Bạn cần gì từ CMO/company để execute plan?

---

<details>
<summary><b>👉 CLICK ĐỂ XEM ĐÁP ÁN BÀI 7</b></summary>

### Đáp án:

**1. Target realistic analysis:**

```
Current: $298,500/month (March)
Target:  $380,000/month (June) = +$81,500 (+27.3%)
Timeline: 3 months (April, May, June)

Required growth rate: ~8.4%/month compound

Current organic growth rate: ~8.5%/month (March MoM)

ASSESSMENT: ACHIEVABLE BUT AGGRESSIVE

Tại sao achievable:
├── Current growth 8.5%/month ≈ required 8.4% → mathematically possible
├── Pre-summer season (Apr-May-Jun) = PEAK cho weight loss
├── KZ scaling (12.8% MoM) has momentum
├── MX growing fast (14.2%)
└── Multiple levers available

Tại sao aggressive:
├── Organic growth may slow (diminishing returns)
├── Brazil declining → headwind
├── 27% growth requires EXECUTION on multiple fronts simultaneously
├── Need new offers AND new affiliates AND new GEOs
└── Dependency on advertiser capacity (stock, call center)
```

**2. Revenue plan June 2026:**

```
GEO    │Mar Actual│Jun Target│Growth $ │ Growth %│ Strategy
───────┼──────────┼──────────┼─────────┼─────────┼──────────────────
RU     │ $108,360 │ $140,000 │+$31,640 │  +29%   │ Summer push: WL
KZ     │  $37,184 │  $52,000 │+$14,816 │  +40%   │ Scale ManPower+
UA     │  $37,800 │  $48,000 │+$10,200 │  +27%   │ Add 2 offers
TH     │  $17,952 │  $22,000 │ +$4,048 │  +23%   │ Fix AR, new LP
VN     │  $11,564 │  $16,000 │ +$4,436 │  +38%   │ Fix quality, scale
PH     │  $10,800 │  $14,000 │ +$3,200 │  +30%   │ Add beauty offers
BR     │  $15,600 │  $18,000 │ +$2,400 │  +15%   │ Stabilize, SP focus
MX     │  $11,484 │  $18,000 │ +$6,516 │  +57%   │ Scale WL, new affils
ID     │   $1,323 │   $3,000 │ +$1,677 │ +127%   │ Small base, test
Other  │  $46,433 │  $49,000 │ +$2,567 │   +6%   │ Organic
───────┼──────────┼──────────┼─────────┼─────────┼
Total  │ $298,500 │ $380,000 │+$81,500 │  +27%   │
```

**3. Top 3 growth opportunities:**

```
#1: RUSSIA SUMMER PUSH (+$31,640 target)
├── WHY: Pre-summer (Apr-Jun) = PEAK season for weight loss
├── HOW:
│   ├── Launch 2-3 new weight loss offers
│   ├── Increase cap on KetoBurn (200 → 350/day)
│   ├── Recruit 3-5 new affiliates specifically for WL RU
│   └── Request advertisers to increase call center capacity
├── CONFIDENCE: High (seasonal pattern proven)
└── RISK: Competition also knows it's peak → CPL may increase

#2: KAZAKHSTAN SCALE (+$14,816 target)
├── WHY: Highest AR (56%), strong momentum (+12.8% MoM)
├── HOW:
│   ├── ManPower Plus cap increase 350 → 600/day
│   ├── Launch 2 new offers (joint pain, weight loss)
│   ├── Recruit KZ-focused affiliates
│   └── Negotiate better payout from advertiser (volume leverage)
├── CONFIDENCE: High (proven market, proven offer)
└── RISK: Market smaller than RU, ceiling may hit sooner

#3: MEXICO EXPANSION (+$6,516 target)
├── WHY: Fastest growing GEO (+14.2%), underweight in portfolio (3.8%)
├── HOW:
│   ├── Launch 2-3 new offers (weight loss, male enhancement)
│   ├── SlimTea exclusive (if chosen from exercise 5)
│   ├── Recruit Latam-focused affiliates
│   └── Test new categories
├── CONFIDENCE: Medium (growing but still proving)
└── RISK: New advertiser risk, delivery time
```

**4. Top 3 risks:**

```
#1: BRAZIL CONTINUED DECLINE
├── Impact: -$5K to -$10K/month if not stabilized
├── Currently: AR 25%, declining trend
├── Mitigation: SP/Regions split, new offers, new advertiser
├── Worst case: Pause BR entirely → reallocate to MX
└── Probability: Medium (40%)

#2: TOP AFFILIATE CONCENTRATION
├── Impact: -$50K+/month if A01 churns
├── Currently: Top 5 = 63% of revenue
├── Mitigation: Aggressive recruitment, diversify base
├── Worst case: A01 moves to competitor → scramble
└── Probability: Low (15%) but catastrophic

#3: ADVERTISER CAPACITY CONSTRAINTS
├── Impact: Cannot scale even if demand exists
├── Specifically: Call center + stock for summer surge
├── Mitigation: Early communication, commit volumes, backup advertisers
├── Worst case: OOS during peak season → miss $30K+
└── Probability: Medium (30%)
```

**5. Cần từ CMO/Company:**

```
BUDGET:
├── Additional payout budget: ~$8K/month (for bumps to retain/attract)
├── Test budget: $5K for new offer testing
└── Event/conference budget: attend 1 affiliate event for recruitment

RESOURCES:
├── Tech priority: Dashboard improvements (auto-alerts, better drill-down)
├── AM team: Authorize 1 additional AM for affiliate recruitment
├── AR team: Focus on sourcing 5+ new offers for peak season
└── Data/BI: Build forecasting dashboard

DECISIONS:
├── Approve Brazil strategy: stabilize or exit?
├── Approve new GEO entry: Peru/Colombia in Q2?
├── Approve payout structure: authority to bump without CMO approval up to $X?
└── Approve KZ scaling plan: advertiser already confirmed capacity?

ALIGNMENT:
├── Monthly check-in on Q2 progress vs target
├── Authority to pause offers below threshold without approval
├── Clear escalation path if falling behind target >10%
└── Agreement on risk appetite: are we optimizing for growth or margin?
```

**BÀI HỌC:**
- Target analysis: luôn stress-test bằng "where will the growth COME FROM specifically"
- Plan bằng số cụ thể theo GEO, không chỉ "chúng ta sẽ grow"
- Identify risks CÙNG LÚC với opportunities
- Ask for what you NEED to execute — resources, authority, decisions
- Portfolio thinking: don't just add, also subtract (pause/exit underperformers)

</details>

---

## BÀI TẬP 8: Speed Round — Quick Decisions

### Đề bài:

Trả lời nhanh mỗi tình huống trong 30 giây. Chọn action và giải thích ngắn gọn.

```
SCENARIO A:
Affiliate A20 mới join tuần trước. Volume 25 leads/day, AR chưa có data,
trash rate 28%. Hôm nay trash rate lên 32%.
→ Action: ____________

SCENARIO B:
KetoBurn RU (top offer): AR stable 46%, volume 200/day.
Advertiser thông báo tăng payout từ $15 → $16 revenue cho bạn.
→ Action: ____________

SCENARIO C:
Thứ 6, 5PM. Affiliate A01 (top, 18% revenue) nhắn tin:
"Network XYZ vừa offer tôi $11.50/approved cho cùng offer. 
Các bạn đang trả $10. Match không?"
→ Action: ____________

SCENARIO D:
Dashboard hiện AR tổng hôm nay: 52%. (Bình thường: 38-40%)
→ Action: ____________

SCENARIO E:
Advertiser yêu cầu bạn tăng cap từ 200 → 500 leads/day cho 1 offer.
Lý do: "Chúng tôi vừa mở thêm call center."
→ Action: ____________

SCENARIO F:
Đầu tháng. Finance báo: BrazilNutra chưa trả $18,500 (overdue 12 ngày).
Bạn vẫn đang chạy 180 leads/day cho offers của họ.
→ Action: ____________
```

---

<details>
<summary><b>👉 CLICK ĐỂ XEM ĐÁP ÁN BÀI 8</b></summary>

```
SCENARIO A: → PAUSE A20 ngay. Reduce cap = 0.
Lý do: Trash 32% > threshold 25% (auto-pause rule).
New affiliate, no proven value. No reason to tolerate bad quality.
Gửi warning, cho cơ hội improve traffic source rồi re-apply.

SCENARIO B: → Giữ nguyên payout affiliate. Pocket extra $1.
Lý do: Offer đang stable, affiliates hài lòng với $10.
$1 extra × 200/day × 46% = $92/day = $2,760/month thêm margin.
Nếu cần incentivize scale, dùng phần này cho selective bumps sau.
KHÔNG tự động raise payout khi không có pressure.

SCENARIO C: → Reply NGAY (không đợi thứ 2). Offer $10.50-$11.00.
Lý do: A01 = 18% revenue. Mất A01 = crisis.
Đừng match full $11.50 (cho thấy bạn sẵn sàng match bất kỳ giá nào).
$10.50-$11.00 + emphasize: relationship, fast payment, support, reliability.
"Chúng tôi có thể lên $10.75 ngay và review lại nếu volume tăng."
Escalate CMO nếu A01 insist $11.50.

SCENARIO D: → ĐÂY KHÔNG PHẢI TIN TỐT. Investigate ngay.
Lý do: AR 52% khi bình thường 38-40% = BẤT THƯỜNG.
Possible causes:
- Tracking issue (chỉ approved postbacks fire, clicks/leads missing)
- Data lag (hôm nay mới có ít leads, nhưng approved từ hôm qua)
- Sampling error (đầu ngày, ít data → % bị skew)
NEVER celebrate abnormally good numbers — VERIFY first.

SCENARIO E: → KHÔNG agree ngay. Tăng GRADUAL.
Lý do: 200 → 500 = 2.5x = quá nhanh.
Propose: 200 → 300 (tuần 1) → 400 (tuần 2) → 500 (tuần 3).
Monitor AR mỗi bước. New call center cần time to ramp up quality.
"Chúng tôi sẽ tăng dần để đảm bảo quality giữ nguyên."

SCENARIO F: → GIẢM VOLUME NGAY. Escalate.
Lý do: $18,500 overdue 12 ngày = RED FLAG lớn.
180 leads/day × ~$14 rev × 30 ngày = thêm $75,600 exposure.
Action:
├── Giảm cap xuống 50/day (không pause hoàn toàn để giữ relationship)
├── Email BrazilNutra: "Payment overdue. Volume reduced until paid."
├── Escalate to Finance + CMO
├── Calculate total exposure
└── Nếu không trả trong 5 ngày → FULL PAUSE
KHÔNG BAO GIỜ tiếp tục full volume khi payment overdue > 7 ngày.
```

</details>

---

## SCORING GUIDE

Tự đánh giá sau khi làm tất cả bài tập:

```
Bài 1 (Dashboard cơ bản):     /10 — Nhận ra weekend pattern?
Bài 2 (GEO analysis):         /20 — Tìm đúng vấn đề, đúng priority?
Bài 3 (Affiliate payout):     /15 — Decision có data-backed?
Bài 4 (Root cause):           /20 — Tìm đúng root cause, đúng action?
Bài 5 (Financial decision):   /15 — Strategic thinking hay chỉ safe bet?
Bài 6 (Crisis):               /20 — Speed + communication + process?
Bài 7 (Portfolio strategy):   /20 — Specific plan hay generic "grow more"?
Bài 8 (Speed round):          /30 — 5 points mỗi scenario

TOTAL:                         /150

> 120: Sẵn sàng — bạn sẽ on-board nhanh
> 90:  Tốt — cần practice thêm scenarios
> 60:  OK — đọc lại chương 6-7-8, làm lại bài tập
< 60:  Cần thêm thời gian — focus thuật ngữ và metrics trước
```
