## Flow
- Create Github issues from ai/stories/*.md when file have status is approved
- Ai pick a issue
  -  Update status github issue from todo to inprogress
  - Notify to Slack: AI implementing issue ( with title ) and add short content
- Ai coding
    - Write code base on spec
    - Write test
    - Check code quality, clean code
    - Create PR
- Notify to slack: Tag dev to review PR
- DEV: Review code
    - Kiểm tra logic
    - Test trên app
- When PR merged -> Tag Dev and Reviewer PR is merged

## Setup
1. MCP Servers
    github        → đọc/tạo Issues, tạo PR
    slack         → gửi message, reply thread
    filesystem    → đọc/ghi file trong project (built-in)

- Install
```
npm install -g @modelcontextprotocol/server-github
npm install -g @modelcontextprotocol/server-slack
```

- Create new App
- https://api.slack.com/apps?new_app=1&
- OAuth & Permissions -> Bot Token Scopes -> channels:read & chat:write -> Copy Bot User OAuth Token
- vi .mcp.json
```
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_xxxxxxxxxxxx"
      }
    },
    "slack": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-slack"],
      "env": {
        "SLACK_BOT_TOKEN": "xoxb-xxxxxxxxxxxx",
        "SLACK_TEAM_ID": "Txxxxxxxxxxxx"
      }
    }
  }
}
```
claude

# Gõ lệnh này để kiểm tra
/mcp
Phải thấy github và slack trong danh sách với status connected.

2. Commands
/create-issues     → đọc ai/breakdown-tasks.md, tạo GitHub Issues
/start-issue #XXX  → pick issue, update status, notify Slack
/finish-issue #XXX → tạo PR, notify Slack tag dev
/issue-merged #XXX → notify Slack PR merged

3. Skills
implement_feature.md → hướng dẫn chi tiết cách code, structure, quality checks

