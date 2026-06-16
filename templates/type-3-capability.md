<!-- Type 3: 能力增强型 (Capability) -->
<!-- 标杆：Humanizer（33模式×B/A表=自证型参考卡片）· Code-Review（四阶段流程图+严重度颜色编码）· AddyOsmani（借口→反驳表+生命周期组织） -->
<!-- 核心手法：模式清单本身就是推销——读者扫一遍就知道自己需不需要 -->

<!-- ▸ 先放 hero.md 内容 -->

---

## {{CAPABILITY_GAP_TITLE}}
<!-- 没有这个 skill，agent 具体做不到什么 -->

{{CAPABILITY_GAP}}

---

## {{PATTERN_COUNT}} Patterns
<!-- Humanizer 精髓手法：每个模式一行 Before/After，整个表格=自证型产品演示 -->
<!-- 读者不需要截图——文字本身就是产品 -->

### {{CATEGORY_1}}

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 1 | **{{PATTERN_1}}** | {{BEFORE_1}} | {{AFTER_1}} |
| 2 | **{{PATTERN_2}}** | {{BEFORE_2}} | {{AFTER_2}} |
| 3 | **{{PATTERN_3}}** | {{BEFORE_3}} | {{AFTER_3}} |

### {{CATEGORY_2}}

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 4 | **{{PATTERN_4}}** | {{BEFORE_4}} | {{AFTER_4}} |
| 5 | **{{PATTERN_5}}** | {{BEFORE_5}} | {{AFTER_5}} |

### {{CATEGORY_3}}

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 6 | **{{PATTERN_6}}** | {{BEFORE_6}} | {{AFTER_6}} |
| 7 | **{{PATTERN_7}}** | {{BEFORE_7}} | {{AFTER_7}} |

<!-- 模式数量就是说服力：33 > 10 > 3。列全，分类清 -->
<!-- 🎨 升级方式（详见 ../references/visual-toolkit.md）：
     纯文字 B/A 表是及格线。更强的能力展示：
     1. 用 huashu-design 做模式分类信息图（类别色块+模式数量+代表性 B/A）
     2. 覆盖矩阵 → 用 excalidraw-diagram 画生命周期覆盖图（code-review 手法：颜色编码严重度）
     3. 完整示例 → 用 huashu-design 做 diff 可视化（红删绿加，比引用块直观）
     4. 后备 → Mermaid 流程图展示模式检测流程
-->

---

## 完整示例
<!-- Humanizer 手法：一段完整的 Before 文本 → 完整的 After 文本 -->
<!-- 模式表是"逐条看"，这里是"整体感受" -->

**Before:**
> {{FULL_BEFORE_TEXT}}

**After:**
> {{FULL_AFTER_TEXT}}

---

## 覆盖矩阵
<!-- 多领域/多阶段时用。Code-Review 手法：生命周期阶段 × 覆盖状态 -->
<!-- AddyOsmani 手法：按开发生命周期组织而非按技术栈 -->

| {{LIFECYCLE_STAGE}} | 覆盖 | 说明 |
|---------------------|:----:|------|
| {{STAGE_1}} | ✅ | {{STAGE_1_DESC}} |
| {{STAGE_2}} | ✅ | {{STAGE_2_DESC}} |
| {{STAGE_3}} | ⚠️ | {{STAGE_3_DESC}} |
| {{STAGE_4}} | ❌ | {{STAGE_4_DESC}} |

---

## 快速开始

```bash
npx skills add {{ORG}}/{{REPO}}
```

> 安装后对 Agent 说：「{{ACTIVATION_INSTRUCTION}}」

<!-- 能力型必须说明"怎么知道它在工作" -->
**验证方式：** {{HOW_TO_VERIFY}}

---

## 对话示例

```
User: "{{EXAMPLE_USER_INPUT}}"

Agent: "{{EXAMPLE_AGENT_RESPONSE}}"
```

---

## 局限性

- **{{LIM_1}}** — {{LIM_1_DESC}}
- **{{LIM_2}}** — {{LIM_2_DESC}}

---

## {{ORIGIN_TITLE}}

{{ORIGIN_STORY}}

---

<details>
<summary><strong>开发文档</strong></summary>

{{DEV_DOCS}}

</details>

<!-- Humanizer 手法：版本历史内嵌 README，反向时间序 + 模式计数 -->
<!-- 有持续迭代的 skill 加这节：
## 版本历史
| 版本 | 日期 | 变更 |
|------|------|------|
| v{{X}} | {{DATE}} | {{CHANGE}} ({{PATTERN_COUNT}} patterns) |
-->

---

<div align="center">

MIT License

</div>
