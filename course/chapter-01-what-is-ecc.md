# Chapter 1 — What is ECC?

[← Course index](README.md) · Next: [Chapter 2 →](chapter-02-the-building-blocks.md)

---

## In plain words

Imagine you just hired a very talented assistant. They can do almost anything, but
on day one they don't know **your** preferences, **your** process, or **your**
shortcuts. You'd spend weeks teaching them.

Now imagine someone handed you a **giant binder** already filled with:
- ready-made "how we do it" cards,
- specialist helpers you can call on,
- automatic checklists that run on their own.

You hand the binder to your assistant and *instantly* they work like a seasoned pro.

**ECC is that binder — but for AI coding assistants.** Its full name is
*"the harness-native operator system for agentic work."* Don't worry about that
mouthful; just remember: **ECC = a big, shared toolbox that upgrades AI assistants.**

> Designer analogy: ECC is like a **design system** (a Figma library of components,
> color tokens, and usage rules). Instead of designing every button from scratch,
> you pull from the library. ECC is that library, but the "components" are
> instructions and helpers for an AI.

---

## How ECC actually does it

ECC is a **repository** on GitHub (`github.com/affaan-m/ECC`). Inside it packs a
huge amount of reusable material:

- **63 agents** (specialist helpers)
- **249 skills** (instruction cards — the main attraction)
- **79 commands** (typed shortcuts)
- **34 rule sets** (always-follow guidelines, organized by programming language)
- plus **hooks** (automations), **MCP configs** (outside-tool connections), and a
  **memory/learning** system.

It's **free and open-source** (MIT license) and works across many "harnesses" —
the apps that host AI assistants: Claude Code, Cursor, Codex, OpenCode, and more.

You don't need to understand all of those yet. The rest of this course unpacks them
one at a time. For now, the headline: **ECC is a packaged collection of AI
upgrades, shared as a GitHub repository.**

---

## Git in this chapter — what & why

**The word of the day: _repository_ (repo).**

A **repository** is just a project folder that **git** watches. Git is a tool that
remembers *every saved version* of the folder, forever. Designers "Save As v1, v2,
v3…"; git does that automatically and lets you see exactly what changed and when.

ECC lives in a repo so that:
1. **Anyone can copy it.** The whole toolbox is one downloadable package.
2. **Changes are tracked.** ECC has ~2,000 saved snapshots (called *commits*) — a
   complete history of how it grew.
3. **People can collaborate.** Many contributors add to the same binder safely.

**The command:** to get your own copy of any repo, you *clone* it:

```bash
git clone https://github.com/affaan-m/ECC.git
```

`clone` = "download the entire project, history and all, into a new folder on my
computer." That's the very first step of using almost any code project. (You won't
run this yet — just recognize it.)

> **Why this matters to you:** the repo *you* are reading this in is also a git
> repository. In Chapter 8 you'll make your own commits in it.

---

## Check your understanding

**Q1. In one sentence, what is ECC?**

<details><summary>Show answer</summary>

A big, shared, open-source toolbox of ready-made upgrades (skills, agents,
commands, rules, hooks, integrations) that make AI coding assistants smarter and
more consistent.
</details>

**Q2. What does "repository" mean, in plain words?**

<details><summary>Show answer</summary>

A project folder that git tracks — it remembers every saved version of the folder.
</details>

**Q3. What does `git clone` do?**

<details><summary>Show answer</summary>

It downloads a full copy of a repository (all files **and** its history) onto a
computer.
</details>

**Q4. True or false: you must understand all 6 building blocks of ECC before it's
useful.**

<details><summary>Show answer</summary>

False. You can use one part (say, a single skill) without understanding the rest.
This course teaches them one at a time.
</details>

### Hands-on exercise

You don't need to install anything. Just **open the ECC repo in your browser**:
visit `https://github.com/affaan-m/ECC` and find the list of folders near the top
(you should see `agents/`, `skills/`, `commands/`, etc.).

Write down (on paper or a note) **which folder name you're most curious about.**
We'll cover all of them — this just primes your brain.

---

## Key terms

| Term | Plain meaning |
|------|---------------|
| ECC | A shared toolbox of AI-assistant upgrades, stored as a GitHub repo |
| Repository (repo) | A project folder git tracks, with full version history |
| Clone | Download a full copy of a repo (`git clone <url>`) |
| Harness | The app that hosts the AI assistant (Claude Code, Cursor, …) |
| Open-source (MIT) | Free to use, copy, and modify |

---

Next up: the **six building blocks** that make ECC tick.
**[Chapter 2 →](chapter-02-the-building-blocks.md)**
