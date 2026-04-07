# Chương 16: Automation & Process Engineering

## 16.1 Automation Mindset

```
QUY TẮC: Nếu bạn làm 1 việc > 3 lần/tuần và nó có pattern lặp lại → AUTOMATE

Ví dụ các việc nên automate:
├── Daily report → auto-generate + send to Slack
├── Alert khi AR drop → auto-detect + notify
├── Affiliate trash rate check → auto-pause khi vượt threshold
├── Weekly reconciliation → auto-pull data + flag discrepancies
├── Cap utilization check → auto-alert khi under/over-utilized
└── New lead notification → auto-route to call center
```

## 16.2 Automation Stack cho MKT Ops

```
TIER 1: No-code (Bắt đầu từ đây)
├── Google Sheets + formulas + Apps Script
├── Zapier (https://zapier.com) — connect 5,000+ apps
├── Make/Integromat (https://www.make.com) — more powerful than Zapier
└── Slack Workflows + Incoming Webhooks

TIER 2: Low-code
├── Google Apps Script (JavaScript based, free)
├── Python scripts (nếu bạn biết code)
├── AffScale API + webhooks
└── Retool (https://retool.com) — build internal tools fast

TIER 3: Full automation
├── Custom dashboard (Metabase/Looker connected to database)
├── Airflow / cron jobs cho scheduled tasks
├── Custom fraud scoring system
└── ML-based anomaly detection
```

## 16.3 Automation Recipes thực tế

### Recipe 1: Auto Daily Report to Slack

```
FLOW:
Google Sheets (data source) 
    → Google Apps Script (format report) 
    → Slack Webhook (post to channel)

GOOGLE APPS SCRIPT:
─────────────────────

function sendDailyReport() {
  var sheet = SpreadsheetApp.getActiveSpreadsheet()
                            .getSheetByName('DailyMetrics');
  
  // Get today's data
  var today = sheet.getRange('B2').getValue();     // Total leads
  var approved = sheet.getRange('B3').getValue();   // Approved
  var ar = sheet.getRange('B4').getValue();         // AR %
  var revenue = sheet.getRange('B5').getValue();    // Revenue
  var margin = sheet.getRange('B6').getValue();     // Margin
  var alerts = sheet.getRange('B7').getValue();     // Alert text
  
  // Format message
  var message = {
    "text": ":chart_with_upwards_trend: *DAILY REPORT — " 
            + new Date().toLocaleDateString() + "*\n\n"
            + "Leads: *" + today + "* | Approved: *" + approved 
            + "* | AR: *" + ar + "%*\n"
            + "Revenue: *$" + revenue + "* | Margin: *$" + margin + "*\n"
            + (alerts ? "\n:warning: *Alerts:*\n" + alerts : 
               "\n:white_check_mark: No alerts")
  };
  
  // Send to Slack
  var webhook = 'https://hooks.slack.com/services/YOUR/WEBHOOK/URL';
  UrlFetchApp.fetch(webhook, {
    method: 'post',
    contentType: 'application/json',
    payload: JSON.stringify(message)
  });
}

// Schedule: Triggers → Time-driven → Day timer → 9:00-10:00 AM
```

### Recipe 2: Auto Alert khi AR Drop

```
FLOW (Zapier/Make):

Trigger: Schedule (every 1 hour)
    → Action: Fetch data from Google Sheets / API
    → Filter: AR < threshold cho bất kỳ offer nào
    → Action: Send Slack alert + Email

ZAPIER SETUP:
1. Trigger: Schedule by Zapier (every 1 hour)
2. Action: Google Sheets — Get Row (latest metrics row)
3. Filter: Only continue if AR < 35%
4. Action: Slack — Send Channel Message
   Channel: #mkt-ops-alerts
   Message: "🔴 AR ALERT: Offer {offer_name} at {ar}% 
            (threshold: 35%). GEO: {geo}. Check dashboard."
5. Action: Email — Send to you + CMO (if AR < 25%)
```

### Recipe 3: Affiliate Auto-pause System

```
LOGIC (implement trên AffScale hoặc custom script):

Every 30 minutes:
    FOR each active affiliate:
        last_24h_leads = query leads last 24 hours
        trash_count = count where status = 'trash'
        trash_rate = trash_count / last_24h_leads
        
        IF trash_rate > 0.35 AND last_24h_leads > 20:
            → Set affiliate cap = 0 (auto-pause)
            → Send Slack alert: "Auto-paused {affiliate} — trash {trash_rate}%"
            → Send email to AM team
            → Log to incident tracker
        
        ELIF trash_rate > 0.25 AND last_24h_leads > 20:
            → Send Slack warning: "⚠️ {affiliate} trash at {trash_rate}%"
            → Flag for manual review

IMPLEMENTATION OPTIONS:
├── AffScale built-in rules (if available)
├── Google Apps Script + AffScale API
├── Python script on cron job
└── Zapier with AffScale webhook triggers
```

### Recipe 4: Weekly Reconciliation Auto-check

```
FLOW:
1. AffScale API → pull weekly approved count by offer
2. Advertiser report → import to Google Sheets (manual upload OR API)
3. Google Sheets formula: =AffScale_count - Advertiser_count
4. Conditional formatting: 
   ├── Diff < 3% → green
   ├── Diff 3-5% → yellow  
   └── Diff > 5% → red + auto-alert
5. Apps Script: auto-send reconciliation summary to Finance + AR team
```

## 16.4 API Basics — Kết nối hệ thống

### Hiểu API ở mức cần thiết:

```
API = Application Programming Interface
= Cách 1 phần mềm "nói chuyện" với phần mềm khác

VÍ DỤ: Bạn muốn tự động lấy data leads từ AffScale

HTTP Request:
GET https://api.affscale.com/v1/leads?
    date_from=2026-04-01
    &date_to=2026-04-05
    &offer_id=1234
    &api_key=your_secret_key

Response (JSON):
{
  "data": [
    {"lead_id": 1001, "status": "approved", "affiliate_id": 567, ...},
    {"lead_id": 1002, "status": "trash", "affiliate_id": 567, ...},
    ...
  ],
  "total": 1250,
  "page": 1
}
```

### Test API với Postman

```
POSTMAN (https://www.postman.com — miễn phí):

1. Download Postman
2. Tạo request mới
3. Method: GET
4. URL: https://api.affscale.com/v1/stats/daily
5. Headers: 
   ├── Authorization: Bearer your_api_key
   └── Content-Type: application/json
6. Params:
   ├── date_from: 2026-04-01
   ├── date_to: 2026-04-05
   └── group_by: offer,geo
7. Click Send → xem response

Bạn KHÔNG CẦN biết code để dùng Postman.
Chỉ cần đọc API docs của AffScale và fill đúng fields.
```

## 16.5 Tools & Resources

### Automation Tools
- **Zapier** — https://zapier.com — No-code automation, 5000+ app integrations
- **Make (Integromat)** — https://www.make.com — More powerful, visual workflow builder
- **Google Apps Script** — https://script.google.com — Free, JavaScript-based
- **n8n** — https://n8n.io — Open-source alternative to Zapier (self-hosted)

### API Tools
- **Postman** — https://www.postman.com — API testing, miễn phí
- **Insomnia** — https://insomnia.rest — Lightweight API client

### Dashboard / BI
- **Metabase** — https://www.metabase.com — Free, open-source BI
- **Google Looker Studio** — https://lookerstudio.google.com — Free dashboards
- **Retool** — https://retool.com — Build internal tools quickly

### Learning
- **Zapier University** — https://zapier.com/university
- **Google Apps Script Guide** — https://developers.google.com/apps-script
- **Automate the Boring Stuff** — https://automatetheboringstuff.com — Python automation (free book)
