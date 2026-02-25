# 📱 Story — Employee Mobile App
> Chiến lược: UI-only trước → chờ API chốt → cắm data sau
> Template: https://github.com/longnm2707/flutter_riverpod_base

---

## Phase 1: Project Setup

- [ ] 1. Clone & đọc hiểu cấu trúc template (Riverpod, folder structure, conventions)
- [ ] 2. Cấu hình môi trường (dev/prod flavor, app name, bundle ID)
- [ ] 3. Setup navigation — định nghĩa toàn bộ routes (go_router)
- [ ] 4. Setup theme & design system (màu, font, spacing, component base)

> Không setup repository pattern, mock data, local storage — chờ API chốt

---

## Phase 2: Authentication

- [ ] 5. UI màn hình Login (Email/Password + Google button) — static UI
- [ ] 6. Google Sign-In button — UI only, chưa tích hợp logic
- [ ] ⏸️ Auth logic (xử lý login, token storage, auth state) — chờ API

---

## Phase 3: Home Screen

- [ ] 7. Layout shell Home screen + bottom navigation
- [ ] 8. Widget "Hôm nay" — trạng thái timesheet + CTA (UI only)
- [ ] 9. Widget "Tháng này" — thống kê ngày làm & OT (UI only)
- [ ] 10. Widget "Gần đây" — leave request status + payroll notification (UI only)
- [ ] 11. Avatar dropdown — tên, email, nút Đăng xuất (UI only)

---

## Phase 4: Timesheet

- [ ] 12. Calendar widget (standalone, reusable)
- [ ] 13. UI danh sách timesheet theo tháng — tích hợp calendar widget
- [ ] 14. UI form nhập timesheet (giờ làm, project/task)
- [ ] 15. UI nhập muộn — backfill (UI only)
- [ ] ⏸️ Logic tạo/sửa timesheet entry — chờ API

---

## Phase 5: Leave Request

- [ ] 16. UI danh sách leave request + badge trạng thái
- [ ] 17. UI form tạo leave request (loại nghỉ, ngày, lý do)
- [ ] 18. UI chi tiết leave request
- [ ] ⏸️ Logic tạo leave request — chờ API
- [ ] ⏸️ Notification leave approved/rejected — chờ API + FCM

---

## Phase 6: OT Request

- [ ] 19. UI danh sách OT request + badge trạng thái
- [ ] 20. UI form tạo OT request (loại OT, ngày, số giờ)
- [ ] ⏸️ Logic tạo OT request — chờ API
- [ ] ⏸️ Notification OT approved/rejected — chờ API + FCM

---

## Phase 7: Payroll

- [ ] 21. UI danh sách payroll theo tháng (month selector)
- [ ] 22. UI chi tiết bảng lương (read-only)

---

## Phase 8: Data Layer — khi API chốt

- [ ] 23. Định nghĩa data models từ API response
- [ ] 24. Setup repository pattern + dependency injection
- [ ] 25. Implement Auth logic (login, token, auth state, logout)
- [ ] 26. Implement Timesheet data layer + kết nối UI
- [ ] 27. Implement Leave Request data layer + kết nối UI
- [ ] 28. Implement OT Request data layer + kết nối UI
- [ ] 29. Implement Payroll data layer + kết nối UI
- [ ] 30. Implement Home screen data (tổng hợp từ các feature)

---

## Phase 9: Notifications & Polish — sau khi có API

- [ ] 31. Setup Firebase Cloud Messaging
- [ ] 32. Xử lý push notification (foreground/background)
- [ ] 33. Handle notification per type (leave, OT approved/rejected)
- [ ] 34. Testing & bug fixes
- [ ] 35. Build TestFlight + Firebase App Distribution

---

## 🚀 Thứ tự implement

| Thứ tự | Phase | Lý do |
|--------|-------|-------|
| 1 | Phase 1 — Setup | Nền tảng, đọc hiểu template trước |
| 2 | Phase 2 — Auth UI | Entry point của app |
| 3 | Phase 3 — Home UI | Shell + navigation shape rõ app |
| 4 | Phase 4 — Timesheet UI | Feature chính, có calendar phức tạp nhất |
| 5 | Phase 5 — Leave UI | Feature quan trọng thứ 2 |
| 6 | Phase 6 — OT UI | Tương tự Leave, reuse component |
| 7 | Phase 7 — Payroll UI | Read-only, đơn giản nhất |
| 8 | Phase 8 — Data Layer | Sau khi API chốt |
| 9 | Phase 9 — Notifications | Polish cuối cùng |

---

## 📌 Ghi chú

- Task đánh dấu ⏸️ = chờ API, không làm trước
- Phase 1-7 hoàn toàn không phụ thuộc backend
- Khi API sẵn sàng: chỉ làm Phase 8, UI không cần đụng vào
