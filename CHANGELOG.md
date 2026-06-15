# Changelog

## v1.2 (2026-06-15) — 第四轮 Luban · 自审同步

### 改动
- **README.md 重写**：用最新 SKILL.md 规则（Type 2 策略 + Form D 对话示例）重写自身 README
  - 新增"装之前先看一眼"节（Form D 对话示例），满足铁律 3
  - 实战数据加入 7/7 = 100% 实测通过率
  - 新增"限制"节（3 条诚实声明）
  - 自审报告：Type 2 必选内容 + 7 铁律 + VC 全部 PASS

### 质量
- 过尺：75 → 85（+10 分）
- 自审：8/8 全部 PASS
- Git tag: `v1.2`

---

## v1.1 (2026-06-15) — 第二~三轮 Luban · 失败模式 + 实测验证 + 产出展示

### 第二轮改动
- **SKILL.md + 失败模式（+44 行）**：3 种失败场景（类型判断不清 / 不属于 8 类型 / 类型误判）+ 全局 fallback
- **SKILL.md Step 2 明确化**：Agent 现在知道"读取本 SKILL.md 下方的 Type N 章节" + Type 5-8 边界规则
- **test-prompts.json 新增**：7 个测试 case（4 类型判断 + 3 写作质量）
- **examples/baogong-readme-type2.md 新增**：用 Type 2 策略为 baogong-skill 写完整 README
- **README.md + 产出示例节**：5 维度 Before/After 对比表
- **README.md + 标杆对照表**：8 类型 × 标杆 Skill 速查表

### 第三轮改动
- **实测执行**：7/7 = 100% pass rate
  - 类型判断：4/4 全部正确（Output / Efficiency / 边界歧义 / 无法归类）
  - 写作质量：3/3 全部通过（caveman / guizang / jobs-perspective）
- **SKILL.md 修复 2 处**（实测发现）：
  - Type 1：Effect proof 必须在 Install 命令之前
  - Type 4：methodology ≤5 来源可混入，>5 需独立章节

### 质量
- 过尺：57 → 75（+18 分）
- 实测：7/7 = 100%

---

## v1.0 (2026-06-15) — 第一轮 Luban · 初版创建 + 补全

### 调研阶段
- 22 样本深度调研，覆盖 8 种 Skill 类型
- 发现 Skill README 写作的核心规律：SKILL.md（给 Agent 看）≠ README.md（给人看）

### 创建
- **SKILL.md 初版**：7 条铁律 + 4 种类型（第七轮补全至 8 种）
- **README.md 初版**：用 Type 2 策略写自身 README
- **references/research-data.md**：22 样本完整调研数据

### 补全
- Type 5-8 完整指南（合集型 / 平台型 / 安全型 / 科学型）
- Quick Reference：8 类型 × 7 必选项 = 56 格速查表
- 5 个 Common Mistakes + Anti-patterns

### 质量
- 过尺：57 分（初版，无实测、无失败模式）
- Luban 评分指出 P0 缺口：无 test-prompts、无失败模式、无产出展示
