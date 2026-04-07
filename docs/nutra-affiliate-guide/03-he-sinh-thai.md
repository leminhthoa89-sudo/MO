# Chương 3: Hệ sinh thái các bên tham gia

## 3.1 Bản đồ các bên (Stakeholder Map)

```
┌─────────────────────────────────────────────────────────┐
│                    ADVERTISER / BRAND                     │
│  (Sở hữu sản phẩm, call center, warehouse, fulfillment) │
└──────────────────────┬──────────────────────────────────┘
                       │ Offer + Payout
                       ▼
┌─────────────────────────────────────────────────────────┐
│              AFFILIATE NETWORK (AffScale)                │
│  BẠN Ở ĐÂY — quản lý offer, tracking, payout, ops      │
│  ┌─────────┐ ┌──────────┐ ┌──────────┐ ┌────────────┐  │
│  │ Offer   │ │ Tracking │ │ Payment  │ │ Analytics  │  │
│  │ Mgmt    │ │ System   │ │ System   │ │ Dashboard  │  │
│  └─────────┘ └──────────┘ └──────────┘ └────────────┘  │
└──────────────────────┬──────────────────────────────────┘
                       │ Offer links + Tracking
                       ▼
┌─────────────────────────────────────────────────────────┐
│            AFFILIATES / PUBLISHERS / MEDIA BUYERS        │
│  (Chạy ads, mua traffic, tạo landing pages)             │
└──────────────────────┬──────────────────────────────────┘
                       │ Ads
                       ▼
┌─────────────────────────────────────────────────────────┐
│                  TRAFFIC SOURCES                         │
│  Facebook, Google, TikTok, Native Ads, Push, SEO...     │
└──────────────────────┬──────────────────────────────────┘
                       │ Impressions / Clicks
                       ▼
┌─────────────────────────────────────────────────────────┐
│                     END USER / KHÁCH HÀNG                │
└─────────────────────────────────────────────────────────┘
```

## 3.2 Chi tiết từng bên

### A. Advertiser (Nhà quảng cáo / Brand Owner)

**Họ là ai:**
- Công ty sở hữu sản phẩm nutra
- Có thể tự sản xuất hoặc OEM/white-label
- Thường sở hữu hoặc thuê call center + warehouse

**Họ cung cấp gì cho Network:**
- Product (sản phẩm vật lý)
- Offer (điều khoản: payout, cap, GEO, flow)
- Landing pages (có thể cung cấp hoặc để affiliate tự làm)
- Call center capacity
- Fulfillment (đóng gói, giao hàng)

**Họ quan tâm điều gì:**
- **Lead quality** → approval rate cao = lãi
- **Volume** → càng nhiều lead tốt càng tốt (trong khả năng xử lý)
- **Consistency** → volume ổn định, không lên xuống thất thường
- **Compliance** → quảng cáo không vi phạm pháp luật

**Red flags từ Advertiser:**
- Approval rate thấp bất thường → có thể đang shave
- Giảm payout đột ngột → offer đang decline hoặc margin bị ép
- Trả tiền chậm → cash flow bermasalah
- Cap thấp bất ngờ → hết hàng hoặc call center quá tải

**Các Advertiser lớn trong Nutra:**
- Thường là các công ty private, ít public information
- Một số nổi tiếng: COD Network, Everad (vừa network vừa advertiser), Dr.Cash

---

### B. Affiliate Network (AffScale — Công ty của bạn)

**Vai trò:**
- **Trung gian** kết nối Advertiser và Affiliate
- Cung cấp platform tracking
- Quản lý thanh toán 2 chiều
- Quality control (chặn fraud, monitor compliance)

**Các bộ phận trong Network (bạn cần phối hợp):**

```
┌─────────────────────────────────────────────────┐
│              AFFILIATE NETWORK                   │
│                                                  │
│  ┌──────────────┐    ┌──────────────────────┐   │
│  │ Affiliate    │    │ Advertiser Relations │   │
│  │ Management   │    │ (AR team)            │   │
│  │ (AM team)    │    └──────────────────────┘   │
│  └──────────────┘                                │
│  ┌──────────────┐    ┌──────────────────────┐   │
│  │ Media Buying │    │ Tech / Development   │   │
│  │ (nội bộ)     │    │                      │   │
│  └──────────────┘    └──────────────────────┘   │
│  ┌──────────────┐    ┌──────────────────────┐   │
│  │ Finance /    │    │ Compliance /         │   │
│  │ Accounting   │    │ Anti-fraud           │   │
│  └──────────────┘    └──────────────────────┘   │
│  ┌──────────────┐    ┌──────────────────────┐   │
│  │ Analytics /  │    │ MKT Operations       │   │
│  │ BI           │    │ ★ BẠN Ở ĐÂY ★       │   │
│  └──────────────┘    └──────────────────────┘   │
└─────────────────────────────────────────────────┘
```

**Bạn phối hợp với ai:**

| Team | Bạn cần gì từ họ | Họ cần gì từ bạn |
|------|-------------------|-------------------|
| **AM (Affiliate Manager)** | Thông tin affiliate performance, quality issues | Quyết định offer nào push, cap allocation |
| **AR (Advertiser Relations)** | Offer mới, payout updates, approval data | Forecast volume, quality reports |
| **Media Buying** | Campaign performance data | Budget allocation, offer recommendations |
| **Tech** | Dashboard, tracking fixes, API support | Feature requests, bug reports |
| **Finance** | P&L data, payment schedules | Forecast revenue, cost alerts |
| **Compliance** | Regulatory updates, creative approval | Performance data per creative |

---

### C. Affiliates / Publishers / Media Buyers

**Họ là ai:**
- Cá nhân hoặc team chạy quảng cáo để kiếm lead cho network
- Từ solo media buyer đến agency hàng trăm người
- Có thể là internal (team in-house) hoặc external (bên ngoài)

**Phân loại Affiliate:**

```
TIER 1 — TOP AFFILIATES (5-10% số lượng, 60-80% revenue)
├── Volume: 500-5000+ leads/ngày
├── Quality: Approval rate cao
├── Đặc quyền: Payout cao hơn, cap ưu tiên, thanh toán nhanh
└── Rủi ro: Nếu mất → revenue drop đáng kể

TIER 2 — MID-LEVEL (20-30%, 15-25% revenue)
├── Volume: 50-500 leads/ngày
├── Quality: Ổn định
├── Standard terms
└── Tiềm năng grow lên Tier 1

TIER 3 — SMALL / NEW (60-70%, 5-10% revenue)
├── Volume: < 50 leads/ngày
├── Quality: Chưa ổn định
├── Cần monitor chặt hơn
└── Nguồn tìm kiếm talent mới
```

**Họ quan tâm điều gì:**
1. **Payout cao** → muốn được trả nhiều nhất có thể
2. **Approval rate tốt** → payout cao nhưng AR thấp = vẫn lỗ
3. **Cap đủ lớn** → đủ chỗ để scale
4. **Thanh toán đúng hạn** → cash flow của họ phụ thuộc vào bạn
5. **Support nhanh** → khi có vấn đề tracking, cần fix ngay
6. **Exclusive offers** → offer mà network khác không có

**Red flags từ Affiliate:**
- Trash rate > 30% → có thể đang chạy bot traffic
- Volume spike đột ngột → check quality ngay
- Chỉ chạy 1 offer → vulnerable, cần diversify
- Đòi payout quá cao → có thể đang leverage hoặc sẽ chuyển network

---

### D. Traffic Sources (Nguồn traffic)

**Các nguồn chính cho Nutra:**

| Source | Ưu điểm | Nhược điểm | Phù hợp GEO |
|--------|---------|-----------|-------------|
| **Facebook/Meta** | Volume lớn, targeting tốt | Ban account thường xuyên, compliance strict | Tất cả |
| **Google Ads** | Intent cao | Rất strict với nutra, hay ban | US, EU |
| **TikTok** | Rẻ, reach trẻ | Chất lượng lead thấp hơn | Asia, Latam |
| **Native Ads** (MGID, Taboola, Outbrain) | Ít ban, volume ổn | CR thấp hơn social | CIS, EU |
| **Push Notifications** | Rẻ, dễ scale | Quality thấp | CIS, Asia |
| **SEO / Organic** | Free traffic, quality cao | Chậm, cần đầu tư dài hạn | Tất cả |
| **Email** | ROI cao | Cần database, compliance | US, EU |
| **In-app / Pop** | Rất rẻ | Quality rất thấp | Test only |

**Compliance quan trọng:**
- Facebook/Google CẤM quảng cáo nutra trực tiếp
- Affiliates dùng **cloaking** (hiện trang khác cho reviewer, trang thật cho user)
- Nếu bị phát hiện → ban account → affiliate mất khả năng chạy
- Đây là rủi ro lớn cho network: top affiliate bị ban → volume drop ngay

---

### E. Call Center

**Vai trò:** Gọi điện xác nhận đơn hàng từ lead

**Tại sao Call Center QUYẾT ĐỊNH lợi nhuận:**

```
Ví dụ: 100 leads vào

Call Center TỐT:                    Call Center KÉM:
- Gọi trong 15 phút                 - Gọi sau 2 giờ
- Confirm 55 đơn                    - Confirm 30 đơn
- Upsell thêm 20 đơn               - Không upsell
- Approval rate: 55%                - Approval rate: 30%

Revenue chênh lệch: gần GẤP ĐÔI
```

**Metrics Call Center cần theo dõi:**
- **Response time**: Thời gian từ lead vào → gọi lần đầu (< 15 phút là tốt)
- **Contact rate**: % lead liên lạc được
- **Confirm rate**: % lead xác nhận mua
- **Upsell rate**: % khách mua thêm sản phẩm
- **Callback rate**: % cần gọi lại
- **Talk time**: Thời gian trung bình mỗi cuộc gọi

**Call Center thường:**
- In-house (của advertiser) — kiểm soát tốt hơn
- Outsourced — rẻ hơn nhưng khó kiểm soát
- Đặt tại nước có nguồn nhân lực rẻ + nói được ngôn ngữ target (VD: call center tiếng Nga đặt ở Kazakhstan)

---

### F. Warehouse & Fulfillment

**Vai trò:** Lưu kho, đóng gói, giao hàng

**Ảnh hưởng đến performance:**
- **OOS (Out of Stock)** → không ship được → lead expire → MẤT TIỀN
- **Delivery time** → giao lâu → khách quên/đổi ý → approval giảm
- **Delivery rate** → % giao thành công (ảnh hưởng bởi địa chỉ sai, khách không có nhà)

**Metrics cần theo dõi:**
- Stock level per SKU per warehouse
- Average delivery time per GEO
- Delivery success rate
- Return rate

## 3.3 Mối quan hệ và Power Dynamics

```
ADVERTISER có quyền lực khi:
├── Sở hữu offer exclusive hot
├── Approval rate tốt
└── Payout cạnh tranh
→ Network phải chiều, sợ mất offer

NETWORK có quyền lực khi:
├── Có nhiều top affiliates
├── Volume lớn (leverage đàm phán payout)
└── Cung cấp giá trị gia tăng (analytics, optimization)
→ Cả 2 bên cần network

AFFILIATE có quyền lực khi:
├── Volume lớn, quality tốt
├── Có nhiều lựa chọn network
└── Expertise traffic source khó (FB, Google)
→ Network phải giữ bằng payout cao, support tốt
```

**Bạn cần hiểu dynamic này để:**
- Biết khi nào có thể đàm phán tăng payout từ advertiser
- Biết khi nào cần giữ affiliate bằng payout bump
- Biết khi nào offer đang mất competitive advantage

## 3.4 Các platform & tool trong hệ sinh thái

### Platform chính (bạn sẽ dùng hàng ngày):

| Tool | Mục đích | Ví dụ |
|------|---------|-------|
| **Affiliate Platform** | Quản lý offer, affiliate, tracking | **AffScale**, HasOffers, Everflow, Affise |
| **Tracker** | Tracking campaign chi tiết | Binom, Keitaro, Voluum, RedTrack |
| **BI / Dashboard** | Phân tích data | Metabase, Looker, Google Data Studio, Tableau |
| **CRM** | Quản lý lead & call center | Custom-built, amoCRM |
| **Communication** | Liên lạc nội bộ & affiliate | Slack, Telegram, Skype |
| **Payment** | Thanh toán affiliate | Tipalti, Payoneer, Wire, Crypto |
| **Anti-fraud** | Phát hiện lead fraud | FraudScore, Forensiq, custom rules |
| **Creative Spy** | Xem quảng cáo đối thủ | AdSpy, SpyHero, Anstrex |

### AffScale — Platform chính của bạn

Những gì AffScale (hoặc tương tự) cung cấp:
1. **Offer Management** — tạo, cấu hình, quản lý offer
2. **Affiliate Management** — approve, tier, payout management
3. **Tracking** — click, lead, conversion tracking
4. **Reporting** — dashboard, custom reports
5. **API** — kết nối với hệ thống bên ngoài
6. **Postback Management** — S2S tracking setup
7. **Fraud Detection** — rules cơ bản chống fraud
8. **Billing** — quản lý thanh toán

**Bạn cần làm trong tuần đầu:**
- Đăng nhập AffScale, explore TOÀN BỘ menu
- Hiểu cách tạo/edit offer
- Hiểu cách tracking hoạt động
- Hiểu cách đọc reports
- Hiểu cách quản lý affiliate accounts
