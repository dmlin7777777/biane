<!-- Type 1: 作品产出型 (Output) -->
<!-- Start with hero.md content, then these sections: -->

---

## {{HOOK_TITLE}}
<!-- One sentence: storytelling, direct, or emotional -->

{{HOOK}}

## Effect Proof
<!-- 40-60% of first screen. Real output screenshots/GIFs, not descriptions. BEFORE install. -->

{{SCREENSHOTS_OR_GIFS}}

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

## Deliverables

| Output | Description |
|--------|------------|
| {{FORMAT_1}} | {{DESC_1}} |
| {{FORMAT_2}} | {{DESC_2}} |

---

## Examples

### {{EXAMPLE_1_TITLE}}

{{EXAMPLE_1_CONTENT}}

### {{EXAMPLE_2_TITLE}}

{{EXAMPLE_2_CONTENT}}

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
