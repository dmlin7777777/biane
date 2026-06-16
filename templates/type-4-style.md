<!-- Type 4: 风格/视角型 (Style) -->
<!-- 标杆：Nuwa（多视角对话：Naval/Musk/Jobs）· Colleague（19.4K⭐ 情感钩子+多源蒸馏） -->
<!-- 核心手法：读者靠"感受"决定——同一 prompt 的两种输出，差异不用解释就能体会 -->

<!-- ▸ 先放 hero.md 内容 -->

---

## 风格锚点
<!-- 一句话 IN the style 本身，不是描述 style -->
<!-- ✅ Colleague: "Clean code isn't about following rules — it's about respecting the humans who'll read it next." -->
<!-- ❌ "这个 skill 会让你的文字更有情感" -->

> {{STYLE_ANCHOR_IN_THE_STYLE_ITSELF}}

---

## 对比示例
<!-- 同一 prompt → 通用输出 vs 风格输出，至少 3 组 -->
<!-- 用真实 prompt（读者会实际用的），不用玩具示例 -->
<!-- Nuwa 手法：多视角展示——同一话题，不同角色/风格如何处理 -->
<!-- 🎨 升级方式（详见 ../references/visual-toolkit.md）：
     风格型的文字本身是产品，但排版能放大感受差异：
     1. 用 huashu-design 做对比卡片（左右分栏，通用=灰色/朴素，风格=品牌色/精排版）
     2. 长文本对比 → 用 huashu-design 做杂志风排版截图，比 markdown 表格更直观
     3. 多视角展示 → 用 huashu-design 做人物卡片（Nuwa: Naval/Musk/Jobs 各一张卡）
     4. 后备 → markdown 表格已经够用，风格型最不依赖视觉
-->

### 示例 1

**Prompt:** {{REALISTIC_PROMPT_1}}

| 通用输出 | {{STYLE_NAME}} |
|---------|---------------|
| {{GENERIC_1}} | {{STYLED_1}} |

> **差异点：** {{ANNOTATION_1_EXPLAIN_WHY_NOT_JUST_WHAT}}

### 示例 2

**Prompt:** {{REALISTIC_PROMPT_2}}

| 通用输出 | {{STYLE_NAME}} |
|---------|---------------|
| {{GENERIC_2}} | {{STYLED_2}} |

> **差异点：** {{ANNOTATION_2}}

### 示例 3

**Prompt:** {{REALISTIC_PROMPT_3}}

| 通用输出 | {{STYLE_NAME}} |
|---------|---------------|
| {{GENERIC_3}} | {{STYLED_3}} |

> **差异点：** {{ANNOTATION_3}}

<!-- 差异注释要解释 WHY（为什么这样更好），不只是 WHAT（哪里不同） -->

---

## 触发方式
<!-- 什么词/句式会激活这个风格 -->

{{TRIGGER_PHRASES}}

---

## 快速开始

```bash
npx skills add {{ORG}}/{{REPO}}
```

> 安装后对 Agent 说：「{{FIRST_USE_INSTRUCTION}}」

---

## 对话示例

```
User: "{{EXAMPLE_USER_INPUT}}"

Agent: "{{EXAMPLE_AGENT_RESPONSE_IN_STYLE}}"
```

---

## 方法论
<!-- 风格的来源、原理、框架。建立学术可信度 -->
<!-- Colleague 手法：多数据源蒸馏——列出所有参考来源 -->
<!-- 简单风格可融入风格锚点；多源蒸馏型独立成节 -->

{{METHODOLOGY_SOURCES_AND_PRINCIPLES}}

---

## 什么时候不该用
<!-- 风格型最容易过度应用。明确边界 -->

- {{BOUNDARY_1}}
- {{BOUNDARY_2}}
- {{BOUNDARY_3}}

---

## {{ORIGIN_TITLE}}

{{ORIGIN_STORY}}

---

<div align="center">

MIT License

</div>
