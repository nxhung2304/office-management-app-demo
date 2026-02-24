┌─────────────────────────────────────────────────┐
│  1. DEV: Lên ý tưởng feature                    │
│     - Brainstorm màn hình cần làm               │
│     - Mô tả bằng app tham khảo                  │
│     - VD: "Giống màn login của Notion"          │
└─────────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────────┐
│  2. AI: Tạo demo UI (5-10 phút)                 │
│     - Code giao diện mẫu                        │
│     - Chụp screenshots tự động                  │
│     - Gửi cho dev xem trước                     │
└─────────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────────┐
│  3. DEV: Review screenshots                     │
│     ✅ OK → Approve                             │
│     ❌ Sai → Góp ý → AI sửa lại                 │
└─────────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────────┐
│  4. AI: Tạo spec chi tiết + lưu vào hệ thống    │
│     - GitHub Issues hoặc Notion                 │
│     - Kèm screenshots đã approve                │
│     - 📢 Slack: Thông báo feature mới           │
└─────────────────────────────────────────────────┘
                    ↓
        ⏸️  ĐỢI BACKEND API (1-2 tuần)
                    ↓
┌─────────────────────────────────────────────────┐
│  5. BACKEND: API sẵn sàng                       │
│     - Dev cập nhật API docs                     │
│     - Đánh dấu issue "Ready"                    │
│     - 📢 Slack: Thông báo có thể code           │
└─────────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────────┐
│  6. DEV: Approve để AI bắt đầu code             │
│     - 1 câu lệnh: "implement issue #XXX"        │
└─────────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────────┐
│  7. AI: Code hoàn chỉnh (10-30 phút)            │
│     - Viết code theo đúng spec                  │
│     - Tự động tạo tests                         │
│     - Chạy quality checks                       │
│     - Tạo Pull Request                          │
│     - 📢 Slack: Tag dev review                  │
└─────────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────────┐
│  8. DEV: Review code                            │
│     - Kiểm tra logic                            │
│     - Test trên app                             │
│     ✅ OK → Tag sếp                             │
│     ❌ Cần sửa → Comment → AI fix               │
└─────────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────────┐
│  9. SẾP: Review cuối                            │
│     - Kiểm tra nghiệp vụ                        │
│     - Test UX flow                              │
│     ✅ Approve → Merge                          │
└─────────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────────┐
│  10. ✅ FEATURE HOÀN THÀNH                      │
│      - 📢 Slack: Thông báo shipped              │
│      - Dashboard tự động cập nhật               │
└─────────────────────────────────────────────────┘

