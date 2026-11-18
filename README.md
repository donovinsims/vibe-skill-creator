# Vibe Skill Creator

A skill that teaches an AI agent how to build skills — plus a finished example skill that shows what "good" actually looks like.

Most skills are mediocre because the author doesn't know what good looks like, which questions to ask, or how to improve a draft. This package fixes that. It walks an agent through ten steps of building a skill from scratch: explore where the model fails on its own, research the domain, extract principles, draft, self-critique, test against a real scenario, and iterate until the output is measurably better than the default.

You don't need to know anything about skill authoring to use it. You need a conversation.

**Two things live here:**

1. `vibe-skill-creator` — a skill-building skill. Load it, describe a domain, get guided through the build.
2. `cold-outreach` — a complete, usable skill for writing cold email, LinkedIn DMs, and X/Twitter DMs. Also serves as the worked example of the process.

Plus reference material on research method, anti-patterns, and a full research case study.

---

## What's inside

| File | Lines | What it is |
|------|------:|------------|
| [`vibe-skill-creator-SKILL.md`](vibe-skill-creator-SKILL.md) | 676 | The skill-building skill. This is the main file. |
| [`cold-outreach-SKILL.md`](cold-outreach-SKILL.md) | 454 | A finished example skill you can use immediately. |
| [`bad-skill-patterns.md`](bad-skill-patterns.md) | 530 | Ten patterns that make skills mediocre, with bad/good rewrites of each. |
| [`research-methodology.md`](research-methodology.md) | 347 | How to research a domain: tool tiers, question sets, quality checklist. |
| [`research-example-ai-creative.md`](research-example-ai-creative.md) | 350 | Full case study of research that produced a visual/creative skill. |
| [`START-HERE.md`](START-HERE.md) | 187 | Original short intro and install notes (upstream copy, kept as-is). |
| [`SHAREABLE-README.md`](SHAREABLE-README.md) | 160 | Original shareable readme (upstream copy, kept as-is). |

Eight files, ~2,700 lines, no build step, no dependencies. Everything is plain Markdown.

---

## Quick start

### "I want to write better cold emails right now"

```bash
mkdir -p ~/.claude/skills/cold-outreach
cp cold-outreach-SKILL.md ~/.claude/skills/cold-outreach/SKILL.md
```

Then ask: *"Write a cold email to [prospect] about [your service]. Context: [anything you know about them]."*

### "I want to build my own skill"

```bash
mkdir -p ~/.claude/skills/vibe-skill-creator
cp vibe-skill-creator-SKILL.md ~/.claude/skills/vibe-skill-creator/SKILL.md
```

Then ask: *"Help me build a skill for [your domain]."*

The file must be renamed to `SKILL.md` and placed in a folder matching the skill name — see [docs/installation.md](docs/installation.md) for why and for every other install path.

---

## The four core truths

Everything in the skill descends from these. They're worth reading even if you never install anything.

**1. Expertise transfer, not instructions.**
A skill should make the model *think* like an expert, not follow rules.
> Wrong: "Step 1: Write a headline. Step 2: Write body copy."
> Right: "The headline does 80% of the work. One headline can outpull another by 19.5x. Here's what separates the winners."

**2. Flow, not friction.**
Skills should produce output. If a skill produces an intermediate document the user then feels obligated to apply, it makes the next step worse, not better. The package documents this with its own failure: an audience-research skill produced excellent segmentation, and copy written *with* that research was worse than copy written without it, because comprehensive input creates pressure to use all of it.

**3. Voice matches domain.**
A copywriting skill sounds like a copywriter. If it reads like documentation, it's wrong.

**4. Focused beats comprehensive.**
"Cold outreach for selling services" beats "all sales communication." Every section must earn its place.

---

## The process at a glance

| # | Step | What happens | Gate |
|---|------|--------------|------|
| 1 | **Understand** | Pin down domain, problem, output, and what "good" looks like | Can't state what the model gets wrong → not ready |
| 2 | **Explore** | Produce the output *without* guidance, deliberately | You have a concrete default-output sample to fix |
| 3 | **Research** | Foundational experts, real examples, anti-patterns, the *why* | Research passes the breadth/depth/synthesis checklist |
| 4 | **Synthesize** | Turn findings into principles with reasons | Each finding maps to a transferable principle |
| 5 | **Draft** | Write a working first draft in domain voice | Principles + anti-patterns + before/after present |
| 6 | **Self-critique** | Five checks: voice, principles, anti-patterns, examples, focus | Gaps identified and prioritized |
| 7 | **Iterate** | Fix, present honestly, get feedback, repeat | Passes review |
| 8 | **Test** | Run the skill on a real scenario, compare to Step 2 | Output is genuinely better than default |
| 9 | **Finalize** | Structure it: frontmatter, sections, under 500 lines | Matches the target shape |
| 10 | **Reference** | Add deep material only if the domain needs it | "Does removing this make output worse?" |

Full detail, including the critique criteria and the test protocol: [docs/workflow.md](docs/workflow.md).

---

## The example skill: cold-outreach

`cold-outreach-SKILL.md` is both a usable tool and the demonstration of everything above. Its structure is a template worth copying:

- **Why most cold outreach fails** — the 2-second threat-detection filter, and what triggers it.
- **Seven core principles** — research *is* the message; give before you ask; show don't claim; short beats long; soft CTA beats hard CTA; follow up; timing beats personalization.
- **Three named frameworks** — Alex Berman's 3C's, Josh Braun's 4T, Will Allred's Mouse Trap.
- **Platform tactics** — email, LinkedIn, X/Twitter, each with different length and tone rules.
- **Anti-patterns** — the phrases that kill a reply, plus structural and tone mistakes.
- **Before/after examples** — two full rewrites with a "what changed" breakdown.
- **Quality checklist** — including the only test that matters: *would you reply to this?*

The skill claims 1–3% reply rates for generic outreach versus 15–25% for researched outreach. Those figures come from the source material; they are not benchmarked by this repo.

---

## Repository layout

```
vibe-skill-creator/
├── README.md                        ← you are here
├── vibe-skill-creator-SKILL.md      ← the skill-building skill
├── cold-outreach-SKILL.md           ← the example skill
├── bad-skill-patterns.md            ← 10 anti-patterns
├── research-methodology.md          ← how to research
├── research-example-ai-creative.md  ← research case study
├── START-HERE.md                    ← original intro (upstream)
├── SHAREABLE-README.md              ← original readme (upstream)
└── docs/
    ├── installation.md              ← every install path + troubleshooting
    ├── skill-anatomy.md             ← what a skill file is made of
    ├── workflow.md                  ← the 10 steps in depth
    ├── file-reference.md            ← what's in each file, when to read it
    └── faq.md                       ← common questions, gaps, limitations
```

---

## Documentation

| Doc | Read it when |
|-----|--------------|
| [docs/installation.md](docs/installation.md) | You want the skill running in Claude Desktop, Claude Code, or another agent |
| [docs/skill-anatomy.md](docs/skill-anatomy.md) | You want to understand the file format, frontmatter, and length budget |
| [docs/workflow.md](docs/workflow.md) | You're actually building a skill and want the step-by-step detail |
| [docs/file-reference.md](docs/file-reference.md) | You want to know what's in each file before opening it |
| [docs/faq.md](docs/faq.md) | Something isn't working, or you have a licensing/scope question |

---

## Notes on this repository

This repo is a copy of the "Vibe Skill Creator" package, published for convenience and version control. It is **not** the original distribution and is not affiliated with the author.

Known gaps, documented rather than papered over:

- **Filenames don't match the layout the original readmes describe.** Those readmes refer to `SKILL.md` and `cold-outreach/SKILL.md`; the actual files are flat (`vibe-skill-creator-SKILL.md`, `cold-outreach-SKILL.md`) and the references aren't in a `references/` folder. Install instructions in [docs/installation.md](docs/installation.md) account for this with explicit renames. The files themselves were left untouched.
- **Prose says "10 steps," the diagram in the skill shows 9 boxes.** Step 10 (reference material) is real and documented in prose but missing from the ASCII flow.
- **No license file.** Usage rights are unresolved. See [docs/faq.md](docs/faq.md) before redistributing or using commercially.

Source material is by The Vibe Marketer (thevibemarketer.com), which distributes a broader paid skills pack. Links in the original files point there.
