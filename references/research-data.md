# Skill README 调研数据集（22 样本）

## 样本清单

### 作品产出型
| # | Skill | 仓库 | 核心策略 | 效果展示形式 |
|---|-------|------|---------|------------|
| 1 | guizang-ppt | LearnPrompt | 首屏60%截图 + 主题微缩矩阵 | 全宽截图 + 主题色预览 |
| 2 | nuwa-skill | LearnPrompt | 故事叙事 + 4段对话示例 | 真实对话 + Star 趋势图 |
| 3 | cailun-skill | LearnPrompt | 七种纸展示 + 造纸三律 | 独立视觉描述 + 铁律 |
| 4 | colleague-skill | titanwings | 情绪钩子 + 痛点排比 | 对话示例 + 5个 Your...? |

### 提效/流程型
| # | Skill | 仓库 | 核心策略 | Before/After 形式 |
|---|-------|------|---------|------------------|
| 5 | baogong-skill | LearnPrompt | Before/After 全宽大图 + diff | 点名批评 AI 润色 + 铡刀门 |
| 6 | luban-skill | LearnPrompt | 反问共情 + 数字轰炸 | 竞品对比表 (Agent vs 鲁班) |
| 7 | paoding-skill | LearnPrompt | 痛点场景 + 对称句式 | 数字 + 竞品对比 |
| 8 | diagnose (无 README) | 用户本地 | 仅 SKILL.md | 需要补 Before/After |
| 9 | caveman (无 README) | 用户本地 | 仅 SKILL.md | 需要补对话对比 |

### 能力增强型
| # | Skill | 仓库 | 核心策略 | 效果展示形式 |
|---|-------|------|---------|------------|
| 10 | humanizer | niclasgronning | 24 模式清单 + Before/After | 5 大类分类 + 每类示例 |
| 11 | self-improving-agent | OpenAgentBuilder | 极简 4 行 | 几乎无效果展示 |
| 12 | addyosmani/agent-skills | addyosmani | 24 技能按生命周期组织 | 借口→反驳表 |

### 合集/目录型
| # | Skill | 仓库 | 核心策略 |
|---|-------|------|---------|
| 13 | VoltAgent/awesome-agent-skills | VoltAgent | 按提供者分类 + 统一格式 |
| 14 | heilcheng/awesome-agent-skills | heilcheng | 6 条质量标准 + 分类 |
| 15 | ComposioHQ/awesome-claude-skills | ComposioHQ | 按类型分类 |
| 16 | github/awesome-copilot | GitHub | 35K stars, Powered by Copilot 徽章 |
| 17 | csfuwwc/md-skills | csfuwwc | 按分类展示 |

### 平台/工具型
| # | Skill | 仓库 | 核心策略 |
|---|-------|------|---------|
| 18 | vercel-labs/skills | Vercel | npx 一行上手 + 渐进披露 |
| 19 | agentskills/agentskills | AgentSkills | 技能规范定义 |

### 安全/专业领域型
| # | Skill | 仓库 | 核心策略 |
|---|-------|------|---------|
| 20 | trailofbits/skills | Trail of Bits | Trophy Case + 动词驱动描述 |

### 科学/研究型
| # | Skill | 仓库 | 核心策略 |
|---|-------|------|---------|
| 21 | K-Dense-AI/claude-scientific-skills | K-Dense | 16 领域 emoji 分类 + 6 个工作流示例 |

### Anthropic 官方技能
| # | Skill | 仓库 | 核心策略 |
|---|-------|------|---------|
| 22 | anthropics/skills | Anthropic | 全部仅有 SKILL.md，无 README |

## 六种吸睛手法

按出现频率排序：

1. **徽章 + 数字 = 社会认同** — 100% 的标杆仓库使用。GitHub stars、License、skills.sh 状态、Powered by 徽章
2. **一句话价值主张** — 10-20 词短句，直击结果。不是"本项目旨在帮助…"
3. **演示先行** — 截图/GIF/对话示例靠前，先让人看到效果再讲理论
4. **痛点否定式开场** — 否定常识制造认知缺口。"Not all READMEs are the same."
5. **坦诚营销** — "它不写代码""蒸馏不了直觉""只抄录对话不编一个字"
6. **安装命令前置** — 零摩擦试一下。首屏滚动范围内必须出现

## 七条跨类型通用铁律

1. **首屏 10 秒内回答"我要不要装"**
2. **安装命令必须在首屏滚动范围内**
3. **对话示例 > 代码示例**（Skill 品类特有）
4. **效果展示形式由类型决定**（产出型=截图/GIF、提效型=对比+数字、增强型=模式清单、风格型=对话示例）
5. **诚实 > 吹嘘**（所有标杆的共同特征）
6. **攻击锚点必须点名**（差异化最快方式）
7. **命名仪式感建立品牌**（如 LearnPrompt 五动作/四种纸/四层肌理）

## 两种标杆流派

| 维度 | LearnPrompt 派 | Anthropic 派 |
|------|---------------|-------------|
| 风格 | 中文叙事 + 文化隐喻 + 强人格 | 英文技术文档 + 极简 + 去人格 |
| README | 有独立 README，面向人类 | 无 README，仅 SKILL.md |
| 信任建立 | 诚实边界 + 安全声明 + 强制停手点 | 免责声明 + 双重许可 |
| 品牌 | 同门手艺矩阵 + 金句 | 生态合作 + 规范制定 |
| 适用场景 | 社区分发，需说服安装 | 内置分发，无需 README |

## 效果展示形式速查

| 类型 | 展示形式 | 代表案例 |
|------|---------|---------|
| 作品产出型 | 截图/GIF/对话示例 | guizang 全宽截图、nuwa 4段对话 |
| 提效/流程型 | Before/After 对比 + 数字 | baogong diff、luban 83,725条回放 |
| 能力增强型 | 模式清单 + 样例 | humanizer 24 patterns |
| 风格/视角型 | 3 段生成文本对比 | nuwa examples 对话 |
| 合集/目录型 | 表格 + 描述 | awesome-* repos |
| 平台/工具型 | 命令演示 + 架构图 | vercel-labs/skills |
| 安全/专业型 | Trophy Case + 动词描述 | trailofbits/skills |
