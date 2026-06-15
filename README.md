# Skill README Writer

**你的 Skill README 该有的都有：标题、简介、安装、用法。很完整。但还是没人装。**

不是产品不行。是这套结构——「该有的都有」——是一份**说明书**。说明书回答「这是什么」。而真正让人 10 秒内点安装的，是**销售页**。

销售页回答的是另一个问题：「你凭什么不装。」——用截图砸脸，而不是文字描述功能。用 Before/After 对比，而不是「更快更好」。用生成文本让你自己感受风格，而不是形容词堆砌。

而不同类型的 Skill，凭什么不装的答案完全不同——产出型靠截图、提效型靠对比、风格型靠示例。市面上没人在讲这个区别。

这个 Skill 就讲这个。

---

## 装之前先看一眼：Agent 被这个 Skill 唤醒后会发生什么

```
User: "帮我写 caveman-skill 的 README"

Agent: "让我理解一下你的 skill —— caveman 的核心改进
      是'省掉 75% 废话但保留全部技术精度'。
      这是提效型（Type 2），README 需要 Before/After 对比。

      我先确认：caveman 有触发退出机制吗？
      —— 这对 README 的信任系统章节很重要。"

User: "有。说 'stop caveman' 或 'normal mode' 就退出"

Agent: "好。按 Type 2 策略，你的 README 结构：

      1. 痛点钩子：'AI 回复总是先写 3 行客套话再给答案？'
      2. Before/After：180 词 → 35 词，同一问题，两种回答
      3. 安装：npx skills add caveman（首屏第 3 行）
      4. 自动化退出：3 种触发场景
      5. 限制：中文效果约 50-60%

      现在开始写。你随时喊停。"

（3 分钟后输出完整 README.md）
```

> 这不是预制模板。「先判断类型，再给对应策略」是这个 Skill 和所有通用 README 生成器的本质区别。它不会给你一个 Install/Usage/Contributing 三件套然后让你自己填——它会诊断、确认、选择策略、然后才动笔。

---

## Before/After

| 维度 | 不用这个 Skill | 用这个 Skill |
|------|--------------|-------------|
| **类型识别** | 不知道 Skill 也分类型，一个模板套所有 | 8 种类型 + 每种有独立的策略和必选内容 |
| **效果展示** | 文字描述功能（"可以生成 PPT"） | 按类型匹配：截图 / B&A 对比 / 模式清单 / 生成文本 |
| **首屏钩子** | 项目名 + 一句话简介，然后陷入功能罗列 | 类型匹配的钩子（反问共情 / 故事叙事 / 风格锚点） |
| **信任建立** | "欢迎 Star / PR / Issue" | 诚实边界 + 攻击锚点点名 + 量化证明 |
| **差异化** | 没说和同类有什么不同 | 竞品对比表 + 攻击锚点（"别的工具给你润色。包公开堂——一条龙审完"） |
| **参考基准** | 凭感觉写 | 22 个样本调研 + 每个类型的标杆 README 参考 |

**具体来说：**

```
# Before — 不用 skill-readme-writer
一个 PPT 生成 Skill 的 README：
  "本项目可以生成精美的 HTML 演示文稿。支持多种版式。"
  → 没有一张图。没有一句对话示例。读者不知道长什么样。

# After — 用了 skill-readme-writer  
识别为「作品产出型」→ 策略：截图主导
  首屏 60% 面积是效果截图 + 风格变体微缩预览
  + "30 秒开始"段（安装命令 + 一句发给 Agent 的话）
  → 读者不用读文字，看图就知道要不要装
```

---

## 产出示例：baogong-skill README 重写

用 Type 2（提效型）策略重写了 [baogong-skill](https://github.com/LearnPrompt/baogong-skill) 的 README：

| 维度 | 原 README | Type 2 策略重写后 |
|------|----------|-----------------|
| **首屏钩子** | "卷宗未到，不开堂。"（品牌叙事，纯 slogan） | "AI 帮你写简历，你敢直接交吗？"（攻击用户信任焦虑） |
| **安装命令位置** | 在 100 行之后（四幕表格 + 效果示例之后） | **首屏第 3 行**，badge 下方立刻出现 |
| **效果证明** | 一个示例对话 + 一个 diff（有力但淹没在文字中） | Before → After 对比前置为独立章节，数字标注信息来源 |
| **信任系统** | 铡刀门 5 条 + 三色签 | 铡刀门 4 条精炼 + 三色签面试可信度（"你答得出来 / 你答不出来"） |
| **安全边界** | 混在工作原理中 | 独立章节「包公不做的事」—— 6 条硬承诺 |

[查看完整示例 →](examples/baogong-readme-type2.md)

> 核心差异：原 README 很强，但它假设读者有耐心读完全文。Type 2 策略做的是：让读者在 3 秒内看到「凭什么装」——不靠读完，靠扫读。

---

## 安装

```bash
# 本地 skill 目录（已在 ~/.workbuddy/skills/ 下）
# 无需额外安装，触发词即可激活

# 触发方式（把这句话发给 Agent）
"用 skill-readme-writer 帮我写 [skill-name] 的 README"
"review 一下这个 README"
"我的 skill 是提效型的，怎么写 README"
```

---

## 它怎么工作

启动后走三步：

| 步骤 | 做什么 | 输出 |
|------|--------|------|
| **1. 类型识别** | 根据 Skill 的功能判断 8 种类型中的哪一种（用你听得懂的话说，不问你"是不是 Type 3"） | 类型标签 + 对应策略 |
| **2. 策略分发** | 加载该类型的必选内容清单 + 标杆 README 参考 | 结构化 README 提纲 |
| **3. 写作执行** | 按 8 条铁律 + 反模式检查 + 标杆对标来写。每写完一个大节停一下让你确认 | 完整的 README.md |

---

## 8 种类型 — 决策流

```
你问：这个 Skill 让人看到什么才愿意装？

"看它能产出什么"              → Type 1  作品产出型  → 截图/GIF/对话示例主导
"看它比我现在的方法好多少"     → Type 2  提效/流程型  → Before/After 对比主导
"看它给 Agent 加了什么能力"    → Type 3  能力增强型  → 模式清单 + 覆盖矩阵
"听它说话是什么感觉"           → Type 4  风格/视角型  → 3 段生成文本对比

"看有什么 Skill 可以选"        → Type 5  合集/目录型  → 质量标准 + 分类列表
"看怎么管理/安装 Skill"        → Type 6  平台/工具型  → 一行命令上手
"看在关键场景能不能信任"       → Type 7  安全/专业型  → 战绩墙 + 动词驱动描述
"看能解锁什么复杂工作流"       → Type 8  科学/研究型  → 完整多步骤工作流
```

8 种类型 × 7 项必选内容速查表已内置在 SKILL.md 中。

| 类型 | 标杆 Skill | 学什么 |
|------|-----------|--------|
| **产出型** | `guizang-ppt-skill` `nuwa-skill` `cailun-skill` | 截图主导首屏 / 故事叙事钩子 / 命名仪式感 |
| **提效型** | `baogong-skill` `luban-skill` `paoding-skill` | Before/After 对比 / 数字轰炸 / 痛点反问 |
| **能力型** | `humanizer` `addyosmani/agent-skills` | 24 模式 5 分类 / 生命周期组织 |
| **风格型** | `nuwa-skill` `colleague-skill` | 生成文本对比 / 情感钩子 |
| **合集型** | `VoltAgent/awesome` `heilcheng/awesome` | 供应商分类 / 入选标准前置 |
| **平台型** | `vercel-labs/skills` | `npx` 一键上手 + 渐进式披露 |
| **安全型** | `trailofbits/skills` | 战绩墙 + 动词驱动描述 |
| **科学型** | `K-Dense-AI/claude-scientific-skills` | 领域矩阵 + 16 领域 × 6 工作流 |

> 全部 22 样本的详细分析见 [references/research-data.md](references/research-data.md)。

---

## 7 条通用铁律

不管你是什么类型，以下 7 条没有例外：

1. **首屏 10 秒内回答「要不要装」** — 钩子 + 效果证明 + 安装命令必须在第一屏
2. **安装命令必须在首屏滚动范围内** — 读者不能翻页才能装
3. **对话示例 > 代码示例** — 人要知道「跟 Agent 说什么」，不是「代码怎么跑」
4. **效果展示形式由类型决定** — 不要用截图证明提效，不要用文字描述产出
5. **诚实 > 吹嘘** — 每个标杆 README 都有 Limitations 章节
6. **攻击锚点必须点名** — 「比传统做法更好」没用。「点名批评 AI 空泛形容词堆砌」有用
7. **徽章矩阵是最便宜的社会认同** — License + skills.sh 状态 + GitHub stars 是最低配置

---

## 实战战绩

| 指标 | 数据 |
|------|------|
| 调研样本 | 22 个 Skill 仓库/单品 |
| 覆盖类型 | 8 种（产出 / 提效 / 能力 / 风格 / 合集 / 平台 / 安全 / 科学） |
| 测试用例 | 7 个（4 类型判断 + 3 写作质量） |
| 实测通过率 | **7/7 = 100%**（含边界歧义和无法归类两个压力 case） |
| 文档规模 | SKILL.md 550 行 + test-prompts.json + examples/ + references/ |
| 跨类型速查表 | 8 类型 × 7 必选项 = 56 格完整覆盖 |
| 失败模式 | 3 种失败场景 + 全局 fallback（2 轮兜底 → 保守型 README） |

> *实测数据截至 2026-06-15。测试覆盖了 Output / Efficiency / Style 三种类型的完整 README 写作，以及边界歧义和无法归类的 fallback 行为。详细报告见 [test-output/test-report.md](test-output/test-report.md)。*

---

## 和同类有什么不同

| 维度 | 传统 README 模板 | 市面上 README skill | Skill README Writer |
|------|-----------------|-------------------|-------------------|
| 对象 | 开源项目 | 开源项目 | **Agent Skill 专属** |
| 结构 | Install / Usage / Contributing | 同上，稍作变体 | 按 8 种类型分发不同结构 |
| 效果展示 | 无 | 无 | **按类型匹配**（截图/B&A/模式清单/文本对比） |
| 用户语言 | 假设英文 | 英文为主 | 中文 + 英文双轨（调研覆盖南北两派） |
| 信任系统 | Star / License | 无 | 诚实边界 + 攻击锚点 + 量化证明 |
| 决策支持 | 无 | 无 | 8 种类型识别决策流 + 标杆对标 |
| 失败处理 | 无 | 无 | 3 种失败模式 + fallback（类型不明先问，再不明兜底） |

大部分 README skill 的模板是十年前的，对象是传统开源项目，没考虑「Agent Skill」这个品类。也没考虑「AI Agent 也是 README 的读者」。这个 Skill 从调研到结构都只为一件事：**给 Skill 写 README**。

---

## 安全边界

**做什么：**
- 识别你的 Skill 属于哪种类型
- 告诉你该类型的 README 应该有哪些章节、什么顺序、怎么展示效果
- 对标该类型的标杆 README，告诉你「他们是怎么做的」
- 检查你的 README 是否违反通用铁律或类型专属反模式

**不做什么：**
- 不替你决定审美风格（古文派 vs 极简派，你自己选）
- 不生成虚构的安装量、用户数、性能数据
- 不保证「照做就爆」—— README 只是销售页，产品本身才是产品
- 不给合集型 Skill 写单品 README（反过来也不行——类型边界不混淆）

**强制停手点：** 如果你说「随便写一个」，这个 Skill 会停下来问类型。不猜。

---

## 限制

- **Skill 尚新**（2026-06 创建），实战战绩中的"22 样本 / 550 行 / 7/7 pass"是结构性指标和测试数据，非大规模外部用户使用数据
- Type 5-8（合集 / 平台 / 安全 / 科学）的样本量相对少（每类 1-3 个），策略覆盖率低于 Type 1-4
- 无法自动截图——对于 Output 型 Skill，如果用户没有提供截图，Agent 会使用视觉锚点描述替代（效果不如真实截图）

---

## 致谢

这个 Skill 的方法论建立在以下仓库的 README 分析之上：

**提效型标杆** — [baogong-skill](https://github.com/LearnPrompt/baogong-skill)（铡刀门 + Before/After）、[luban-skill](https://github.com/LearnPrompt/luban-skill)（数字轰炸 + 反问共情）、[paoding-skill](https://github.com/LearnPrompt/paoding-skill)（痛点场景 + 对称句式）

**产出型标杆** — [guizang-ppt-skill](https://github.com/LearnPrompt/guizang-ppt-skill)（截图主导 + 30 秒开始）、[nuwa-skill](https://github.com/LearnPrompt/nuwa-skill)（故事叙事 + 诚实边界）、[cailun-skill](https://github.com/LearnPrompt/cailun-skill)（七纸展示 + 命名仪式）

**生态调研** — 22 个样本覆盖 Anthropic / Vercel / ComposioHQ / VoltAgent / trailofbits / K-Dense-AI 等仓库

---

## License

MIT
