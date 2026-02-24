  📱 Task Breakdown — Employee Mobile App

  Phase 1: Project Setup

  1. Khởi tạo Flutter project
  2. Setup dependencies
  3. Cấu hình môi trường + mock flag
  4. Setup theme & design system
  5. Tạo repository pattern base
  6. Tạo mock data service
  7. Setup local storage

  ---
  Phase 2: Authentication

  5. UI màn hình Login (Email/Password + Google button)
  6. Tích hợp Google Sign-In
  7. Xử lý đăng nhập Email/Password
  8. Quản lý auth state & token storage
  9. UI & logic Logout

  ---
  Phase 3: Home Screen

  10. Layout Home screen
  11. Widget "Hôm nay" — trạng thái timesheet + CTA
  12. Widget "Tháng này" — thống kê ngày làm & OT
  13. Widget "Gần đây" — leave request status + payroll notification

  ---
  Phase 4: Timesheet

  14. UI danh sách timesheet theo tháng (calendar view)
  15. UI form nhập timesheet (giờ làm, project/task)
  16. Logic tạo/sửa timesheet entry
  17. Hỗ trợ nhập muộn (backfill)

  ---
  Phase 5: Leave Request

  18. UI danh sách leave request + trạng thái
  19. UI form tạo leave request (loại nghỉ, ngày, lý do)
  20. Logic tạo leave request
  21. Chi tiết leave request

  ---
  Phase 6: OT Request

  22. UI danh sách OT request + trạng thái
  23. UI form tạo OT request (loại OT, ngày, số giờ)
  24. Logic tạo OT request

  ---
  Phase 7: Payroll

  25. UI danh sách payroll theo tháng
  26. UI chi tiết bảng lương

  ---
  Phase 8: Notifications & Polish

  27. Setup Firebase Cloud Messaging
  28. Xử lý push notification (foreground/background)
  29. Deep linking từ notification
  30. Testing & bug fixes

  ---
  🚀 Đề xuất thứ tự implement

  | Thứ tự | Task                    | Lý do                                      |
  |--------|-------------------------|--------------------------------------------|
  | 1      | Phase 1 (Setup)         | Nền tảng cho toàn bộ app                   |
  | 2      | Phase 2 (Auth)          | Cần đăng nhập trước khi dùng features khác |
  | 3      | Phase 4 (Timesheet)     | Feature chính, dùng hàng ngày              |
  | 4      | Phase 3 (Home)          | Dashboard tổng hợp data từ các feature     |
  | 5      | Phase 5 (Leave)         | Feature quan trọng thứ 2                   |
  | 6      | Phase 6 (OT)            | Tương tự Leave, có thể reuse component     |
  | 7      | Phase 7 (Payroll)       | Read-only, đơn giản                        |
  | 8      | Phase 8 (Notifications) | Polish cuối cùng                           |

