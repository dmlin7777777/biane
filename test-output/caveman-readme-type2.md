# 🦴 Caveman

> AI 回复总是先写 3 行客套话再给答案？Caveman 模式能省掉 ~75% 的废话，但保留全部技术精度。

```bash
npx skills add caveman
```

---

## Before vs After

**同一个问题，两种回答：**

```
Before（通常回复，~180 词）:
"Sure! I'd be happy to help you with that. Let me take a look at the
issue you're experiencing. Based on my analysis, the problem appears
to be related to the authentication middleware. Specifically, the
token expiry check is using `<` (less than) when it should actually
be using `<=` (less than or equal to). This means that tokens that
expire exactly at the current timestamp are incorrectly being treated
as still valid. I would recommend changing the comparison operator
on line 47 of auth.ts to fix this issue. Would you like me to show
you the exact code change?"

After（Caveman，~35 词）:
"Bug in auth middleware. Token expiry check use `<` not `<=`.
Fix: line 47 auth.ts. Change to `<=`.
→ Want exact diff?"
```

**节省对比：**

| 指标 | 普通回复 | Caveman |
|------|---------|---------|
| 词数 | ~180 | ~35 |
| 废话占比 | ~45% | 0% |
| 首次提到根因 | 第 4 句 | 第 1 句 |
| 技术精度 | 完整 | 完整 |

---

## 真实对话示例

```
User: "帮我看下这个 bug — 登录接口返回 500"

Agent: "Auth middleware bug. Token expiry uses `<` not `<=`.
Fix: line 47 auth.ts. Change to `<=`.
→ Want exact diff?"

[极简回复，但根因和修复方案在 3 句话内传达完毕]
```

---

## 怎么用

对话中说以下任意一句即可触发：

```
caveman mode
talk like caveman
less tokens
be brief
/caveman
```

**关闭：** 说 `stop caveman` 或 `normal mode`。
**持续：** 一旦触发，**每一条回复**都是 Caveman 风格，直到你主动关闭。

---

## 它做了什么

去掉所有废话，保留全部技术内容：

| 去掉 | 保留 |
|------|------|
| 冠词（a/an/the） | 技术术语（原样） |
| 填充词（just/really/basically/actually） | 代码块（不改动） |
| 客套话（sure/certainly/of course） | 错误信息（原文引用） |
| 模糊语（hedging） | 因果箭头（X → Y） |

---

## 安全边界

Caveman 自动在以下场景**临时退出**极简模式，回到完整表达：

- **安全警告** — 涉及不可逆操作时，完整描述风险
- **多步骤序列** — 当片段式表达可能被误读顺序时
- **用户追问** — 当你重复提问时，说明上一轮没说清楚

触发完成后自动回到 Caveman。

---

## 限制

- 极简回复不适合教程、文档生成、需要完整解释的场景
- 对英文效果最好；中文省略冠词的空间较小，效果约 50-60% 节省
- 不改变命令执行行为——只改变回复的文字量
