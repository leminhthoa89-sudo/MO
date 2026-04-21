# MKT OPS TRACKING SYSTEM — Setup Guide

## Tổng quan

Bộ tracking system gồm **6 tabs** (sheets) để quản lý toàn bộ hoạt động daily của team Operations.

```
WORKBOOK STRUCTURE:
═══════════════════

📊 1. Dashboard          — Tổng quan hàng ngày (auto-calc từ các tabs khác)
📋 2. Issue Log          — Nhật ký tất cả issues trong ngày
🔄 3. Request Tracker    — Tracking mọi request MO ↔ AM (với SLA)
⭐ 4. AM Proactivity     — Weekly scorecard từng AM
🚨 5. Escalation Log     — Log các escalation + outcome
👥 6. Staff Performance  — Quản lý nhân viên Ops của bạn
```

---

## Cách setup vào Google Sheets (RECOMMENDED)

### Bước 1: Tạo workbook mới
1. Mở https://sheets.google.com
2. Tạo spreadsheet mới, đặt tên: **"MKT Ops Daily Tracking"**

### Bước 2: Import từng CSV vào từng tab
Với mỗi file CSV trong folder này:

1. Click nút **+** ở góc dưới bên trái để tạo tab mới
2. Đổi tên tab theo CSV file
3. File → Import → Upload → chọn file CSV
4. Chọn "Append to current sheet" hoặc "Replace current sheet"
5. Import location: **Current sheet**

### Bước 3: Apply formatting (dưới đây)

---

## TAB 1: Dashboard

**Mục đích:** Màn hình đầu tiên bạn mở mỗi sáng. Auto-calculate từ các tabs khác.

### Cell values (cell A1 trở đi):

```
A1: MKT OPS DAILY DASHBOARD
A2: Last updated: =NOW()

A4: 🔴 Open Critical Issues: =COUNTIFS('Issue Log'!E:E,"Critical",'Issue Log'!H:H,"Open")
A5: 🟡 Open High Issues:     =COUNTIFS('Issue Log'!E:E,"High",'Issue Log'!H:H,"Open")
A6: 🔵 Open Normal Issues:   =COUNTIFS('Issue Log'!E:E,"Normal",'Issue Log'!H:H,"Open")

A8:  Pending Requests:         =COUNTIF('Request Tracker'!I:I,"Pending")
A9:  Overdue Requests (🚨):    =COUNTIFS('Request Tracker'!I:I,"Pending",'Request Tracker'!J:J,"<"&NOW())
A10: Resolved Today:           =COUNTIFS('Request Tracker'!I:I,"Resolved",'Request Tracker'!K:K,">="&TODAY())

A12: Escalations This Week:    =COUNTIFS('Escalation Log'!B:B,">="&TODAY()-7)
A13: Avg Resolution Time (h):  =AVERAGE('Request Tracker'!L:L)
```

### Formatting:
- A4 background **red** nếu > 0
- A5 background **yellow** nếu > 0
- A9 background **red** nếu > 0

---

## TAB 2: Issue Log

**Mục đích:** Ghi lại MỌI issue xảy ra trong ngày, không quên cái nào.

**Who uses it:** Ops staff ghi liên tục. MO Manager review morning + end of day.

**File:** `02-issue-log.csv`

### Cách dùng daily:
1. Khi bất kỳ issue nào xuất hiện → ghi vào đây ngay (đừng để cuối ngày mới nhớ)
2. MO Manager review vào 9:00 AM, 2:00 PM, 5:00 PM
3. Mỗi issue phải có: Owner + Due date + Status

### Conditional Formatting:
- Column E (Severity):
  - "Critical" → bg đỏ, text trắng
  - "High" → bg vàng
  - "Normal" → bg xanh nhạt
- Column H (Status):
  - "Open" → bg đỏ nhạt
  - "In Progress" → bg vàng nhạt
  - "Resolved" → bg xanh nhạt
  - "Escalated" → bg cam

### Dropdown lists (Data → Data validation):
- Column C (Type): `Traffic Quality, Stock/OOS, Payment, Tracking, LP Issue, Call Center, Other`
- Column D (Team): `AM, Call Center, Finance, Product, Tech, Publisher, Internal Ops`
- Column E (Severity): `Critical, High, Normal, Low`
- Column H (Status): `Open, In Progress, Resolved, Escalated`

---

## TAB 3: Request Tracker

**Mục đích:** Track MỌI request MO ↔ AM (hoặc ↔ teams khác) với SLA countdown.

**File:** `03-request-tracker.csv`

### Cách dùng:
1. Mọi request nhận được → ghi ngay vào
2. Tự động tính SLA deadline: `=E2+IF(F2="Urgent",1/6,1)` (4h cho urgent, 1 ngày cho normal)
3. Tự động highlight nếu quá SLA

### Formulas tự động:
- Column J (SLA Deadline): `=E2+IF(F2="Urgent",TIME(4,0,0),TIME(24,0,0))`
- Column L (Resolution Time hours): `=IF(K2<>"",(K2-E2)*24,"")`
- Column M (SLA Status): 
  `=IF(I2="Resolved",IF(K2<=J2,"✅ Met","❌ Missed"),IF(NOW()>J2,"🚨 OVERDUE","⏳ In Window"))`

### Conditional Formatting:
- Column M:
  - Contains "OVERDUE" → bg đỏ, text trắng, bold
  - Contains "Missed" → bg đỏ nhạt
  - Contains "Met" → bg xanh nhạt

### Dropdown:
- Column C (Type): `Payout Change, Cap Change, New Deal, Commit, LP Issue, Stock Check, Other`
- Column F (Priority): `Urgent, Normal`
- Column G (Direction): `AM→MO, MO→AM, MO→CC, MO→Finance, MO→Product, MO→Tech`
- Column I (Status): `Pending, In Review, Approved, Rejected, Escalated, Resolved`

---

## TAB 4: AM Proactivity

**Mục đích:** Track tuần performance của từng AM — fix vấn đề "AM chưa chủ động".

**File:** `04-am-proactivity.csv`

### Cách dùng:
- Update hàng ngày (tick mỗi negotiation action)
- Review cuối tuần (Friday afternoon)
- Score công bố cho cả team → peer pressure

### Formulas:
- Column J (Total Actions): `=SUM(C2:I2)`
- Column K (Score): 
  - `=IF(J2>=5,"🟢 Excellent",IF(J2>=3,"🟡 Meeting Min",IF(J2>=1,"🟠 Below Target","🔴 Not Proactive")))`

### Weekly Target: ≥ 3 proactive actions per AM

---

## TAB 5: Escalation Log

**Mục đích:** Track các escalation, xem team nào có nhiều vấn đề cần escalate → xử lý root cause.

**File:** `05-escalation-log.csv`

### Cách dùng:
- Ghi lại mỗi khi có escalation (bất kỳ hướng nào)
- Monthly review: team/issue type nào escalate nhiều → tại sao?

### Conditional Formatting:
- Column H (Resolution Time > 48h) → highlight đỏ
- Column I (Outcome):
  - "Resolved" → xanh
  - "Escalated Further" → cam
  - "Unresolved" → đỏ

---

## TAB 6: Staff Performance

**Mục đích:** Quản lý team Ops của bạn. KPI cá nhân, review weekly.

**File:** `06-staff-performance.csv`

### Cách dùng:
- Mỗi tuần update metrics cho từng nhân viên
- 1-on-1 meetings sử dụng data này
- Monthly: review performance, identify coaching needs

### Metrics mỗi staff:
- **Issues Handled** — từ Issue Log, filter by owner
- **Request Resolved** — từ Request Tracker
- **SLA Hit Rate** — % requests resolved on time
- **Proactive Flags** — issues they caught BEFORE becoming critical
- **Escalations Raised** — appropriate escalations (không phải quá nhiều)
- **Weekly Score** — composite 1-10

### Formula cho Weekly Score:
```
=ROUND(
  (SLA_Hit_Rate * 0.3) +
  (Proactive_Flags / Target * 0.25) +
  (Issues_Handled / Target * 0.25) +
  (10 - Escalations_Raised * 0.5) * 0.2
, 1)
```

---

## 📊 WORKFLOW HÀNG NGÀY

```
MORNING (9:00 AM):
├── [Bạn] Open Dashboard — xem overnight issues
├── [Bạn] Review Issue Log — assign owners cho issues chưa có
├── [Bạn] Check Request Tracker — có overdue requests không?
└── [Bạn] Standup 15 min với team Ops — priorities hôm nay

THROUGHOUT DAY:
├── [Staff] Log issues ngay khi xảy ra
├── [Staff] Update request status real-time
├── [Staff] Tick proactivity actions
└── [Bạn] Spot-check 2-3 lần/ngày (11AM, 2PM, 5PM)

END OF DAY (5:00 PM):
├── [Bạn] Review Dashboard
├── [Bạn] Ensure all issues have owner + due date
├── [Bạn] Note any escalations needed
└── [Bạn] Prepare tomorrow priorities

WEEKLY (Friday 4:00 PM):
├── [Bạn] AM Proactivity Review
├── [Bạn] Staff Performance 1:1s (15 min each)
├── [Bạn] Escalation Log — any patterns?
└── [Bạn] Archive week's data, reset

MONTHLY:
├── [Bạn] Trend analysis: issue types, teams involved
├── [Bạn] Process improvements based on patterns
└── [Bạn] Staff performance reviews
```

---

## 🎯 RULES FOR YOUR TEAM (đưa vào team policy)

### Rule 1: Log Everything
> "If it's not in the tracker, it didn't happen."
> Issues không log = không được count cho KPI.

### Rule 2: Data-backed requests only
> Mọi request phải có data. AM submit request không đủ data → Reject, yêu cầu bổ sung.

### Rule 3: Proactive > Reactive
> Staff được reward dựa trên proactive flags, không chỉ issues handled.

### Rule 4: SLA is sacred
> Miss SLA 3 lần/tuần → review với staff member.
> Overdue request > 48h → auto-escalate.

### Rule 5: Weekly review is mandatory
> Friday 4PM — không cancel. Pattern là gì, không ngại discuss.

---

## 🛠️ Alternative: Tools thay thế Google Sheets

Nếu team lớn hơn, có thể upgrade sang:

| Tool | Pros | Cost |
|------|------|------|
| **Airtable** | Database + UI tốt, formula mạnh, views | Free → $10/user/month |
| **Notion** | All-in-one, good for docs + tracker | Free → $8/user/month |
| **ClickUp** | Project management + custom fields | Free → $7/user/month |
| **Monday.com** | Visual, good for dashboards | $8+/user/month |
| **Jira Service Management** | Best for issue tracking at scale | $7.75+/user/month |

**Recommendation:** Bắt đầu với Google Sheets, khi team > 5 người thì move sang **Airtable**.
