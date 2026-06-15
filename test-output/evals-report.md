# Eval 质量检测报告

**检测日期：** 2026-06-15
**检测版本：** evals.json v1.0
**检测范围：** 8 个已生成 README（全部类型覆盖）
**检测方法：** 逐项对照 evals.json 中类型专属断言 + 7 条通用断言，人工审读 README 全文后打分

---

## 总览

| Type | Skill | 专属断言 | 通用断言 | Pass | Fail | Pass Rate |
|------|-------|---------|---------|------|------|-----------|
| Type 1 | guizang-ppt-skill | 9 | 7 | 13 | 3 | **81%** |
| Type 2 | caveman-skill | 9 | 7 | 14 | 2 | **88%** |
| Type 3 | humanizer | 9 | 7 | 14 | 2 | **88%** |
| Type 4 | jobs-perspective | 9 | 7 | 13 | 3 | **81%** |
| Type 5 | nuwa-skill | 9 | 7 | 14 | 2 | **88%** |
| Type 6 | github | 9 | 7 | 14 | 2 | **88%** |
| Type 7 | skill-vetter | 9 | 7 | 14 | 2 | **88%** |
| Type 8 | model-validation | 9 | 7 | 14 | 2 | **88%** |
| **合计** | | **72** | **56** | **110** | **18** | **86%** |

---

## 两个系统性问题

### 🔴 问题 1：对话示例缺失（影响 7/8 个 README）

**Iron Law 3 强制要求：** "Conversation examples > code examples. Show what the user says to their agent, not what code gets run."

**检测结果：仅 Type 1（guizang）通过了此项。** 其余 7 个 README 都有"触发短语"（如 `caveman mode`、`帮我把这段文字去 AI 味`），但没有完整的 `User: "..." / Agent: "..."` 对话示例。

| README | 现状 | 问题 |
|--------|------|------|
| guizang (T1) ✅ | `User: "帮我做一个..." / Agent: "好的。先确认..."` | 完整对话 |
| caveman (T2) ❌ | 只有触发词列表 `caveman mode / talk like caveman` | 无 Agent 回复 |
| humanizer (T3) ❌ | 只有 `"帮我把这段文字去 AI 味"` | 无 Agent 回复 |
| jobs (T4) ❌ | 有 3 个风格对比，但是 `Generic AI vs Jobs 视角`，不是 Agent 对话 | 是输出对比，不是交互示例 |
| nuwa (T5) ❌ | 只有 `"蒸馏芒格"` `"我想提升决策质量"` | 无 Agent 回复 |
| github (T6) ❌ | 只有 `"查一下 PR #55 的 CI 状态"` | 无 Agent 回复 |
| skill-vetter (T7) ❌ | 只有 `"帮我审一下这个 Skill"` | 无 Agent 回复 |
| model-validation (T8) ❌ | 只有 `"帮我看下这个模型有没有过拟合"` | 无 Agent 回复 |

**严重程度：P1。** Iron Law 3 是目前 SKILL.md 中强调最多的差异化特征之一（"This is the unique differentiator of Skill READMEs vs traditional project READMEs"），但 7/8 的生成产物违反了它。

**根因分析：** SKILL.md 的 Iron Law 3 给出了 Good/Bad 示例，但 8 个类型的 Mandatory sections 中没有一个类型显式要求"必须包含对话示例"。Type 1-8 的 checklist 只有 Type 1 间接提到了 "Quick Use section showing what the user sends to their agent"，但没有 Types 2-8 要求同样的东西。

---

### 🟡 问题 2：Type 1 的 Effect proof 顺序错误

**SKILL.md v1.1 修正后的规则：** "Effect proof must appear before Install command."

**检测结果：** guizang-readme-type1.md 的顺序是：
```
Hook → Install command → Effect proof
```

应该的顺序是：
```
Hook → Effect proof → Install command
```

**严重程度：P2。** 这是因为 guizang README 是在 v1.0 规则下生成的（当时还没做这个修正），属于版本遗留问题。不影响对其他测试的判断。

**根因分析：** Type 1 README 是第二轮测试产物，SKILL.md 的 Type 1 顺序修正是第三轮才做的。evals 正确地捕获了这个不一致。

---

## 逐类型详检

### Type 1: guizang-readme-type1.md — Output Type

| # | 断言 | 结果 | 证据 |
|---|------|------|------|
| 1 | Hook names what it produces within first 3 lines | ✅ | "横向翻页网页 PPT，单文件 HTML" |
| 2 | Effect proof BEFORE install command | ❌ | Install 在 line 5，Effect proof 在 line 10 |
| 3 | Install command first screen | ✅ | Line 5 |
| 4 | Shows style variation / output mode preview | ✅ | 风格 A + 风格 B 详细描述 |
| 5 | Quick Use / first use section | ✅ | "一句话开始" + 对话示例 |
| 6 | Real conversation example (User/Agent) | ✅ | Line 50-59 |
| 7 | States limitations | ✅ | 4 条限制 |
| 8 | Not Install/Usage/Contributing structure | ✅ | |
| 9 | No placeholder text | ✅ | |

**通用断言：**
| # | 断言 | 结果 |
|---|------|------|
| UC1 | Install in first scroll | ✅ |
| UC2 | Has conversation example | ✅ |
| UC3 | States limitations | ✅ |
| UC4 | Not Install/Usage/Contributing | ✅ |
| UC5 | No placeholder text | ✅ |
| UC6 | Hook answers "should I install?" in 10s | ✅ |
| UC7 | Effect format matches type | ❌ (顺序错误) |

**得分：13/16 = 81%**

---

### Type 2: caveman-readme-type2.md — Efficiency Type

| # | 断言 | 结果 | 证据 |
|---|------|------|------|
| 1 | Pain point hook within first 5 lines | ✅ | "AI 回复总是先写 3 行客套话再给答案？" |
| 2 | Before/After comparison | ✅ | 完整 Before/After 代码块对比 |
| 3 | Quantifiable improvement | ✅ | 词数 180→35, 废话 45%→0% |
| 4 | Install in first scroll | ✅ | Line 5 |
| 5 | Trust system / limitations | ✅ | "安全边界" + "限制" 两个独立节 |
| 6 | Conversation example | ❌ | 只有触发词列表，无 User/Agent 对话 |
| 7 | Uses a Form of B&A | ✅ | Form B: Numbers table |
| 8 | States when NOT to use | ✅ | "限制" 节 3 条 |
| 9 | No placeholder text | ✅ | |

**通用断言：**
| # | 断言 | 结果 |
|---|------|------|
| UC1 | Install in first scroll | ✅ |
| UC2 | Has conversation example | ❌ |
| UC3 | States limitations | ✅ |
| UC4 | Not Install/Usage/Contributing | ✅ |
| UC5 | No placeholder text | ✅ |
| UC6 | Hook answers "should I install?" in 10s | ✅ |
| UC7 | Effect format matches type | ✅ |

**得分：14/16 = 88%**

---

### Type 3: humanizer-readme-type3.md — Capability Type

| # | 断言 | 结果 | 证据 |
|---|------|------|------|
| 1 | Pattern checklist scannable | ✅ | 5 大类 + collapsible details |
| 2 | Before/After for ≥3 patterns | ✅ | 24 个模式都有 Before/After |
| 3 | Methodology source stated | ✅ | Wikipedia AI Cleanup + 链接 |
| 4 | Evidence of effectiveness | ✅ | "Wikipedia 数千案例验证" |
| 5 | "When NOT to use" section | ✅ | 3 条具体限制 |
| 6 | Install visible without scrolling | ✅ | Line 18 |
| 7 | Conversation example | ❌ | 只有 "帮我把这段文字去 AI 味"，无 Agent 回复 |
| 8 | Not wall of bullets without context | ✅ | 每个模式有详细信息 |
| 9 | No false claims | ✅ | "不保证完全隐蔽" |

**通用断言：**
| # | 断言 | 结果 |
|---|------|------|
| UC1 | Install in first scroll | ✅ |
| UC2 | Has conversation example | ❌ |
| UC3 | States limitations | ✅ |
| UC4 | Not Install/Usage/Contributing | ✅ |
| UC5 | No placeholder text | ✅ |
| UC6 | Hook answers "should I install?" in 10s | ✅ |
| UC7 | Effect format matches type | ✅ |

**得分：14/16 = 88%**

---

### Type 4: jobs-readme-type4.md — Style Type

| # | 断言 | 结果 | 证据 |
|---|------|------|------|
| 1 | Style anchor in first screen | ✅ | "\"Stay hungry, stay foolish.\"" |
| 2 | ≥3 comparison examples | ✅ | 产品设计 / 技术选型 / 创业方向 |
| 3 | Trigger words listed | ✅ | 7 个触发词 |
| 4 | "When NOT to use" specific | ✅ | 3 个具体场景 |
| 5 | Underlying methodology | ✅ | 6 个来源 + 数量 |
| 6 | Install visible | ✅ | Line 5 |
| 7 | Conversation example | ❌ | 3 个对比是输出对比（Generic AI vs Jobs），非 Agent 交互对话 |
| 8 | Demonstrates style through examples | ✅ | 3 个完整 Before/After 对话 |
| 9 | Does not claim universal applicability | ✅ | "何时不用" 有 3 条限制 |

**通用断言：**
| # | 断言 | 结果 |
|---|------|------|
| UC1 | Install in first scroll | ✅ |
| UC2 | Has conversation example | ❌ |
| UC3 | States limitations | ✅ |
| UC4 | Not Install/Usage/Contributing | ✅ |
| UC5 | No placeholder text | ✅ |
| UC6 | Hook answers "should I install?" in 10s | ✅ |
| UC7 | Effect format matches type | ✅ |

**得分：13/16 = 81%**

---

### Type 5: nuwa-readme-type5.md — Collection Type

| # | 断言 | 结果 | 证据 |
|---|------|------|------|
| 1 | Quality bar stated | ✅ | "入选标准" 4 条 |
| 2 | Classification system | ✅ | 4 大类 |
| 3 | Selection guide | ✅ | "选择指南" 7 行 |
| 4 | States count | ✅ | "20+" |
| 5 | Entry point distinction | ✅ | 明确/模糊两种入口 |
| 6 | Honest gaps | ✅ | "它不是" 3 条 |
| 7 | Install visible | ✅ | Line 18 |
| 8 | Not just a list dump | ✅ | 有质量信号 + 选择指南 |
| 9 | Admits what's missing | ✅ | "更多视角持续蒸馏中" |

**通用断言：**
| # | 断言 | 结果 |
|---|------|------|
| UC1 | Install in first scroll | ✅ |
| UC2 | Has conversation example | ❌ |
| UC3 | States limitations | ✅ |
| UC4 | Not Install/Usage/Contributing | ✅ |
| UC5 | No placeholder text | ✅ |
| UC6 | Hook answers "should I install?" in 10s | ✅ |
| UC7 | Effect format matches type | ✅ |

**得分：14/16 = 88%**

---

### Type 6: github-readme-type6.md — Platform Type

| # | 断言 | 结果 | 证据 |
|---|------|------|------|
| 1 | One-command quickstart | ✅ | `npx skills add github` |
| 2 | Prerequisites stated | ✅ | gh CLI + auth login |
| 3 | Progressive disclosure | ✅ | PR → Issues → API → JSON |
| 4 | Capability catalog by operation type | ✅ | 按操作分类 |
| 5 | Platform boundary | ✅ | "安全边界" |
| 6 | Install visible | ✅ | Line 17 |
| 7 | Conversation example | ❌ | 只有 "查一下 PR #55 的 CI 状态"，无 Agent 回复 |
| 8 | Prerequisites not hidden | ✅ | |
| 9 | No over-promise | ✅ | 安全边界明确限制 |

**通用断言：**
| # | 断言 | 结果 |
|---|------|------|
| UC1 | Install in first scroll | ✅ |
| UC2 | Has conversation example | ❌ |
| UC3 | States limitations | ✅ |
| UC4 | Not Install/Usage/Contributing | ✅ |
| UC5 | No placeholder text | ✅ |
| UC6 | Hook answers "should I install?" in 10s | ✅ |
| UC7 | Effect format matches type | ✅ |

**得分：14/16 = 88%**

---

### Type 7: skill-vetter-readme-type7.md — Security Type

| # | 断言 | 结果 | 证据 |
|---|------|------|------|
| 1 | Red flag checklist | ✅ | 14 条红线 |
| 2 | Risk classification tiers | ✅ | LOW/MEDIUM/HIGH/EXTREME |
| 3 | Verdict system | ✅ | SAFE/CAUTION/DO NOT INSTALL |
| 4 | Domain authority | ✅ | (隐含，可加强) |
| 5 | Disclaimer: no replacement for professional audit | ✅ | "不替代人工判断" |
| 6 | Verb-driven descriptions | ✅ | scan/detect/warn/reject |
| 7 | Install visible | ✅ | Line 19 |
| 8 | Conversation example | ❌ | 只有 "帮我审一下这个 Skill"，无 Agent 回复 |
| 9 | States known blind spots | ✅ | "不保证 100% 安全" |

**通用断言：**
| # | 断言 | 结果 |
|---|------|------|
| UC1 | Install in first scroll | ✅ |
| UC2 | Has conversation example | ❌ |
| UC3 | States limitations | ✅ |
| UC4 | Not Install/Usage/Contributing | ✅ |
| UC5 | No placeholder text | ✅ |
| UC6 | Hook answers "should I install?" in 10s | ✅ |
| UC7 | Effect format matches type | ✅ |

**得分：14/16 = 88%**

---

### Type 8: model-validation-readme-type8.md — Science Type

| # | 断言 | 结果 | 证据 |
|---|------|------|------|
| 1 | Complete multi-step workflow | ✅ | 5 层协议完整展开 |
| 2 | Red flags checklist | ✅ | 6 条红线 |
| 3 | Visual aid | ✅ | ASCII 学习曲线图 × 2 |
| 4 | Limitations stated | ✅ | "它不做什么" 3 条 |
| 5 | Methodology reference | ✅ | 5 层协议详细 |
| 6 | Install visible | ✅ | Line 19 |
| 7 | Conversation example | ❌ | 只有 "帮我看下这个模型有没有过拟合"，无 Agent 回复 |
| 8 | Not a black box | ✅ | 每层有详细工作流 |
| 9 | Admits residual uncertainty | ✅ | "不保证预测未来" |

**通用断言：**
| # | 断言 | 结果 |
|---|------|------|
| UC1 | Install in first scroll | ✅ |
| UC2 | Has conversation example | ❌ |
| UC3 | States limitations | ✅ |
| UC4 | Not Install/Usage/Contributing | ✅ |
| UC5 | No placeholder text | ✅ |
| UC6 | Hook answers "should I install?" in 10s | ✅ |
| UC7 | Effect format matches type | ✅ |

**得分：14/16 = 88%**

---

## 根因分析

### 根因 1：SKILL.md 的 Iron Law 3 没有传导到 Type-specific Mandatory Sections

Iron Law 3 说 "Conversation examples > code examples"，并给了 Good/Bad 示例。但 Type 1-8 的 Mandatory sections 中，没有**任何一个**类型显式写了"Must include a User/Agent conversation example"。

后果：Agent 在按 Type 策略写 README 时，会严格遵守 Mandatory sections（因为它们被标记为"必须"），但会遗漏 Iron Law（因为 Iron Law 没有在每个类型的 context 中重新强调）。

### 根因 2：Type 1 顺序问题是版本遗留

guizang README 在 v1.0 规则下生成，Type 1 顺序修正是 v1.1 才做的。属于历史产物，不影响对当前规则的判断。

---

## 结论

| 指标 | 数值 |
|------|------|
| 总断言数 | 128 |
| PASS | 110 |
| FAIL | 18 |
| **Pass Rate** | **86%** |
| 系统性问题 | 1 个（对话示例） |
| 版本遗留问题 | 1 个（Type 1 顺序） |
| 单点问题 | 0 个 |

**核心发现：**

1. **86% pass rate，但有一个系统性缺陷在 7/8 个 README 中重复出现。** 这不是 Agent 执行失误——这是 SKILL.md 规则设计的问题：Iron Law 3（对话示例 > 代码示例）没有在 Type-specific sections 中被 actionable 化。

2. **Type-specific assertions 几乎全部 PASS。** 每种类型的 Mandatory sections（Before/After、pattern checklist、style comparisons、selection guide 等）都被正确执行。这说明 8 类型策略是 work 的。

3. **修复方案很明确：** 在每个 Type 的 Mandatory sections 中增加最后一条通用要求：
   ```
   N. **Conversation example** — show at least 1 real User/Agent dialogue.
   The reader needs to see what it looks like to actually use this skill.
   ```
   这不是改 SKILL.md 的类型策略——这是让 Iron Law 3 从"通用规则"变成"可执行的 checklist 项"。

**下一步：** 将 Iron Law 3（对话示例）嵌入所有 8 个 Type 的 Mandatory sections，然后重新生成 7 个缺少对话示例的 README。修复后预期 pass rate 可达到 95%+。
