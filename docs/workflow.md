# The Workflow

The ten-step process from `vibe-skill-creator-SKILL.md`, expanded with what each step produces and how to know you're done.

The short version: don't start by writing the skill. Start by producing the *bad* output, then research why it's bad. Everything else follows from that contrast.

```
1  Understand   → what skill, what problem
2  Explore      → see the model fail without guidance
3  Research     → go deep on the domain
4  Synthesize   → extract principles from research
5  Draft        → write the initial skill
6  Self-critique→ review against five criteria
7  Iterate      → fix gaps, get feedback
8  Test         → run it on a real scenario
9  Finalize     → codify into optimal structure
10 Reference    → add deep material, only if needed
```

Steps 2 and 8 are the ones people skip, and they're the two that determine whether the skill works.

---

## Step 1 — Understand

**Produce:** a written scope, in one or two sentences, of the problem the skill solves.

Four questions, answered explicitly:

| Question | Why it matters |
|----------|----------------|
| What domain? | "Email marketing" is too broad. "Cold outreach for selling services" is focused. |
| What problem does this solve? | Not what it *does* — what the model gets **wrong** without it. |
| What does good look like? | You need named examples of excellent work in this domain. |
| What's the output? | Landing page? Email? Strategy memo? Be specific about the artifact. |

Ask the user:

- "What are you trying to produce with this skill?"
- "What have you tried? What wasn't good enough?"
- "Do you have examples of excellent work in this domain?"

**Gate:** if you can't articulate the problem clearly, stop. A skill built on a fuzzy problem becomes a document about a fuzzy problem.

---

## Step 2 — Explore

**Produce:** one or more samples of the model's *default* output, plus a list of what's wrong with them.

Try to produce the target output with no special guidance, on purpose. It will be mediocre. That's the material the skill is built to fix.

The original build, for a video production agency, produced:

> "Hi [Name], I came across your YouTube channel while researching companies in the [industry] space, and I was impressed by the valuable insights you're sharing. I noticed your posting schedule has been inconsistent lately... At [Agency], we specialize in helping SaaS founders create high-quality video content. I'd love to schedule a quick 15-minute call to discuss..."

And the diagnosis:

- Generic opener ("I came across your...")
- Backhanded compliment ("impressed... *but* inconsistent")
- Me-focused pitch (talks about the agency, not the prospect)
- Hard CTA ("schedule a 15-minute call")
- 150+ words

Document the findings as you go:

- What patterns does the model default to?
- What reads as generic or obviously generated?
- What would an expert do differently?

**Gate:** you have a concrete sample in hand. Without it, every later decision is a guess — including whether the finished skill actually helped.

---

## Step 3 — Research

**Produce:** a synthesis, not a bibliography.

Four things to find:

1. **Foundational experts** — recognized authorities and the frameworks they teach.
2. **What actually works** — case studies, real examples, specific patterns with outcomes.
3. **Anti-patterns** — what makes work in this domain bad; the tells.
4. **The *why*** — the psychology or mechanism behind the techniques.

Prompt template from the skill:

```
Research [domain] deeply. I need to understand what separates expert-level
work from amateur work.

Find:
1. Who are the foundational experts/thinkers? What frameworks do they teach?
2. What actually works? Case studies, real examples, specific patterns.
3. What are the anti-patterns? Common mistakes, things that make output feel generic/AI.
4. Why do the good techniques work? What's the underlying psychology?

Search for blogs, case studies, expert content, community discussions.
Return a synthesis of principles, not just a list of facts.
```

What that produced for cold outreach: Berman's 3C's, Braun's 4T, Allred's Mouse Trap, the "each long sentence reduces reply rate by 17%" data point, and the catalogue of phrases that kill replies.

Full method — tool tiers, question sets by skill type, quality checklist, time budgets: [`research-methodology.md`](../research-methodology.md). A complete worked case study: [`research-example-ai-creative.md`](../research-example-ai-creative.md).

**Gate:** the breadth/depth/synthesis checklist in the methodology file passes. Surface-level research produces a surface-level skill.

---

## Step 4 — Synthesize

**Produce:** a table mapping each finding to a principle with a reason.

Don't list what you found. Extract the generalization behind it.

| Research finding | Principle |
|------------------|-----------|
| "Emails under 80 words get more replies" | **Short beats long** — people scan, not read. If it isn't understood in 2 seconds, it's filtered. |
| "Berman uses Compliment → Case Study → CTA" | **Give before ask** — reciprocity is hardwired. Lead with value, not request. |
| "'I hope this email finds you well' kills response rate" | **Anti-pattern: template openers** — they signal "I sent this to 1,000 people." |

The middle column becomes the core of the skill. The right column is what makes it transferable; a principle without a reason can't be applied to a case the research didn't cover.

---

## Step 5 — Draft

**Produce:** a working first draft. Not a good one.

Write in the domain's voice. Include:

- What the exploration (Step 2) revealed the model gets wrong
- Principles with *why*
- Concrete before/after examples
- Explicit anti-patterns

Suggested first-draft skeleton:

```markdown
# Skill Name

[Opening that establishes voice and frames the problem]

## Why [Default Approach] Fails
## Core Principles
## Anti-Patterns
## Examples
```

**Do not aim for comprehensive.** Aim for a draft that could plausibly improve output on one real scenario.

---

## Step 6 — Self-critique

**Produce:** an honest assessment with prioritized fixes. This is the step that separates a draft from a skill.

Five checks:

**Voice**
- Does this sound like an expert in the domain, or like a wiki article?
- *If documentation voice, rewrite with personality.*

**Principles**
- Are you explaining *why* techniques work, not just *what* to do?
- Could the model adapt these to a situation the skill didn't anticipate?
- *If it's procedure without reasoning, add the why.*

**Anti-patterns**
- Is what to *avoid* named explicitly?
- What does the model get wrong by default?
- *If there are none, add them — often the most valuable section.*

**Examples**
- Are there concrete before/after pairs?
- Do they demonstrate the principles viscerally, or describe them abstractly?
- *If theoretical, make them concrete.*

**Focus**
- Does every section earn its place?
- Would removing any section make output worse?
- *Cut anything that's "just in case."*

Write the critique as a verdict per criterion, not a vibe. The skill's own example:

> ✓ **Voice:** good — sounds like someone who sends cold outreach
> ✓ **Principles:** strong — explains why short emails work, why soft CTAs convert
> ⚠️ **Anti-patterns:** present but could be more explicit
> ❌ **Examples:** missing follow-up sequence examples
> ❌ **Missing:** trigger events section
> **Priority fixes:** add follow-up examples, add trigger events section

---

## Step 7 — Iterate

**Produce:** draft 2+ that closes the priority gaps.

The loop:

1. Fix the priority issues from the critique.
2. Present with an honest assessment: what improved, what's still weak.
3. Get feedback.
4. Incorporate feedback **only if it improves output** — not if it merely adds coverage.
5. Re-critique.
6. Repeat until it passes.

Presenting honestly matters more than it sounds. Announcing "here's what's still weak" surfaces the gap the user cares about; presenting a polished draft gets approval for the wrong things.

> "Here's draft 2. **Improved:** added a 4-email follow-up sequence, added a trigger-events table. **Still weak:** the LinkedIn section is thinner than email — may need more examples. **Questions:** does this cover the scenarios you care about? Any anti-patterns missing?"

---

## Step 8 — Test

**Produce:** proof. One real scenario, run with the skill loaded, compared against the Step 2 baseline.

This is non-negotiable. You don't know the skill works until it runs.

**Protocol:**

1. Ask for a real scenario: a specific service sold to a specific type of prospect.
2. Produce the output with the skill applied.
3. Compare against the default output captured in Step 2.
4. Judge: is it *genuinely* better, or just different?

The original test — AI automation services to a small personal-injury law firm:

> Sarah — saw you're hiring a paralegal. Guessing intake volume is part of why.
>
> Quick observation: your contact form goes to a generic inbox. Morgan & Morgan's triggers an instant callback + text sequence + case qualifier — all automated.
>
> We built something similar for [Small PI Firm] — went from 30% lead response rate to 85% without adding staff.
>
> Worth a 10-min look?

Against the baseline, what changed:

- Specific trigger (hiring → intake volume)
- Competitive comparison
- Concrete proof (30% → 85%)
- Soft CTA
- 71 words instead of 150

**Gate:** the test passes. If it fails, go back to Step 6 — don't move to finalize and hope.

---

## Step 9 — Finalize

**Produce:** the shipped file.

Apply the structure described in [skill-anatomy.md](skill-anatomy.md): frontmatter with a trigger-bearing description, then opening / why-default-fails / principles / frameworks / anti-patterns / examples / checklist. Under 500 lines.

Two details people get wrong here:

- **The description is not a summary**, it's the matching surface. Include the phrases a user would actually type.
- **Length is a signal.** If the file is bloated, the scope is probably still too broad — fix the scope rather than compressing the prose.

---

## Step 10 — Reference material (if needed)

**Produce:** deep reference files, or a deliberate decision that none are needed.

Some skills fit in one file. Cold outreach does, at 454 lines, because the domain is narrow. Others — visual creative strategy, direct response copywriting, SEO content — carry too much expertise for that.

| Skill type | References needed? |
|------------|-------------------|
| Focused domain (cold outreach, lead magnets) | Usually no |
| Deep expertise domain (visual design, copywriting) | Yes — vocabulary, examples, psychology |
| Tool-heavy domain (image generation, video) | Yes — model IDs, prompts, specs |
| Multi-format domain (content atomizer) | Yes — platform-specific rules |

Build references from what you collected in Step 3. Ask: what expertise is too deep for the main file, what vocabulary does the model need, and what examples define "good" here.

**Gate:** the same test as everywhere else — does it improve output, or just make the package more complete? In the ai-creative case study, extensive color-theory and art-history research was cut for exactly this reason.

---

## Time expectations

| Skill scope | Research alone |
|-------------|----------------|
| Simple (single technique) | 1–2 hours |
| Medium (multiple techniques) | 4–8 hours |
| Complex (full domain) | 2–5 days |

Real examples from the source material: cold outreach took about one hour of conversation end to end. `direct-response-copy` took ~40 hours of research. `ai-creative-strategist` took ~20–24 hours across research and testing.

The asymmetry is the point: narrow scope, fast build; deep domain, slow build. What you can't do is skip Step 2 or Step 8 and expect the skill to work.

---

## Where builds fail

| Step | Failure | Symptom |
|------|---------|---------|
| 1 | Scope too broad | Skill has no opinion; reads like an overview |
| 2 | Skipped | Skill fixes imaginary problems |
| 3 | Stopped at summaries | Principles are borrowed slogans |
| 4 | Collected instead of synthesized | 50 pages of notes, no transferable rules |
| 5 | Aimed for comprehensive | First draft is already unfixable |
| 6 | Went easy on the draft | Documentation voice survives to production |
| 7 | Accepted every suggestion | Bloat by accretion |
| 8 | Skipped | Skill ships unvalidated |
| 9 | Bloated past 500 lines | Scope problem disguised as formatting |
| 10 | Added everything researched | Reference section becomes friction |
