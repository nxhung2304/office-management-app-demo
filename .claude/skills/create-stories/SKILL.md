---
allowed-tools: Grep, Bash(touch:*), Bash(mkdir:*), Read, Edit
description: Create stories from ai/story.md file. Use when use ask "Create story, create stories"
---

# Skill: Create Stories

## Mục đích
Đọc file `ai/story.md`, tạo ra file story riêng cho từng task trong thư mục `ai/stories/`.
Mỗi story là roadmap chi tiết của 1 task — dev review và đổi status thành `approved` trước khi implement.

---

## Các bước thực hiện

### 1. Đọc source file
```
Đọc: ai/story.md
```
- Parse từng task theo format: `- [ ] [number]. [title]`
- Bỏ qua task đánh dấu ⏸️ (chờ API)
- Xác định phase, number, title, labels cho mỗi task

### 2. Chuẩn bị thư mục
```bash
mkdir -p ai/stories
```

### 3. Với mỗi task → tạo file story

**Tên file:** `ai/stories/[phase-number]/[number]-[slug-title].md`

Ví dụ:
```
phase-1/001-project-setup-clone-template.md
phase-2/005-ui-login-screen.md
```

**Slug rule:** lowercase, replace space → `-`, bỏ ký tự đặc biệt

### 4. Nội dung mỗi file — theo template.md

Điền thông tin tự động:
- `ID` → STORY-[number] (3 chữ số: 001, 002...)
- `Title` → tên task từ story.md
- `Phase` → phase tương ứng
- `Status` → luôn là `pending`
- `Labels` → tự suy luận:
  - Task UI → `ui, ready`
  - Task ⏸️ → `blocked-api` (skip, không tạo)
  - Task setup → `setup, ready`
- `Created` → ngày hôm nay
- `Wireframe Reference` → map theo phase/tên task với file trong `.claude/designs/`
- `Description` → viết 2-3 câu mô tả rõ task
- `UI Structure` → gợi ý widget tree dựa trên tên task + wireframe
- `Suggested File Structure` → đường dẫn file Flutter phù hợp
- `Acceptance Criteria` → ít nhất 3 tiêu chí cụ thể
- `Implementation Checklist` → giữ nguyên từ template
- `Flow` → chỉ thêm nếu task có user interaction (form, navigation,...)
- `Notes` → ghi dependency với story khác nếu có

### 5. Sau khi tạo xong tất cả

In ra summary:
```
✅ Đã tạo [X] stories tại ai/stories/
⏸️  Bỏ qua [X] tasks (blocked-api)
...

→ Review từng file, đổi status: pending → approved để bắt đầu implement
```

---

## Wireframe mapping

> Có 2 file HTML trong `ai/designs/`:
> - `primary-screens.html` — 5 màn hình chính (Login, Home, Timesheet list, Leave list, OT list, Payroll)
> - `forms.html` — các form tạo mới (Timesheet entry, Leave Request form, OT Request form)

| Task keyword | File | Màn hình |
|---|---|---|
| login | `primary-screens.html` | 01 — Login |
| home, avatar, bottom nav | `primary-screens.html` | 02 — Home |
| timesheet list, calendar | `primary-screens.html` | 03 — Timesheet |
| timesheet form, nhập giờ | `forms.html` | 03a — Nhập Timesheet |
| leave list, danh sách nghỉ | `primary-screens.html` | 04 — Xin Nghỉ |
| leave form, tạo đơn nghỉ | `forms.html` | 04a — Tạo Leave Request |
| OT list, danh sách OT | `primary-screens.html` | 05 — OT Request |
| OT form, tạo OT | `forms.html` | 05a — Tạo OT Request |
| payroll, bảng lương | `primary-screens.html` | 06 — Bảng Lương |
| setup, navigation, theme | không có wireframe | — |

---

## Quy tắc quan trọng

- **KHÔNG** tạo story cho task ⏸️
- **KHÔNG** tự implement — chỉ tạo file story
- Status luôn là `pending` — dev tự đổi thành `approved`
- Mỗi task = 1 file riêng, không gộp
- Nếu file đã tồn tại → skip, không overwrite
