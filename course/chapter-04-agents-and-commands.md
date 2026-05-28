# Chapter 4 — Agents & Commands

[← Chapter 3](chapter-03-skills-in-depth.md) · [Index](README.md) · Next: [Chapter 5 →](chapter-05-rules-and-hooks.md)

---

## In plain words

You now know **skills** (cards the AI grabs by itself). ECC has two more helpers that
people often mix up: **agents** and **commands**. Here's the clean distinction.

- **Agent** = a **specialist you delegate to.** The main AI is a generalist; when a
  job needs focused expertise, it hands the task to an agent who works on it and
  reports back. *Design analogy:* you art-direct, but you bring in a **retoucher**
  for one photo. They go away, do the retouching, return the result.

- **Command** = a **shortcut you type yourself.** It starts with a slash, like
  `/plan` or `/code-review`. *Design analogy:* a keyboard shortcut — ⌘G to group.
  Nothing happens until *you* press it.

The big difference in **who triggers it**:

| Helper | Who decides to use it? |
|--------|------------------------|
| Skill | The **AI**, automatically, when a task matches |
| Command | **You**, by typing it |
| Agent | The **AI**, by delegating a sub-task |

---

## How ECC actually does it

- **63 agents** live in `agents/`. Examples: `code-reviewer`, `architect`,
  `security-reviewer`. Each is a persona with a **limited scope** — it focuses on
  one job so it does it well, then reports back to the main conversation. Keeping an
  agent narrow is a feature: less distraction, better results.

- **79 commands** live in `commands/`. Examples: `/plan`, `/code-review`,
  `/build-fix`, `/security-scan`. ECC keeps these for people used to typing
  shortcuts, but it's **transitioning to "skills-first"** — meaning new capability
  is added as skills (auto-grabbed) rather than commands (manually typed). You'll see
  notes in ECC like *"commands maintain backward compatibility."*

So the trend is: **skills are the future, commands are the familiar shortcut, agents
are the delegated specialists.** All three can work together — an agent can use
skills; a command can kick off a workflow.

---

## Git in this chapter — what & why

**Concept: reading a project's _history_ with `git log`.**

ECC has **~2,000 commits**. That history is a story of every change ever made. The
command to read it:

```bash
git log --oneline
```

This prints one line per commit — its short message and an ID. You can learn an
enormous amount about a project by skimming its log: what's actively worked on, how
features arrived, who changed what.

Why this matters for understanding *any* repo (including ECC):
- A busy `git log` around `skills/` tells you skills are where the action is.
- Commit messages double as a changelog you can read for free.

You can also view this history visually on GitHub: each file and folder has a
**"History"** button, and the repo has a **commits** page. That's `git log` with a
nicer face.

> **One main branch:** ECC keeps a single main line of history (the `main` branch)
> with ~2,000 commits stacked on it. You'll learn what *branches* are in Chapter 8,
> when you make your own.

---

## Check your understanding

**Q1. Who triggers an agent, and who triggers a command?**

<details><summary>Show answer</summary>

An **agent** is triggered by the **AI** (it delegates a sub-task). A **command** is
triggered by **you** (you type it, like `/plan`).
</details>

**Q2. Why are ECC's agents kept narrow in scope?**

<details><summary>Show answer</summary>

A narrow scope means the agent focuses on one job (e.g. code review) and does it
well, with less distraction, before reporting back.
</details>

**Q3. ECC is moving toward "skills-first." What does that mean?**

<details><summary>Show answer</summary>

New capabilities are added as **skills** (which the AI grabs automatically) rather
than as commands (which you must type). Commands stay for backward compatibility.
</details>

**Q4. What does `git log --oneline` show you?**

<details><summary>Show answer</summary>

A compact, one-line-per-commit list of the project's history — each commit's short
message and ID — so you can skim how the project evolved.
</details>

### Hands-on exercise

On GitHub, open the ECC repo and find the **commits** count near the top (it links to
the full history). Click it and read the **5 most recent commit messages**.

Write down: *Are recent changes mostly about skills, agents, hooks, or something
else?* This tells you what the project is focused on right now.

---

## Key terms

| Term | Plain meaning |
|------|---------------|
| Agent | A specialist the AI delegates a sub-task to |
| Command | A typed shortcut (e.g. `/plan`) you trigger |
| Skills-first | Preferring auto-grabbed skills over typed commands |
| `git log` | Command to read a repo's commit history |
| Branch | A line of commits (more in Ch8); ECC uses one `main` |

---

Next: the quieter-but-powerful pair — **rules and hooks** — and why ECC keeps its
config *inside* the repo.
**[Chapter 5 →](chapter-05-rules-and-hooks.md)**
