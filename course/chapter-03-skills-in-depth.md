# Chapter 3 — Skills in Depth

[← Chapter 2](chapter-02-the-building-blocks.md) · [Index](README.md) · Next: [Chapter 4 →](chapter-04-agents-and-commands.md)

---

## In plain words

A **skill** is the single most important idea in this whole course, so let's nail it.

A skill is a **labeled instruction card** you write once. The AI reads only the
*label* of every card all the time, and when a task matches a label, it **pulls out
that card by itself** and follows the instructions. You never have to say "use the
card" — recognition is automatic.

> Designer analogy: a well-labeled **swatch drawer**. You don't read every swatch;
> you read the drawer's tab ("Brand Blues") and open it when you need blues. A skill's
> *label* is the tab; the *card inside* is the detailed how-to.

Why this is powerful: you capture **your taste and process once**, and from then on
the AI applies it consistently without being reminded. ECC ships **249** of these.

---

## How ECC actually does it

In ECC (and in Claude Code generally), a skill is simply **a folder with a special
file inside it called `SKILL.md`**:

```
skills/
└── api-design/
    └── SKILL.md
```

The `.md` means **Markdown** — plain text with light formatting, like writing in
Notion. A `SKILL.md` has **two parts**:

### Part 1 — the label ("frontmatter")

At the very top, fenced by `---` lines, sits a tiny label:

```markdown
---
name: api-design
description: Use when designing a new web API — endpoints, naming, versioning.
---
```

- **name** — what the skill is called.
- **description** — *when* to use it. **This is the line the AI scans** to decide
  whether to grab the card. A clear description is the difference between a skill
  that gets used and one that's ignored.

### Part 2 — the instructions (the "body")

Below the label, you write the how-to in plain English:

```markdown
# API Design

When designing an API:
1. Use nouns for resource names, not verbs.
2. Version every endpoint, e.g. /v1/users.
3. Return clear error messages with a code and a message.
```

That's a complete skill. **No programming required to start** — it's a really good
brief that the AI never forgets. ECC's 249 skills are exactly this, ranging from
`accessibility` and `frontend-a11y` to `django-patterns` and `docker-patterns`.

---

## Git in this chapter — what & why

**Concept: _committing_ — saving a snapshot.**

A skill is just a text file. To make it part of the project permanently, you
**commit** it. A *commit* is a saved snapshot with a short message describing the
change. ECC's 249 skills got there through hundreds of commits.

The typical flow to add one skill:

```bash
git add skills/api-design/SKILL.md     # stage: "include this file in the snapshot"
git commit -m "Add api-design skill"   # save the snapshot with a message
```

- **`git add`** = pick which changes go into the next snapshot (like selecting
  layers before exporting).
- **`git commit`** = take the snapshot and label it.

**Why commit messages matter:** "Add api-design skill" tells future readers *why*
the change happened. With ~2,000 commits, ECC's history is readable because each
message is meaningful. Good messages are a kindness to future-you.

> You'll run `git add` and `git commit` for real in Chapter 8.

---

## Check your understanding

**Q1. What two parts does every `SKILL.md` have?**

<details><summary>Show answer</summary>

(1) The **frontmatter** — a label with `name` and `description`, fenced by `---`.
(2) The **body** — the plain-English instructions.
</details>

**Q2. Which part does the AI read to decide *when* to use the skill?**

<details><summary>Show answer</summary>

The **description** in the frontmatter. That's why it must clearly say *when* to use
the skill.
</details>

**Q3. Do you need to know programming to write a basic skill?**

<details><summary>Show answer</summary>

No. A basic skill is plain-English instructions in a text file. (Skills *can* later
include scripts, but they don't have to.)
</details>

**Q4. What does `git commit` do, and why does the message matter?**

<details><summary>Show answer</summary>

It saves a labeled snapshot of your staged changes. The message explains *why* the
change was made, keeping the project's history understandable.
</details>

### Hands-on exercise (paper only — building comes in Ch8)

Draft a skill *label* for something **you** do as a designer. Fill this in:

```
name: __________________________
description: Use when ___________________________________________
```

Example: `name: contrast-checker` / `description: Use when reviewing UI colors to
ensure text meets WCAG AA contrast.` Keep your description focused on *when*.

---

## Key terms

| Term | Plain meaning |
|------|---------------|
| Skill | A folder with a `SKILL.md` the AI loads automatically |
| `SKILL.md` | The file holding a skill's label + instructions |
| Frontmatter | The `---`-fenced label at the top (name, description) |
| Markdown (.md) | Plain text with light formatting |
| `git add` | Choose which changes go in the next snapshot |
| Commit | A saved, labeled snapshot of changes |

---

Next: the *other* helpers — **agents and commands** — and how they differ from skills.
**[Chapter 4 →](chapter-04-agents-and-commands.md)**
