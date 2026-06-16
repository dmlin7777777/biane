<!-- Type 7: 安全/专业领域型 (Security) -->
<!-- 标杆：trailofbits/skills（Trophy Case+动词驱动+10领域目录）· code-audit（750⭐ 反幻觉方法论+55+漏洞类型）· claude-code-owasp（234⭐ OWASP Top 10:2025 + ASVS 5.0 标准矩阵）· claude-cybersecurity（149⭐ 8-agent 架构图+vs GitHub Advanced Security 对比） -->
<!-- 核心手法：精确=营销。随意语气在这里反作用。"我检测到了 X"胜过"我能检测 X" -->

<!-- ▸ 先放 hero.md 内容 -->
<!-- ⚠️ 安全型 hero 禁止 emoji。用精确技术术语定位 -->

---

## 领域定位
<!-- 具体问题 + 精确技术术语。不用营销语言 -->

{{PRECISE_DOMAIN_POSITIONING}}

---

## 战绩
<!-- Trail of Bits 精髓手法：真实发现+链接到实际 PR/Issue -->
<!-- "I have detected X, here's the CVE" vs "I claim to detect X" -->
<!-- 邀请手法："发现了漏洞？告诉我们！" + 现成归因文本 -->

| 发现 | 严重度 | 详情 |
|------|:------:|------|
| {{FINDING_1}} | 🔴 Critical | [{{DETAIL_1}}]({{LINK_TO_PR_1}}) |
| {{FINDING_2}} | 🟠 High | [{{DETAIL_2}}]({{LINK_TO_PR_2}}) |
| {{FINDING_3}} | 🟡 Medium | [{{DETAIL_3}}]({{LINK_TO_PR_3}}) |

> 用这个 skill 发现了漏洞？[提交到这里]({{ISSUE_TEMPLATE_LINK}})

---

## 能力清单
<!-- 动词驱动（Trail of Bits 手法）：Detect/Audit/Identify/Analyze/Prevent -->
<!-- 每个动词→一个具体能力，不是模糊描述 -->

- **检测 (Detect)** — {{DETECT_SPECIFIC_CAPABILITY}}
- **审计 (Audit)** — {{AUDIT_SPECIFIC_CAPABILITY}}
- **识别 (Identify)** — {{IDENTIFY_SPECIFIC_CAPABILITY}}
- **分析 (Analyze)** — {{ANALYZE_SPECIFIC_CAPABILITY}}
- **防御 (Prevent)** — {{PREVENT_SPECIFIC_CAPABILITY}}

---

## 反幻觉方法论
<!-- code-audit 独有手法：安全领域假阳性=致命，必须说明如何控制幻觉 -->

{{ANTI_HALLUCINATION_METHODOLOGY}}

---

## 标准覆盖
<!-- claude-code-owasp 手法：标准矩阵+具体版本号+覆盖百分比 -->

| 标准 | 版本 | 覆盖 |
|------|------|:----:|
| {{STANDARD_1}} | {{VERSION_1}} | {{COVERAGE_1}} |
| {{STANDARD_2}} | {{VERSION_2}} | {{COVERAGE_2}} |

<!-- 有竞品对比时加（claude-cybersecurity 手法）：
## 对比
| 维度 | {{COMPETITOR}} | {{THIS_SKILL}} |
|------|---|---|
| {{DIM_1}} | {{COMP_1}} | {{THIS_1}} |
-->

---

## 漏洞类型覆盖
<!-- code-audit 手法：列出所有检测的漏洞类型，数量=说服力 -->
<!-- 🎨 升级方式（详见 references/visual-toolkit.md）：
     1. 多 Agent 架构 → 用 excalidraw-diagram 画架构图（claude-cybersecurity 手法：8-agent 并行扫描）
     2. 标准覆盖 → 用 show_widget 做覆盖率热力图
     3. 漏洞类型 → 用 huashu-design 做分类信息图
-->

### {{VULN_CATEGORY_1}}

| # | 漏洞类型 | 说明 |
|---|---------|------|
| 1 | {{VULN_1}} | {{VULN_1_DESC}} |
| 2 | {{VULN_2}} | {{VULN_2_DESC}} |

### {{VULN_CATEGORY_2}}

| # | 漏洞类型 | 说明 |
|---|---------|------|
| 3 | {{VULN_3}} | {{VULN_3_DESC}} |

---

## 安装 + 作用域
<!-- 安全型必须精确定义边界："它会碰什么"和"它不会碰什么" -->

```bash
npx skills add {{ORG}}/{{REPO}}
```

### 会检查

{{WILL_TOUCH}}

### 不会碰

{{WILL_NOT_TOUCH}}

---

<div align="center">

MIT License

</div>
