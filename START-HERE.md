# Start Here: What Are Claude Skills?

**Read time: 3 minutes**

---

## The Problem

You ask Claude to write a cold email. It produces this:

> "I hope this email finds you well! I came across your company and was impressed by your innovative approach. I'd love to schedule a quick 15-minute call to discuss how we might help you achieve your goals..."

Generic. Template-sounding. The kind of email everyone deletes.

---

## The Solution: Skills

A **skill** is a document that gives Claude domain expertise. Not instructions — expertise. The thinking patterns, principles, and anti-patterns that separate amateurs from professionals.

With the `cold-outreach` skill loaded, Claude produces this instead:

> "[Name] — noticed you've posted 4 videos in the last 6 months while [Competitor] is doing 4/month. Your content is actually better, but they're winning on volume.
>
> We helped [Similar Company] go from sporadic posting to weekly without adding headcount.
>
> Worth seeing how they did it?"

Same AI. Different expertise.

---

## What's In This Package

| File | What It Does |
|------|--------------|
| **START-HERE.md** | You're reading it |
| **SKILL.md** | The skill that teaches you to build skills |
| **cold-outreach/SKILL.md** | A finished example skill (use it or study it) |
| **references/** | Deep-dive materials for skill builders |

---

## How to Use This

### Option 1: Build Your Own Skills

Use `SKILL.md` to create skills for your domain. The skill guides you through a 10-step process — you don't need to know how skills work. Just have the conversation.

**Start by saying:**
> "Help me build a skill for [your domain]"

### Option 2: Use the Cold Outreach Skill

Drop `cold-outreach/SKILL.md` into Claude and immediately write better outreach.

### Option 3: Both

Build your own skills AND use the cold-outreach skill. They work independently.

---

## Installation

### For claude.ai (Claude Desktop)

**Method A: Upload as File (Easiest)**
1. Start a new chat
2. Click the attachment icon (📎)
3. Upload `SKILL.md` (or `cold-outreach/SKILL.md`)
4. Start chatting — the skill is now active for this conversation

**Method B: Add to a Project (Persistent)**
1. Create a new Project (or open existing)
2. Click "Project knowledge" → "Add content"
3. Paste the contents of the skill file
4. The skill stays active for all chats in that project

**Method C: Install as Custom Skill (Permanent)**
1. Create a folder named `vibe-skill-creator` (or `cold-outreach`)
2. Put `SKILL.md` inside the folder
3. ZIP the folder
4. Go to Settings → Features → "Custom skills"
5. Click "Upload skill" and select your ZIP
6. The skill appears in your Skills list and activates automatically when relevant

### For Claude Code (Terminal)

**Method A: Project Skill (For Teams)**
```bash
# From your project root:
mkdir -p .claude/skills/vibe-skill-creator
cp SKILL.md .claude/skills/vibe-skill-creator/

# Commit to git — teammates get it automatically
```

**Method B: Personal Skill (Just You)**
```bash
mkdir -p ~/.claude/skills/vibe-skill-creator
cp SKILL.md ~/.claude/skills/vibe-skill-creator/

# Available in all your Claude Code projects
```

**Method C: Slash Command (Manual Trigger)**
```bash
mkdir -p .claude/commands
cp SKILL.md .claude/commands/build-skill.md

# Invoke with: /build-skill
```

**How Claude Code Skills Work:**
- Skills are **auto-invoked** based on the description in the frontmatter
- You don't call them explicitly — just work normally
- Claude detects when the skill is relevant and uses it

---

## Quick Start

**To build a skill:**
```
I want to build a skill for [YOUR DOMAIN]. Guide me through the process —
explore where you fail without guidance, research the domain, then help me
build a skill that actually improves your output.
```

**To use cold outreach:**
```
Write a cold email to [PROSPECT] about [YOUR SERVICE].
Context: [Any relevant details about the prospect]
```

---

## What Makes This Different

Most "prompt engineering" teaches you tricks. This teaches you how to transfer expertise.

The difference:
- **Tricks**: "Use these magic words for better output"
- **Skills**: "Give Claude the thinking patterns experts use"

Skills compound. One well-built skill improves hundreds of future outputs.

---

## Next Steps

1. **Try the cold-outreach skill** — see the difference immediately
2. **Build one skill** for something you do repeatedly
3. **Study the references** if you want to go deeper

---

## Want More?

This is one skill-building skill + one example. Here's how to go deeper:

### Option 1: Get the Full Skills Pack

15+ production-ready skills: Direct Response Copy, Lead Magnets, Email Sequences, SEO Content, Newsletters, AI Image Generation, AI Product Photography, and more.

Each skill is battle-tested with deep reference material.

**Get the skills pack:** [thevibemarketer.com/skills](https://thevibemarketer.com/skills)

---

### Option 2: Join the Community (Best Value)

The Vibe Marketer community is where these skills come from.

What you get:
- **50% off the skills pack** (members-only discount)
- Access to 2,800+ marketers building with AI
- Weekly skill updates and improvements
- Share what you build, get feedback
- Direct access to skill creators

**$199/year** — [thevibemarketer.com](https://thevibemarketer.com)

---

*Built by The Vibe Marketer community — 2,800+ marketers building with AI.*
