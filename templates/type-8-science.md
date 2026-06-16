<!-- Type 8: 科学/研究型 (Science) -->
<!-- 标杆：academic-research-skills（31.7K⭐ 4-skill 流水线+人类在回路+反幻觉门控）· Stanford REAP（1.9K⭐ 机构背书+"2分钟自己验证"）· K-Dense（17领域+160K科学家+badges-as-dashboard+Citation 段） -->
<!-- 核心手法：研究者靠"能跑我的 pipeline 吗"决定，不靠功能列表 -->

<!-- ▸ 先放 hero.md 内容 -->
<!-- K-Dense 手法：badges-as-dashboard，用 badge 展示 skill 数/领域数/数据库数 -->
<!-- [![Skills](https://img.shields.io/badge/skills-{{N}}-blue)]() [![Domains](https://img.shields.io/badge/domains-{{N}}-green)]() -->

---

## 领域矩阵
<!-- K-Dense 手法：emoji + 类目 + skill 数。一眼传达广度 -->

| | 领域 | Skills |
|---|------|:------:|
| 🧬 | {{DOMAIN_1}} | {{COUNT_1}} |
| 🧪 | {{DOMAIN_2}} | {{COUNT_2}} |
| 📊 | {{DOMAIN_3}} | {{COUNT_3}} |
| 🔬 | {{DOMAIN_4}} | {{COUNT_4}} |
| 📐 | {{DOMAIN_5}} | {{COUNT_5}} |

---

## 工作流示例
<!-- academic-research 精髓手法：完整端到端 pipeline，不是功能演示 -->
<!-- 🎨 升级方式（详见 references/visual-toolkit.md）：
     表格流水线只是及格线。更强的展示：
     1. 用 excalidraw-diagram 画 pipeline 流程图（标注人工审核点）
     2. 用 huashu-design 做每步的产出截图序列
     3. 后备 → Mermaid 流程图代码块（GitHub 原生渲染）
-->
<!-- 每个工作流：研究问题 → 步骤 → 产出 -->
<!-- 研究者评估逻辑："能跑我的 pipeline 吗" -->

### 工作流 1: {{WORKFLOW_1_TITLE}}

**研究问题：** {{RESEARCH_QUESTION_1}}

| 步骤 | 动作 | 产出 |
|:----:|------|------|
| 1 | {{STEP_1_ACTION}} | {{STEP_1_OUTPUT}} |
| 2 | {{STEP_2_ACTION}} | {{STEP_2_OUTPUT}} |
| 3 | {{STEP_3_ACTION}} | {{STEP_3_OUTPUT}} |
| 4 | {{STEP_4_ACTION}} | {{STEP_4_OUTPUT}} |

<!-- academic-research 手法：在 pipeline 关键节点标注人类审核点 -->
> ⚠️ **人工审核点：** 步骤 {{N}} 产出需要研究者确认后再继续

### 工作流 2: {{WORKFLOW_2_TITLE}}

**研究问题：** {{RESEARCH_QUESTION_2}}

| 步骤 | 动作 | 产出 |
|:----:|------|------|
| 1 | {{STEP_2_1}} | {{OUTPUT_2_1}} |
| 2 | {{STEP_2_2}} | {{OUTPUT_2_2}} |
| 3 | {{STEP_2_3}} | {{OUTPUT_2_3}} |

---

## 期望管理
<!-- academic-research 手法："加速器，不是替代品"。预防"它能写我的论文吗"问题 -->
<!-- 反幻觉门控：明确说明哪些结论必须人工验证 -->

⚡ **这个 skill 是研究加速器，不是研究替代品。**

- **会做：** {{WILL_DO}}
- **不会做：** {{WILL_NOT_DO}}
- **需要你验证：** {{HUMAN_VERIFICATION_REQUIRED}}

---

## 2 分钟验证
<!-- Stanford REAP 精髓手法："自己验证"比任何声明都有说服力 -->

{{QUICK_VERIFICATION_STEPS}}

---

## 快速开始

```bash
npx skills add {{ORG}}/{{REPO}}
```

### 领域激活
<!-- 说明如何激活特定领域能力 -->

{{DOMAIN_ACTIVATION_INSTRUCTIONS}}

---

## 对话示例

```
User: "{{EXAMPLE_RESEARCH_PROMPT}}"

Agent: "{{EXAMPLE_AGENT_RESPONSE}}"
```

---

## 社会证明
<!-- K-Dense: "160,000+ scientists"。学术领域数字=信任 -->

{{SOCIAL_PROOF_NUMBERS_AND_INSTITUTIONS}}

---

## 引用
<!-- K-Dense 精髓手法：提供 4 种学术引用格式。信号="这是严肃研究基础设施，不是玩具" -->

<details>
<summary>BibTeX</summary>

```bibtex
@software{{{BIBTEX_KEY}},
  author = {{{AUTHOR}}},
  title = {{{TITLE}}},
  year = {{{YEAR}}},
  url = {https://github.com/{{ORG}}/{{REPO}}}
}
```

</details>

<details>
<summary>APA</summary>

{{APA_CITATION}}

</details>

<!-- 太早期没有引用需求时删除这节 -->

---

## 致谢
<!-- K-Dense 手法：列出上游项目和贡献者 -->

{{ACKNOWLEDGMENTS}}

---

<div align="center">

MIT License

</div>
