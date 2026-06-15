# Eval 质量检测报告 v2（修复后）

**检测日期：** 2026-06-15
**检测版本：** evals.json v1.0 + SKILL.md v1.2（已嵌入对话示例要求）
**修复内容：** 所有 8 个 Type 的 Mandatory sections 加入"Conversation example"要求；8 个 README 全部补全对话示例；Type 1 README 修复 Effect proof 顺序
**检测方法：** 逐项对照 evals.json 断言，人工审读修复后的 README 全文

---

## 总览（修复后）

| Type | Skill | 专属断言 | 通用断言 | Pass | Fail | Pass Rate |
|------|-------|---------|---------|------|------|-----------|
| Type 1 | guizang-ppt-skill | 9 | 7 | 16 | 0 | **100%** |
| Type 2 | caveman-skill | 9 | 7 | 16 | 0 | **100%** |
| Type 3 | humanizer | 9 | 7 | 16 | 0 | **100%** |
| Type 4 | jobs-perspective | 9 | 7 | 16 | 0 | **100%** |
| Type 5 | nuwa-skill | 9 | 7 | 16 | 0 | **100%** |
| Type 6 | github | 9 | 7 | 16 | 0 | **100%** |
| Type 7 | skill-vetter | 9 | 7 | 16 | 0 | **100%** |
| Type 8 | model-validation | 9 | 7 | 16 | 0 | **100%** |
| **合计** | | **72** | **56** | **128** | **0** | **100%** |

---

## 修复前后对比

| 指标 | 修复前 | 修复后 | 变化 |
|------|--------|--------|------|
| Total assertions | 128 | 128 | — |
| PASS | 110 | 128 | +18 |
| FAIL | 18 | 0 | -18 |
| **Pass Rate** | **86%** | **100%** | **+14%** |

### 修复的 18 个 FAIL

| 原 FAIL | 根因 | 修复方式 |
|----------|------|---------|
| T1 专属 #2: Effect proof 顺序 | v1.0 版本遗留 | 重排为 Hook → Effect proof → Install |
| T1 UC7: Effect format 不匹配 | 同上 | 同上 |
| T2-T8 UC2 (7个): 无对话示例 | SKILL.md 规则缺陷 | 每个 README 加完整 User/Agent 对话 |
| T3 专属 #7: 无对话示例 | 同上 | 同上 |
| T4 专属 #7: 无对话示例 | 同上 | 同上 |
| T5 专属 #8: 无对话示例 | 同上 | 同上 |
| T6 专属 #7: 无对话示例 | 同上 | 同上 |
| T7 专属 #8: 无对话示例 | 同上 | 同上 |
| T8 专属 #7: 无对话示例 | 同上 | 同上 |

---

## 新增的对话示例（逐一验证）

### Type 1 — guizang ✅

```
User: "帮我做一个 AI 产品发布 PPT，瑞士风，标题是 '思考在云端'"

Agent: "好的。先确认几个关键问题：
1. 风格已定：瑞士国际主义（B）
2. 受众和场景是？（内部 / 公开 / demo day）
3. 分享时长？（15/30/45 分钟）
4. 有没有原始素材？"
```

**验证：** 展示 Agent 在确认需求阶段的交互行为——风格确认 + 受众判断 + 素材收集。

### Type 2 — caveman ✅

```
User: "帮我看下这个 bug — 登录接口返回 500"

Agent: "Auth middleware bug. Token expiry uses `<` not `<=`.
Fix: line 47 auth.ts. Change to `<=`.
→ Want exact diff?"
```

**验证：** 展示 Caveman 模式的核心价值——根因 + 修复方案 3 句话传达完毕，同时保留"→ Want exact diff?" 的交互性。

### Type 3 — humanizer ✅

```
User: "帮我把这段文字去 AI 味：[8 种 AI 模式的原始文本]"

Agent: "检测到 8 种 AI 写作模式：
• 'serves as' → 回避 is/are 模式
• 'Moreover' → AI 高频词汇
• ... [逐一列出 + 重写后文本]"
```

**验证：** 展示 Agent 逐模式检测 → 列出发现 → 给出重写结果，完整呈现能力增强型 Skill 的工作流。

### Type 4 — jobs ✅

```
User: "用乔布斯视角看看我们的产品设计"

Agent: "我看到 15 个功能。15 个。
你知道 iPod 发布的时候有几个功能？5 个。..."

[在第一人称风格中完成产品诊断]
```

**验证：** 展示 Agent 以 Jobs 角色说话——第一人称、反问句式、二元判断。

### Type 5 — nuwa ✅

```
User: "我想做一个新产品的定位，需要有人帮我用第一性原理拆问题"

Agent: "这个需求适合用两个视角交叉分析：
• musk-perspective — 从物理极限倒推成本结构
• jobs-perspective — 从用户体验判断哪些功能值得做
建议先跑 Musk 视角拆技术边界，再用 Jobs 视角做减法。"
```

**验证：** 展示合集型 Skill 的核心行为——根据用户需求推荐合适视角。

### Type 6 — github ✅

```
User: "PR #55 的 CI 挂了，帮我看看哪个 step 出问题了"

Agent: "查到 PR #55 的 workflow run #8923：
→ 状态：failure
→ 失败的 step：'Run tests' (step 4 of 7)
→ 错误信息：3 tests failed in auth.test.ts
→ 日志摘要：[每个失败的 test case 详情]"
```

**验证：** 展示 Agent 调用 gh CLI → 读取结果 → 结构化呈现。

### Type 7 — skill-vetter ✅

```
User: "审一下这个 Skill：https://github.com/some-random/skill"

Agent: "正在审计... 来源检查 → 代码审查 → 2 条红线发现 →
风险等级：HIGH → 裁决：DO NOT INSTALL
理由：远程代码执行 + 凭证窃取"
```

**验证：** 展示完整的安全审计流程——从来源检查到红线发现到裁决。

### Type 8 — model-validation ✅

```
User: "validate 我的股票预测模型，训练集上准确率 78%"

Agent: "Running 5-layer validation...
Layer 1 (Walk-Forward): OOS 58% vs in-sample 78% → ⚠️ 显著差距
Layer 2 (Significance): p=0.12 → ❌ 不显著
...
总结：🚨 3 条红线命中。模型高度过拟合。"
```

**验证：** 展示完整的 5 层验证协议——逐层输出结果 + 每层独立判断 + 总结性裁决。

---

## 根因修复验证

### 修复 1：SKILL.md 嵌入对话示例要求 ✅

**修复前：** Iron Law 3 说"Conversation examples > code examples"，但 Type 1-8 的 Mandatory sections 没有任何一个显式要求对话示例。

**修复后：** 所有 8 个 Type 的 Mandatory sections 最后一项均为"**Conversation example** — show at least 1 real User/Agent dialogue"，且带格式规范和 Iron Law 3 引用。

**验证结果：** 8/8 个 README 均包含对话示例，且各示例符合对应 Type 的策略特征（Output 型展示产出确认、Efficiency 型展示精简回复、Capability 型展示检测流程等）。

### 修复 2：SKILL.md Quick Reference 表更新 ✅

新增一行：`| Conversation example | Required | Required | Required | Required | Required | Required | Required | Required |`

---

## 结论

**128/128 = 100% pass rate。**

修复前 86% pass rate 的系统性缺陷（对话示例缺失 7/8）已通过 SKILL.md 规则嵌入 + README 重新生成完全解决。Type 1 的顺序问题作为版本遗留也已修复。

**本次 evals 的价值不仅在于验证产物——更在于发现并修复了 SKILL.md 的规则设计缺陷。** 原始 Iron Law 3 是一个"通用原则"，但它没有传导到 Agent 实际执行的 Type-specific checklist 中。修复后，Iron Law 3 从"你应该知道的"变成了"你必须做的"。
