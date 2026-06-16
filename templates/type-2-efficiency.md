<!-- Type 2: 提效/流程型 (Efficiency) -->
<!-- 标杆：Luban（反问共情+数字轰炸+态度列+"实战战绩"）· Paoding（痛点场景+对称句式+零API）· Karpathy（176K⭐ 极简：纯问题→规则映射） -->
<!-- 核心手法：读者靠"对比"决定——看到改善幅度才安装 -->

<!-- ▸ 先放 hero.md 内容 -->

---

## 它解决什么问题
<!-- Cailun/Luban 共享手法：第二人称叙事 + 3 个痛点 + 粗体揭示 -->

{{RHETORICAL_QUESTION_OR_SCENARIO}}

- {{PAIN_1_SECOND_PERSON}}
- {{PAIN_2_SECOND_PERSON}}
- {{PAIN_3_SECOND_PERSON}}

**{{ONE_SENTENCE_SOLUTION}}**

---

## Before / After
<!-- 整个 README 最重要的一节。选对形式：-->

<!-- 形式 A：并排表（默认，最强可扫描性） -->
| 维度 | Before | After |
|:----:|:------:|:-----:|
| **{{DIM_1}}** | {{BEFORE_1}} | {{AFTER_1}} |
| **{{DIM_2}}** | {{BEFORE_2}} | {{AFTER_2}} |
| **{{DIM_3}}** | {{BEFORE_3}} | {{AFTER_3}} |
| **{{DIM_4}}** | {{BEFORE_4}} | {{AFTER_4}} |

<!-- 形式 B：数字表（量化改善最直观）
| 指标 | 之前 | 之后 | 节省 |
|------|------|------|------|
| {{METRIC_1}} | {{FROM_1}} | {{TO_1}} | {{SAVE_1}} |
-->

<!-- 形式 C：竞品对比（Luban 手法）
| 维度 | 传统方式 | {{SKILL_NAME}} |
|------|---------|---------------|
| {{DIM}} | {{OLD}} | {{NEW}} |
-->

<!-- ❌ 避免：上下顺序排列无视觉分隔——读者无法对比看不到的东西 -->

<!-- 🎨 升级方式（详见 ../references/visual-toolkit.md）：
     文字表格只是及格线。更强的 B/A 展示：
     1. 信息图 → 用 huashu-design：「做一张 Before/After 对比信息图，左边 [旧方式] 右边 [新方式]，并排布局，用红绿色差」
     2. 截图 diff → 真实截图标注差异（红框/箭头）
     3. GIF → 操作录屏：旧方式 10 步 vs 新方式 2 步，速度对比
     4. 流程图 → 用 excalidraw-diagram 画旧流程 vs 新流程
-->

---

## 它会交付什么
<!-- Luban 手法：3 个粗体交付物 + em-dash 说明 -->

- **{{DELIVERABLE_1}}** — {{DELIVERABLE_1_DESC}}
- **{{DELIVERABLE_2}}** — {{DELIVERABLE_2_DESC}}
- **{{DELIVERABLE_3}}** — {{DELIVERABLE_3_DESC}}

---

## 快速开始

```bash
npx skills add {{ORG}}/{{REPO}}
```

> 安装后对 Agent 说：「{{FIRST_USE_INSTRUCTION}}」

<details>
<summary>其他安装方式</summary>

```bash
git clone https://github.com/{{ORG}}/{{REPO}}.git ~/.claude/skills/{{SKILL_NAME}}
```

</details>

---

## 对话示例

```
User: "{{EXAMPLE_USER_INPUT}}"

Agent: "{{EXAMPLE_AGENT_RESPONSE}}"
```

---

## {{PROCESS_SECTION_NAME}}
<!-- 品牌隐喻命名（Luban: "五个动作"；Baogong: "堂审四幕"） -->

<!-- Luban 精髓手法：第三列"一句狠话"——给每步加态度/哲学，流程表变人格宣言 -->
| 步骤 | 做什么 | 一句狠话 |
|------|--------|---------|
| **{{STEP_1_BRAND}}** | {{STEP_1_DESC}} | {{STEP_1_ATTITUDE}} |
| **{{STEP_2_BRAND}}** | {{STEP_2_DESC}} | {{STEP_2_ATTITUDE}} |
| **{{STEP_3_BRAND}}** | {{STEP_3_DESC}} | {{STEP_3_ATTITUDE}} |

<!-- 没有品牌态度时去掉第三列，用 Output 列替代 -->

---

## 实战战绩
<!-- Luban 手法：具体案例 + 真实数字，不是"大幅提升" -->
<!-- 示例："在 83,725 条数据的项目中，8 天流水线故障 → 2 小时修复" -->

{{BATTLE_RECORD_WITH_NUMBERS}}

---

## 安全边界
<!-- 提效型最需要信任系统——读者问"它会不会搞坏我的东西" -->

- **会做：** {{WILL_DO}}
- **不会做：** {{WILL_NOT_DO}}
- **强制停手点：** {{HARD_STOP}}

---

## 局限性

- **{{LIM_1}}** — {{LIM_1_DESC}}
- **{{LIM_2}}** — {{LIM_2_DESC}}
- **{{LIM_3}}** — {{LIM_3_DESC}}

---

## {{ORIGIN_TITLE}}

{{ORIGIN_STORY}}

---

<details>
<summary><strong>开发文档</strong></summary>

{{DEV_DOCS}}

</details>

---

<div align="center">

MIT License

</div>
