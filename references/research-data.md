# Skill README 调研数据集（35 样本）

> **数据校验日期：2026-06-16**
> 第一轮：Claude Sonnet 4 调研（2026-06-15），Opus 4.6 于 2026-06-16 逐一 WebFetch 验证，修正 6 个错误 org/repo 名、1 个错标"无 README"、3 处描述低估。
> 第二轮：Opus 4.6 于 2026-06-16 扩充 13 个新样本，重点补强 Security（+3）、Science（+3）、Platform（+2）、Collection（+3）、Capability（+1）、Efficiency（+1）类型。全部 GitHub URL 经 WebFetch 验证。

## 样本清单

### 作品产出型
| # | Skill | 仓库 | GitHub URL | README 行数 | 核心策略 | 效果展示形式 |
|---|-------|------|-----------|------------|---------|------------|
| 1 | guizang-ppt | op7418 | [op7418/guizang-ppt-skill](https://github.com/op7418/guizang-ppt-skill) | ~800 | 首屏截图 + 双视觉系统（杂志风/瑞士风） | 多张预览截图 + 主题色预设 + 横向翻页演示 |
| 2 | nuwa-skill | alchaincyf | [alchaincyf/nuwa-skill](https://github.com/alchaincyf/nuwa-skill) | 大型（中/英/日三语） | 故事叙事 + 分类展示 20+ 视角 | 真实对话 + Star 趋势图 + 入选标准 |
| 3 | cailun-skill | LearnPrompt | [LearnPrompt/cailun-skill](https://github.com/LearnPrompt/cailun-skill) | ~400 | 七种纸展示 + 造纸三律 | 6 张真实产出截图（fangzhi/duizhi/zhaozhi/juzhi/liuzhi/qianzhi） + 铁律 |
| 4 | colleague-skill | titanwings | [titanwings/colleague-skill](https://github.com/titanwings/colleague-skill) | 大型 | 情绪钩子 + 多数据源蒸馏 | 19.4K stars · 已进化为 dot-skill · 6 种数据源 · 多宿主兼容 · 学术 citation |

### 提效/流程型
| # | Skill | 仓库 | GitHub URL | README 行数 | 核心策略 | Before/After 形式 |
|---|-------|------|-----------|------------|---------|------------------|
| 5 | baogong-skill | dmlin7777777 | [dmlin7777777/baogong-skill](https://github.com/dmlin7777777/baogong-skill) | ~300 | Before/After 截图 + diff + 铡刀门 | 点名批评 AI 润色 + 三色签审计 + Writer/Auditor 分离 |
| 6 | luban-skill | LearnPrompt | [LearnPrompt/luban-skill](https://github.com/LearnPrompt/luban-skill) | ~400 | 反问共情 + 数字轰炸 | 竞品对比表 (Agent vs 鲁班) + demo GIF |
| 7 | paoding-skill | LearnPrompt | [LearnPrompt/paoding-skill](https://github.com/LearnPrompt/paoding-skill) | ~450 | 痛点场景 + 对称句式 + 零 API | 数字 + 竞品对比 + badges |
| 8 | diagnose | 用户本地 | — | — | 仅 SKILL.md | 需要补 Before/After |
| 9 | caveman | 用户本地 | — | — | 仅 SKILL.md | 需要补对话对比 |
| 23 | andrej-karpathy-skills | forrestchang | [forrestchang/andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills) | ~400 | 176K⭐ · 4 条原则（Think→Simplify→Surgical→Goal-driven）| 极简反模式：无 badge、无 B/A、纯问题→规则映射，靠 Karpathy 个人品牌 + 共鸣痛点驱动安装 |

### 能力增强型
| # | Skill | 仓库 | GitHub URL | README 行数 | 核心策略 | 效果展示形式 |
|---|-------|------|-----------|------------|---------|------------|
| 10 | humanizer | blader | [blader/humanizer](https://github.com/blader/humanizer) | ~450 | 33 模式清单（原 24，已扩展）+ Before/After | 5 大类分类 + 每模式 Before/After 表 + 完整文章级示例 |
| 11 | self-improving-agent | pskoett（原作）→ skillhub 分发 | [pskoett/pskoett-ai-skills](https://github.com/pskoett/pskoett-ai-skills/tree/main/skills/self-improvement) | 短 | OpenClaw 自改进机制 | README 极简，主要靠 SKILL.md |
| 12 | addyosmani/agent-skills | addyosmani | [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) | ~600 | 24 技能按生命周期组织 | 借口→反驳表 + 支持 7+ IDE |
| 24 | code-review-skill | awesome-skills | [awesome-skills/code-review-skill](https://github.com/awesome-skills/code-review-skill) | ~800 | 1K⭐ · 中英双语 + 四阶段流程图 + 颜色编码严重性标签 | 20+ 语言框架覆盖 + 渐进加载（核心 190 行，语言指南按需加载）+ 16,000+ 行审查规则 |

### 合集/目录型
| # | Skill | 仓库 | GitHub URL | README 行数 | 核心策略 |
|---|-------|------|-----------|------------|---------|
| 13 | VoltAgent/awesome-agent-skills | VoltAgent | [VoltAgent/awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills) | 1000+ | 按提供者分类 + 统一格式 · 1424+ skills |
| 14 | heilcheng/awesome-agent-skills | heilcheng | [heilcheng/awesome-agent-skills](https://github.com/heilcheng/awesome-agent-skills) | 1500+ | 6 条质量标准 + 分类 · 200+ skills |
| 15 | ComposioHQ/awesome-claude-skills | ComposioHQ | [ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) | 2000+ | 10 大类 + 78 个预置工作流 |
| 16 | github/awesome-copilot | GitHub | [github/awesome-copilot](https://github.com/github/awesome-copilot) | 大型 | 35.1K stars · agents/instructions/skills/plugins/hooks/workflows |
| 17 | csfuwwc/md-skills | csfuwwc | [csfuwwc/md-skills](https://github.com/csfuwwc/md-skills) | 短 | 8 个 skill 按分类展示 |
| 25 | awesome-cursorrules | PatrickJS | [PatrickJS/awesome-cursorrules](https://github.com/PatrickJS/awesome-cursorrules) | 1500+ | 40K⭐ · 13 大类 200+ cursor rules · "Why Cursor Rules" 价值主张段 |
| 26 | claude-skills (337) | alirezarezvani | [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) | 1200+ | 18.2K⭐ · 345 个 skill · 17 域分类 · 跨平台兼容矩阵（Claude/Codex/Gemini CLI 等） |
| 27 | awesome-claude-skills | travisvn | [travisvn/awesome-claude-skills](https://github.com/travisvn/awesome-claude-skills) | 1500+ | 13.5K⭐ · "Skills vs Other Approaches" 对比矩阵 + 安全最佳实践章节 + 渐进披露架构说明 |

### 平台/工具型
| # | Skill | 仓库 | GitHub URL | README 行数 | 核心策略 |
|---|-------|------|-----------|------------|---------|
| 18 | vercel-labs/skills | Vercel | [vercel-labs/skills](https://github.com/vercel-labs/skills) | ~800 | npx 一行上手 + 渐进披露 + 兼容性矩阵 |
| 19 | agentskills/agentskills | AgentSkills | [agentskills/agentskills](https://github.com/agentskills/agentskills) | ~100 | 技能规范定义 + agentskills.io 链接 |
| 28 | claude-code-skills | daymade | [daymade/claude-code-skills](https://github.com/daymade/claude-code-skills) | 8000+ | 1.2K⭐ · 64+ skill 的 marketplace-as-README：每个 skill 配 GIF demo + "When to use / Key features" 卡片 |
| 29 | agent-sandbox-skill | disler | [disler/agent-sandbox-skill](https://github.com/disler/agent-sandbox-skill) | ~450 | 375⭐ · 难度分级 starter prompts（Very Easy→Very Hard）作为上手坡道 + E2B 沙箱隔离执行 |

### 安全/专业领域型
| # | Skill | 仓库 | GitHub URL | README 行数 | 核心策略 |
|---|-------|------|-----------|------------|---------|
| 20 | trailofbits/skills | Trail of Bits | [trailofbits/skills](https://github.com/trailofbits/skills) | ~300 | Trophy Case + 动词驱动描述 + 10 领域分类 |
| 30 | code-audit | 3stoneBrother | [3stoneBrother/code-audit](https://github.com/3stoneBrother/code-audit) | ~500 | 750⭐ · 反幻觉方法论章节 + 双轨审计模型 + 55+ 漏洞类型 + 9 语言 14 框架覆盖 |
| 31 | claude-code-owasp | agamm | [agamm/claude-code-owasp](https://github.com/agamm/claude-code-owasp) | ~250 | 234⭐ · 标准覆盖矩阵（OWASP Top 10:2025 + ASVS 5.0）+ 语言特定安全 quirks 表 |
| 32 | claude-cybersecurity | AgriciDaniel | [AgriciDaniel/claude-cybersecurity](https://github.com/AgriciDaniel/claude-cybersecurity) | ~800 | 149⭐ · 8 并行 agent 架构图 + vs GitHub Advanced Security 对比表 + 评分体系可视化 |

### 科学/研究型
| # | Skill | 仓库 | GitHub URL | README 行数 | 核心策略 |
|---|-------|------|-----------|------------|---------|
| 21 | K-Dense-AI/claude-scientific-skills | K-Dense | [K-Dense-AI/claude-scientific-skills](https://github.com/K-Dense-AI/claude-scientific-skills) | 2000+ | 17 领域 emoji 分类 + 6 个工作流示例 + "160,000+ scientists" |
| 33 | academic-research-skills | Imbad0202 | [Imbad0202/academic-research-skills](https://github.com/Imbad0202/academic-research-skills) | 大型（4 语言版本） | 31.7K⭐ · 4 skill 流水线（Deep Research→Paper→Reviewer→Pipeline）+ 人类在回路 + 反幻觉门控 |
| 34 | Awesome-Agent-Skills-for-Empirical-Research | brycewang-stanford | [brycewang-stanford/Awesome-Agent-Skills-for-Empirical-Research](https://github.com/brycewang-stanford/Awesome-Agent-Skills-for-Empirical-Research) | 大型（5 语言版本） | 1.9K⭐ · Stanford REAP 机构背书 + 1,080 内置 skill + 23,000 外部 skill 索引 + "2 分钟自己验证" |
| 35 | academic-paper-skills | lishix520 | [lishix520/academic-paper-skills](https://github.com/lishix520/academic-paper-skills) | ~450 | 891⭐ · 双 skill 流水线图（strategist→composer）+ 35 维审稿人模拟 + 预印本平台适配 |

### Anthropic 官方技能
| # | Skill | 仓库 | GitHub URL | README 行数 | 核心策略 |
|---|-------|------|-----------|------------|---------|
| 22 | anthropics/skills | Anthropic | [anthropics/skills](https://github.com/anthropics/skills) | 实质性 | 根目录有完整 README（安装指南 + Skill 创建教程 + Partner Skills）；单个 skill 文件夹仅有 SKILL.md |

## 校验修正记录（2026-06-16）

| # | 原始记录 | 问题 | 修正 |
|---|---------|------|------|
| 1 | guizang-ppt → LearnPrompt | org 错误 | → op7418 |
| 2 | nuwa-skill → LearnPrompt | org 错误 | → alchaincyf（花叔） |
| 4 | colleague-skill → 仅"情绪钩子 + 痛点排比" | 严重低估 | 19.4K stars · 进化为 dot-skill · 多宿主 · 学术 citation |
| 5 | baogong-skill → LearnPrompt | org 错误 | → dmlin7777777（用户自有 repo） |
| 10 | humanizer → niclasgronning, "24 模式" | org 错误 + 数据过时 | → blader/humanizer · 已扩展至 33 patterns |
| 11 | self-improving-agent → OpenAgentBuilder | org 错误 | → pskoett/pskoett-ai-skills (skills/self-improvement) |
| 3 | cailun-skill → "独立视觉描述" | 描述低估 | 实际有 6 张真实产出截图 |
| 22 | anthropics/skills → "无 README" | 事实性错误 | 根目录有完整 README |

## 六种吸睛手法

按出现频率排序：

1. **徽章 + 数字 = 社会认同** — 100% 的标杆仓库使用。GitHub stars、License、skills.sh 状态、Powered by 徽章
2. **一句话价值主张** — 10-20 词短句，直击结果。不是"本项目旨在帮助…"
3. **演示先行** — 截图/GIF/对话示例靠前，先让人看到效果再讲理论
4. **痛点否定式开场** — 否定常识制造认知缺口。"Not all READMEs are the same."
5. **坦诚营销** — "它不写代码""蒸馏不了直觉""只抄录对话不编一个字"
6. **安装命令前置** — 零摩擦试一下。首屏滚动范围内必须出现

## 八条跨类型通用铁律

1. **首屏 10 秒内回答"我要不要装"**
2. **安装命令必须在首屏滚动范围内**
3. **对话示例 > 代码示例**（Skill 品类特有）
4. **效果展示形式由类型决定**（产出型=截图/GIF、提效型=对比+数字、增强型=模式清单、风格型=对话示例）
5. **诚实 > 吹嘘**（所有标杆的共同特征）
6. **攻击锚点必须点名**（差异化最快方式）
7. **徽章矩阵是最便宜的社会认同**（License + skills.sh 状态 + GitHub stars 是最低配置；更深层社会证明：用量、推荐、方法论透明度）
8. **情感连接打开逻辑关不上的门**（起源故事 + 个人动机 + 共鸣痛点，让人在意"为什么造它"）

## 两种标杆流派

| 维度 | LearnPrompt 派 | Anthropic 派 |
|------|---------------|-------------|
| 风格 | 中文叙事 + 文化隐喻 + 强人格 | 英文技术文档 + 极简 + 去人格 |
| README | 有独立 README，面向人类 | 根目录有 README（安装 + 创建指南），单个 skill 仅 SKILL.md |
| 信任建立 | 诚实边界 + 安全声明 + 强制停手点 | 免责声明 + 双重许可 |
| 品牌 | 同门手艺矩阵 + 金句 | 生态合作 + 规范制定 |
| 适用场景 | 社区分发，需说服安装 | 内置分发，README 面向生态建设者而非最终用户 |

## 效果展示形式速查

| 类型 | 展示形式 | 代表案例 |
|------|---------|---------|
| 作品产出型 | 截图/GIF/对话示例 | guizang 多张预览截图、nuwa 分类表 + 对话 |
| 提效/流程型 | Before/After 对比 + 数字 | baogong diff + 三色签、luban 竞品对比 + demo GIF、**karpathy 极简反模式：纯规则映射无 B/A** |
| 能力增强型 | 模式清单 + 样例 | humanizer 33 patterns + 每模式 Before/After、**code-review 四阶段流程图 + 严重性颜色编码** |
| 风格/视角型 | 3 段生成文本对比 | nuwa examples 对话 |
| 合集/目录型 | 表格 + 描述 | awesome-* repos、**alirezarezvani 跨平台兼容矩阵**、**travisvn "Skills vs Other Approaches" 对比** |
| 平台/工具型 | 命令演示 + 兼容性矩阵 | vercel-labs/skills、**daymade 每 skill 配 GIF demo 卡片** |
| 安全/专业型 | Trophy Case + 动词描述 | trailofbits/skills、**code-audit 反幻觉方法论**、**claude-cybersecurity 8-agent 架构图** |
| 科学/研究型 | 领域矩阵 + 多步骤工作流 | K-Dense 17 领域、**academic-research 4 skill 流水线**、**Stanford REAP 机构背书 + "自己验证"** |
