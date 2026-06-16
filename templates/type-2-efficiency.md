<!-- Type 2: 提效/流程型 (Efficiency) -->
<!-- Start with hero.md content, then these sections: -->

---

## {{PAIN_POINT_HOOK_TITLE}}
<!-- Rhetorical question or direct attack that makes reader feel the pain -->

{{PAIN_POINT_HOOK}}

## Before / After

<!-- Side-by-side table (default). Columns: dimension, before, after. -->

| Dimension | Before | After |
|:---------:|:------:|:-----:|
| **{{DIM_1}}** | {{BEFORE_1}} | {{AFTER_1}} |
| **{{DIM_2}}** | {{BEFORE_2}} | {{AFTER_2}} |
| **{{DIM_3}}** | {{BEFORE_3}} | {{AFTER_3}} |
| **{{DIM_4}}** | {{BEFORE_4}} | {{AFTER_4}} |

<!-- Alternative forms if side-by-side doesn't fit:
     - Numbers table: from X → Y, saving Z
     - Competitor comparison: Old Way | This Skill
     - Diff format: red/green or strikethrough -->

---

## Install

```bash
npx skills add {{ORG}}/{{REPO}}
```

{{FIRST_USE_INSTRUCTION}}

<details>
<summary>Other install methods</summary>

**Manual (Claude Code):**
```bash
git clone https://github.com/{{ORG}}/{{REPO}}.git ~/.claude/skills/{{SKILL_NAME}}
```

</details>

---

## Conversation Example

```
User: "{{EXAMPLE_USER_INPUT}}"

Agent: "{{EXAMPLE_AGENT_RESPONSE}}"
```

---

## How It Works

<!-- Workflow as table, diagram, or numbered steps. Use brand metaphor for step names if applicable. -->

| Step | What happens | Output |
|------|-------------|--------|
| **{{STEP_1}}** | {{STEP_1_DESC}} | {{STEP_1_OUT}} |
| **{{STEP_2}}** | {{STEP_2_DESC}} | {{STEP_2_OUT}} |
| **{{STEP_3}}** | {{STEP_3_DESC}} | {{STEP_3_OUT}} |

---

## Quantitative Proof

<!-- Real numbers from real usage, or specific case studies. -->

{{QUANTITATIVE_PROOF}}

---

## Trust System

<!-- Safeguards, limits, failure modes. Efficiency skills need trust most. -->

{{TRUST_SYSTEM}}

---

## Limitations

- **{{LIM_1}}** — {{LIM_1_DESC}}
- **{{LIM_2}}** — {{LIM_2_DESC}}
- **{{LIM_3}}** — {{LIM_3_DESC}}

---

## {{ORIGIN_TITLE}}

{{ORIGIN_STORY}}

---

<details>
<summary><strong>Developer Docs</strong></summary>

{{DEV_DOCS}}

</details>

---

<div align="center">

MIT License

</div>
