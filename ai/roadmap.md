# 🗺️ Roadmap — Employee Mobile App

---

## Phase 0: Setup (1-2 ngày)

**Mục tiêu:** Chuẩn bị nền tảng trước khi code

- Setup Flutter project + cấu trúc thư mục theo workflow
- Tạo `.claude/context.md` để Claude Code load mỗi lần mới
- Setup GitHub Issues (hoặc Notion) cho specs
- Setup Slack channel `#dev-employee-app`
- Tạo `specs/design_system.md` (màu, font, spacing)
- Tạo `specs/app_references.md` (reference apps cho từng màn)

---

## Phase 1: Authentication (1 tuần)

**Chờ API:** Login (Google OAuth + Email/Password), Logout

| Issue | Feature | Màn hình |
|---|---|---|
| #001 | Login screen | Email/Password + Google Sign-in |
| #002 | Auth flow | Token storage, auto-login, logout |

---

## Phase 2: Home Dashboard (1 tuần)

**Chờ API:** Timesheet status hôm nay, monthly summary, leave request status

| Issue | Feature |
|---|---|
| #003 | Home screen — Timesheet hôm nay + CTA |
| #004 | Home screen — Monthly summary (ngày nhập / OT) |
| #005 | Home screen — Leave request status gần nhất |

---

## Phase 3: Timesheet (1-2 tuần)

**Chờ API:** CRUD timesheet, projects/tasks list

| Issue | Feature |
|---|---|
| #006 | Nhập timesheet hôm nay |
| #007 | Nhập theo project/task |
| #008 | Bổ sung timesheet ngày trước (nhập muộn) |
| #009 | Danh sách timesheet tháng |
| #010 | Push notification nhắc nhở |

---

## Phase 4: Leave Request (1 tuần)

**Chờ API:** Leave types, CRUD leave request

| Issue | Feature |
|---|---|
| #011 | Tạo leave request |
| #012 | Danh sách requests + trạng thái |
| #013 | Notification khi approved/rejected |

---

## Phase 5: OT Request (1 tuần)

**Chờ API:** OT types, CRUD OT request

| Issue | Feature |
|---|---|
| #014 | Tạo OT request |
| #015 | Lịch sử OT đã đăng ký |
| #016 | Notification khi approved/rejected |

---

## Phase 6: Payroll (3-5 ngày)

**Chờ API:** Payroll by month (read-only)

| Issue | Feature |
|---|---|
| #017 | Xem bảng lương theo tháng |
| #018 | Chi tiết payroll items |

---

## Phase 7: Polish & Release (1 tuần)

- Bug fixes từ internal testing (18 người)
- Empty states, loading states, error handling toàn app
- Onboarding flow (lần đầu dùng app)
- Build TestFlight + Firebase App Distribution
- Gửi cho toàn công ty test

---

## Timeline Tổng Quan

```
Tuần 1     │ Phase 0 + Phase 1 (Auth)
Tuần 2     │ Phase 2 (Home) + chờ API timesheet
Tuần 3-4   │ Phase 3 (Timesheet)
Tuần 5     │ Phase 4 (Leave)
Tuần 6     │ Phase 5 (OT)
Tuần 7     │ Phase 6 (Payroll)
Tuần 8     │ Phase 7 (Polish + Release)
```

> **Lưu ý:** Timeline phụ thuộc vào tốc độ Rails API team. Phase nào API chưa sẵn thì AI làm UI demo + spec trước, đợi API ready là implement ngay.

---

## Dependency Quan Trọng

Mỗi phase **bắt đầu bằng AI tạo UI demo** → Dev review → Khi API ready mới implement thật. Điều này giúp các phase có thể **chạy song song** với backend team mà không bị block hoàn toàn.
