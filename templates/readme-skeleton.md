<!-- 
  Skill README Skeleton
  Usage: Copy this file, fill in placeholders, delete unused sections.
  Placeholders use {{PLACEHOLDER}} format.
  Sections marked [TYPE X ONLY] are type-specific — keep the ones matching your type, delete the rest.
-->

<div align="center">

# {{SKILL_NAME}}

> _「{{BRAND_QUOTE}}」_
<!-- Optional: only if the skill has a brand metaphor / cultural anchor. Delete this line if not. -->

[![Version](https://img.shields.io/badge/version-{{VERSION}}-blue)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-Standard-green)](https://agentskills.io)
[![skills.sh](https://img.shields.io/badge/skills.sh-Compatible-blue)](https://skills.sh)
[![Multi-Runtime](https://img.shields.io/badge/Runtime-Claude%20Code%20%C2%B7%20Codex%20%C2%B7%20Gemini%20CLI%20%C2%B7%20Cursor-blueviolet)](#install)
<!-- Keep applicable badges, delete the rest. Add stars badge if repo has traction:
[![GitHub stars](https://img.shields.io/github/stars/{{ORG}}/{{REPO}})](https://github.com/{{ORG}}/{{REPO}})
-->

{{HERO_POSITIONING}}
<!-- 1-2 sentences. Specific action chain, not abstract description.
     Lead with the most differentiating capability.
     Example: "先查面经和公司动态，再逐条审你的经历——追出数字、砍掉编造、对齐关键词，
     交付一份面试官追不穿的定制简历和一套基于真实面经的应对准备包。" -->

</div>

---

## {{HOOK_SECTION_TITLE}}
<!-- Type 1: storytelling / direct / emotional grab
     Type 2: pain point hook — rhetorical question or direct attack
     Type 3: capability gap statement
     Type 4: style anchor — one sentence IN the style itself
     Type 5: collection positioning + quality standards
     Type 6: one-command quickstart (this IS the hook)
     Type 7: domain positioning — precise technical terms
     Type 8: domain matrix — emoji + category + skill count -->

{{HOOK_CONTENT}}

## {{PROOF_SECTION_TITLE}}
<!-- Type 1: Effect proof — screenshots/GIFs, 40-60% of first screen
     Type 2: Before/After comparison table (side-by-side preferred)
     Type 3: Pattern/capability checklist, categorized
     Type 4: 3 comparison examples — same prompt, generic vs styled
     Type 5: Categorized listing with one-line descriptions
     Type 6: Installation methods + core commands table
     Type 7: Trophy case — real findings, real bugs caught
     Type 8: 2-3 complete end-to-end workflow examples -->

{{PROOF_CONTENT}}

<!-- [TYPE 2 ONLY] Before/After table template: -->
<!--
| Dimension | Before | After |
|:---------:|:------:|:-----:|
| **{{DIM_1}}** | {{BEFORE_1}} | {{AFTER_1}} |
| **{{DIM_2}}** | {{BEFORE_2}} | {{AFTER_2}} |
| **{{DIM_3}}** | {{BEFORE_3}} | {{AFTER_3}} |
-->

---

## Install

```bash
npx skills add {{ORG}}/{{REPO}}
```

{{FIRST_USE_INSTRUCTION}}
<!-- One line the user sends to the agent to start. Example:
     "装好后一句话启动：帮我针对这个 JD 调简历" -->

<details>
<summary>Other install methods</summary>

**Manual (Claude Code):**
```bash
git clone https://github.com/{{ORG}}/{{REPO}}.git ~/.claude/skills/{{SKILL_NAME}}
```

**Cursor / Codex / other runtimes:** Place `SKILL.md` in the corresponding skills directory.

</details>

---

## Conversation Example

<!-- Iron Law 3: at least 1 User/Agent dialogue. Show realistic interaction, not toy examples. -->

```
User: "{{EXAMPLE_USER_INPUT}}"

Agent: "{{EXAMPLE_AGENT_RESPONSE}}"
```

---

## How It Works

<!-- Process visualization: table, diagram, or numbered steps.
     If the skill has a brand metaphor, use it for section/step names. -->

| Step | What happens | Output |
|------|-------------|--------|
| **{{STEP_1_NAME}}** | {{STEP_1_DESC}} | {{STEP_1_OUTPUT}} |
| **{{STEP_2_NAME}}** | {{STEP_2_DESC}} | {{STEP_2_OUTPUT}} |
| **{{STEP_3_NAME}}** | {{STEP_3_DESC}} | {{STEP_3_OUTPUT}} |

---

## {{TRUST_SECTION_TITLE}}
<!-- Type 1: Limitations
     Type 2: Trust system — safeguards, limits, failure modes
     Type 3: Verification mechanism
     Type 4: When NOT to use
     Type 5: Quality standards
     Type 6: Compatibility matrix
     Type 7: Standards coverage / endorsements
     Type 8: Expectation management ("accelerator, not replacement") -->

{{TRUST_CONTENT}}

---

## Limitations

<!-- Iron Law 5: specific limitations section. Stating limits builds trust. -->

- **{{LIMITATION_1_TITLE}}** — {{LIMITATION_1_DESC}}
- **{{LIMITATION_2_TITLE}}** — {{LIMITATION_2_DESC}}
- **{{LIMITATION_3_TITLE}}** — {{LIMITATION_3_DESC}}

---

## {{ORIGIN_SECTION_TITLE}}
<!-- Iron Law 8: Origin story / personal pain / relatable frustration.
     Even 2 sentences beat 10 feature bullets.
     Example title: "Why I built this" / "为什么叫包公" -->

{{ORIGIN_STORY}}

---

<details>
<summary><strong>Developer Docs</strong></summary>

### File Structure

```
{{SKILL_NAME}}/
├── SKILL.md
├── scripts/
├── templates/
├── references/
└── ...
```

### Dependencies

{{DEPENDENCIES}}

</details>

---

<div align="center">

MIT License

</div>
