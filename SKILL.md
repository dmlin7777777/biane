---
name: skill-readme-writer
version: "2.0"
description: >
  Use when the user needs to write, improve, or review a README.md for an Agent Skill.
  Triggers: "write a README for my skill", "improve my skill's README", "review this README",
  "帮我写 README", "优化 README", "怎么写 skill 的 README", "README 不够好".
  Covers 8 skill types, each requiring a different README strategy because each answers
  a different human decision question.
  NOT for traditional project READMEs (Install/Usage/Contributing) — those are a different format.
---

# Skill README Writer

Traditional project READMEs don't work for Agent Skills. A Skill README is a **sales page** — it answers "should I install this?" in 10 seconds. The SKILL.md handles the agent; the README handles the human.

Different skill types need different proof. A PPT generator proves itself with screenshots; a debugger proves itself with Before/After comparison. This skill identifies the type first, then applies the matching strategy.

## Workflow

### Step 1: Identify type

Ask what the skill does. State your judgment in plain language the user can verify:

```
"Your skill produces [specific output] — that's Output Type.
 The README should lead with screenshots of the output."
→ User confirms: "yes, it produces PPT files" or "no, it's not that"

"Your skill makes [process] faster/better — that's Efficiency Type.
 The README needs a Before/After comparison."
→ User confirms: "yes, it saves time" or "no, it adds capability"
```

Do NOT ask "is this Type 3?" — the user doesn't know the taxonomy. Ask about behavior.

If unclear after 2 questions → default to Type 2 (Efficiency). Its Before/After + trust system is the most transferable baseline.

### Step 2: Load type card + identify the ONE proof

Find the matching Type (1-8) below. Each card has a "ONE proof" line — this is the single element that will do 80% of the convincing. Before writing anything, identify what this proof IS for the user's skill:

```
"For your skill, the ONE proof is [specific thing].
 If this lands, readers install. If it doesn't, nothing else saves it.
 I'll build the README around this."
```

**Boundary rule:** Types 5-8 are specialized (collection, platform, security, science). If the skill doesn't clearly match, default to Types 1-4.

### Step 3: Draft + verify

After each major section, show a 2-line summary:

```
Section: Hook + Before/After comparison
Answers: "should I install?" in 10 seconds
→ Does this feel right?
```

**Cross-reference check (mandatory after full draft):**
Re-read the target skill's SKILL.md and verify:
- Every claim in README traces to SKILL.md
- Every number (pattern count, step count, percentage) matches SKILL.md
- No section implies capability SKILL.md doesn't implement
- Conversation examples show behavior consistent with SKILL.md instructions

If a claim can't be traced back, remove it or flag it. Don't round up, don't extrapolate. Agent 在总结时天然倾向"圆"出更完整的能力——这个检查就是拦这个的。

## 8 Iron Laws

All types, no exceptions.

| # | Law | How to check | Fail signal |
|---|-----|-------------|-------------|
| 1 | First screen answers "should I install?" | Hook + proof + install visible without scrolling | Feature list with no proof; install below the fold |
| 2 | Install command in first scroll range | Copy-pasteable `npx skills add` or equivalent | Reader must scroll to find install |
| 3 | Conversation example > code example | At least 1 `User: / Agent:` dialogue | `from skill import X; result = run()` |
| 4 | Proof format matches type | See type card below | Screenshots for efficiency skill; text for output skill |
| 5 | Honesty > hype | Specific limitations section exists | "Best tool ever" with no caveats |
| 6 | Attack target named | Specific problem or competitor called out by name | "Better than traditional approaches" |
| 7 | Social proof layered | Badges + at least one deeper signal | Badges only, or no proof at all |
| 8 | Emotional connection present | Origin story, personal pain, or relatable frustration | Pure feature list with no human voice |

**Law 3 format reference:**
```
User: "审一下这份 JD — 腾讯微信事业群高级产品经理"
Agent: "JD 解析完成。量化追问第 1 轮..."
```
NOT: `from skill import analyze_jd; result = analyze_jd("job.pdf")`

**Law 7 deeper signals** (beyond badges): usage data, real testimonials with links, third-party validation, methodology transparency. When too new for usage data, the creator's research process IS the social proof.

**Law 8 elements:** "I built this because [pain]. The existing options [gap]." Even 2 sentences of origin story beat 10 feature bullets.

## Universal Structure (all types)

Before any type-specific section, every README starts with:

1. **Title + badge row** — skill name as H1, then badges (version, license, stars if applicable). Badges = first social proof signal (Iron Law 7)
2. **One-line positioning** — what this skill does, in one sentence. Comes from the skill's `description` field

Then proceed to the type card's Mandatory sections (Hook, Proof, etc.).

## 4 Writing Principles (from 35-sample research)

Iron Laws say WHAT must be in the README. These principles say HOW to write it. They emerged from analyzing why the highest-performing READMEs in the dataset outperform — and are more important than any individual section checklist.

**Principle 1: Find the ONE dominant proof.**

Every high-star README has one thing that does 80% of the convincing:
- guizang = the full-width screenshots
- humanizer = the 33-pattern checklist
- colleague = "You AI guys are traitors to the codebase"
- karpathy = the 4 rules themselves
- academic-research = the 4-skill pipeline diagram

No one succeeds with "10 features, equally weighted." Readers don't read READMEs — they scan. They hit one proof strong enough to decide, or they leave.

**Your first job in Step 2 is to identify this ONE proof for the user's skill. Every type card below has a "Proof format" line — that's where the ONE proof lives. Everything else is supporting structure.**

**Principle 2: Proof must touch every claim.**

Strong READMEs: `claim → proof (within 3 lines) → claim → proof → claim → proof`
Weak READMEs: `claim → claim → claim → ... → proof section (reader already gone)`

Every assertion needs evidence within 3 lines. Not "we'll prove it later" — proof and claim travel as a unit. A Limitations section the reader never scrolls to is the same as no Limitations section.

**Principle 3: Name what you're killing.**

Every individual skill that broke 1K stars has a named attack target:
- luban → "直接让 Agent 改"
- paoding → "看完 50 条笔记还是说不清为什么爆"
- colleague → "traitors to the codebase"

"Better than existing tools" = invisible. Naming the specific pain/competitor/bad-practice creates instant "I have that problem!" recognition.

This is the single highest-ROI sentence in any Skill README. It belongs in the first 3 lines, not buried in a comparison table.

**Principle 4: Brand metaphor runs through, not just the hook.**

High-star Chinese skills share one pattern: the cultural metaphor doesn't stop at the hook — it runs through section names, process descriptions, and terminology choices:
- cailun（蔡伦）→ "造纸三律" + 7 种纸命名贯穿全文
- baogong（包公）→ "堂审四幕"（调卷宗/当堂陈词/案卷归档/应对回话）+ 铡刀门
- paoding（庖丁）→ 解牛隐喻贯穿分析流程

The metaphor is not decoration — it's a memory anchor. Readers remember "堂审四幕" long after they forget "4-Phase Pipeline." When a skill has a natural metaphor, weave it into section headings and key terms. When it doesn't, don't force one — a clean technical README (karpathy style) beats a bad metaphor.

---

## Type 1: 作品产出型 (Output)

**Decision question:** "What does this produce? Show me."
**ONE proof:** A real output screenshot or demo that takes 40-60% of first screen. Reader decides by seeing, not reading. Everything else supports this.
**Proof format:** Full-width screenshots, GIFs, or rendered conversation output.

**Mandatory sections (in order):**
1. **Hook** — one sentence: storytelling, direct, or emotional
2. **Effect proof** — 40-60% of first screen. Real output, not descriptions. Must appear BEFORE install. If no screenshots, use visual anchor descriptions + conversation examples
3. **Install + first use** — one command to install, one line to send to agent
4. **Deliverables** — output formats and quality guarantees
5. **Limitations** — what it cannot produce, what it might get wrong
6. **Examples** — at least 2, showing different styles/use cases

Optional: style variation thumbnails, star history chart, naming ritual for process steps.

**Anti-patterns:** describing output in text instead of showing it · tiny thumbnails · install after philosophy

**Benchmarks:** `guizang-ppt-skill` (screenshot-first layout, dual visual system), `nuwa-skill` (storytelling + star history, multi-language), `cailun-skill` (6 real screenshots + naming ritual)

**Verify (first-time reader, 15 seconds):**
- [ ] Can they see what the skill produces (not just read about it)?
- [ ] Can they install without scrolling?
- [ ] Can they name one differentiator?
- [ ] Do they see what interacting with this skill looks like?

---

## Type 2: 提效/流程型 (Efficiency)

**Decision question:** "How much better/faster is this than what I do now?"
**ONE proof:** A Before/After comparison that makes the improvement undeniable in one glance. This single comparison does 80% of the convincing.
**Proof format:** Side-by-side table (preferred), diff, numbers table, or competitor comparison.

**Mandatory sections (in order):**
1. **Pain point hook** — rhetorical question or direct attack that makes reader feel the pain
2. **Before/After comparison** — the most important section. Choose the right form:
   - **Side-by-side table** (default) — columns: Before | After, rows: specific metrics. Best scannability
   - **Numbers table** — from X → Y, saving Z. Best for quantifiable improvements
   - **Competitor comparison table** — columns: Old Way | This Skill. Best for method displacement
   - **Diff format** — red/green or strikethrough. Best for text transformation
   - Avoid: sequential top-bottom blocks without visual separation — readers can't compare what they can't see simultaneously
3. **Install + first use** — one command, one agent instruction
4. **Process visualization** — workflow as table, diagram, or numbered steps
5. **Quantitative proof** — real numbers from real usage, or specific case studies with measurable outcomes
6. **Trust system** — safeguards, limits, failure modes. Efficiency skills need trust most
7. **Limitations** — honest trade-offs (tokens, model requirements, failure modes)

**Anti-patterns:** "80% better" without showing what that means · B/A that looks like rephrasing · no quantitative evidence · trust system missing

**Benchmarks:** `luban-skill` (numbers + competitor comparison table + demo GIF), `paoding-skill` (pain point scenarios + symmetric phrasing + zero API), `karpathy-skills` (176K⭐ extreme minimalism: 4 rules, no B/A, pure problem→solution — proves clarity alone can win at scale)

**Verify (first-time reader, 15 seconds):**
- [ ] Can they see a Before/After in the first screen?
- [ ] Are numbers specific (not "80% better" but "from X to Y")?
- [ ] Is there a trust system (safeguards explicit)?
- [ ] Can they tell what process this improves without reading a paragraph?

---

## Type 3: 能力增强型 (Capability)

**Decision question:** "What can my agent do now that it couldn't before?"
**ONE proof:** The categorized pattern/capability checklist. When readers see the full list of what you detect/transform, they self-assess whether they need it. The list IS the pitch.
**Proof format:** Categorized pattern/capability list + before/after capability demo.

**Mandatory sections (in order):**
1. **Capability gap** — what the agent cannot do without this skill, concretely
2. **Pattern/capability checklist** — list every pattern, rule, or capability added. Categorize them. This is the strongest weapon for this type
3. **Before/After capability demo** — "cannot do X → can do X" (not "bad → good")
4. **Coverage matrix** — if multi-domain, show coverage table or lifecycle diagram
5. **Install + activation** — how to install AND how to know it's working
6. **Verification mechanism** — capability skills must prove they work. "Looks correct" is never enough

**Anti-patterns:** abstract descriptions without demos · missing pattern checklist · no verification method

**Benchmarks:** `humanizer` (33 patterns in 5 categories + per-pattern B/A), `code-review-skill` (1K⭐, four-phase flowchart + severity color coding, bilingual), `addyosmani/agent-skills` (lifecycle organization + rationalization tables)

**Verify (first-time reader, 15 seconds):**
- [ ] Can they see the full capability list (not just one example)?
- [ ] Is there a capability demo ("can't → can")?
- [ ] Can they verify the skill is working?
- [ ] Do they know how to activate it?

---

## Type 4: 风格/视角型 (Style)

**Decision question:** "What does it sound like? Let me feel the difference."
**ONE proof:** Side-by-side text comparison — same prompt, generic vs styled output. The reader FEELS the difference without being told. If this comparison doesn't land, nothing else will.
**Proof format:** Same prompt → generic output vs styled output, side by side.

**Mandatory sections (in order):**
1. **Style anchor** — one sentence IN the style itself, not describing the style
2. **3 comparison examples** — same prompt, generic vs styled output, with brief annotation explaining the difference
3. **Trigger words** — exactly what phrases activate this style
4. **Methodology** — sources, principles, or frameworks. Builds credibility. Weave into Style anchor for simple styles; standalone section for multi-source distillations
5. **When NOT to use** — style skills are easy to over-apply. Define the boundary

Good comparisons use realistic prompts the reader would actually use, and annotate the difference rather than just showing it.

**Anti-patterns:** describing style in adjectives without showing it · toy examples · no methodology

**Benchmarks:** `nuwa-skill` (multi-perspective dialogue: Naval, Musk, Jobs), `colleague-skill` (19.4K⭐, emotional hook + multi-source distillation)

**Verify (first-time reader, 15 seconds):**
- [ ] Can they see 3 comparisons (same input, two outputs)?
- [ ] Can they FEEL the difference by reading?
- [ ] Do they know what phrases trigger this style?
- [ ] Can they tell when NOT to use it?

---

## Type 5: 合集/目录型 (Collection)

**Decision question:** "What skills are available? Help me browse and choose."
**ONE proof:** The categorized listing itself — its scan speed IS the product quality. If a reader can find a relevant skill in 10 seconds, the README works.
**Proof format:** Categorized tables with functional one-line descriptions.

For skill COLLECTIONS and awesome-lists, not individual skills.

**Mandatory sections (in order):**
1. **Collection positioning** — what's curated, selection criteria. One paragraph max
2. **Quality standards** — what earns a spot. Filters submissions AND builds trust
3. **Categorized listing** — by domain/provider, not tech stack. Each entry: `[org/repo](link) — what AND why`
4. **Install guide** — how to install skills from this collection
5. **Contribution guide** — submission process and standards

Good one-liner: tells what AND why. Bad: "A collection of skills." Worse: "Revolutionary AI-powered ecosystem."

**Anti-patterns:** alphabetical without categories · entries without descriptions · no quality standards

**Benchmarks:** `awesome-cursorrules` (40K⭐, 13-category index), `alirezarezvani/claude-skills` (18.2K⭐, cross-platform compatibility matrix), `travisvn/awesome-claude-skills` (13.5K⭐, "Skills vs Other Approaches" comparison)

**Verify (first-time reader, 15 seconds):**
- [ ] Can they find a skill within 10 seconds?
- [ ] Does every entry tell what AND why?
- [ ] Are skills categorized (not alphabetical)?
- [ ] Can they tell the quality standards?

---

## Type 6: 平台/工具型 (Platform)

**Decision question:** "How do I manage/install/organize skills?"
**ONE proof:** The one-command quickstart. If the reader can copy-paste one line and it works, trust is established. Everything after is progressive disclosure.
**Proof format:** Copy-pasteable commands + compatibility matrix.

For CLI tools, package managers, and platforms that handle skills.

**Mandatory sections (in order):**
1. **One-command quickstart** — one copy-paste line, must work, must be in first screen
2. **Installation methods** — all supported ways, ordered by simplicity
3. **Core commands** — scannable table (install, list, search, remove, validate)
4. **Compatibility** — agents, runtimes, platforms supported. Core trust point
5. **Progressive disclosure** — quick start → common workflows → advanced → create your own

**Anti-patterns:** architecture diagrams before commands · "revolutionary platform" language · buried compatibility

**Benchmarks:** `vercel-labs/skills` (npx quickstart + progressive disclosure), `daymade/claude-code-skills` (1.2K⭐, marketplace-as-README: per-skill GIF demo cards)

**Verify (first-time reader, 15 seconds):**
- [ ] Can they copy-paste one command and have it work?
- [ ] Can they find the compatibility statement?
- [ ] Can they find the command they need?
- [ ] Does the README answer "how to use" before "what is this"?

---

## Type 7: 安全/专业领域型 (Security)

**Decision question:** "Can I trust this in my critical workflow?"
**ONE proof:** The trophy case — real findings, real bugs caught, real vulnerabilities discovered. "I claim to detect X" vs "I have detected X, here's the CVE." Casual tone works AGAINST you here — precision IS the marketing.
**Proof format:** Trophy case (real findings) + verb-driven capability list + standards coverage.

**Mandatory sections (in order):**
1. **Domain positioning** — specific problem, precise technical terms. No marketing language
2. **Trophy case** — real findings, bugs caught, vulnerabilities discovered. Converts "I claim" into "I have proven"
3. **Verb-driven capability list** — Detect, Audit, Identify, Analyze, Prevent. Each verb → one concrete capability
4. **Standards/endorsement** — compliance badges, OWASP/ASVS coverage, certification references
5. **Install + scope** — how to install AND what it will/won't touch. Define boundary precisely

**Anti-patterns:** casual tone or emoji · "trust me" without results · vague "helps with security" · no scope definition

**Benchmarks:** `trailofbits/skills` (trophy case + verb-driven, 10 domains), `code-audit` (750⭐, anti-hallucination methodology + 55+ vuln types), `claude-code-owasp` (234⭐, OWASP Top 10:2025 + ASVS 5.0 standards matrix)

**Verify (first-time reader, 15 seconds):**
- [ ] Can they see verifiable results (not claims)?
- [ ] Can they tell exactly what the tool will/won't touch?
- [ ] Is the language precise (no casual emoji)?
- [ ] Can they see standards coverage or endorsements?

---

## Type 8: 科学/研究型 (Science)

**Decision question:** "What complex workflows does this unlock for my research?"
**ONE proof:** A complete end-to-end workflow example — from research question to final output. Researchers evaluate by "can this do MY pipeline?", not by feature counts.
**Proof format:** Domain matrix + end-to-end pipeline examples + institutional/usage proof.

**Mandatory sections (in order):**
1. **Domain matrix** — emoji + category + skill count. Communicates breadth instantly
2. **Workflow examples** — 2-3 COMPLETE end-to-end pipelines (not feature demos). Each: research question → steps → output
3. **Expectation management** — "accelerator, not replacement." Preempt the "can it do my PhD?" question
4. **Install + domain activation** — how to install AND activate specific domain capabilities
5. **Social proof** — scientist count, citations, institutional affiliation

**Anti-patterns:** features without workflows · "AI-powered" hype · missing expectation management · no domain categorization

**Benchmarks:** `academic-research-skills` (31.7K⭐, 4-skill pipeline + human-in-the-loop + anti-hallucination gates), `Stanford REAP` (1.9K⭐, institutional backing + "verify yourself in 2 minutes"), `K-Dense-AI` (17 domains + "160,000+ scientists")

**Verify (first-time reader, 15 seconds):**
- [ ] Can they see at least 2 complete workflow examples?
- [ ] Can they tell what domain this covers?
- [ ] Is expectation management clear?
- [ ] Can they see social proof (count, institution)?

---

## Quick Reference

| Section | Output | Efficiency | Capability | Style | Collection | Platform | Security | Science |
|---------|--------|-----------|------------|-------|-----------|---------|---------|---------|
| Hook | Story/grab | Pain point | Gap statement | Style anchor | Criteria | One-command | Domain precision | Domain matrix |
| Proof | Screenshots | Before/After | Pattern list | 3 comparisons | Categorized list | Install methods | Trophy case | Workflows |
| Install | After proof | After B/A | + activation | + triggers | Ecosystem guide | IS the hook | + scope | + domain |
| Trust | Limitations | Safeguards | Verification | Boundaries | Quality standards | Compatibility | Standards | Expectation mgmt |
| Social proof | Demo count | Savings numbers | Pattern count | User count | Entry count | Install count | Audit cases | Scientist count |
| Emotional hook | Creator story | Pain resonance | "I kept seeing" | "I want to sound like" | Curation philosophy | "Tired of switching" | "I got burned" | Research motivation |

## Failure Modes

**Can't determine type in 2 questions →** Default to Type 2 (Efficiency). Its B/A + trust system is the most transferable. Note "type uncertain" for future improvement.

**Skill doesn't match any type →** Use Type 2 baseline, skip verification checklist, ask user for a README they admire.

**User corrects type mid-draft →** Stop. Ask user to describe the skill in their own words. Restart from Step 2. Do NOT patch — rewrite is faster.

**Any failure after 2 rounds →** Conservative README: hook + install + 1 example + 1 limitation. Append `<!-- WARNING: Fallback mode. Type not determined. -->`.

## Common Mistakes

- **Wrong type strategy** — screenshots for efficiency, text for output. Identify type FIRST.
- **README = shorter SKILL.md** — SKILL.md tells agent HOW. README tells human WHY. Different audience.
- **Install buried** — past 3 paragraphs = bounced. First scroll range, always.
- **No limitations** — stating limits builds trust. Hiding them destroys it.
- **Generic claims** — "better/faster" is invisible. "从~2天→实时告警" beats "提升效率" every time.

## References

35-sample research dataset with per-sample analysis: [references/research-data.md](references/research-data.md).
