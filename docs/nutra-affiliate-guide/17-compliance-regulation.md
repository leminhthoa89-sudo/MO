# Chương 17: Compliance, Regulation & Legal

## 17.1 Tại sao Compliance quan trọng trong Nutra?

```
NUTRA = HIGH-RISK VERTICAL

Rủi ro nếu vi phạm:
├── Landing page bị ban → mất traffic source → revenue = 0
├── Advertiser bị cơ quan quản lý phạt → dừng offer → mất revenue
├── Payment processor ban → không nhận/gửi tiền được
├── Legal action → phạt tiền, kiện tụng
└── Reputation damage → affiliates và advertisers không muốn hợp tác
```

## 17.2 Regulation theo GEO

### Russia (RU) — CIS

```
CƠ QUAN: FAS (Federal Antimonopoly Service) — Roskomnadzor

RULES:
├── Quảng cáo thuốc / thực phẩm chức năng cần disclaimer
├── Cấm claim "chữa khỏi" bệnh (chỉ được nói "hỗ trợ")
├── Cần ghi rõ "NOT a medicine" trên landing page
├── Celebrity endorsement cần consent thật
│   (Fake doctor/celebrity testimonials = vi phạm)
├── "Before/after" photos cần real results
└── Age restriction warnings cho certain products

THỰC TẾ:
├── Enforcement level: TRUNG BÌNH
├── Hầu hết affiliates dùng cloaking để bypass
├── Nhưng nếu bị catch → fine + block domain
└── Trend: enforcement đang TĂNG dần

TRÊN LANDING PAGE CẦN CÓ:
├── Disclaimer: "Đây không phải thuốc điều trị"
├── "Hãy tham khảo ý kiến bác sĩ"
├── Thông tin nhà sản xuất thật
├── Chính sách hoàn trả
└── Thông tin liên hệ thật
```

### Brazil (BR)

```
CƠ QUAN: ANVISA (Agência Nacional de Vigilância Sanitária)

RULES:
├── Sản phẩm health phải có đăng ký ANVISA
├── Cấm claim chữa bệnh
├── Quảng cáo phải bằng tiếng Bồ Đào Nha
├── Cần hiển thị CNPJ (company registration number)
├── "Before/after" photos bị hạn chế
├── LGPD (Lei Geral de Proteção de Dados) — data privacy law
│   ├── Tương tự GDPR của EU
│   ├── Consent rõ ràng trước thu thập data
│   └── Right to delete
└── Bưu phẩm có thể bị customs kiểm tra → product phải legit

THỰC TẾ:
├── Enforcement: TRUNG BÌNH - CAO
├── ANVISA active check online products
├── Customs có thể giữ hàng nếu không có giấy tờ
└── LGPD enforcement đang tăng (fines đã có)
```

### Thailand (TH)

```
CƠ QUAN: FDA Thailand + Office of Consumer Protection Board

RULES:
├── Sản phẩm health/beauty cần FDA Thailand approval
├── Cấm claim "giảm X kg trong Y ngày" (specific claims)
├── Label phải bằng tiếng Thái
├── Online advertising cần comply với Computer Crime Act
├── PDPA (Personal Data Protection Act) — effective 2022
│   ├── Consent required
│   ├── Data breach notification mandatory
│   └── Cross-border transfer restrictions
└── Celebrity endorsement phải real

THỰC TẾ:
├── Enforcement: TRUNG BÌNH
├── FDA Thailand check Shopee/Lazada nhiều hơn direct
├── Nhưng complaint-based enforcement tồn tại
└── PDPA mới → đang trong giai đoạn enforce
```

### General Rules áp dụng MỌI GEO

```
KHÔNG BAO GIỜ được claim trên Landing Page:

❌ "Chữa khỏi [bệnh] trong X ngày"
❌ "Bác sĩ [tên thật] khuyên dùng" (nếu fake)
❌ "Đã được FDA/WHO approved" (nếu không thật)
❌ "100% không tác dụng phụ"
❌ "Giảm 20kg trong 2 tuần" (specific unrealistic claims)
❌ Fake news articles (impersonating CNN, BBC, etc.)
❌ Fake customer reviews (with stock photos)

CÓ THỂ nói:
✅ "Hỗ trợ quá trình [giảm cân/đẹp da/...]"
✅ "Thành phần tự nhiên"
✅ "Nhiều người đã thử và hài lòng"
✅ "Kết quả có thể khác nhau tùy người" (disclaimer)
✅ Real testimonials (với consent)
```

## 17.3 Traffic Source Compliance

### Facebook/Meta Advertising Policies

```
FACEBOOK CẤM NUTRA:

Facebook chính thức CẤM:
├── Before/after images
├── Health claims
├── Misleading buttons/UI elements
├── Cloaking (hiện page khác cho reviewer)
└── Supplements making disease claims

THỰC TẾ TRONG NGÀNH:
├── 90%+ nutra affiliates dùng cloaking trên Facebook
├── Facebook AI đang improve detection
├── Account ban rate cao (5-30 accounts/tháng cho 1 buyer)
├── Cost: mỗi banned account = $250+ (BM, cards, warmup)
└── Cat-and-mouse game liên tục

BẠN (MKT Ops) CẦN BIẾT:
├── Bạn KHÔNG trực tiếp chạy ads (affiliates chạy)
├── NHƯNG bạn cần hiểu rủi ro
├── Top affiliates bị ban = volume drop ngay
├── Diversify traffic sources = risk mitigation
└── Track account survival rate per affiliate/creative type
```

### Google Ads

```
Google stricter hơn Facebook cho nutra
├── Hầu như không thể chạy nutra trực tiếp
├── Cần LegitScript certification cho supplements (US)
├── Không dùng cloaking (Google detect tốt hơn FB)
└── Chủ yếu dùng cho remarketing hoặc branded terms
```

### Native Ads (MGID, Taboola, Outbrain)

```
Native networks lenient hơn Facebook/Google:
├── MGID: rất phổ biến cho nutra CIS/Latam
├── Taboola: trung bình strict
├── Outbrain: strict hơn Taboola
├── Creative guidelines: no fake news, no extreme before/after
└── Approval process: manual review, 24-48h
```

## 17.4 Payment Compliance

```
KYC (Know Your Customer):
├── Affiliate registration cần verify identity
├── Payment method verification
├── Address verification cho high-value affiliates
└── Company registration documents (cho corporate affiliates)

AML (Anti-Money Laundering):
├── Monitor large/unusual payments
├── Flag sudden payout increases
├── Report suspicious patterns to compliance
└── Keep payment records minimum 5 years

PAYMENT PROCESSOR RISK:
├── PayPal: rất strict với nutra → dễ bị frozen
├── Stripe: không accept nutra merchants
├── Wire transfer: safe nhưng chậm, phí cao
├── Payoneer: phổ biến cho affiliate payments
├── Crypto: growing, nhưng regulatory uncertainty
└── Tipalti: enterprise-level, handles compliance
```

## 17.5 Compliance Checklist cho MKT Ops

```
MONTHLY COMPLIANCE REVIEW:

□ Audit 5 random landing pages (đang active)
   ├── Check claims — có vi phạm không?
   ├── Check disclaimers — có đủ không?
   └── Check fake testimonials — có không?

□ Review advertiser compliance
   ├── Products có proper registration?
   ├── Labeling đúng regulation?
   └── Call center scripts compliant?

□ Review affiliate compliance
   ├── Traffic sources declared đúng?
   ├── Creatives approved?
   └── Any complaints from users?

□ Data privacy check
   ├── Lead data stored securely?
   ├── Consent flows in place?
   └── Data retention policy followed?

□ Payment compliance
   ├── KYC complete cho active affiliates?
   ├── Any suspicious payment patterns?
   └── Tax documentation up to date?
```

## 17.6 Resources

### Regulatory Bodies
- **FAS Russia** — https://fas.gov.ru (tiếng Nga, dùng Google Translate)
- **ANVISA Brazil** — https://www.gov.br/anvisa
- **FDA Thailand** — https://www.fda.moph.go.th
- **GDPR Official** — https://gdpr.eu
- **LGPD Brazil** — https://www.gov.br/cidadania/lgpd

### Compliance Tools
- **LegitScript** — https://www.legitscript.com — Supplement certification
- **Termly** — https://termly.io — Privacy policy generator
- **OneTrust** — https://www.onetrust.com — Data privacy management

### Learning
- IAB Compliance Guide — https://www.iab.com/guidelines/
- FTC Advertising Guidelines — https://www.ftc.gov/business-guidance/advertising-marketing
