# 📋 PRD — Employee Mobile App

---

## 1. Tổng Quan

| | |
|---|---|
| **Mục tiêu** | App nội bộ cho nhân viên: chấm công, xin nghỉ, xem lương |
| **Platform** | iOS & Android (Flutter) |
| **Người dùng** | Toàn công ty — 18 người |
| **Deadline** | Chưa xác định, không gấp |
| **Distribution** | TestFlight (iOS) / Firebase App Distribution (Android) |
| **Maintain** | Dev + Claude Code |

---

## 2. Người Dùng & Use Case

| | |
|---|---|
| **Đối tượng** | Nhân viên toàn công ty |
| **Tần suất** | Hàng ngày |
| **Thời điểm dùng chính** | ~17h — cuối giờ làm việc |
| **Thiết bị** | Mobile (di động) |
| **Role trên app** | 1 role duy nhất: `user` |

---

## 3. Features & Màn Hình

### 3.1 Authentication
- Đăng nhập bằng **Google (Gmail tổ chức)** hoặc **Email / Password**
- Đăng xuất

---

### 3.2 Home
Hiển thị nhanh tình trạng trong ngày và tháng:

**Hôm nay**
- Trạng thái timesheet hôm nay (đã nhập / chưa nhập)
- Nút CTA nhanh "Nhập Timesheet" nếu chưa nhập

**Tháng này**
- Số giờ OT tháng này

**Gần đây**
- Trạng thái leave request mới nhất (pending / approved / rejected)
- Thông báo bảng lương đã có chưa

---

### 3.3 Timesheet
- Nhập **tổng số giờ làm** trong ngày
- Nhập theo **project**
- Cho phép **nhập muộn** (bổ sung ngày trước)
- **Push notification** nhắc nhở lúc tu Server

---

### 3.4 Xin Nghỉ (Leave Request)
- Tạo request nghỉ (chọn loại nghỉ, ngày, lý do)
- Xem danh sách request đã tạo + trạng thái
- **Notification** khi Admin duyệt hoặc từ chối

---

### 3.5 OT Request
- Tạo OT request (loại OT, ngày, số giờ)
- Xem lịch sử OT đã đăng ký
- Notification khi được duyệt / từ chối

---

### 3.6 Bảng Lương (Payroll)
- Xem bảng lương theo tháng
- Dữ liệu lấy từ API (read-only, không chỉnh sửa)

### 3.7 Setting
- Cần hiển thị tên hoặc email nếu không có setting tên
- Nút đăng xuất

---

## 4. Notifications
- Push Notification từ Server ?

## 5. Design & UX

| | |
|---|---|
| **Phong cách** | Minimal, clean |
| **Design** | Claude Code tạo wireframe → Dev review |
| **Reference apps** | Claude Code đề xuất |
| **Logo** | Tạm thời để trống |

---

## 6. Backend & Data

| | |
|---|---|
| **Trạng thái** | ERD đang hoàn thiện |
| **Team** | Dev nội bộ (Rails API) |
| **Tài liệu API** | Sẽ bổ sung vào thư mục dự án |

**Models liên quan:**

| Nhóm | Models |
|---|---|
| Người dùng | `User`, `Employee`, `Role`, `User Roles` |
| Chấm công | `Timesheet`, `Monthly Work Settings`, `Holidays` |
| Nghỉ phép | `Leave Request`, `Quotations` |
| OT | `OT Request`, `OT Type` |
| Lương | `Payroll`, `Payroll Items`, `Salary Histories` |
| Dự án | `Project Member` |

