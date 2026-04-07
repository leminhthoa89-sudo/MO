# Chương 14: Fraud Detection & Anti-fraud Nâng cao

## 14.1 Landscape — Fraud trong Nutra Affiliate

```
CHI PHÍ FRAUD TRONG NGÀNH:

Ước tính 15-30% leads trong nutra affiliate là fraudulent
→ Nếu network xử lý 2,000 leads/ngày
→ 300-600 leads có thể là fake
→ Ở payout $8/lead → $2,400 - $4,800 / ngày tiền mất
→ $72,000 - $144,000 / tháng

PHÁT HIỆN VÀ CẮT ĐƯỢC FRAUD = TĂNG MARGIN NGAY LẬP TỨC
```

## 14.2 Phân loại Fraud chi tiết

### Type 1: Bot Traffic

```
MÔ TẢ:
Phần mềm tự động điền form, giả lập user thật

DẤU HIỆU:
├── Leads đến đều đặn (interval < 5% variance)
├── User agent giống nhau hoặc pattern lặp
├── IP addresses clustered
├── Session time gần như bằng 0 (instant form fill)
├── JavaScript disabled (bots thường không chạy JS)
├── No mouse movement / scroll events
└── Form fill time < 3 giây (người thật cần 15-60 giây)

TOOLS PHÁT HIỆN:
├── IP intelligence: MaxMind, IP2Location
├── Device fingerprinting: FingerprintJS
├── Behavioral analysis: time-on-page, mouse heatmap
└── Custom rules trên AffScale

PREVENTION:
├── CAPTCHA trên form (nhưng giảm CR cho real users)
├── Honeypot fields (hidden field, bot sẽ fill, real user không thấy)
├── JavaScript validation (require JS enabled)
├── Minimum time-on-page threshold
└── Rate limiting per IP
```

### Type 2: Click Fraud

```
MÔ TẢ:
Inflate click count để tăng EPC giả, hoặc steal conversions

SUBTYPES:

a) Click Injection (Mobile)
├── Malware trên phone user fire click ngay trước khi install
├── "Steal" attribution từ organic hoặc advertiser khác
└── Ít phổ biến trong nutra COD, chủ yếu mobile app

b) Click Spamming
├── Fire hàng triệu fake clicks hoping random match
├── Very low CR nhưng "có" conversions bằng xác suất
└── Detect: abnormally low CR (< 0.1%)

c) Click Stacking
├── Đặt nhiều click trackers chồng lên nhau
├── 1 real click = multiple tracked clicks
└── Detect: multiple clicks cùng timestamp, same user
```

### Type 3: Lead Injection / Database Stuffing

```
MÔ TẢ:
Affiliate inject leads từ database phone numbers mua ngoài chợ đen

DẤU HIỆU:
├── Volume spike mà không tương ứng tăng ad spend
├── Phone numbers từ cùng provider/prefix
├── Geographic mismatch (IP from Moscow, phone from Vladivostok)
├── Call center feedback: "Tôi không đặt hàng gì cả"
├── Very low confirm rate (< 10%) mặc dù trash thấp
└── Leads vào ngoài giờ cao điểm (3-5 AM)

PREVENTION:
├── Phone number validation API (Twilio Lookup, NumVerify)
├── IP-to-phone-area matching
├── Volume cap per affiliate per hour (not just daily)
├── Mandatory cooling period cho new affiliates
└── Random sample audit: call 10 leads hỏi "bạn có đặt hàng không?"
```

### Type 4: Incentivized Traffic

```
MÔ TẢ:
Affiliate hứa "quà miễn phí", "cashback" để lấy leads

DẤU HIỆU:
├── Leads "real" (SĐT đúng, có người nghe)
├── NHƯNG confirm rate rất thấp
├── Khách nói: "Tôi chỉ đăng ký lấy quà" / "Ai đó bảo tôi đăng ký"
├── AR thấp hơn rõ rệt vs cùng offer trên affiliates khác
└── Review landing page / creative của affiliate (nếu có access)

PREVENTION:
├── Trong hợp đồng affiliate: cấm incentivized traffic
├── Monitor confirm rate by affiliate (chỉ số quan trọng nhất)
├── Random landing page audit
└── Mystery shopping: đăng ký qua link affiliate xem flow thật
```

### Type 5: Cookie Stuffing / Attribution Fraud

```
MÔ TẢ:
Force cookies/clicks lên browser user mà user không biết

DẤU HIỆU:
├── Conversions from users who never visited LP
├── No pre-lander / LP view in click path
├── Click-to-conversion time abnormally short
└── Traffic source suspicious (porn, piracy sites)

PREVENTION:
├── S2S tracking (không dựa vào cookies)
├── Click-to-lead time analysis
├── Require LP view before lead accepted
└── Block known suspicious domains
```

### Type 6: Advertiser-side Fraud (Shaving)

```
MÔ TẢ:
ADVERTISER cắt bớt conversions, không tính tiền cho network

DẤU HIỆU:
├── Discrepancy > 5% giữa AffScale data và advertiser CRM
├── Discrepancy tăng dần theo thời gian (bắt đầu nhỏ, lớn dần)
├── Selective shaving: chỉ shave high-payout leads
├── "Technical issues" giải thích cho missing conversions
└── Competitor networks cũng report shaving từ cùng advertiser

ACTION:
├── Weekly reconciliation BẮT BUỘC
├── Demand lead-level reports từ advertiser
├── Cross-check click_ids: gửi list → advertiser phải account for all
├── If confirmed shaving > 5%: formal complaint → negotiate → switch
└── NEVER rely on 1 advertiser cho majority revenue
```

## 14.3 Anti-fraud Rules Engine

### Rules bạn nên implement:

```
AUTOMATED RULES (set trên AffScale hoặc custom):

TIER 1 — AUTO-PAUSE:
├── Trash rate > 35% trong 24h → pause affiliate
├── > 5 leads từ same IP trong 1 giờ → flag + hold
├── Form fill time < 3 giây → reject lead
├── Duplicate phone number within 7 days → reject
├── > 50 leads/hour từ 1 affiliate khi cap = 100/day → pause
└── Phone number fails validation → trash

TIER 2 — AUTO-FLAG (review manually):
├── Trash rate 20-35% → warning notification
├── Volume tăng > 3x trong 24h → flag for review
├── Leads từ VPN/proxy IP → flag
├── Night leads (00:00 - 06:00 local time) > 30% → flag
├── Click-to-lead time < 10 giây → flag
└── Same device fingerprint > 3 leads/day → flag

TIER 3 — MONITORING:
├── New affiliate first 14 days → enhanced monitoring
├── Affiliate switched traffic source → monitor 7 days
├── Payout increased → monitor quality 7 days
└── Seasonal anomaly (holiday traffic patterns) → adjust thresholds
```

### Fraud Score Model (đơn giản)

```
Mỗi lead được tính fraud score 0-100:

FACTOR                          POINTS
─────────────────────────────────────────
Known VPN/proxy IP              +30
Form fill time < 5 sec          +20
Duplicate phone (7 days)        +25
IP-phone geo mismatch           +15
Suspicious user agent           +15
Night submission (00-06)        +10
No JS / no cookies              +20
Referrer missing/suspicious     +10
Same device fingerprint reuse   +20

THRESHOLDS:
├── Score 0-30:  Accept normally
├── Score 31-50: Accept but flag for review
├── Score 51-70: Hold for manual review
└── Score 71+:   Auto-reject / trash
```

## 14.4 Fraud Investigation Workflow

```
SOP: FRAUD INVESTIGATION
═════════════════════════

TRIGGER: Affiliate flagged by automated rules OR manual detection

STEP 1: ISOLATE (0-30 minutes)
├── Reduce affiliate cap to minimum (not full pause yet)
├── Start collecting evidence
└── Do NOT alert affiliate yet

STEP 2: GATHER DATA (30 min - 2 hours)
├── Pull last 7-14 days of lead data
├── Run fraud detection queries (timestamp, IP, phone patterns)
├── Check call center feedback for this affiliate's leads
├── Compare AR with same offer/GEO on other affiliates
└── Screenshot any suspicious landing pages

STEP 3: ANALYZE (1-2 hours)
├── Calculate fraud percentage estimate
├── Calculate financial exposure
├── Determine fraud type
└── Assess: intentional fraud or poor quality traffic?

STEP 4: DECIDE
├── If clear fraud (> 50% fake leads): BAN + hold payment
├── If borderline (20-50% suspicious): Warning + reduced cap + probation
├── If poor quality (not intentional): Education + guidelines + monitor
└── Document decision and reasoning

STEP 5: ACT
├── Execute decision on AffScale
├── Communicate to affiliate (via AM)
├── Adjust automated rules if gap found
├── Report to Finance (payment hold/adjustment)
└── Update blacklist if banned

STEP 6: POST-MORTEM
├── How did fraud get through?
├── What rules need updating?
├── Total financial impact?
└── Share learnings with team
```

## 14.5 Tools & Resources

### Anti-fraud Tools
- **FraudScore** — https://fraudscore.ai — Real-time fraud detection cho affiliate
- **Forensiq** (Impact) — https://impact.com — Click & lead fraud detection
- **HUMAN (formerly White Ops)** — https://www.humansecurity.com — Bot detection
- **FingerprintJS** — https://fingerprint.com — Device fingerprinting
- **MaxMind** — https://www.maxmind.com — IP intelligence, GeoIP, proxy detection
- **IPQualityScore** — https://www.ipqualityscore.com — Proxy/VPN detection, email/phone validation
- **NumVerify** — https://numverify.com — Phone number validation API
- **Twilio Lookup** — https://www.twilio.com/lookup — Phone carrier & type lookup

### Learning Resources
- Blog: "Affiliate Fraud Detection" trên Forensiq blog
- TUNE Anti-fraud Guide — https://www.tune.com/resources/ (search fraud prevention)
- Kochava Fraud Guide — https://www.kochava.com/fraud/
