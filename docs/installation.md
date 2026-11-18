# Installation

Everything in this repo is plain Markdown. There's no build step, no package manager, and no dependency.

The one thing that trips people up: **the files here are not named `SKILL.md`.** They're named after their skill (`vibe-skill-creator-SKILL.md`). Most skill systems require the file inside a skill folder to be exactly `SKILL.md`, in a folder matching the skill's `name` field. Copy with a rename, as shown below.

---

## Which file do I install?

| Goal | Install this | As |
|------|--------------|-----|
| Build your own skills | `vibe-skill-creator-SKILL.md` | `vibe-skill-creator/SKILL.md` |
| Write cold outreach now | `cold-outreach-SKILL.md` | `cold-outreach/SKILL.md` |
| Do both | both files | two separate skill folders |

The reference files (`bad-skill-patterns.md`, `research-methodology.md`, `research-example-ai-creative.md`) are **not** standalone skills. They're supporting material the main skill points at. Install them only if you want the agent to be able to open them; otherwise they're for you to read.

---

## Claude Code

### Personal skills (available in all projects)

```bash
mkdir -p ~/.claude/skills/vibe-skill-creator
cp vibe-skill-creator-SKILL.md ~/.claude/skills/vibe-skill-creator/SKILL.md

mkdir -p ~/.claude/skills/cold-outreach
cp cold-outreach-SKILL.md ~/.claude/skills/cold-outreach/SKILL.md
```

### Project skills (shared with a team)

```bash
# from the root of the project that should have the skill
mkdir -p .claude/skills/vibe-skill-creator
cp /path/to/vibe-skill-creator-SKILL.md .claude/skills/vibe-skill-creator/SKILL.md
```

Commit `.claude/skills/` and teammates get it automatically.

### Optional: reference files alongside the skill

If you want the agent to be able to consult the deep references, put them next to `SKILL.md` and keep the paths consistent:

```bash
mkdir -p ~/.claude/skills/vibe-skill-creator/references
cp bad-skill-patterns.md research-methodology.md research-example-ai-creative.md \
   ~/.claude/skills/vibe-skill-creator/references/
```

Note: the skill body refers to them as `references/research-methodology.md` and so on, so this layout matches what the text expects.

### Optional: slash command instead of auto-invocation

```bash
mkdir -p .claude/commands
cp vibe-skill-creator-SKILL.md .claude/commands/build-skill.md
```

Then invoke with `/build-skill`. This skips the frontmatter-driven auto-trigger and just injects the document.

---

## Claude Desktop / claude.ai

### Method A — upload per conversation

1. Start a new chat.
2. Attach `vibe-skill-creator-SKILL.md` (or `cold-outreach-SKILL.md`) with the paperclip.
3. Ask your question.

The skill is active for that conversation only.

### Method B — project knowledge (persistent)

1. Create or open a Project.
2. **Project knowledge → Add content**.
3. Paste the file contents.
4. Active for every chat in that project.

### Method C — custom skill (permanent, auto-invoked)

1. Create a folder named `vibe-skill-creator`.
2. Put the file inside it, renamed to `SKILL.md`.
3. Zip the **folder** (not just the file).
4. Settings → Features → Custom skills → **Upload skill** → select the zip.

Resulting structure, verified before zipping:

```
vibe-skill-creator.zip
└── vibe-skill-creator/
    └── SKILL.md
```

A common failure: the zip contains `vibe-skill-creator/SKILL.md` *nested inside another folder* because you zipped the parent directory. Upload fails or the skill never appears. Zip the skill folder itself.

---

## Other agents and tools

These files are ordinary Markdown, so anything that accepts a system prompt, rules file, or reference document can use them.

| Tool | Practical approach |
|------|--------------------|
| Cursor | Put the content in `.cursor/rules/` (as an `.mdc` rule), or paste into a rules file |
| Windsurf | Same idea — project rules / memories |
| ChatGPT (custom GPT) | Paste into the GPT's instructions, or upload as knowledge |
| Gemini | Paste into system instructions, or attach as a document |
| Any agent with tool access | Include the file in the repo and reference its path from your agent config |

Caveat worth stating plainly: frontmatter-driven **auto-invocation** is a Claude-specific mechanic. Elsewhere, treat these as reference documents you (or your agent config) choose to load. The content still works; the automatic triggering may not.

---

## Verifying it works

Auto-invoked skills are matched on their `description` field, not their filename. To check that installation succeeded:

1. Start a fresh session.
2. Say something that matches the description without naming the skill: *"help me build a skill for technical RFCs"* (for vibe-skill-creator) or *"write a cold email to a law firm about automation"* (for cold-outreach).
3. The agent should start following the skill's process — asking what you're trying to produce, or producing a short, researched message under 80 words.

If it answers generically instead, see the troubleshooting section in [faq.md](faq.md#the-skill-is-installed-but-never-triggers).

---

## Uninstalling

```bash
rm -rf ~/.claude/skills/vibe-skill-creator
rm -rf ~/.claude/skills/cold-outreach
```

For claude.ai custom skills, remove them from Settings → Features → Custom skills. For project skills, delete the folder under `.claude/skills/` and commit the removal.
