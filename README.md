<div align="center">

# 匾额 | Biane

> *「三个字的匾，定一家店的生死。十秒钟的 README，定一个 skill 的装机量。」*

[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-Compatible-blue)](https://github.com/anthropics/skills)
[![skills.sh](https://img.shields.io/badge/skills.sh-installable-brightgreen)](https://skills.sh)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-2.0-blue)]()
[![Types](https://img.shields.io/badge/types-8-orange)]()
[![Benchmarks](https://img.shields.io/badge/benchmarks-35-red)]()

**读你的 SKILL.md，判断 8 种类型中的哪种，加载对应标杆手法和模板，交付一份让人 10 秒决定安装的 README。**

[看效果](#beforeafter) · [安装](#快速开始) · [怎么用](#对话示例) · [局限](#局限性)

</div>

---

## 它解决什么问题

你的 Skill README 该有的都有：标题、简介、安装、用法。很完整。但还是没人装。

- 你让 AI「帮我写个 README」，拿到的是 **Install / Usage / Contributing 三件套**——十年前开源项目的模板，不是 Agent Skill 的销售页
- 你的 PPT 生成 skill 写了 200 字描述功能，**但没贴一张图**——读者不知道效果长什么样就走了
- 你的提效 skill 说「大幅提升效率」，**但没有 Before/After 对比**——「大幅」是多少？读者没有锚点

**README 不是说明书。是匾额——路人扫一眼就决定进不进店。**

---

## Before/After

用匾额 v2.0 重写 [baogong-skill](https://github.com/dmlin7777777/baogong-skill) 的 README，实测对比：

| 维度 | 重写前 | 匾额重写后 |
|:----:|:------:|:-----:|
| **首屏** | 品牌 slogan + 安装命令在第 100 行 | 痛点钩子 + B/A 对比 + 安装，首屏解决「要不要装」 |
| **效果展示** | 一个对话示例淹没在文字中 | 6 维 Before/After 对比表前置，一目了然 |
| **信任系统** | 铡刀门混在工作原理里 | 独立安全边界章节 + 三层安全机制表 |
| **品牌一致性** | AI 自动生成功能总结，原始品牌声音丢失 | 模板引导保留「卷宗未到，不开堂」原始品牌声音 |
| **流程展示** | 纯文字描述四阶段 | 「堂审四幕」表格 + 态度列（Luban 手法） |
| **产出物** | 交付物 bullet 列表 | 交付物 + 截图占位（Writing Principle 5） |

> 完整产出见 [baogong-skill README](https://github.com/dmlin7777777/baogong-skill)

---

## 它会交付什么

- **完整 README.md** — 按 8 种类型匹配不同结构和证明方式，不是一个模板套所有
- **类型诊断** — 告诉你的 skill 属于哪种类型、该用什么证明方式（用你听得懂的话，不问「是不是 Type 3」）
- **跨引用审查** — 每个 README 声明必须追溯到 SKILL.md，追不到就删。不编数字、不夸大能力

<!-- TODO: 视觉素材 — 用 huashu-design 截一张匾额产出的 README 效果图 -->

---

## 快速开始

```bash
npx skills add dmlin7777777/biane
```

> 安装后对 Agent 说：「帮我写 [skill-name] 的 README」

<details>
<summary>其他安装方式</summary>

```bash
git clone https://github.com/dmlin7777777/biane.git ~/.claude/skills/skill-readme-writer
```

</details>

---

## 对话示例

```
User: "帮我写 caveman-skill 的 README"

Agent: "让我看看 caveman 的 SKILL.md...
       核心改进是'省掉 75% 废话但保留全部技术精度'。
       这是提效型（Type 2），README 需要 Before/After 对比。

       🔴 CP1 — 类型确认：
       caveman 的读者首先想知道'比普通回复好多少'，
       不是'能产出什么'。所以用 Type 2 策略。对吗？"

User: "对"

Agent: "🔴 CP2 — ONE proof + hero 定位：
       ONE proof: 同一问题，普通回复 180 词 vs caveman 35 词
       Hero: '砍掉 AI 回复里 75% 的客套话，只留技术精度。'
       → 这两个方向对吗？"

User: "对，开写"

（3 分钟后输出完整 README.md，含 B/A 对比表 + 安全边界 + 品牌隐喻）
```

---

## 题匾三步

| 步骤 | 做什么 | 一句狠话 |
|------|--------|---------|
| **验明正身** | 读 SKILL.md，判断 8 种类型，用你听得懂的话确认 | 不问你「是不是 Type 3」——你不需要懂分类法，你只需要确认你的 skill 干了什么 |
| **选匾题字** | 找到 ONE proof + 定位句。一个元素做 80% 的说服 | 十个功能平均用力 = 一个都记不住。找到那一个砸脸的 |
| **挂匾验收** | 按模板写全稿，跨引用审查，逐节确认 | README 里的每句话必须追溯到 SKILL.md。追不到就删 |

### 三道检查点

每步结束都有强制停车点（🔴 CP），等你确认后才继续：

| CP | 卡什么 | 为什么卡 |
|----|--------|---------|
| **CP1** | 类型判断 | 类型错了整个 README 结构就错 |
| **CP2** | ONE proof + hero 定位句 | 这是最关键的决策——proof 错了全篇方向错，定位句抽象了用户一定要返工 |
| **CP3** | 全稿 + 跨引用审查 | Agent 天然倾向「圆」出更完整的能力——这道检查拦的就是这个 |

---

## 8 种类型

```
读者首先想知道...

  "它能产出什么？给我看"          → Type 1  产出型   → 截图/GIF 主导
  "比我现在的方法好多少？"        → Type 2  提效型   → Before/After 对比
  "给 Agent 加了什么能力？"       → Type 3  能力型   → 模式清单 + 覆盖矩阵
  "说话什么感觉？让我听听"        → Type 4  风格型   → 同一 prompt 两种输出对比
  "有什么 skill 可以选？"         → Type 5  合集型   → 分类目录 + 质量标准
  "怎么管理/安装 skill？"         → Type 6  平台型   → 一行命令上手
  "关键场景能不能信任它？"        → Type 7  安全型   → 战绩墙 + 标准覆盖
  "能解锁什么复杂工作流？"        → Type 8  科学型   → 完整端到端流水线
```

每种类型有独立模板，编入了该类型标杆 README 的核心手法（不是通用占位符）。

---

## 实战战绩

| 指标 | 数据 |
|------|------|
| 调研样本 | **35 个** Skill 仓库（Anthropic / Vercel / trailofbits / K-Dense / Stanford 等） |
| 类型模板 | **8 套**，每套编入 2-3 个标杆的手法（Luban 态度列、Cailun 叙事痛点、Humanizer B/A 表...） |
| 写作原则 | **5 条**（从 35 样本统计 + baogong 实验中提炼） |
| 铁律 | **8 条**通用铁律，跨类型无例外 |
| Darwin 评分 | **91.7 / 100**（8 维度：前置声明 / 工作流 / 边界 / 检查点 / 指令 / 资源集成 / 架构 / 实测） |
| 实验验证 | baogong-skill README 从零产出，hero 定位 1 轮通过（v1.0 需要 3 轮） |

---

## 安全边界

- **会做：** 判断类型、选择策略、按模板写 README、跨引用审查确保每句话追溯到 SKILL.md
- **不会做：** 编造安装量 / 用户数 / 性能数据；替你决定审美风格（古文派 vs 极简派你自己选）
- **强制停手点：** 你说「随便写一个」→ 停下来问类型，不猜

---

## 局限性

- **Type 5-8 样本少** — 每类 1-3 个标杆，策略覆盖率低于 Type 1-4。冷门类型可能需要你补充标杆参考
- **无法自动截图** — Output 型 skill 如果你没提供截图，只能用文字占位符替代，效果打折
- **品牌隐喻靠你** — 匾额能保护已有的品牌声音（模板有正反例引导），但不会凭空发明一个。没有自然隐喻时走 karpathy 极简路线

---

## 为什么叫匾额

写 Skill 的人通常不写 README。写了也是功能列表 + 安装命令——像一家好店挂了块白底黑字的门牌。

但老店的匾额从来不是自己随便写的。好匾请大师题，三个字定调性——路人远远看一眼就知道这家店值不值得进。

匾额做的事一样：你给 SKILL.md，它看你是什么店，选对的题法，交一块让人 10 秒决定进门的匾。

---

<details>
<summary><strong>开发文档</strong></summary>

### 文件结构

```
biane/
├── SKILL.md                    # Agent 指令（v2.0，~400 行）
├── templates/
│   ├── hero.md                 # 通用 hero 区块
│   ├── type-1-output.md        # 作品产出型模板
│   ├── type-2-efficiency.md    # 提效/流程型模板
│   ├── type-3-capability.md    # 能力增强型模板
│   ├── type-4-style.md         # 风格/视角型模板
│   ├── type-5-collection.md    # 合集/目录型模板
│   ├── type-6-platform.md      # 平台/工具型模板
│   ├── type-7-security.md      # 安全/专业型模板
│   └── type-8-science.md       # 科学/研究型模板
├── references/
│   ├── research-data.md        # 35 样本调研数据
│   └── visual-toolkit.md       # 视觉素材制作指南
├── evals/                      # 评估用例
├── examples/                   # 产出示例
└── test-output/                # 测试报告
```

### 标杆对照表

| 类型 | 标杆 | 学什么 |
|------|------|--------|
| 产出 | guizang · nuwa · cailun | 截图主导 · 故事叙事 · 命名仪式 |
| 提效 | luban · paoding · karpathy | 数字轰炸 · 对称句式 · 极简映射（176K⭐） |
| 能力 | humanizer · code-review · addyosmani | 模式清单 · 严重性编码 · 生命周期 |
| 风格 | nuwa · colleague | 多视角对比 · 情感钩子 |
| 合集 | awesome-cursorrules · alirezarezvani · travisvn | 13 类索引 · 兼容矩阵 · Skills vs Others |
| 平台 | vercel-labs · daymade | npx 一键 · GIF 卡片 |
| 安全 | trailofbits · code-audit · owasp | 战绩墙 · 反幻觉 · 标准矩阵 |
| 科学 | academic-research · K-Dense · Stanford REAP | 流水线 · 领域矩阵 · 机构背书 |

### 方法论来源

35 样本调研覆盖 Anthropic / Vercel / ComposioHQ / VoltAgent / trailofbits / K-Dense-AI / Stanford REAP / PatrickJS 等仓库。详细分析见 [references/research-data.md](references/research-data.md)。

</details>

---

<div align="center">

MIT License

</div>
