---
name: skill-readme-writer
version: "1.2"
description: >
  Use when the user needs to write, improve, or review a README.md file for an Agent Skill.
  Triggers include "write a README for my skill", "improve my skill's README", "review this README",
  "帮我写 README", "优化 README", "怎么写 skill 的 README".
  Covers 8 types: output (screenshots/demos), efficiency (Before/After comparisons), capability (pattern checklists),
  style (generated text samples), collection (quality standards + categorization),
  platform (one-command quickstart), security (trophy case + domain authority),
  and science (multi-step workflow examples).
  NOT for traditional project READMEs (use other tools for those).
---

# Skill README Writer

## Overview

Skill READMEs are fundamentally different from traditional project READMEs. A Skill README is a **sales page for human readers** — it answers "should I install this?" in 10 seconds. The SKILL.md handles the agent; the README handles the human.

**Core insight:** Different skill types need different README strategies. An output-type skill (eg. PPT generator) proves itself with screenshots; an efficiency-type skill (eg. debugger) proves itself with Before/After comparisons.

This guide covers all 8 types identified through 22-sample research (7 original + 1 derived during analysis). Each type has a unique strategy because each answers a different human decision question.

## Workflow

Follow this 3-step flow for every README writing task. The type knowledge sections (Type 1-8 below) are loaded after step 2.

### Step 1: Identify type (ask 1-2 questions)

Ask the user what their skill does. Then state your type judgment in **plain language the user can verify**:

```
Your skill produces [specific output] when triggered — that's Output Type.
The README should lead with screenshots of the output.
→ User can confirm: "yes, it produces PPT files" or "no, it's not that".

Your skill makes [process] faster/better — that's Efficiency Type.
The README needs a Before/After comparison so people can see the difference.
→ User can confirm: "yes, it saves time" or "no, it adds capability".
```

**Only confirm what the user can judge.** Do NOT ask "is this Type 3 or Type 7?" — the user doesn't know the taxonomy. Ask about their skill's behavior in plain language.

### Step 2: Load the type guide

Read the Type section in **this SKILL.md file** below. Find the corresponding `Type N:` heading (Type 1-8), then read that entire section. Each type guide has:
- Core question + strategy
- Mandatory sections (in order)
- Anti-patterns to avoid
- Benchmark examples to study
- Verification Checklist at the end

**Type 5-8 boundary rule:** Types 5-8 (Collection, Platform, Security, Science) are for specialized skill categories. If the user's skill does NOT match one of these clearly (collection of skills, a platform/tool, a security scan tool, research workflows), default to Types 1-4. Do NOT force a skill into Type 5-8 just because types 1-4 don't fit neatly.

### Step 3: Draft + verify

After drafting each major section, show a 2-line summary:
```
Section: Hook + Before/After comparison
Answers: "should I install?" in the first 10 seconds
→ Does this section feel right to you?
```

The user can judge whether the effect matches their intent, even if they can't judge the technical approach.

## Failure Modes & Fallback

When things go wrong, do NOT continue silently. Follow these fallback rules.

### Failure 1: Can't determine the type in 1 question

**Symptom:** After asking 1 plain-language question, the user's answer is too vague to determine type.
**Fallback:**
1. Ask 1 more question, with more specific framing:
   ```
   "Let me try a different angle. When someone uses your skill, what do they SEE at the end?
   A) A file or document (screenshots, PPT, HTML, PDF) → Output Type
   B) The same task done faster/better (debugging, formatting, planning) → Efficiency Type
   C) New behavior the agent couldn't do before (detection, transformation, analysis) → Capability Type
   D) A different way of speaking or writing (style, tone, perspective) → Style Type"
   ```
2. If still unclear after 2 questions → **default to Type 2 (Efficiency) as conservative baseline**.
   - Type 2's "Before/After comparison + Trust system" works reasonably for most skills.
   - If the skill doesn't fit, the user will spot it during Step 3 verification and correct.
3. **Record:** Note "type uncertain, defaulted to Type 2" so the user's feedback can improve future type detection.

### Failure 2: Skill doesn't match any of the 8 types

**Symptom:** The skill's domain is genuinely outside all 8 categories (e.g., a skill for teaching, medical diagnosis, legal reasoning).
**Fallback:**
1. State honestly: "Your skill doesn't map neatly to any of our 8 type categories. I'll use Type 2 (Efficiency) as a baseline since it has the most transferable sections: Before/After comparison, trust system, and limitations."
2. Skip the Verification Checklist (it won't apply).
3. Ask the user: "Does this skill type need special README treatment? If you found a similar skill's README you admired, share it and I'll adapt."

### Failure 3: Type was judged incorrectly — user corrects mid-draft

**Symptom:** During Step 3 verification, user says "no, it's not that type."
**Fallback:**
1. Stop drafting immediately.
2. Ask the user to describe what the skill produces or improves in their own words.
3. Restart from Step 2 with the new type.
4. **Do NOT patch** — rewriting with the correct type strategy is faster than retrofitting the wrong structure.

### Fallback for ALL failures

When any failure mode triggers and can't be resolved in 2 rounds of interaction:
- Write a conservative README with: hook line, install command, 1 example, 1 limitation.
- Append `<!-- WARNING: This README was written under fallback mode. Type could not be determined. -->` at the bottom.
- Tell the user: "I've written a basic README. If you find examples of READMEs you like for similar skills, share them and I'll rewrite."

## 7 Universal Iron Laws

These apply to ALL skill types. No exceptions.

**1. Answer "should I install?" in the first 10 seconds.**

First screen must contain: what it does + why it's different + install command. Do not bury the hook below a wall of text.

**2. Install command must appear in the first scroll range.**

`npx skills add <name>`, or equivalent. The reader must not scroll to install.

**3. Conversation examples > code examples.**

Show what the user says to their agent, not what code gets run. This is the unique differentiator of Skill READMEs vs traditional project READMEs.

```
# Good (conversation example)
User: "审一下这份 JD — 腾讯微信事业群高级产品经理"
Agent: "JD 解析完成。量化追问第 1 轮..."

# Bad (code example)
```python
from skill import analyze_jd
result = analyze_jd("job_description.pdf")
```
```

**4. Effect display format is determined by skill type.**

| Type | Display Format | Example |
|------|---------------|---------|
| Output | Screenshots, GIFs, real conversation | guizang full-width preview |
| Efficiency | Before/After comparison, numbers, diffs | baogong diff + before/after image |
| Capability | Pattern checklist, coverage matrix | humanizer 24 patterns |
| Style | 3 generated text comparisons | nuwa dialogue examples |
| Collection | Quality criteria + categorized tables | VoltAgent awesome list |
| Platform | One-command quickstart + architecture | vercel-labs/skills |
| Security | Trophy case + verb-driven descriptions | trailofbits/skills |
| Science | Domain matrix + multi-step workflows | K-Dense-AI 6 workflows |

**5. Honesty > hype.**

State limitations explicitly. Every top-performing README has a "limitations" section. Examples:
- nuwa: "蒸馏不了直觉。捕捉不了突变。"
- baogong: 铡刀门 10 条铁律 + 三色签标注
- luban: "强制停手点" + "你的疑问句不构成授权"

**6. Name your attack anchor explicitly.**

The fastest way to differentiate is to name what you're attacking:
- baogong attacks "AI 空泛润色（空泛形容词堆砌）"
- luban attacks "直接让 Agent 改"
- paoding attacks "看完 50 条笔记还是说不清任何一个为什么爆"

Generic claims like "better quality" don't work. Specific attacks do.

**7. Badge matrix is the cheapest social proof.**

Minimum: License + skills.sh status. Recommended: GitHub stars + runtime badges + any third-party endorsement. They signal legitimacy in under 1 second.

## Type 1: 作品产出型 (Output Type)

**Core question:** "What does this produce? Show me."

**Core strategy:** Screenshots, demos, and real examples dominate the first screen. The reader judges by seeing, not by reading.

### Mandatory sections (in order)

1. **Hook line** — one sentence that captures the unique value. Can be storytelling (nuwa: "你想蒸馏的下一个员工，何必是同事"), direct (guizang: "横向翻页网页 PPT"), or emotional (colleague-skill: "You AI guys are traitors to the codebase").
2. **Effect proof** — the most important section. Takes 40-60% of first screen. Full-width screenshots, real conversation examples, or GIF demos. NOT thumbnails, NOT descriptions of what it does. **Must appear before Install command** — readers need to see the output BEFORE they decide to install. If screenshots are unavailable (text-only README), use visual anchor descriptions (e.g., "像 Monocle 杂志贴上了代码") + conversation examples.
3. **Install + first use** — one command to install, one line to send to agent. Place AFTER Effect proof, not before.
4. **What it delivers** — structured list of output formats, quality guarantees.
5. **Honest limitations** — what it CANNOT produce, what it might get wrong.
6. **Real examples** — at least 2, preferably 3-4, showing different styles/use cases.

### Optional but powerful

- **Style variation preview** — if the skill has multiple styles/modes, show micro-thumbnails of each. guizang-ppt does this brilliantly with 5+4 theme previews.
- **Star history chart** — if the project has GitHub traction, show the growth curve.
- **Naming ritual** — create memorable names for your process steps. Creates brand identity (cailun's "章纸·方纸·对纸·招纸·流纸·据纸·签纸").

### Anti-patterns

- Describing output in text instead of showing it
- Using tiny thumbnails that require clicking to see
- Putting the install command after 3 paragraphs of philosophy

### Benchmark

Study `guizang-ppt-skill` README for screenshot-first layout, `nuwa-skill` README for storytelling + dialogue examples, `cailun-skill` README for ritual naming + iron laws.

### ✅ Verification Checklist (for the human)

Have someone who's never seen this skill read the README for 15 seconds, then ask them:
- [ ] Can they tell what this skill produces within 10 seconds?
- [ ] Can they see the output (not just read about it)?
- [ ] Do they know how to install it without scrolling?
- [ ] Can they name one thing that makes it different from similar tools?

If any answer is "no", the README is not done.

## Type 2: 提效/流程型 (Efficiency Type)

**Core question:** "How much better/faster/cheaper is this than my current approach?"

**Core strategy:** Before/After comparison is the soul. The form can vary—images, diffs, numbers, tables—but the comparison MUST be specific and quantified.

### Mandatory sections (in order)

1. **Pain point hook** — make the reader feel the pain they already know. Use rhetorical questions (luban: "你写了一个 Skill，自己用着挺好。然后呢？") or direct attacks (baogong: "别的工具给你润色。包公开堂——一条龙审完").
2. **Before/After comparison** — the most important section. Form depends on skill nature:
   - Visual output → full-width Before/After screenshot
   - Text output → diff-format comparison with specific line changes
   - Process improvement → numbers table (from X to Y, saving Z)
   - Method comparison → competitor comparison table
3. **Install + first use** — one command, one agent instruction.
4. **Process visualization** — show the workflow. The reader needs to understand WHAT changes, not just that something changes. Use tables, ASCII diagrams, or numbered steps.
5. **Quantitative proof** — real numbers from real usage. luban: "83,725 条回放、327 假 AI、15/20→4/20、806→523 卡". If no large-scale data, use specific case studies with measurable outcomes.
6. **Trust system** — efficiency skills need trust more than any other type. If the skill makes decisions autonomously, explain the safeguards. Examples: baogong's "铡刀门 10 条", luban's "强制停手点".
7. **Cost/limitations** — be honest about trade-offs. Does it consume more tokens? Require specific models? Have failure modes?

### Before/After forms (choose the right one)

```
# Form A: Visual diff (baogong)
Before: 负责数据分析相关工作，得到领导认可
After:  **数据监控体系**：搭建核心指标看板，覆盖 12 条业务线，
        异常检出从人工抽查（~2天）→ 实时告警

# Form B: Numbers table (luban)
| 指标 | 打磨前 | 打磨后 |
|------|--------|--------|
| 卡点数 | 20 | 4 |

# Form C: Competitor comparison (luban, paoding)
| 维度 | 直接让Agent改 | 鲁班 |
|------|-------------|------|
| 方法论 | 无 | 五动作体系 |

# Form D: Conversation comparison (caveman-style)
Before: [verbose agent response, 200 words]
After:  [caveman response, 50 words, same precision]
```

### Anti-patterns

- "Improves efficiency by 80%" without showing what 80% means
- Before/After that looks like the same thing rephrased
- No quantitative evidence at all
- Trust system missing or hand-wavy

### Benchmark

Study `baogong-skill` README for Before/After + trust system, `luban-skill` README for numbers + competitor comparison +反问共情, `paoding-skill` README for pain point scenarios.

### ✅ Verification Checklist (for the human)

Have someone who's never seen this skill read the README for 15 seconds, then ask them:
- [ ] Can they see a Before/After comparison in the first screen?
- [ ] Are the numbers specific (not "80% better" but "from X to Y, saving Z")?
- [ ] Is there a trust system (safeguards/limitations explicit)?
- [ ] Can they tell what process this improves without reading a paragraph?

If any answer is "no", the README is not done.

## Type 3: 能力增强型 (Capability Type)

**Core question:** "What capability does this add to my agent that it doesn't have now?"

**Core strategy:** Pattern checklists and coverage matrices. The reader needs to see the RANGE of new capabilities, not just one example.

### Mandatory sections (in order)

1. **Capability gap statement** — what the agent CANNOT do without this skill, in concrete terms.
2. **Pattern/capability checklist** — the strongest weapon for this type. List every pattern, detection rule, or capability the skill adds. Categorize them. humanizer does this brilliantly with 24 patterns in 5 categories (Content / Language / Style / Communication / Filler).
3. **Before/After capability demo** — show what the agent can do with the skill that it couldn't do before. NOT "before was bad, after is good" but "before: cannot do X at all → after: can do X, and here's proof."
4. **Coverage matrix** — if the skill covers multiple domains, show a table or visual of coverage. addyosmani's agent-skills uses a lifecycle diagram (Define → Plan → Build → Verify → Review → Ship).
5. **Install + activation** — how to install AND how to know it's working.
6. **Verification mechanism** — capability skills must prove they're working. "看起来正确" is never enough.

### Anti-patterns

- Describing capabilities abstractly without showing them in action
- Missing the pattern checklist — this is the #1 weapon, don't skip it
- No verification method — capability skills are invisible when they fail

### Benchmark

Study `humanizer` README for the 24-pattern checklist structure, `addyosmani/agent-skills` README for lifecycle organization + rationalization tables.

### ✅ Verification Checklist (for the human)

Have someone who's never seen this skill read the README for 15 seconds, then ask them:
- [ ] Can they see the FULL list of capabilities (not just one example)?
- [ ] Is there a Before/After capability demo ("can't do X" → "can do X")?
- [ ] Can they verify the skill is working (verification method stated)?
- [ ] Do they know how to activate the skill after install?

If any answer is "no", the README is not done.

## Type 4: 风格/视角型 (Style Type)

**Core question:** "What does it sound like? Let me feel the difference."

**Core strategy:** Generated text comparisons. The reader judges by reading, not by being told.

### Mandatory sections (in order)

1. **Style anchor** — one sentence that captures the essence. "江南体：画面先行，悲壮热血美学。" Not a description—a sample line in the style itself.
2. **3 comparison examples** — the soul of style-type READMEs. Each shows:
   - The same prompt
   - Generic AI output (left/before)
   - Style-specific output (right/after)
   - Brief annotation explaining what the style adds
3. **Trigger words** — exactly what phrases activate this style. Users need to know what to say to their agent.
4. **Underlying methodology** — what sources, principles, or frameworks the style is built from. This builds credibility. Can be a standalone section or woven into the Style anchor paragraph. For small/single-source styles, weaving is fine; for multi-source distillations (>5 sources), use a standalone section.
5. **When NOT to use** — style skills are easy to over-apply. Define the boundary.

### What makes a good comparison example

- Same input, two outputs side by side
- Realistic, non-trivial prompts the reader would actually use
- Annotation explains the difference, not just shows it
- At least one example from a domain the reader cares about (tech, product, writing)

### Anti-patterns

- Describing the style in adjectives without showing it
- Using toy examples that prove nothing
- Skipping the methodology section (style skills feel like magic without it)

### Benchmark

Study `nuwa-skill` README dialogue examples (Naval, Musk, Jobs, Zhang Xuefeng), `colleague-skill` README for emotional hook + dialogue flow.

### ✅ Verification Checklist (for the human)

Have someone who's never seen this skill read the README for 15 seconds, then ask them:
- [ ] Can they see 3 comparison examples (same input, two outputs)?
- [ ] Can they FEEL the difference by reading, not by being told?
- [ ] Do they know exactly what phrases trigger this style?
- [ ] Can they tell when NOT to use this style?

If any answer is "no", the README is not done.

## Type 5: 合集/目录型 (Collection/Catalog Type)

**Core question:** "What skills are available? Help me browse and choose."

**Core strategy:** Uniform format + quality standards + discoverable categorization. The reader needs to scan, not read. Every entry answers "what is it and why should I care" in one line.

**Note:** This type is for skill COLLECTIONS and awesome-lists, not for individual skills. If you're writing a README for a single skill, this type does not apply.

### Mandatory sections (in order)

1. **Collection positioning** — what kind of skills are curated here, what's the selection criteria. One paragraph max.
2. **Quality standards** — what makes a skill earn a spot in this list. heilcheng defines 6 criteria upfront. This simultaneously filters submissions and builds reader trust.
3. **Categorized listing** — skills organized by domain/provider, not by tech stack. Each entry: `[org/repo](link) — one-line description of what it does and why it matters`.
4. **Install guide for the ecosystem** — how to install skills from this collection. Link to platform/tool if applicable.
5. **Contribution guide** — how to submit, what standards to meet.

### What makes a good one-line description

```
# Good: tells you what AND why
[anthropics/skills](link) — Official Claude Code skills for documents (docx, pdf, pptx, xlsx)

# Bad: tells you what but not why
[anthropics/skills](link) — A collection of skills

# Bad: marketing fluff, no information
[some/skill](link) — Revolutionary AI-powered skill ecosystem platform
```

### Anti-patterns

- Alphabetical listing without categorization (forces linear scan)
- Entries without descriptions ("a skill" — meaningless)
- No quality standards (reader can't trust curation)
- Descriptions that are marketing copy instead of functional summaries

### Benchmark

Study `VoltAgent/awesome-agent-skills` for provider-based categorization, `heilcheng/awesome-agent-skills` for upfront quality criteria, `github/awesome-copilot` for badge-driven social proof at scale (35K stars).

### ✅ Verification Checklist (for the human)

Have someone who's never seen this collection read the README for 15 seconds, then ask them:
- [ ] Can they find a skill in the list within 10 seconds?
- [ ] Does every entry have a one-line description that tells what AND why?
- [ ] Are skills categorized (not just alphabetically listed)?
- [ ] Can they tell what quality standards a skill must meet?

If any answer is "no", the README is not done.

## Type 6: 平台/工具型 (Platform/Tool Type)

**Core question:** "How do I manage, install, or organize skills?"

**Core strategy:** One-command quickstart dominates. Progressive disclosure: the reader's first question is "how do I use this in the next 30 seconds?", not "what's the philosophy?".

**Note:** This type is for CLI tools, package managers, and platforms that handle skills. Examples: `npx skills`, `agentskills` spec, skill marketplaces.

### Mandatory sections (in order)

1. **One-command quickstart** — literally one line the user can copy-paste. `npx skills add <name>`. Must work. Must be visible in first screen area.
2. **Installation methods** — all supported ways to install/use the tool. Usually 2-3 methods ordered by simplicity.
3. **Core commands reference** — fast-scannable table of what you can do: install, list, search, remove, validate.
4. **Compatibility statement** — which agents, runtimes, platforms are supported. This is a core trust point for platform tools.
5. **Progressive disclosure** — quick start → common workflows → advanced features → create your own. Each section is progressively deeper. The reader self-selects their depth.

### Anti-patterns

- Starting with architecture diagrams before showing a single command
- "Revolutionary platform" language instead of "here's how to use it"
- Burying compatibility info (users will find out the hard way)

### Benchmark

Study `vercel-labs/skills` README for `npx` quickstart + progressive disclosure, `agentskills/agentskills` for spec-first presentation.

### ✅ Verification Checklist (for the human)

Have someone who's never used this tool read the README for 15 seconds, then ask them:
- [ ] Can they copy-paste one command and have it work?
- [ ] Can they find the compatibility statement without searching?
- [ ] Can they find the command they need in the reference table?
- [ ] Does the README answer "how do I use this?" before "what is this?"?

If any answer is "no", the README is not done.

## Type 7: 安全/专业领域型 (Security/Specialized Type)

**Core question:** "Can I trust this in my critical/production workflow?"

**Core strategy:** Domain authority established through precise terminology, verifiable results, and professional credibility signals. General audience tactics (emojis, casual tone) often work AGAINST you here — precision IS the marketing.

### Mandatory sections (in order)

1. **Domain positioning** — what specific security/domain problem does this solve, in precise technical terms. No marketing language.
2. **Trophy case / Results** — game-changing for this type. List real findings, bugs caught, vulnerabilities discovered. trailofbits uses "Found using Trail of Bits Skills" tags. This converts "I claim to detect X" into "I have detected X, here's proof."
3. **Verb-driven capability list** — use precise action verbs: Detect, Audit, Identify, Analyze, Prevent. Each verb maps to a concrete capability with a one-line explanation.
4. **Domain-specific badge/endorsement** — if applicable: compliance badges, certification references, industry recognition.
5. **Install + scope** — how to install AND what it will/won't touch. Security tools that "scan everything" scare users. Define the boundary precisely.

### Anti-patterns

- Casual tone or emoji-heavy presentation for security tools
- "Trust me" claims without verifiable results
- Vague capability descriptions ("helps with security" — how?)
- No scope definition (users fear the tool will break things)

### Benchmark

Study `trailofbits/skills` README for trophy case + verb-driven descriptions.

### ✅ Verification Checklist (for the human)

Have someone who's never seen this skill read the README for 15 seconds, then ask them:
- [ ] Can they see verifiable results (not just claims)?
- [ ] Can they tell exactly what the tool will/won't touch?
- [ ] Is the language precise (no casual tone/emoji)?
- [ ] Can they see domain-specific badges/endorsements?

If any answer is "no", the README is not done.

## Type 8: 科学/研究型 (Science/Research Type)

**Core question:** "What complex, multi-step workflows does this unlock?"

**Core strategy:** Domain categorization + complete workflow examples. Scientists and researchers evaluate tools by what workflows they enable, not by feature lists.

### Mandatory sections (in order)

1. **Domain matrix** — emoji + category name + skill count. K-Dense-AI uses 16 domains (🧬 Genomics, 💊 Drug Discovery, 🔬 Protein Design...). Instantly communicates breadth and specialization.
2. **Multi-step workflow examples** — the soul of this type. Show 2-3 COMPLETE workflows from start to finish. Not feature demos — real end-to-end research pipelines. Each workflow should answer: "What research question does this answer? What are the steps? What's the output?"
3. **Expectation management** — critical for this type. "Not a ceiling, but an accelerator." "Not replacing scientists, augmenting them." Preempt the "can it do my entire PhD?" question.
4. **Install + domain activation** — how to install AND how to activate specific domain capabilities.
5. **Social proof** — scientist count, citations, institutional affiliations. "160,000+ scientists" (K-Dense-AI) is powerful — it says "your peers are already using this."
6. **Star history / growth** — academic adoption curves build credibility.

### Anti-patterns

- Listing features without showing complete workflows they enable
- "AI-powered" language (scientists are skeptical of hype)
- Missing expectation management (scientists will find edge cases and judge harshly)
- No domain categorization (scientists search by their field, not by feature name)

### Benchmark

Study `K-Dense-AI/claude-scientific-skills` README for domain matrix + 6 multi-step workflow examples + "160,000+ scientists" social proof.

### ✅ Verification Checklist (for the human)

Have someone who's never seen this skill read the README for 15 seconds, then ask them:
- [ ] Can they see at least 2 complete workflow examples?
- [ ] Can they tell what domain this covers (not just "AI for science")?
- [ ] Is the expectation management clear ("not a ceiling, but an accelerator")?
- [ ] Can they see social proof (scientist count, institutional affiliations)?

If any answer is "no", the README is not done.

## Quick Reference: Section Checklist by Type

| Section | Output | Efficiency | Capability | Style | Collection | Platform | Security | Science |
|---------|--------|-----------|------------|-------|-----------|---------|---------|---------|
| Hook/positioning | Story/grab | Pain point | Gap statement | Style anchor | Selection criteria | One-command | Domain precision | Domain matrix |
| Effect proof | Screenshots | Before/After | Pattern list | 3 comparisons | Categorized list | Install methods | Trophy case | Workflow examples |
| Install | Required | Required | Required | Required | Ecosystem guide | Core commands | Scope boundary | Domain activation |
| Process/methodology | Output flow | Workflow viz | Coverage matrix | Source principles | Quality standards | Progressive disclosure | Verb-driven list | Expectation mgmt |
| Quantitative proof | Variants count | Real numbers | Verification | N/A | Entry count | Compatibility | Verified findings | Scientist count |
| Trust system | Limitations | Safeguards | Verification | Boundaries | Curation criteria | — | Domain badges | Star history |
| Real examples | 3-4 demos | Case studies | Activation demo | Trigger words | — | Workflows | — | — |

## Common Mistakes

### Applying the wrong type strategy

Using screenshots for an efficiency skill (shows nothing about improvement). Using text descriptions for an output skill (reader can't see the output). Identify the type FIRST, then choose the strategy.

### Treating README as a shorter SKILL.md

The worst READMEs copy-paste SKILL.md content. SKILL.md tells the agent HOW to work. README tells the human WHY to install. Different audience, different content.

### Missing the install command in first screen

If the reader scrolls past 3 paragraphs to find the install command, they've already bounced. Install command must be in the first visible area.

### No limitations section

Every skill has limits. Stating them builds trust. Hiding them destroys it. All 4 benchmark READMEs (baogong, luban, nuwa, guizang) have explicit limitation sections.

### Generic "improves quality" claims

"Better", "faster", "higher quality" are invisible. Show specific changes. "异常检出从人工抽查（~2天）→ 实时告警" beats "提升数据监控效率" every time.

## Further Reading

The full 22-sample research dataset with per-sample analysis is in [references/research-data.md](references/research-data.md). Load it when you need detailed competitive analysis, specific README structure breakdowns, or want to see how a particular benchmark handles a specific section.
