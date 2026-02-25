---
allowed-tools: Bash(find:*), Bash(cat:*), Bash(sed:*), Grep, mcp__github__create_issue, mcp__github__list_issues, mcp__slack__post_message, Bash(git remote:*), Bash(gh issue:*)
description: Create GitHub Issues from approved stories in ai/stories/phase-*/
---

# Command: Create GitHub Issues from Stories

## Mục đích
Đọc các file trong `ai/stories/phase-*/`, tìm story có `Status: approved`, tạo GitHub Issue, rồi update ngược lại story file với số issue và đổi status.

---

## Các bước thực hiện

### 1. Scan tất cả story files

```bash
find ai/stories -name "*.md" | sort
```

Với mỗi file tìm được:
- Đọc nội dung
- Kiểm tra dòng `**Status:**`
- Chỉ xử lý nếu `Status: approved`
- Bỏ qua nếu đã có `**GitHub Issue:**` (đã tạo rồi)

---

### 2. Với mỗi story approved → tạo GitHub Issue

**Labels:**
- Label `ui` nếu Labels chứa `ui`
- Label `setup` nếu Labels chứa `setup`
- Label `blocked-api` nếu Labels chứa `blocked-api`
- Label `ready` nếu KHÔNG phải `blocked-api`

**Title:** lấy từ `**Title:**` trong Metadata

**Body:**
```
## Description
[nội dung từ section Description]

## Acceptance Criteria
[nội dung từ section Acceptance Criteria]

## Wireframe
[nội dung từ section Wireframe Reference]

## Suggested File Structure
[nội dung từ section Suggested File Structure]

## Notes
[nội dung từ section Notes nếu có]

---
Story: [tên file story]
Phase: [Phase từ Metadata]
```

---

### 3. Sau khi tạo issue thành công → update story file

Thêm `**GitHub Issue:**` vào Metadata và đổi status:
```markdown
- **GitHub Issue:** #[số issue]
- **Status:** open
```

Thêm section ở cuối file:
```markdown
---

## GitHub
- **Issue:** #[number]
- **URL:** https://github.com/[repo]/issues/[number]
- **Created:** [datetime]
```

---

### 4. Gửi Slack sau khi tạo xong tất cả

Gửi vào `#claude-code-workflow`:
```
📋 Đã tạo các issues
## Phase [phase-number]
1. title
  - Github issue url
2. title
  - Github issue url
```

---

## Lưu ý

- Chỉ xử lý story có `Status: approved` — bỏ qua `pending`, `open`, `done`
- Không tạo duplicate — bỏ qua nếu đã có `GitHub Issue` trong Metadata
- Nếu tạo issue thất bại → log lỗi, tiếp tục file tiếp theo
- In summary cuối kể cả file bị skip và lý do
