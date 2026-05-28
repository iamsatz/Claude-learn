# Chapter 2 — The Six Building Blocks

[← Chapter 1](chapter-01-what-is-ecc.md) · [Index](README.md) · Next: [Chapter 3 →](chapter-03-skills-in-depth.md)

---

## In plain words

A design system isn't one thing — it's **colors**, **components**, **typography
rules**, **auto-layouts**, and **plugins**, each doing a different job. ECC is the
same: it's made of **six kinds of parts**, each with its own role.

Here they are, with a one-line job description each:

| Part | Its job | Design analogy |
|------|---------|----------------|
| **Agents** | Specialist helpers the AI delegates work to | Calling in a freelancer for one task |
| **Skills** | Instruction cards the AI grabs *automatically* | A labeled drawer in your swatch library |
| **Commands** | Shortcuts *you* type to trigger something | A keyboard shortcut like ⌘G "group" |
| **Rules** | Always-follow guidelines | Your brand's non-negotiables |
| **Hooks** | Automatic actions on an event | "On export, auto-rename the file" |
| **MCP** | Connections to outside tools | A Figma plugin that talks to Jira |

That's the whole vocabulary. The rest of the course zooms into each.

---

## How ECC actually does it

Here's the clever, simple idea: **each kind of part lives in its own folder.**

```
ECC/
├── agents/        ← 63 specialist helpers
├── skills/        ← 249 instruction cards   (the main surface)
├── commands/      ← 79 typed shortcuts
├── rules/         ← 34 guideline sets (by language)
├── hooks/         ← automatic actions
├── mcp-configs/   ← outside-tool connections
├── scripts/       ← small programs the hooks run
└── .claude-plugin/← packaging info so it installs as a "plugin"
```

When you look at ECC on GitHub, the folder names **are** the feature list. That's a
huge beginner superpower: **you can understand a project's shape just by reading its
folder names**, before reading a single line of code.

ECC also says **skills are "the primary surface going forward"** — meaning skills
are the most important, most modern part. That's why Chapter 3 is dedicated to them.

> The `.claude/` idea: when these parts are used in the Claude Code app, they live in
> a folder named `.claude/` (e.g. `.claude/skills/`, `.claude/agents/`). The leading
> dot just means "config folder." ECC's job is to fill that folder with good stuff.

---

## Git in this chapter — what & why

**Concept: a repo's _folder structure_ is information.**

You don't always need to run git commands to *learn from* git. Just by browsing a
repository's folder tree on GitHub you can answer "what can this project do?"

Why this works: git tracks the **whole folder layout**, and good projects organize
folders by purpose (one folder per feature type). So:

- `skills/` existing → "this project has skills."
- `hooks/` existing → "this project automates things on events."

**Try the read-only git mindset:** on GitHub, clicking into a folder is the visual
version of these commands a developer might run after cloning:

```bash
ls          # list the files/folders here
ls skills   # list what's inside the skills folder
```

`ls` means "list." It's how you look around a project from the command line. (You're
just recognizing it for now — no need to run it.)

> **Why it matters:** when *you* build your own toolbox later, putting each kind of
> thing in a clearly named folder is what makes it understandable to others (and to
> future-you).

---

## Check your understanding

**Q1. Match the part to its job:** Skill, Command, Hook.
(a) fires automatically on an event, (b) the AI grabs it on its own when relevant,
(c) you type it as a shortcut.

<details><summary>Show answer</summary>

Skill = (b) the AI grabs it on its own · Command = (c) you type it ·
Hook = (a) fires automatically on an event.
</details>

**Q2. How can you guess what a project does *before* reading its code?**

<details><summary>Show answer</summary>

Read its folder names. Well-organized repos name folders by purpose
(`skills/`, `hooks/`, etc.), so the structure reveals the feature set.
</details>

**Q3. Which part does ECC call its "primary surface going forward"?**

<details><summary>Show answer</summary>

Skills. (That's why the next chapter focuses on them.)
</details>

**Q4. What does the `.` mean in a folder named `.claude/`?**

<details><summary>Show answer</summary>

It marks a hidden/config folder. It's a convention for "settings live here," not
something users browse day-to-day.
</details>

### Hands-on exercise

In the ECC repo in your browser, click into **two** folders — `skills/` and
`agents/`. Notice how each contains many sub-items with descriptive,
hyphenated-names (like `api-design`, `code-reviewer`).

Write a sentence: *"ECC's `agents/` folder contains ____, and its `skills/` folder
contains ____."* Fill the blanks in your own words.

---

## Key terms

| Term | Plain meaning |
|------|---------------|
| Agent | A specialist helper the AI delegates a sub-task to |
| Skill | An instruction card the AI loads automatically when relevant |
| Command | A typed shortcut (e.g. `/plan`) |
| Rule | An always-follow guideline |
| Hook | An automatic action triggered by an event |
| MCP | A connection to an outside tool |
| `ls` | Command to "list" files in a folder |

---

Now the main event — what a **skill** really is, inside and out.
**[Chapter 3 →](chapter-03-skills-in-depth.md)**
