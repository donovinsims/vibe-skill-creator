# Skill Anatomy

What a skill file is actually made of, and what each part does. This is the format the `vibe-skill-creator` skill produces at Step 9.

A skill is one Markdown file with a small YAML header. That's the whole contract.

---

## The two parts

```markdown
---
name: skill-name
description: "One line saying what this does. Use when [trigger]. Produces [output]."
---

# Skill Name

The body: voice, principles, frameworks, anti-patterns, examples, checklist.
```

### Part 1 — Frontmatter

Two fields matter.

| Field | Purpose | Notes |
|-------|---------|-------|
| `name` | Identifier | Should match the containing folder name. Lowercase, hyphenated. |
| `description` | **This is what drives auto-invocation** | The agent decides whether to load the skill by reading this string. Not the filename, not the body. |

The description does the heaviest work in the file, and it's usually the most neglected. The pattern used by both skills here:

```
[What it does]. Use when [situation]. Triggers on: [keyword, keyword, keyword].
Produces [concrete output].
```

Real examples from this repo:

```yaml
name: vibe-skill-creator
description: "Build world-class skills through guided conversation and recursive self-review.
Use when creating or improving a skill. Triggers on: build skill, create skill,
improve skill, help me make a skill. Guides users through discovery, research,
drafting, testing, and iteration until the skill actually works."
```

```yaml
name: cold-outreach
description: "Write cold outreach that gets replies. Use when writing cold emails,
LinkedIn DMs, or Twitter DMs to sell services. Triggers on: cold email, cold outreach,
LinkedIn message, DM prospects. Produces messages that feel human, relevant,
and worth responding to."
```

Why the trigger keywords matter: users don't say "invoke the skill." They say "write a cold email." The description has to anticipate the phrasing.

**Bloat warning:** put nothing in frontmatter that doesn't help matching. It's metadata, not a summary.

### Part 2 — Body

There is no required body structure. There is a structure that repeatedly works, and it's the one the skill recommends:

| Section | Purpose |
|---------|---------|
| **Opening** | 2–3 paragraphs. Establishes voice, frames the problem, states what changes. |
| **Why [default approach] fails** | What the model gets wrong unaided. Derived from Step 2's exploration. |
| **Core principles** | The fundamental truths of the domain, each with a *why*. This is the load-bearing section. |
| **Frameworks** (optional) | Named, concrete methods from real practitioners, with examples. |
| **Anti-patterns** | What to avoid, explicitly, with examples of the failure. |
| **Examples** | Real before/after. Not hypotheticals. |
| **Quality checklist** | Fast review pass for the output. |

Not every skill needs every section. A focused skill can skip frameworks entirely. None of them should appear "just in case."

---

## The length budget

**Target: under 500 lines for `SKILL.md`.**

The two skills in this repo: 676 lines (skill-building, a deep meta-domain) and 454 lines (cold outreach, a focused domain). The original material describes cold-outreach as "~480 lines," which is close enough to illustrate the intent rather than a hard rule.

Over 500 lines, one of two things is usually true: the scope is too broad, or deep reference material belongs in a separate file.

---

## When to add references

| Skill type | References needed? | Why |
|------------|-------------------|-----|
| Focused domain (cold outreach, lead magnets) | Usually no | Fits in one file; stays self-contained |
| Deep expertise domain (visual design, copywriting) | Yes | Vocabulary, examples, psychology won't compress |
| Tool-heavy domain (image generation, video) | Yes | Model IDs, prompt formats, technical specs |
| Multi-format domain (content atomizer) | Yes | Platform-specific rules multiply |

### Two ways to ship them

**Separate files** — better when there are multiple reference topics, when they change independently, or when you want the main skill to stay clean:

```
skill-name/
├── SKILL.md
└── references/
    ├── visual-intelligence.md
    ├── platform-strategies.md
    └── prompt-templates.md
```

**Embedded after a divider** — better for a single cohesive reference and simpler distribution (one file to upload):

```markdown
... main skill ends ...

---
---

# REFERENCE MATERIAL

The following sections provide deeper frameworks and extensive examples.
```

Both are fine. The requirement is that the deep expertise exists somewhere, not where it lives.

### What good reference material contains

1. **Domain vocabulary** — the words experts actually use ("curiosity gap," "pattern interrupt," "chrome aesthetic").
2. **Psychology and principles** — why techniques work, not just that they do.
3. **Examples from the best** — real campaigns, real brands, real before/after.
4. **Anti-patterns with specifics** — the tells that mark amateur work.
5. **Templates and frameworks** — reusable structures, not essays.

Reference material is still expertise transfer. A 40-page literature review is not a reference; it's a liability.

---

## The one test that governs everything

For every section, ask:

> **Does removing this make the output worse?**

If the answer is "no" or "probably not," cut it. This single question kills most skill bloat, and it's the difference between the two files in this repo and the ten failure modes catalogued in [`bad-skill-patterns.md`](../bad-skill-patterns.md).

Corollary from the same document: *if your skill could be a Wikipedia article, it isn't a skill — it's documentation.*
