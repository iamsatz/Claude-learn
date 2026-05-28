# Understanding ECC — A Beginner's Course

> A friendly, no-prior-coding-needed course that explains what the
> **ECC** repo (`github.com/affaan-m/ECC`) is, teaches a little **git** in every
> chapter, and ends with **you building your own first tool (skill)**.

Written for a **designer who is new to code and git**. Every term is defined.
Read slowly. Do the exercises. There are no stupid questions here.

---

## What is ECC, in one sentence?

ECC is a big, free **toolbox of ready-made instructions** that make AI coding
assistants (like Claude Code) smarter and more consistent — it bundles together
*agents, skills, commands, rules, hooks,* and *external tool connections (MCP)*.

By the end of this course you'll understand each of those words **and** you'll have
made your own small version of one.

---

## How to use this course

1. Read the chapters **in order** — each builds on the last.
2. In every chapter, look for these three boxes:
   - **In plain words** — the idea explained with everyday/design analogies.
   - **Git in this chapter — what & why** — a tiny, practical git lesson.
   - **Check your understanding** — a short quiz (answers are hidden — click to
     reveal) and one small hands-on exercise.
3. Don't rush. One chapter per sitting is totally fine.

> **Tip:** To reveal a hidden answer in these files, click the little triangle
> next to "Show answer." On GitHub and most Markdown viewers it expands.

---

## The chapters

| # | Chapter | You'll learn | Git lesson |
|---|---------|--------------|------------|
| 1 | [What is ECC?](chapter-01-what-is-ecc.md) | The big picture | What a *repository* is; `git clone` |
| 2 | [The building blocks](chapter-02-the-building-blocks.md) | The 6 parts of ECC | How folders map to features |
| 3 | [Skills in depth](chapter-03-skills-in-depth.md) | What a *skill* really is | How files are *committed* |
| 4 | [Agents & commands](chapter-04-agents-and-commands.md) | Helpers vs. shortcuts | Reading history with `git log` |
| 5 | [Rules & hooks](chapter-05-rules-and-hooks.md) | Standards & automation | Why config lives in the repo |
| 6 | [MCP, memory & learning](chapter-06-mcp-memory-learning.md) | Connecting outside tools | Versioning settings |
| 7 | [Installing ECC](chapter-07-installing-ecc.md) | The 3 install paths | `git clone`, `git pull` |
| 8 | [Build your own](chapter-08-build-your-own.md) | **Make your first skill** | branch → commit → push → PR |

---

## Glossary (skim now, return often)

### Git words

- **Repository ("repo")** — a project folder that git tracks. Think: a design
  project folder that remembers every saved version.
- **GitHub** — a website that stores repos online so others can see/use them.
- **Clone** — download a full copy of a repo to a computer. (`git clone <url>`)
- **Commit** — a saved snapshot of your changes, with a short message. Like
  "Save As… v3, added contact slide."
- **Branch** — a parallel copy where you can experiment without touching the
  main version. Like a "draft" art board.
- **Push** — upload your commits from your computer to GitHub.
- **Pull** — download new commits from GitHub to your computer.
- **Pull Request (PR)** — a proposal that says "please add my changes to the main
  project," which others can review before accepting.
- **Merge** — accept a branch's changes into the main version.

### AI-assistant words (the stars of ECC)

- **Harness** — the *app* you run the AI assistant inside (Claude Code, Cursor,
  etc.). ECC works across several harnesses.
- **Agent** — a specialized helper persona (e.g. "code-reviewer") the main AI can
  hand a sub-task to.
- **Skill** — a labeled instruction card the AI loads *by itself* when a task
  matches. ECC's main building block.
- **Command** — a shortcut you type, like `/plan`, to trigger something.
- **Rule** — an always-follow guideline (e.g. "always check color contrast").
- **Hook** — an automatic action that fires on an event (e.g. auto-format after
  saving a file).
- **MCP (Model Context Protocol)** — a standard way to connect the AI to outside
  tools (GitHub, calendars, databases).
- **Instinct / memory** — patterns ECC saves from past sessions so the AI keeps
  learning and remembering across time.

---

Ready? Start with **[Chapter 1 →](chapter-01-what-is-ecc.md)**.
