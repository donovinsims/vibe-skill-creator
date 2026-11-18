# FAQ and Troubleshooting

## General

### What is a "skill" exactly?

A Markdown file with a YAML header. It gives an AI agent domain expertise — thinking patterns, principles, anti-patterns — rather than a procedure to follow. The agent decides whether to load it by reading the `description` field.

The distinction the package keeps making: *documentation tells you what to do; a skill changes how the model thinks.* If the file could be a Wikipedia article, it isn't a skill.

### Do I need Claude specifically?

No, but triggering works best there. These are plain Markdown files; any agent that accepts a system prompt, rules file, or attached document can use the content. Frontmatter-driven auto-invocation is a Claude mechanic — elsewhere you'll usually load the file manually or via your agent's config. See [installation.md](installation.md#other-agents-and-tools).

### Do I need to know how to build skills already?

No. That's the premise. You have a conversation; the skill guides the process and asks the questions. Steps 1, 6, and 7 are explicitly conversational.

### Is this only for marketing?

No. The main skill includes a table of non-marketing domains it was designed to handle: code documentation, investor updates, technical RFCs, legal briefs, product specs, academic writing. The cold-outreach file is the worked example, not the scope.

### How long does building a skill take?

| Skill scope | Research alone |
|-------------|----------------|
| Simple (single technique) | 1–2 hours |
| Medium (multiple techniques) | 4–8 hours |
| Complex (full domain) | 2–5 days |

Cold outreach was built in about an hour of conversation. `direct-response-copy` took ~40 hours of research. `ai-creative-strategist` took roughly 20–24 hours including testing.

### How many skills should I build?

One at a time, and narrow. "Cold outreach for selling services" beats "all sales communication." If a skill covers two jobs, split it.

### What's the difference between a skill and a subagent?

| | Skills | Subagents |
|---|--------|-----------|
| Purpose | Execution — produce the output | Research — return findings |
| Availability | claude.ai and Claude Code | Claude Code |
| Typical use | "Write cold outreach" | "Research cold outreach best practices" |

The skill's own guidance: use a subagent for Step 3, and make it return 3–5 insights, not a 30-page document. A subagent that hands back a report creates the friction problem (see below).

### What is "friction" and why does it matter?

A friction skill produces an intermediate document the user then feels obligated to apply. The repo's own case: an audience-research skill generated excellent segmentation, and copy written *with* that research was worse than copy written without it — because comprehensive input creates pressure to cover everything, which dilutes the output.

The fix: bake the expertise into the skill itself. Don't hand the user research and ask them to synthesize it.

---

## Installation problems

### The files aren't named `SKILL.md`

Correct — they're named after their skills. Most skill systems require the file inside a skill folder to be exactly `SKILL.md`, in a folder matching the `name` field. Copy with a rename:

```bash
mkdir -p ~/.claude/skills/vibe-skill-creator
cp vibe-skill-creator-SKILL.md ~/.claude/skills/vibe-skill-creator/SKILL.md
```

Full instructions: [installation.md](installation.md).

### The skill is installed but never triggers

The `description` field is the only thing used for matching. Check:

1. **Filename** — it must be `SKILL.md`, in a folder matching the `name` field. `vibe-skill-creator-SKILL.md` sitting loose in a skills folder won't load.
2. **Frontmatter** — the file must start with `---` on line 1, contain `name:` and `description:`, and close with `---`. A stray blank line before the opening `---` breaks parsing.
3. **Phrasing** — the description lists trigger words (build skill, create skill, improve skill, help me make a skill). If you ask in vocabulary that isn't there, matching is weaker. Either phrase your request closer to those words, or add your own to the description.
4. **Session freshness** — skills are read at session start. Restart the session after installing.

Test with the most literal phrasing available: *"help me build a skill for technical RFCs."* If that works and your normal phrasing doesn't, it's a description problem — edit the description rather than the body.

### The zip upload fails or the skill doesn't appear

The archive structure is almost always the cause. Required:

```
vibe-skill-creator.zip
└── vibe-skill-creator/
    └── SKILL.md
```

Wrong: zipping the *parent* directory, producing `vibe-skill-creator/vibe-skill-creator/SKILL.md`. Zip the skill folder itself, with `SKILL.md` directly inside it.

### Can I install both skills?

Yes — they're independent, in separate folders. `vibe-skill-creator` builds skills; `cold-outreach` writes outreach. They don't reference each other's paths.

### Do I need the reference files installed?

No. The main skill works without them. It *points* at them, so if the agent tries to open `references/research-methodology.md` and it's missing, it will proceed without it. Install them alongside `SKILL.md` under a `references/` folder if you want the agent to be able to consult them.

---

## Using it

### What do I actually type?

To build a skill:

> "I want to build a skill for [domain]. Guide me through the process — explore where you fail without guidance, research the domain, then help me build a skill that actually improves your output."

To write outreach:

> "Write a cold email to [prospect] about [service]. Context: [anything relevant]."

### Can I skip the research step?

You can, and the skill will tell you the result is a guess. Step 2 (exploration) and Step 8 (testing) are the two that determine whether the skill works; research is what makes the principles transferable rather than slogans. Skipping research is the most common way to end up with a file that reads fine and changes nothing.

### How do I know it actually worked?

Compare against a baseline, not against your impression. Step 2 exists to capture the model's default output before the skill exists. Step 8 re-runs the same scenario with the skill loaded. If you didn't capture the baseline, capture it now — produce the output in a fresh session without the skill, then compare.

### The reply-rate numbers — are they real?

They come from the source material and from named practitioners' published frameworks. They are not benchmarked, reproduced, or independently verified by this repo. Treat them as directional claims from the authors, which is also how the skill itself frames them.

---

## Licensing and provenance

### Where did this come from?

From The Vibe Marketer (thevibemarketer.com), which distributes a larger paid skills pack and a community membership. The two original files (`START-HERE.md`, `SHAREABLE-README.md`) contain that author's promotional links, preserved unmodified.

### Can I use it commercially? Redistribute it? Publish it?

**Unresolved.** This repository contains **no license file**. Absent an explicit license, default copyright applies: you don't automatically have redistribution rights, and this repo's public visibility doesn't grant any.

Before using this commercially, publishing derivatives, or shipping it inside a product, check the terms at the original source. If you need certainty, get written permission from the author.

This is a genuine gap, not a formality — it's listed here because it's the kind of thing that's expensive to discover later.

### Is this the official repo?

No. It's a copy published for convenience and version control. It's not affiliated with or endorsed by The Vibe Marketer.

### Can I modify it?

Locally, yes — these are text files and the whole point is adapting skills to your domain. Note that modifying and then redistributing is the case the licensing question above governs.

---

## Known inconsistencies in the source material

Documented rather than fixed, so you know what you're looking at. The original files were copied verbatim.

| Issue | Detail |
|-------|--------|
| Filenames vs. documented layout | The original readmes reference `SKILL.md`, `cold-outreach/SKILL.md`, and `references/`. The actual files are flat: `vibe-skill-creator-SKILL.md`, `cold-outreach-SKILL.md`. Renames are required for installation. |
| Nine boxes, ten steps | The ASCII flow diagram in the main skill draws nine steps; the prose documents ten (Step 10 covers reference material). |
| Reference paths | The main skill points to `references/research-methodology.md` etc.; those files sit at the repo root. |
| "~480 lines" | The skill describes cold outreach as fitting in ~480 lines; the file is 454. |
| Research hours | `research-methodology.md` cites ~20 hours of research for `ai-creative-strategist`; `research-example-ai-creative.md` totals ~24 hours including testing. Both can be true; they measure different things. |
| A named tool ID | `bad-skill-patterns.md` uses a specific Glif model ID as its example of a *good* tool reference. It's illustrative and may be stale — don't copy it as a working configuration. |

None of these break the process. The two that affect installing and running are the filenames and the reference paths.

---

## Still stuck?

Read in this order:

1. [`bad-skill-patterns.md`](../bad-skill-patterns.md) — your skill's symptoms are almost certainly in the list, with the fix beside each.
2. Step 6 of [`vibe-skill-creator-SKILL.md`](../vibe-skill-creator-SKILL.md) — the five critique criteria, with "if X, do Y" corrections.
3. [`research-methodology.md`](../research-methodology.md) — if the output is generic, the research was generic.
