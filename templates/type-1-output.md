<!-- Type 1: 作品产出型 (Output) -->
<!-- 标杆：Guizang（产品画廊+适合/不适合）· Cailun（叙事痛点+命名仪式+六张截图）· Nuwa（Star History+多视角展示） -->
<!-- 核心手法：读者靠"看到"决定，不靠"读到" -->

<!-- ▸ 先放 hero.md 内容 -->

---

## 它解决什么问题
<!-- Cailun 手法：第二人称叙事，描述读者亲历过的 3 个挫败场景，最后一句粗体揭示答案 -->

你刚{{SCENARIO_1}}，想{{GOAL}}——

- {{PAIN_1_SECOND_PERSON_NARRATIVE}}
- {{PAIN_2_SECOND_PERSON_NARRATIVE}}
- {{PAIN_3_SECOND_PERSON_NARRATIVE}}

**{{ONE_SENTENCE_SOLUTION}}**

---

## {{EFFECT_SECTION_NAME}}
<!-- 命名用品牌隐喻（Cailun: "七种纸"；Guizang: "效果"） -->
<!-- 占首屏 40-60%。真实产出截图/GIF，不是文字描述 -->

<!-- Guizang 手法：在表格单元格里嵌入 <img> 缩略图，把 README 变成可浏览的产品画廊 -->
<!-- 🎨 制作方式（详见 ../references/visual-toolkit.md）：
     1. 有真实产出 → 直接截图放 assets/screenshots/
     2. 没有真实截图 → 用 huashu-design 生成效果图：
        「用 huashu-design 做一组产品截图画廊，展示 [产品名] 的 [N 种变体]，瑞士极简风，每张 800×600」
     3. 展示交互流程 → 用 huashu-design 做 GIF：
        「用 huashu-design 做一个动画 demo，展示从 [输入] 到 [输出] 的完整流程，导出 GIF」
     4. 后备方案 → 用对话示例代码块代替
-->
| {{VARIANT_1_NAME}} | {{VARIANT_2_NAME}} |
|:---:|:---:|
| <img src="assets/screenshots/{{IMG_1}}.png" width="400" alt="{{VARIANT_1_DESC}}"> | <img src="assets/screenshots/{{IMG_2}}.png" width="400" alt="{{VARIANT_2_DESC}}"> |
| {{VARIANT_1_DESC}} | {{VARIANT_2_DESC}} |

<!-- 没有截图时的后备：用完整对话示例代替，展示真实输入→输出 -->

---

## 适合 / 不适合
<!-- Guizang 独有手法：明确说"不适合"反而增强信任 -->

**✅ 适合：**
- {{FIT_1}}
- {{FIT_2}}

**❌ 不适合：**
- {{UNFIT_1}}
- {{UNFIT_2}}

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

## 使用流程
<!-- 品牌隐喻命名步骤（Cailun: 造纸三律；Baogong: 堂审四幕） -->

| 步骤 | 做什么 | 产出 |
|------|--------|------|
| **{{STEP_1_BRAND_NAME}}** | {{STEP_1_DESC}} | {{STEP_1_OUTPUT}} |
| **{{STEP_2_BRAND_NAME}}** | {{STEP_2_DESC}} | {{STEP_2_OUTPUT}} |
| **{{STEP_3_BRAND_NAME}}** | {{STEP_3_DESC}} | {{STEP_3_OUTPUT}} |

---

## 对话示例

```
User: "{{EXAMPLE_USER_INPUT}}"

Agent: "{{EXAMPLE_AGENT_RESPONSE}}"
```

---

## 交付物

| 产出 | 说明 |
|------|------|
| {{FORMAT_1}} | {{DESC_1}} |
| {{FORMAT_2}} | {{DESC_2}} |

---

## 更多示例
<!-- 至少 2 个，展示不同风格/场景 -->

### {{EXAMPLE_1_TITLE}}

{{EXAMPLE_1_CONTENT}}

### {{EXAMPLE_2_TITLE}}

{{EXAMPLE_2_CONTENT}}

---

## 局限性

- **{{LIM_1}}** — {{LIM_1_DESC}}
- **{{LIM_2}}** — {{LIM_2_DESC}}
- **{{LIM_3}}** — {{LIM_3_DESC}}

---

## {{ORIGIN_TITLE}}
<!-- Iron Law 8：2 句起源故事胜过 10 条功能列表 -->
<!-- "我做这个是因为 [痛点]。现有方案 [缺口]。" -->

{{ORIGIN_STORY}}

---

<details>
<summary><strong>开发文档</strong></summary>

{{DEV_DOCS}}

</details>

<!-- 有 star history 再加（Nuwa 手法）：
## Star History
[![Star History Chart](https://api.star-history.com/svg?repos={{ORG}}/{{REPO}}&type=Date)](https://star-history.com/#{{ORG}}/{{REPO}}&Date)
-->

---

<div align="center">

MIT License

</div>
