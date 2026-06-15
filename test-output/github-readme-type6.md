# GitHub CLI Skill

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="License">
  <img src="https://img.shields.io/badge/type-Platform-gray" alt="Type: Platform">
  <img src="https://img.shields.io/badge/requires-gh%20CLI-lightgrey" alt="Requires gh CLI">
</p>

> **Agent 需要查 PR 状态、看 CI 日志、搜 Issue——但你不想每次都手动敲 `gh` 命令。**
>
> 这个 Skill 让 Agent 直接调用 GitHub CLI。一行命令，结果即得。

---

## 快速开始

```bash
npx skills add github
```

前提：已安装并登录 [`gh` CLI](https://cli.github.com/)。

装完直接用自然语言：

> "查一下 PR #55 的 CI 状态"
> "显示最近 10 次 workflow run"
> "PR #55 哪个 step 挂了"

---

## 能力清单

### Pull Requests

| 你想做什么 | Agent 怎么帮你 |
|-----------|--------------|
| 查 PR CI 状态 | `gh pr checks 55 --repo owner/repo` |
| 列出最近 workflow | `gh run list --repo owner/repo --limit 10` |
| 看某个 run 详情 | `gh run view <run-id> --repo owner/repo` |
| 只看失败的 log | `gh run view <run-id> --repo owner/repo --log-failed` |

### Issues

| 你想做什么 | Agent 怎么帮你 |
|-----------|--------------|
| 列出 Issue | `gh issue list --repo owner/repo --json number,title` |
| 看 Issue 详情 | `gh issue view 42 --repo owner/repo` |

### API 高级查询

当标准子命令不够用时，Agent 可以用 `gh api` 直接调 GitHub REST API：

```bash
# 获取 PR 的特定字段
gh api repos/owner/repo/pulls/55 --jq '.title, .state, .user.login'

# 批量操作
gh issue list --repo owner/repo --json number,title --jq '.[] | "\(.number): \(.title)"'
```

### JSON 输出

大部分命令支持 `--json` + `--jq` 做结构化输出，Agent 可以只取需要的字段。

---

## 平台要求

| 依赖 | 说明 |
|------|------|
| `gh` CLI | 必须安装并 `gh auth login` |
| GitHub 账号 | 需要访问目标仓库的权限 |
| 网络 | 需要访问 `api.github.com` |

---

## 安全边界

- **不自动执行破坏性操作** — force push、删除仓库等需要你明确确认
- **不修改你的 git config** — 只读操作为主
- **不访问你没有权限的仓库** — 依赖你的 `gh` 登录状态

---

## License

MIT
