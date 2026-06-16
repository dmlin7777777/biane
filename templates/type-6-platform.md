<!-- Type 6: 平台/工具型 (Platform) -->
<!-- 标杆：vercel-labs/skills（npx 一行上手+渐进披露）· daymade（1.2K⭐ marketplace-as-README：每 skill 配 GIF demo 卡片）· agent-sandbox（难度分级 starter prompts） -->
<!-- 核心手法：一条命令复制粘贴能跑=信任建立完成。之后是渐进披露 -->

<!-- ▸ 先放 hero.md 内容 -->

---

## 30 秒开始
<!-- 首屏必须有一条能直接跑的命令（Guizang/Vercel 手法） -->
<!-- "How to use" 在 "What is this" 之前 -->

```bash
{{ONE_COMMAND_QUICKSTART}}
```

---

## 安装方式
<!-- 按简单到复杂排列 -->

### {{METHOD_1}} (推荐)

```bash
{{INSTALL_CMD_1}}
```

### {{METHOD_2}}

```bash
{{INSTALL_CMD_2}}
```

<details>
<summary>{{METHOD_3}}</summary>

```bash
{{INSTALL_CMD_3}}
```

</details>

---

## 核心命令

| 命令 | 说明 |
|------|------|
| `{{CMD_INSTALL}}` | {{CMD_INSTALL_DESC}} |
| `{{CMD_LIST}}` | {{CMD_LIST_DESC}} |
| `{{CMD_SEARCH}}` | {{CMD_SEARCH_DESC}} |
| `{{CMD_REMOVE}}` | {{CMD_REMOVE_DESC}} |
| `{{CMD_VALIDATE}}` | {{CMD_VALIDATE_DESC}} |

---

## 兼容性
<!-- 平台型的核心信任点——读者问"我的环境能用吗" -->

| Agent/平台 | 支持 |
|-----------|:----:|
| {{PLATFORM_1}} | ✅ |
| {{PLATFORM_2}} | ✅ |
| {{PLATFORM_3}} | ⚠️ |
| {{PLATFORM_4}} | ❌ |

---

## Skill 展示
<!-- daymade 精髓手法：每个 skill 配 GIF/截图 demo 卡片，README 本身=可浏览的市场 -->
<!-- 🎨 制作方式（详见 ../references/visual-toolkit.md）：
     1. 用 huashu-design 为每个 skill 做 GIF demo：
        「用 huashu-design 做一个 8 秒动画，演示 [skill名] 的核心流程：[步骤1]→[步骤2]→[结果]，导出 GIF」
     2. 没有 huashu-design → 用录屏工具录制真实使用过程
     3. 后备 → 表格 + <img> 截图缩略图（Guizang 手法）
-->

### {{SKILL_1_NAME}}
![{{SKILL_1_NAME}} demo](assets/gifs/{{SKILL_1_GIF}})

**适用场景：** {{WHEN_TO_USE_1}}
**核心能力：** {{KEY_FEATURES_1}}

### {{SKILL_2_NAME}}

![{{SKILL_2_NAME}} demo](assets/gifs/{{SKILL_2_GIF}})

**适用场景：** {{WHEN_TO_USE_2}}
**核心能力：** {{KEY_FEATURES_2}}

<!-- 没有 GIF 时用 Guizang 手法：表格 + <img> 缩略图 -->

---

## 上手路径
<!-- agent-sandbox 手法：难度分级的 starter prompts，降低使用坡度 -->
<!-- 渐进披露：快速开始 → 常用工作流 → 高级用法 → 自己造 -->

### 🟢 入门

```
"{{EASY_PROMPT}}"
```

### 🟡 进阶

```
"{{MEDIUM_PROMPT}}"
```

### 🔴 高级

```
"{{HARD_PROMPT}}"
```

---

## 高级用法

<details>
<summary>{{ADVANCED_TOPIC_1}}</summary>

{{ADVANCED_CONTENT_1}}

</details>

<details>
<summary>{{ADVANCED_TOPIC_2}}</summary>

{{ADVANCED_CONTENT_2}}

</details>

---

## 创建你自己的 Skill

{{CREATE_YOUR_OWN_GUIDE}}

---

<div align="center">

MIT License

</div>
