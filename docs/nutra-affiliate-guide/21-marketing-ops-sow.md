# Chương 21 — Scope of Work & Rules cho Marketing Operations

> Tài liệu chuẩn hóa vai trò, phạm vi công việc, quy tắc phối hợp và workflow vận hành cho bộ phận Marketing Operations — trung tâm điều phối giữa AM/Pub, GEO, Finance, Product.

---

## I. VAI TRÒ & ĐỊNH VỊ

**MKT Ops = Trung tâm điều phối giữa 4 trục: AM/Pub ↔ GEO ↔ Finance ↔ Product.**

Không phải team thực thi, không phải team chuyển tin. Là team **nhìn thấy toàn cảnh, phát hiện bất thường sớm nhất, ra quyết định điều phối nhanh nhất.**

**Triết lý cốt lõi:**

> *"MKT Ops tồn tại để các team khác không phải tự đi tìm vấn đề. Nếu GEO / Pub / AM phải tự phát hiện vấn đề trước Ops → Ops đã thất bại."*

**Giá trị lớn nhất của Ops:**
- Ngồi giữa → thấy cả Pub, GEO, pipeline, Finance cùng lúc
- Phát hiện bất thường nhanh hơn bất kỳ team nào khác
- Ra quyết định điều phối mà không cần chờ lệnh ngoài P0

---

## II. PHẠM VI TRÁCH NHIỆM

### 2.1. Ops SỞ HỮU (Owner)

| Hạng mục | Mô tả |
|---|---|
| **Stock & Capacity** | Theo dõi tồn kho theo SKU/GEO, forecast ngày hết hàng, cap/uncap lead |
| **Lead Flow** | Pace tiêu thụ daily, phân bổ lead theo GEO/offer, phát hiện spike/drop |
| **Offer Performance Tracking** | CR, AR, CPL, payout ratio theo từng offer–GEO–Pub |
| **Cross-team Sync** | Daily/weekly alignment giữa AM–GEO–Pub–Product |
| **Payment Reconciliation** | Đối soát số lead ↔ số được duyệt ↔ số được thanh toán |
| **Offer Lifecycle** | Launch / scale / pause / kill offer theo dữ liệu |

### 2.2. Ops KHÔNG sở hữu

- Quyết định budget cuối cùng (→ AM)
- Đàm phán CPL/payout với GEO (→ AM/BD)
- Tạo creative / angle (→ Media Buyer)
- Tech integration (→ Product)

---

## III. STAKEHOLDER RULES

### 3.1. Làm việc với **AM / PUB**

**AM cần gì từ Ops:** quyết định nhanh + số liệu đáng tin + đề xuất rõ ràng.

**Rules:**

1. **Mọi alert gửi AM phải kèm đề xuất action.** Cấm câu *"giờ làm gì anh?"* — phải là *"đề xuất cap lead GEO X xuống Y/day"*.
2. **Format báo stock** bắt buộc 4 trường: `SKU/GEO | Units còn lại | Pace hiện tại | Ngày dự kiến hết | Đề xuất`
3. **SLA response:** ≤2h trong giờ hành chính, ≤6h ngoài giờ
4. **Khi AM/Pub muốn scale lead >20%** → phải ping Ops + GEO **trước 24h**. Không có ngoại lệ cuối tuần.
5. **Daily sync** 15 phút đầu ngày, weekly review 1h cuối tuần.

### 3.2. Làm việc với **GEO**

**GEO cần gì từ Ops:** pace ổn định, forecast chính xác, không bị dump lead đột ngột.

**Rules:**

1. Ops phải là người **phát hiện bất thường TRƯỚC GEO**, không phải ngược lại. Nếu GEO SOS trước → lỗi Ops.
2. Khi stock còn **<15 ngày** → chuyển từ weekly alert sang **daily alert**
3. GEO alert *"còn X ngày"* là **baseline** — Ops phải tự recalculate bằng pace thực tế mỗi ngày
4. **Không tự ý push lead vượt capacity** đã align với GEO
5. Weekly meeting với GEO để confirm: stock thực tế, pace dự kiến tuần tới, restock ETA

### 3.3. Làm việc với **FINANCE**

**Finance cần gì từ Ops:** số sạch, không sửa ngang, đối soát đúng hạn.

**Rules:**

1. **Weekly reconciliation** mỗi thứ Hai: lead delivered vs lead approved vs lead paid
2. **Monthly invoice** gửi trước ngày 5 mỗi tháng, kèm breakdown theo offer–GEO
3. Mọi chỉnh sửa retroactive phải có **log + lý do + approval AM**
4. Dispute với GEO về lead rejected → Ops giải quyết xong rồi mới chuyển Finance, không đẩy Finance đi đôi co
5. Cash flow forecast gửi Finance hàng tuần

### 3.4. Làm việc với **PRODUCT**

**Product cần gì từ Ops:** bug report rõ ràng, priority hợp lý, không spam ticket.

**Rules:**

1. **Tech issue escalation** phải có: screenshot + thời điểm + offer/GEO ảnh hưởng + số lead impacted + mức độ (P0/P1/P2)
2. **Onboard offer mới** — Ops là người test tracking trước khi live, không để Product tự launch
3. **Weekly tech sync** 30 phút để review tracking health, pixel fire rate, postback issues
4. Không ping Product ngoài giờ trừ P0 (revenue blocker >$1k/h)

---

## IV. STANDARD WORKFLOWS

### Workflow 1: Daily Stock Check (bắt buộc mỗi sáng 9h)

```
1. Pull stock report từ tất cả GEO
2. Với mỗi SKU/GEO, ghi:
   - Units remaining
   - Volume hôm qua (lead approved)
   - Pace 3-day rolling average
   - Ngày dự kiến hết = units / pace
3. So sánh với check hôm qua:
   - Lệch <10%: ghi nhận, không alert
   - Lệch 10–20%: note trong daily report
   - Lệch >20%: ALERT NGAY kèm phân tích nguyên nhân
4. Update dashboard + gửi daily digest vào group Ops+AM
```

### Workflow 2: Red Flag Escalation (khi phát hiện bất thường)

```
Điều kiện trigger:
- Stock forecast rớt >20% so với lần check trước
- Pace tăng/giảm >30% so với 3-day average
- GEO SOS
- Pub scale lead >20% không báo trước
- Postback failure rate >5%

Action (trong vòng 30 phút):
1. Post alert vào group MKT Ops + AM (không DM riêng)
2. Kèm: timeline + số liệu + nguyên nhân dự đoán + 2-3 option action
3. Tag decision owner (AM nếu liên quan budget, GEO Lead nếu liên quan stock)
4. Follow up mỗi 2h đến khi resolved
5. Post-mortem trong vòng 48h sau resolve
```

### Workflow 3: Weekend / Off-hour Anomaly

```
1. Sáng thứ 2 (8h30) — BẮT BUỘC check volume T7-CN trước khi làm gì khác
2. Nếu volume cuối tuần lệch >20% so với weekday average:
   - Recalculate pace + ngày hết hàng
   - Ping Pub hỏi nguyên nhân (có scale không? có campaign mới không?)
   - Ping GEO cập nhật pace mới
   - Đề xuất cap lead nếu cần
3. Ops oncall cuối tuần check 1 lần/ngày lúc 11h, chỉ alert nếu P0/P1
```

### Workflow 4: New Offer Launch

```
T-7: Product setup tracking, Ops test postback
T-5: GEO confirm capacity + payout
T-3: AM confirm Pub, creative ready
T-1: Ops test end-to-end 10 leads thật
T-0: Launch — Ops monitor real-time 4h đầu
T+1: Daily review 3 ngày đầu
T+7: Scale/pause decision meeting
```

### Workflow 5: Offer Pause / Kill

```
Trigger:
- Stock hết, restock >7 ngày
- CR drop >40% trong 3 ngày liên tiếp
- Payout ratio <break-even 2 tuần
- Compliance issue (GEO flag)

Action:
1. Ops đề xuất pause với số liệu
2. AM approve trong 4h
3. Ops notify Pub + GEO + Media Buyer đồng thời
4. Redirect traffic sang offer backup (đã chuẩn bị trước)
5. Ghi log vào offer graveyard với lý do
```

### Workflow 6: Payment Reconciliation

```
Mỗi thứ Hai:
1. Pull data 3 nguồn: tracker nội bộ / GEO panel / Pub report
2. So khớp 3-way: lead sent vs approved vs paid
3. Lệch <2%: pass
4. Lệch 2–5%: flag vào dispute list, làm việc với GEO trong tuần
5. Lệch >5%: escalate AM + Finance, hold thanh toán Pub tương ứng
6. Monthly close: gửi Finance trước ngày 5
```

---

## V. META-RULES (bộ quy tắc xuyên suốt)

1. **Proactive > Reactive.** Ops phải thấy vấn đề trước khi nó nổ. Nếu ngoại bộ phát hiện trước Ops → Ops fail.

2. **Data + Recommendation, never data alone.** Không báo con số trần trụi. Luôn kèm: so sánh / nguyên nhân / đề xuất.

3. **Rule 20%.** Bất kỳ metric nào lệch >20% so với baseline → alert ngay, không đợi threshold hết hàng.

4. **Rule 24h.** Mọi quyết định scale >20% phải báo trước 24h. Ngoại lệ duy nhất: P0 emergency.

5. **Single Source of Truth.** Chỉ 1 dashboard chính thức, 1 nơi lưu quyết định. Không quyết định qua DM riêng, không có *"em nghe anh X bảo là..."*.

6. **No silent failure.** Làm sai không sao — **im lặng khi làm sai** mới là không chấp nhận được. Phát hiện lỗi của chính mình → báo ngay, không giấu.

7. **Action-first, apology-later.** Khi thấy bất thường rõ ràng, ra quyết định tạm (cap lead, pause traffic) rồi báo cáo. Không đứng im chờ lệnh.

8. **Log everything.** Mỗi quyết định lớn → ghi vào decision log: ai quyết / lý do / số liệu căn cứ.

---

## VI. REPORTING CADENCE

| Tần suất | Report | Gửi cho |
|---|---|---|
| Daily (9h) | Stock + pace + red flags | AM, GEO Lead |
| Weekly (T2) | Performance by offer/GEO, reconciliation | AM, Finance |
| Weekly (T6) | Next-week forecast, capacity plan | AM, Pub Lead |
| Monthly (ngày 3) | Full P&L by offer, Finance close | Finance, Leadership |
| Ad-hoc | Red flag alert | Ngay lập tức vào group |

---

## VII. KPI CHO MKT OPS

1. **Zero stock-out incidents** — mục tiêu: 0 vụ hết hàng/quý do Ops phát hiện muộn
2. **Forecast accuracy** — sai số ngày dự kiến hết hàng <15%
3. **Alert lead time** — phát hiện vấn đề sớm trước ngày nổ ≥3 ngày
4. **Response SLA** — ≥95% alert được respond đúng SLA
5. **Reconciliation discrepancy** — <2% lệch giữa 3 nguồn
6. **Proactive alert ratio** — ≥70% alert xuất phát từ Ops (không phải forward từ GEO/Pub)

---

## VIII. CASE STUDY — Bài học từ sự cố stock-out

**Timeline thực tế:**

| Ngày | Sự kiện | Lỗi Ops |
|---|---|---|
| 13/4 | Stock còn 23 ngày | — |
| 16/4 | Stock rớt xuống 13 ngày (mất 10 ngày trong 3 ngày) | ❌ Không alert, không recalculate, không ping Pub/GEO |
| 18–19/4 | Pub scale lead cuối tuần không báo | ❌ Không có rule ràng buộc Pub phải báo trước |
| 20/4 | GEO SOS cap lead xuống 20 | ❌ Ops bị động, đợi GEO báo mới action |
| 22/4 | Hết hàng hoàn toàn | — |

**Nguyên nhân gốc:**

1. Check stock 3 ngày/lần thay vì daily → bỏ lỡ trigger 16/4
2. Không có rule "lệch >20% → alert" → rớt 10 ngày stock trong 3 ngày vẫn im lặng
3. Ops reactive — chỉ action khi GEO bảo action
4. Không có rule ràng buộc Pub phải báo trước khi scale

**Nếu áp dụng SOP này:**

- Daily check → phát hiện bất thường ngay 14/4
- Rule 20% → alert bắt buộc ngày 16/4
- Rule 24h scale → Pub không thể scale weekend im lặng
- Workflow 2 (Red Flag) → đề xuất cap lead được đưa lên ngay 16/4 thay vì chờ 20/4

→ **Tránh được stock-out, tiết kiệm ~1 tuần doanh thu.**

---

*Tài liệu này phải được review và cập nhật mỗi quý, hoặc ngay sau mỗi incident P0/P1.*
