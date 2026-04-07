# Chương 5: Offer Management & Optimization

## 5.1 Anatomy of an Offer

Mỗi offer trên AffScale (hoặc bất kỳ affiliate platform nào) gồm các thành phần:

```
OFFER: SlimFit Pro — Russia
├── Offer ID:           #1234
├── Advertiser:         NutraHealth LLC
├── Category:           Weight Loss
├── GEO:                Russia (RU)
├── Payout Model:       CPA (Cost per Approved Lead)
├── Payout to Affiliate: $10.00
├── Revenue from Adv:   $14.00
├── Margin:             $4.00 (28.6%)
├── Cap:                200 leads/day
├── Flow:               COD
├── Landing Pages:      3 active LPs
├── Target Audience:    Women 30-60
├── Restrictions:       No incentivized traffic, no adult
├── Status:             Active
├── Hold Period:        30 days
├── Conversion Type:    Approved (paid & delivered)
└── Notes:              Top performer Q1, trending up
```

## 5.2 Các loại Offer trong Nutra

### Theo flow thanh toán:
| Flow | Mô tả | AR typical | Dùng ở |
|------|--------|-----------|--------|
| **COD** | Trả khi nhận hàng | 30-55% | CIS, Asia, Latam |
| **SS (Straight Sale)** | Trả online | ~95% | US, EU |
| **Trial** | Dùng thử, tự động charge | Varies | US, EU |
| **CC Submit** | Chỉ cần submit thẻ | ~85% | US, EU |

### Theo conversion event:
| Type | Trả tiền khi | Risk cho network |
|------|-------------|-----------------|
| **CPL (Per Lead)** | Lead điền form | Cao (chưa biết quality) |
| **CPA Confirmed** | Call center confirm | Trung bình |
| **CPA Approved** | Giao hàng thành công | Thấp |
| **RevShare** | Chia % doanh thu | Thấp, long-term |

## 5.3 Cách đánh giá 1 Offer (Offer Scorecard)

Khi nhìn vào bất kỳ offer nào, đánh giá theo 8 tiêu chí:

```
OFFER SCORECARD
═══════════════════════════════════════════
Offer: ____________    GEO: ____________

1. VOLUME                           Score: __/10
   Leads/day hiện tại: ___
   Potential: ___
   Trend: ↑ ↓ →

2. APPROVAL RATE                    Score: __/10
   Current AR: ___%
   Benchmark GEO: ___%
   Trend: ↑ ↓ →

3. MARGIN                           Score: __/10
   Revenue/lead: $___
   Payout/lead: $___
   Margin: $____ (__%)

4. STABILITY                        Score: __/10
   How long active: ___ months
   Volume fluctuation: High / Medium / Low
   Advertiser reliability: ___

5. QUALITY (Trash Rate)             Score: __/10
   Current trash: ___%
   Target: < 15%

6. SCALABILITY                      Score: __/10
   Cap headroom: ___
   # affiliates running: ___
   Traffic source diversity: ___

7. COMPETITION                      Score: __/10
   Other networks running same offer: Yes/No
   Payout competitive: Yes/No

8. STRATEGIC VALUE                  Score: __/10
   New GEO entry: Yes/No
   Diversification value: Yes/No
   Advertiser relationship: ___

TOTAL:  __/80
ACTION: Scale / Maintain / Optimize / Test / Pause / Kill
═══════════════════════════════════════════
```

## 5.4 Offer Lifecycle Management

### Phase 1: Sourcing & Evaluation

**Offer mới đến từ đâu?**
- Advertiser pitch trực tiếp
- AR team tìm từ advertiser mới
- Copy từ competitor network (xem họ đang chạy gì hot)
- Affiliate request (affiliate muốn chạy offer cụ thể)

**Checklist trước khi launch:**
```
□ Advertiser đã verify (legit, track record)
□ Payout & revenue terms rõ ràng
□ Landing pages ready & tested
□ Tracking/postback setup & tested
□ Call center capacity confirmed
□ Stock availability confirmed
□ GEO restrictions clear
□ Traffic restrictions clear
□ Test budget approved
□ Assigned affiliates identified
```

### Phase 2: Testing

**Test protocol:**
```
Duration:     7-14 ngày
Volume:       20-50 leads/day
Affiliates:   1-3 trusted affiliates
Budget:       Limited (xác định max loss chấp nhận)

Metrics to monitor DAILY:
├── CR (click → lead)
├── Lead volume
├── Trash rate
├── Confirm rate (call center)
├── Approval rate (nếu delivery cycle đủ ngắn)
└── Any red flags

GO criteria (cần ĐẠT TẤT CẢ):
├── AR > benchmark GEO (VD: > 35% cho RU)
├── Trash rate < 20%
├── CR stable hoặc improving
├── Advertiser feedback positive
└── No compliance issues

NO-GO criteria (1 trong các điều kiện):
├── AR < 25% sau 100 leads
├── Trash > 30%
├── Advertiser complaints
├── No affiliate interest
└── Compliance issues
```

### Phase 3: Scale

**Scaling checklist:**
```
□ Increase cap gradually (50 → 100 → 200 → 500)
□ Add more affiliates
□ Monitor AR as volume increases (AR thường GIẢM khi scale)
□ Ensure call center can handle volume
□ Ensure stock is sufficient
□ Watch for quality drop by sub-sources
□ Set up alerts for anomalies
```

**Scaling pitfalls:**
1. **AR drop**: Khi scale, affiliates mới chất lượng thấp hơn → AR giảm
2. **OOS**: Tăng volume nhưng warehouse không theo kịp
3. **Call center bottleneck**: Quá nhiều lead, call center gọi không kịp
4. **Budget overrun**: Payout tăng nhanh hơn revenue
5. **Quality dilution**: Top affiliate AR 50%, mới thêm affiliate AR 25% → trung bình giảm

### Phase 4: Optimization

**Optimize theo dimension nào?**

```
1. BY AFFILIATE
   ├── Identify top performers → offer higher payout, exclusive terms
   ├── Identify under-performers → warning → optimize → cut
   └── Compare AR by affiliate → same offer, different AR = traffic quality issue

2. BY TRAFFIC SOURCE
   ├── Facebook leads vs Native leads vs Push leads
   ├── Mỗi source có quality khác nhau
   └── Adjust payout by source nếu cần

3. BY LANDING PAGE
   ├── A/B test landing pages
   ├── CR differences → choose winner
   └── Rotate to prevent fatigue

4. BY SUB-GEO
   ├── Russia: Moscow vs regions
   ├── Brazil: São Paulo vs North
   └── Delivery time & AR varies by region

5. BY TIME
   ├── Day of week patterns
   ├── Time of day patterns
   └── Seasonal trends
```

### Phase 5: Decline & Decision

**Signals offer đang decline:**
```
WARNING SIGNS (Cần monitor chặt):
├── AR giảm 5%+ trong 2 tuần liên tiếp
├── CR giảm (landing page fatigue)
├── Top affiliate volume giảm
├── Advertiser giảm cap
└── CPL tăng (competition)

RED FLAGS (Cần action ngay):
├── AR < 25%
├── Advertiser delay payment
├── Stock out > 3 ngày
├── Trash rate > 30%
└── Advertiser thay đổi terms bất lợi
```

**Decision framework:**
```
IF AR declining:
    → Check: call center issue? → escalate to advertiser
    → Check: traffic quality? → audit affiliates
    → Check: delivery issue? → check logistics
    → Check: product fatigue? → test new LPs

IF still declining after optimization:
    → Option 1: Reduce cap, keep only top affiliates
    → Option 2: Negotiate higher revenue from advertiser
    → Option 3: Pause and replace with better offer
```

## 5.5 Offer Portfolio Management

### Đa dạng hóa portfolio

**Không bao giờ phụ thuộc vào 1 offer hoặc 1 GEO.**

Cấu trúc portfolio lý tưởng:
```
BY GEO:
├── CIS:   40-50% revenue
├── Asia:  25-35% revenue
└── Latam: 20-30% revenue

BY CATEGORY:
├── Weight Loss:      30-40%
├── Male Enhancement: 15-25%
├── Joint/Health:     15-20%
├── Skin/Beauty:      10-15%
└── Others:           10-15%

BY LIFECYCLE:
├── Mature/Stable:    60-70% (cash cows)
├── Growing/Scaling:  20-25% (stars)
└── Testing:          10-15% (pipeline)
```

### Offer Rotation Strategy

```
Tại sao cần rotate?

Offer → Affiliates chạy → Audience thấy → MUA
                                         → KHÔNG MUA (nhiều lần)
                                         → AD FATIGUE → CR giảm

Giải pháp:
1. Rotate landing pages (mỗi 2-4 tuần)
2. Rename product (cùng sản phẩm, tên khác, LP mới)
3. Test categories mới liên tục
4. Mở GEO mới cho offer proven
```

## 5.6 Cap Management

### Cap là gì?
- Giới hạn số lead/ngày mà 1 offer chấp nhận
- Set bởi advertiser (dựa trên call center capacity + stock)

### Tại sao cap management quan trọng?

```
Scenario 1: Cap quá thấp
├── Affiliates không đủ chỗ chạy → chuyển network khác
├── Revenue bị giới hạn
└── Miss opportunity

Scenario 2: Cap quá cao
├── Call center không gọi kịp → leads expire → AR giảm
├── Stock hết → OOS
└── Quality giảm (accept lead bừa)

Scenario 3: Cap allocation không công bằng
├── Top affiliate không được đủ cap → bỏ đi
├── Low-quality affiliate chiếm cap → waste
└── Drama nội bộ
```

### Cap Allocation Strategy

```
PRIORITY ORDER:
1. Internal media buying team (nếu có)    → ưu tiên cao nhất
2. Tier 1 affiliates (proven quality)     → cap guarantee
3. Tier 2 affiliates                      → shared remaining cap
4. Tier 3 / new affiliates               → limited test cap

RULES:
- Top affiliate (AR > 50%) → guaranteed X leads/day
- Average affiliate (AR 35-50%) → cap based on performance
- Below average (AR < 35%) → reduced cap hoặc pause
- New affiliate → 20-50 leads/day test cap

DYNAMIC ADJUSTMENT:
- Nếu tổng demand > cap → allocate theo AR ranking
- Nếu cap > demand → recruit thêm affiliates hoặc scale existing
- Monitor cap fill rate: < 70% = under-utilizing, > 95% = need more cap
```

## 5.7 Payout Management

### Khi nào tăng payout cho affiliate?

```
TĂNG khi:
├── Affiliate volume đang grow, AR tốt → incentivize scale
├── Competitor network offer payout cao hơn → giữ affiliate
├── Margin đủ để absorb
└── Strategic affiliate bạn muốn giữ

GIẢM khi:
├── AR giảm → payout chỉ cho approved, nên ok
├── Advertiser giảm revenue → phải adjust
├── Fraud detected → pause trước, investigate
└── Market rate giảm
```

### Payout Bumps & Special Terms

```
Standard Payout:    $8/approved (cho tất cả)
Volume Bump:        $9/approved (nếu > 100 leads/day)
VIP Bump:           $10/approved (top affiliate, exclusive)
Test Payout:        $6/approved (offer mới, chưa proven)
```
