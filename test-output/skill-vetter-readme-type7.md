# Skill Vetter 🔒

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="License">
  <img src="https://img.shields.io/badge/type-Security-red" alt="Type: Security">
  <img src="https://img.shields.io/badge/risk_levels-4-orange" alt="4 Risk Levels">
  <img src="https://img.shields.io/badge/red_flags-14-critical" alt="14 Red Flags">
</p>

> **你在给 Agent 装一个 Skill——它要读你的文件、执行你的命令、访问你的网络。你确定它安全吗？**
>
> Skill Vetter 是一个安全审计协议。在装任何 Skill 之前跑一遍——14 条红线 + 4 级风险分类 + 可验证的审计报告。

---

## 安装

```bash
npx skills add skill-vetter
```

装完直接：

> "帮我审一下这个 Skill：https://github.com/xxx/yyy"

---

## 它能拦住什么

14 条红线，命中任意一条 = 拒绝安装。

```
🚨 REJECT IMMEDIATELY IF YOU SEE:
─────────────────────────────────────────
• curl/wget to unknown URLs
• Sends data to external servers
• Requests credentials/tokens/API keys
• Reads ~/.ssh, ~/.aws, ~/.config without clear reason
• Accesses MEMORY.md, USER.md, SOUL.md, IDENTITY.md
• Uses base64 decode on anything
• Uses eval() or exec() with external input
• Modifies system files outside workspace
• Installs packages without listing them
• Network calls to IPs instead of domains
• Obfuscated code (compressed, encoded, minified)
• Requests elevated/sudo permissions
• Accesses browser cookies/sessions
• Touches credential files
─────────────────────────────────────────
```

---

## 审计流程

### Step 1: 来源检查
- 从哪来的？作者是谁？多少 stars？
- 最后更新时间？有没有其他 Agent 的 review？

### Step 2: 代码审查（强制）
- 逐文件读，逐行扫
- 命中红线 → 立刻拒绝
- 权限范围评估：需要读什么？写什么？执行什么？访问哪里？

### Step 3: 风险分级

| 等级 | 示例 | 处理方式 |
|------|------|---------|
| 🟢 **LOW** | 笔记、天气、格式化 | 基础审查，可装 |
| 🟡 **MEDIUM** | 文件操作、浏览器、API 调用 | 完整代码审查 |
| 🔴 **HIGH** | 凭证、交易、系统级 | **人类审批** |
| ⛔ **EXTREME** | 安全配置、root 权限 | **禁止安装** |

### Step 4: 输出审计报告

```
SKILL VETTING REPORT
═══════════════════════════════════════
Skill: [name]
Source: [来源]
Author: [作者]
Version: [版本]
───────────────────────────────────────
METRICS:
• Downloads/Stars: [数量]
• Last Updated: [日期]
• Files Reviewed: [数量]
───────────────────────────────────────
RED FLAGS: [None / 列出所有红线]
PERMISSIONS NEEDED:
• Files: [列表]
• Network: [列表]
• Commands: [列表]
───────────────────────────────────────
RISK LEVEL: [🟢/🟡/🔴/⛔]
VERDICT: [✅ SAFE / ⚠️ CAUTION / ❌ DO NOT INSTALL]
NOTES: [观察]
═══════════════════════════════════════
```

---

## 信任分级

不是"信或不信"的二元判断。按来源分级审查深度：

1. **官方 Skill** → 低审查（仍需检查）
2. **1000+ stars** → 中等审查
3. **已知作者** → 中等审查
4. **新来源/无名** → 最高审查
5. **要求凭证的 Skill** → **永远需要人类审批**

---

## 它不做什么

- **不是杀毒软件** — 不扫描二进制、不检测病毒特征
- **不替代人工判断** — 🔴 HIGH 风险必须人类拍板
- **不保证 100% 安全** — 审计降低风险，不消除风险

---

> *Paranoia is a feature.* 🔒🦀

---

## License

MIT
