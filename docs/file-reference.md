# File Reference

What's in each file, what it's for, and when to open it. Read this instead of opening all seven.

---

## At a glance

| File | Lines | Type | Read it when |
|------|------:|------|--------------|
| `vibe-skill-creator-SKILL.md` | 676 | Skill | You're building a skill |
| `cold-outreach-SKILL.md` | 454 | Skill | You're writing outreach, or need a model of a finished skill |
| `bad-skill-patterns.md` | 530 | Reference | Your skill feels flat and you can't say why |
| `research-methodology.md` | 347 | Reference | Step 3 of the build, or research keeps coming back shallow |
| `research-example-ai-creative.md` | 350 | Case study | You want to see the whole research process done well |
| `START-HERE.md` | 187 | Upstream doc | Historical: the original 3-minute intro |
| `SHAREABLE-README.md` | 160 | Upstream doc | Historical: the original distribution readme |

---

## `vibe-skill-creator-SKILL.md`

The main file. A guided process for building skills, written as a skill itself — which is worth noticing: it follows its own rules (expert voice, principles with reasons, anti-patterns, real examples, checklist).

**Structure:**

| Section | Contents |
|---------|----------|
| Frontmatter | `name: vibe-skill-creator`, trigger keywords: build skill, create skill, improve skill, help me make a skill |
| Core Truths | Four non-negotiables: expertise transfer not instructions; flow not friction; voice matches domain; focused beats comprehensive |
| Works for Any Domain | Table of six non-marketing domains (code docs, investor updates, RFCs, legal briefs, product specs, academic writing) with what the model gets wrong and what a skill would fix |
| The Process | ASCII flow of the steps |
| Steps 1–10 | Each step's questions, actions, examples, and gates |
| What Claude's Default Gets Wrong | Eight-row table: documentation voice → expert voice, comprehensive → focused, etc. |
| Skills vs Subagents | When a job should be a skill (execution) versus a subagent (research) |
| Self-Review Checklist | Six categories to clear before shipping |
| References | Pointers to the three supporting docs |

**Most valuable parts, if you read only fragments:**

- **The Audience-Intel Lesson** (Truth 2) — the package's own failure story: excellent audience research made the copy *worse* because it created pressure to use all of it. The clearest argument against comprehensive skills anywhere in the repo.
- **Step 2** — the exploration protocol, with the full before sample and its diagnosis. This is the mechanism that makes the rest work.
- **Step 6** — five critique criteria with the "if X, do Y" correction for each.
- **Step 10** — the decision table for when a skill needs reference material at all.

**Known quirk:** the process is described as ten steps, but the ASCII diagram in the file draws nine boxes (Step 10, reference material, is missing from the diagram). The prose is complete.

---

## `cold-outreach-SKILL.md`

A complete, usable skill for cold email, LinkedIn DMs, and X/Twitter DMs — and the worked example the build process refers back to.

**Structure:**

| Section | Contents |
|---------|----------|
| Why Most Cold Outreach Fails | The 2-second threat-detection filter; what triggers instant deletion vs. what passes |
| Seven Core Principles | Research is the message; give before you ask; show don't claim; short beats long; soft CTA; follow up; timing/trigger events |
| Frameworks | Alex Berman's 3C's, Josh Braun's 4T, Will Allred's Mouse Trap — each with a worked example |
| Platform Tactics | Email (word counts, subject lines, send windows), LinkedIn (engage before DMing), X/Twitter (warm-up sequence) |
| Anti-Patterns | Eight phrases that kill replies, structural mistakes, tone mistakes |
| Before/After | Two full rewrites (video agency, freelance designer) with "what changed" breakdowns |
| The Writing Process | Six-step sequence from research to softened CTA |
| Quality Checklist | Seven checks, ending with "would *you* reply to this?" |

**Numbers it asserts** (from the source material, not benchmarked here):

- Each long sentence reduces reply rate by 17%
- Target under 80 words, 3 short paragraphs
- 55% of replies come from follow-ups
- 4–5 touches minimum, 3–5 business days apart
- Generic outreach: 1–3% reply rate; researched: 15–25%

**Most reusable artifact:** the four-email follow-up sequence, complete with day markers (0, 4, 9, 15) and the reasoning for why each email adds a new angle rather than bumping the thread.

---

## `bad-skill-patterns.md`

Ten failure modes, each with a bad example, an explanation of why it fails, and a rewritten good version. This is the diagnostic tool — when a skill underperforms and you can't articulate why, the answer is usually one of these.

| # | Pattern | The tell |
|---|---------|----------|
| 1 | Documentation voice | Reads like a wiki; no point of view |
| 2 | Procedure over principle | "Step 1, Step 2" with no reasoning |
| 3 | Comprehensive coverage | Every platform, every format, no priorities |
| 4 | Generic tool references | "Use descriptive prompts" instead of a real model ID and prompt |
| 5 | Missing anti-patterns | Only says what to do |
| 6 | Friction creation | Produces intermediate documents instead of deliverables |
| 7 | Over-engineered structure | Matrices and phase protocols nobody uses |
| 8 | Theoretical examples | "Widget Pro 3000" |
| 9 | Missing the why | Rules that can't be adapted |
| 10 | The "just in case" addition | Sections that don't change output |

**The meta-pattern** (end of file): all ten are the same mistake — written for comprehensiveness instead of effectiveness. Good skills are opinionated. *If your skill could be a Wikipedia article, it's documentation.*

**Cross-reference:** Pattern 6 is the expanded version of the Audience-Intel Lesson in the main skill. Pattern 5 is the reason the anti-patterns section is mandatory in Step 6.

---

## `research-methodology.md`

The manual for Step 3. Where the main skill says "go deep," this says how.

**Contents:**

- **Research stack, three tiers** — Tier 1 Perplexity MCP (`perplexity_ask`, `perplexity_research`, `perplexity_reason`, with guidance on which to use); Tier 2 built-in web search; Tier 3 manual reading of primary sources. The stated hierarchy: primary sources > summaries > blog posts > AI-generated summaries.
- **Six-step process** — define questions, find foundational sources, find real examples, identify anti-patterns, find current best practices, synthesize into principles.
- **Quality checklist** — three axes: breadth, depth, synthesis.
- **Prompt sets by skill type** — copy/writing, visual/creative, SEO/content, technical/development.
- **Five common mistakes** — stopping at summaries, collecting without synthesizing, skipping anti-patterns, ignoring current context, researching without testing.
- **Time investment table** — simple 1–2h, medium 4–8h, complex 2–5 days. Notes `direct-response-copy` at ~40 hours.
- **The meta-principle** — research isn't information collection, it's taste development. You're ready when you can identify good work instantly, explain why, name what's wrong with bad work, and predict what the model will get wrong.

**Note:** the Perplexity tier names specific MCP tools. If you don't have that MCP configured, skip to Tier 2 — the rest of the method is tool-agnostic.

---

## `research-example-ai-creative.md`

A full case study: the research behind a visual/creative-strategy skill, from problem to skill structure. The most concrete demonstration in the repo of what "deep research" means in practice.

**Five research phases:**

1. **Visual psychology** — neurological processing order (faces → motion → contrast → novelty → text), the 3-second threshold, pattern interrupts that work.
2. **Direct response visual principles** — Ogilvy's rules, attention sequence (focal point → context → CTA), Hick's Law applied to visuals.
3. **Anti-generic AI aesthetics** — the visual and aesthetic tells of "AI slop" (centered composition, uniform lighting, plastic textures, gradient-to-nowhere), why it happens (models predict the average), and the fix: multi-dimensional style architecture across lighting, palette, composition, reference, treatment, texture, emotional register.
4. **Brand case studies** — Perplexity, Anthropic, Figma, Linear, each with what makes it distinctive and why it works.
5. **Platform optimization** — Instagram, YouTube thumbnails, LinkedIn, TikTok.

**Then:** the style-exploration discovery (don't iterate one style, explore genuinely different territories — brutalist, retro nostalgia, editorial, gradient abstract, 3D premium, illustrated, photographic), how research mapped onto skill sections, and **what was cut** (color theory, art history, camera specs, algorithm breakdowns) because it didn't improve output.

**Most useful page for a skeptic:** "What we cut." It's the evidence that the package's anti-comprehensiveness stance is earned rather than rhetorical.

---

## `START-HERE.md` and `SHAREABLE-README.md`

Original upstream documents, preserved unmodified for parity with the source distribution.

Useful for: the short pitch, the three usage options, and install methods as originally written.

**Caveat:** both describe a layout this repo doesn't have — they reference `SKILL.md`, `cold-outreach/SKILL.md`, and a `references/` folder. The actual files are flat and suffixed (`vibe-skill-creator-SKILL.md`, `cold-outreach-SKILL.md`). [`installation.md`](installation.md) gives the correct copy commands with renames. The zipped distribution (`vibe-skill-creator.zip`) is a sibling of the original folder, not part of this repo.

Both files also end with promotional sections for a paid skills pack and a community membership at thevibemarketer.com. Those are the author's, not this repo's.

---

## Reading paths

**"I want to build a skill this afternoon"**
→ `vibe-skill-creator-SKILL.md` (Steps 1–9), then `bad-skill-patterns.md` as a pre-flight check.

**"My skill isn't working and I don't know why"**
→ `bad-skill-patterns.md` first. It's a diagnostic. Then Step 6 of the main skill.

**"My research keeps coming back generic"**
→ `research-methodology.md` (mistakes section), then `research-example-ai-creative.md` for the depth benchmark.

**"Just show me a good skill file"**
→ `cold-outreach-SKILL.md`. Read it as a template, not just a tool.

**"I've never used a skill before"**
→ [`installation.md`](installation.md), then `START-HERE.md` for the original 3-minute framing.
