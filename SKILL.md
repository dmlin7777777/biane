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

### Step 1: Identify type → 🔴 CP1

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

**🔴 CP1 — 类型确认：** 展示判断结果和理由，等用户确认后再进入 Step 2。用户纠正类型 → 不要 patch，从 Step 2 重新开始。

### Step 2: ONE proof + hero 定位 → 🔴 CP2

Find the matching Type (1-8) below. Each card has a "ONE proof" line — this is the single element that will do 80% of the convincing. Before writing anything, identify what this proof IS for the user's skill.

Then draft the hero positioning (1-2 sentences). This is where agent judgment diverges from user intent most often — the agent defaults to abstract descriptions, but the user knows which capability is the real differentiator.

**Hero 定位句规则：**
- 必须说清"从什么到什么"，每个动词具体（不是"针对X的Y工具"）
- 最有差异化的能力放在第一个动词位置
- 品牌隐喻放在 quote / section 标题里，不放在定位句里——两者分工明确
- 正例（luban）：「把一个"能用的Skill"，打磨成"能被理解、能被安装、能被传播、能被验证、能持续进化"的公共资产」
- 反例：「针对 JD 交互式定制简历的求职教练」—— 太抽象，任何同类工具都能这么说

**🔴 CP2 — ONE proof + hero 确认：** 同时展示两项判断，等用户确认：

```
"ONE proof: [具体是什么]
 Hero 定位句: [1-2 句，纯具体动作链]
 → 这两个方向对吗？"
```

这是最关键的决策点。ONE proof 错了整个 README 方向就错，hero 定位句抽象了用户一定会要求返工。等用户确认后再动笔。

**Boundary rule:** Types 5-8 are specialized (collection, platform, security, science). If the skill doesn't clearly match, default to Types 1-4.

### Step 3: Draft + verify → 🔴 CP3

Write the full README following the type card's mandatory sections + Universal Structure.

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

**🔴 CP3 — 全稿确认：** Cross-reference check 通过后，展示完整 README 给用户审阅。用户可能要求调整任何部分——如果涉及类型或 ONE proof 变更，回退到 CP1/CP2 而不是 patch。

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

Every README starts with the hero block from [templates/hero.md](templates/hero.md), then follows the type-specific template（每个 Type card 的 **Template** 行指向对应模板）。

Hero block encodes the universal layer all types share:
1. **Hero block** — centered title + optional brand quote + badge row + hero positioning sentence
2. **Badge row** — version, license, Agent Skills, skills.sh, runtime compatibility. Add stars badge once repo has traction
3. **Hero positioning** — 1-2 sentences following the rules in Step 2 (specific action chain, most differentiating capability first)

Fill in template placeholders, delete sections that don't apply.

## Visual Toolkit（视觉素材制作）

人是视觉动物。截图 > 描述，GIF > 说明书，信息图 > 表格文字。README 里每个"放截图"的位置都应该真的有截图。

详细制作指南见 [references/visual-toolkit.md](references/visual-toolkit.md)，核心工具链：

| 场景 | 推荐 Skill | 产出 |
|------|-----------|------|
| 产品截图/对比信息图/流程 GIF | `huashu-design` | HTML→截图/GIF/MP4 |
| 流程图/架构图 | `excalidraw-diagram` | .excalidraw + PNG |
| 数据图表 | `show_widget`（内置） | SVG 内联 |
| 品牌海报/头图 | `canvas-design` | PNG/PDF |

**工作流：** 先用模板写完文字 → 标记 `<!-- TODO: 视觉素材 -->` → 调用对应 skill 批量制作 → 替换占位符。

没有设计 skill 时的后备：Mermaid 代码块（GitHub 原生渲染）、对话示例代码块、shield.io 徽章。

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
**ONE proof:** A real output screenshot or demo that takes 40-60% of first screen. Reader decides by seeing, not reading.
**Proof format:** Full-width screenshots, GIFs, or rendered conversation output.
**Template:** [templates/type-1-output.md](templates/type-1-output.md)

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
**ONE proof:** A Before/After comparison that makes the improvement undeniable in one glance.
**Proof format:** Side-by-side table (preferred), diff, numbers table, or competitor comparison.
**Template:** [templates/type-2-efficiency.md](templates/type-2-efficiency.md)

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
**ONE proof:** The categorized pattern/capability checklist. The list IS the pitch — readers scan it and self-assess.
**Proof format:** Categorized pattern/capability list + before/after capability demo.
**Template:** [templates/type-3-capability.md](templates/type-3-capability.md)

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
**ONE proof:** Side-by-side text comparison — same prompt, generic vs styled output. The reader FEELS the difference. If this doesn't land, nothing else will.
**Proof format:** Same prompt → generic output vs styled output, side by side.
**Template:** [templates/type-4-style.md](templates/type-4-style.md)

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
**ONE proof:** The categorized listing itself — scan speed IS the product quality. 10 秒内找到相关 skill 就成功。
**Proof format:** Categorized tables with functional one-line descriptions.
**Template:** [templates/type-5-collection.md](templates/type-5-collection.md)

For skill COLLECTIONS and awesome-lists, not individual skills.

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
**ONE proof:** The one-command quickstart. Copy-paste 能跑 = 信任建立完成。
**Proof format:** Copy-pasteable commands + compatibility matrix.
**Template:** [templates/type-6-platform.md](templates/type-6-platform.md)

For CLI tools, package managers, and platforms that handle skills.

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
**ONE proof:** The trophy case — real findings, real bugs caught. "I have detected X, here's the CVE" vs "I claim to detect X." Precision IS the marketing.
**Proof format:** Trophy case (real findings) + verb-driven capability list + standards coverage.
**Template:** [templates/type-7-security.md](templates/type-7-security.md)

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
**ONE proof:** A complete end-to-end workflow example — research question to final output. Researchers evaluate by "can this do MY pipeline?"
**Proof format:** Domain matrix + end-to-end pipeline examples + institutional/usage proof.
**Template:** [templates/type-8-science.md](templates/type-8-science.md)

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

## Entry Modes

Workflow assumes "write from scratch," but users also arrive with existing READMEs or incomplete inputs. Detect entry mode before Step 1:

**Mode W (Write):** No existing README, or user explicitly says "帮我写 README." → Standard workflow (Step 1 → 2 → 3).

**Mode R (Review/Improve):** User says "优化 README" / "review this README" / provides existing README.
1. Read existing README + SKILL.md
2. Score against Iron Laws (8-item checklist, pass/fail each)
3. Identify type from existing README structure (skip CP1 if obvious)
4. 🔴 CP-R: Present diagnosis — which laws fail, which type card sections are missing/weak, hero positioning quality. Ask user: "全部重写 or 定向修改?"
5. Full rewrite → enter Step 1 as normal. Targeted fix → edit specific sections, run cross-reference check, → CP3

**Mode S (No SKILL.md):** User provides only a repo URL or existing README, no SKILL.md available.
1. Read all available context (README, repo structure, code comments, package.json description)
2. Infer skill capabilities from what's available — but mark all inferences as `[推断]`
3. 🔴 CP-S: Present inferred capabilities, ask user to confirm/correct before writing
4. Proceed to Step 1 with confirmed capabilities as source of truth (replacing SKILL.md)
5. Cross-reference check (Step 3) runs against user-confirmed capabilities instead of SKILL.md

## Failure Modes

**Can't determine type in 2 questions →** Default to Type 2 (Efficiency). Its B/A + trust system is the most transferable. Note "type uncertain" for future improvement.

**Skill doesn't match any type →** Use Type 2 baseline, skip verification checklist, ask user for a README they admire.

**Multi-type conflict →** A skill can look like two types (e.g., baogong produces resumes = Type 1, but core value is the process = Type 2). Resolution: ask "What question does the reader ask FIRST — 'what does it produce?' or 'how is it better than what I do now?'" The answer picks the primary type. The secondary type's proof can appear as a supporting section but doesn't drive the README structure.

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
