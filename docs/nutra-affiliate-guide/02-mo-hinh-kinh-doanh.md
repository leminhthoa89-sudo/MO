# Chương 2: Mô hình kinh doanh & Dòng tiền

## 2.1 Hai mô hình chính trong Nutra

### Mô hình 1: COD (Cash on Delivery) — PHỔ BIẾN NHẤT

```
Khách thấy quảng cáo
    ↓
Click vào → Landing Page
    ↓
Điền form (Tên, SĐT, Địa chỉ)        ← ĐÂY LÀ "LEAD"
    ↓
Call Center gọi xác nhận               ← CONFIRM hoặc REJECT
    ↓
Đóng gói & Giao hàng (COD)
    ↓
Khách nhận hàng & trả tiền mặt         ← ĐÂY LÀ "APPROVED"
```

**Đặc điểm COD:**
- Khách KHÔNG cần thẻ tín dụng → conversion rate cao hơn
- Nhưng nhiều người "đặt cho vui" → approval rate thấp (30-60%)
- Call center là khâu QUYẾT ĐỊNH — nếu call center kém → approval thấp
- Phổ biến ở: CIS, Đông Nam Á, Latam, MENA

**Các trạng thái của 1 lead trong COD:**
```
LEAD (mới vào)
  ├── TRASH (lead rác: sai SĐT, spam, duplicate, bot)
  ├── REJECT (call center gọi → khách từ chối)
  ├── HOLD (chờ callback, không nghe máy)
  └── CONFIRMED (khách đồng ý mua)
        ├── SHIPPED (đã gửi hàng)
        │     ├── DELIVERED / APPROVED (giao thành công, thu tiền)
        │     ├── RETURNED (khách không nhận, trả lại)
        │     └── LOST (thất lạc)
        └── CANCELLED (hủy trước khi ship)
```

### Mô hình 2: SS (Straight Sale / Prepaid)

```
Khách thấy quảng cáo
    ↓
Click vào → Landing Page
    ↓
Thanh toán online (thẻ tín dụng)       ← ĐÂY LÀ "SALE"
    ↓
Giao hàng
```

**Đặc điểm SS:**
- Conversion rate thấp hơn COD (cần thẻ)
- Nhưng approval rate ~100% (đã trả tiền rồi)
- Ít phổ biến ở thị trường đang phát triển (CIS, SEA, Latam)
- Chủ yếu ở US, EU, UK, AU

### So sánh

| | COD | Straight Sale |
|---|-----|---------------|
| Barrier mua | Thấp | Cao |
| CR (click→lead) | 5-15% | 1-5% |
| Approval Rate | 30-60% | ~100% |
| Fraud risk | Cao (fake leads) | Thấp |
| Cần Call Center | Có | Không |
| Thị trường phù hợp | CIS, Asia, Latam | US, EU |
| Cash flow | Chậm (đợi delivery) | Nhanh |

## 2.2 Dòng tiền chi tiết

### Tiền chảy như thế nào?

```
                    DÒNG TIỀN TRONG NUTRA COD
                    
Khách trả $40 (COD)
    ↓
Delivery Service giữ $5 (phí giao hàng)
    ↓
Advertiser nhận $35
    ↓
Advertiser trả Network $12/lead approved    ← Revenue của bạn
    ↓
Network trả Affiliate $8/lead approved      ← Payout
    ↓
Network giữ $4/lead                         ← MARGIN
```

### Ví dụ thực tế — 1 ngày hoạt động

```
Giả sử 1 offer Weight Loss ở Nga:

Affiliate chạy ads Facebook, chi $500/ngày
    ↓
Được 200 clicks → 20 leads (CR = 10%)
    ↓ CPL = $500/20 = $25/lead
Call center gọi 20 leads:
    - 3 trash (sai SĐT) = 15%
    - 5 reject (không muốn mua) = 25%
    - 2 hold (không nghe máy) = 10%
    - 10 confirmed = 50%
    ↓
Ship 10 đơn:
    - 7 delivered & paid (approved) = 70% delivery rate
    - 2 returned = 20%
    - 1 lost = 10%
    ↓
KẾT QUẢ:
    - Approval Rate = 7/20 = 35% (tính trên tổng lead)
    - Network Revenue = 7 × $15 = $105
    - Network trả Affiliate = 7 × $10 = $70
    - Network Margin = $105 - $70 = $35
    
Affiliate P&L:
    - Revenue: $70
    - Cost: $500 (ads)
    - Loss: -$430  ← AFFILIATE LỖ NẶNG

Nhưng affiliate GIỎI sẽ:
    - CPL thấp hơn ($5-8 thay vì $25)
    - CR cao hơn (15-20%)
    - Target audience tốt hơn → approval rate 50-60%
```

### Vấn đề Cash Flow — RẤT QUAN TRỌNG

```
Timeline thực tế:

Ngày 1:    Affiliate chi $500 chạy ads           ← TIỀN RA
Ngày 1:    20 leads vào hệ thống
Ngày 2-3:  Call center gọi confirm               ← CHƯA CÓ TIỀN VÀO
Ngày 3-5:  Ship hàng                              
Ngày 5-10: Delivery                               
Ngày 10-15: Advertiser reconcile                  ← BẮT ĐẦU TÍNH TIỀN
Ngày 15-30: Advertiser trả Network (Net-15)       ← TIỀN VÀO NETWORK
Ngày 30-45: Network trả Affiliate (Net-7/15)      ← TIỀN VÀO AFFILIATE

→ Khoảng cách 30-45 ngày từ lúc chi tiền đến lúc nhận tiền
→ Đây là lý do cash flow management CỰC KỲ quan trọng
```

## 2.3 Cấu trúc giá & Margin

### Payout models

**1. CPA (Cost Per Action) — Phổ biến nhất**
- Trả cố định cho mỗi approved lead
- Ví dụ: $10/approved lead
- Affiliate thích vì biết trước được bao nhiêu

**2. CPL (Cost Per Lead)**
- Trả cho mỗi lead (chưa cần approved)
- Ví dụ: $3/lead
- Risk cho network cao hơn (lead có thể trash)

**3. CPS (Cost Per Sale)**
- Trả % doanh thu bán hàng
- Ví dụ: 30% giá bán

**4. RevShare**
- Chia sẻ doanh thu dài hạn
- Ít phổ biến trong nutra COD

### Cách tính margin cho Network

```
Margin = Revenue (từ Advertiser) - Payout (cho Affiliate) - Chi phí vận hành

Margin target thường: 20-40% trên mỗi offer

Ví dụ:
- Advertiser trả Network: $12/approved lead
- Network trả Affiliate: $8/approved lead
- Margin: $4/lead = 33%

NHƯNG phải tính thêm:
- Chi phí platform (AffScale hosting, licenses)
- Lương team (call center, media buyers nội bộ nếu có)
- Chi phí tracking, servers
- Bad debt (advertiser không trả)
```

## 2.4 Các model thanh toán & rủi ro

### Thanh toán từ Advertiser

| Model | Mô tả | Rủi ro |
|-------|--------|--------|
| Net-7 | Trả sau 7 ngày | Thấp |
| Net-15 | Trả sau 15 ngày | Trung bình |
| Net-30 | Trả sau 30 ngày | Cao |
| Weekly | Trả hàng tuần | Thấp |
| Bi-weekly | 2 tuần/lần | Trung bình |

### Thanh toán cho Affiliate

| Model | Khi nào dùng |
|-------|-------------|
| Net-7 | Affiliate đáng tin cậy, volume cao |
| Net-15 | Mặc định |
| Net-30 | Affiliate mới, chưa verify |
| Weekly | Top affiliates, giữ chân |
| Daily | Rất hiếm, chỉ cho VIP |

### Rủi ro tài chính cần theo dõi

1. **Advertiser không trả tiền**: Đã trả affiliate rồi nhưng advertiser chạy mất → LỖ
2. **Lead fraud**: Affiliate gửi lead fake → network trả tiền cho lead rác
3. **Shaving**: Advertiser cắt bớt lead approved → revenue thấp hơn thực tế
4. **Currency risk**: Thanh toán USD nhưng chi phí RUB/BRL → biến động tỷ giá
5. **Chargeback**: (Cho SS model) khách đòi lại tiền qua ngân hàng

## 2.5 Unit Economics — Con số bạn PHẢI biết

### Cho mỗi Offer/GEO combo, bạn cần biết:

```
Ví dụ: Offer "SlimFit" tại Russia

1. Average Payout to Affiliate:     $8.00 / approved lead
2. Average Revenue from Advertiser:  $12.00 / approved lead
3. Gross Margin per lead:            $4.00 (33%)
4. Average Approval Rate:            42%
5. Average Leads/day:                150
6. Approved leads/day:               63 (150 × 42%)
7. Daily Revenue:                    $756 (63 × $12)
8. Daily Payout:                     $504 (63 × $8)
9. Daily Gross Profit:               $252
10. Monthly Gross Profit:            ~$7,560

Câu hỏi bạn phải tự trả lời:
- $7,560/tháng có đủ cover chi phí vận hành cho offer này?
- Approval rate 42% có thể cải thiện không?
- Nếu tăng cap lên 300 leads/day, call center có handle nổi không?
- Offer này đang ở giai đoạn nào? (growing / stable / declining)
```

## 2.6 Vòng đời của một Offer

```
TEST → SCALE → STABLE → DECLINE → PAUSE/KILL

TEST (1-2 tuần):
- Chạy volume thấp (20-50 leads/day)
- Đánh giá CR, approval rate, trash rate
- Quyết định: scale hay kill

SCALE (2-8 tuần):
- Tăng cap dần (100 → 300 → 500+ leads/day)
- Thêm nhiều affiliates
- Monitor chặt approval rate (thường giảm khi scale)

STABLE (1-6 tháng):
- Volume ổn định
- Focus optimize margin
- Maintain approval rate

DECLINE:
- CR giảm (audience fatigue)
- Approval rate giảm
- Advertiser giảm payout
- Cạnh tranh tăng

PAUSE/KILL:
- ROI < threshold
- Advertiser dừng offer
- Regulation issues
```
