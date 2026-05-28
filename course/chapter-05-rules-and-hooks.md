# Chapter 5 — Rules & Hooks

[← Chapter 4](chapter-04-agents-and-commands.md) · [Index](README.md) · Next: [Chapter 6 →](chapter-06-mcp-memory-learning.md)

---

## In plain words

Two more building blocks, both about **consistency** and **automation**.

- **Rules** = your **non-negotiables**. Things that must *always* be true, no matter
  the task. *Design analogy:* "Never use pure black (#000) for text" or "every screen
  must pass accessibility contrast." You don't restate them each time — they're just
  the law.

- **Hooks** = **automatic actions that fire on an event**. Something happens, and a
  hook reacts without anyone asking. *Design analogy:* an export preset that
  **auto-renames** files `ClientName_v01.png` the moment you hit export. You set it
  once; it runs forever.

Rules tell the AI *what must always hold true.* Hooks make certain things *happen
automatically.*

---

## How ECC actually does it

- **Rules** live in `rules/`, organized into `common/` (universal principles) plus
  one folder per language (TypeScript, Python, Go, Swift, PHP, …) — **34 sets** in
  total. They cover coding standards, security requirements, testing expectations,
  and git workflows. When working in Python, ECC applies the Python rules; in
  TypeScript, the TypeScript rules. Always-on, context-appropriate guardrails.

- **Hooks** live in `hooks/` (with helper programs in `scripts/`). They fire on
  **tool events** — for example:
  - **block** a bad action (stop a `console.log` from sneaking into TypeScript),
  - **auto-format** code after it's written,
  - **save/restore session state** so context persists.

  ECC notes a practical gotcha: in newer versions hooks are **auto-loaded** from the
  plugin, so you should *not* also declare them manually, or they'd load twice. (A
  good reminder that automation needs care.)

The shared theme: rules + hooks turn "please remember to…" into "it just happens."

---

## Git in this chapter — what & why

**Concept: config belongs _inside_ the repo so it travels with the project.**

Here's a subtle but crucial idea. Anything you set up only on **your own computer**
(personal settings, secret notes) is invisible to teammates and to cloud sessions.
But anything **committed into the repo** travels everywhere the repo goes.

That's exactly why ECC ships rules and hooks **as files in the repository** rather
than as personal settings. When you clone ECC, you get its rules and hooks too —
automatically.

In Claude Code, the place for committed project config is a file called:

```
.claude/settings.json
```

Because it's committed, every clone (and every cloud session) gets the same hooks
and behavior. The principle:

> **If you want it to apply everywhere, commit it. If it lives only on your laptop,
> it stays on your laptop.**

This is the single most important git habit for configuration: **commit the config,
don't keep it personal.**

---

## Check your understanding

**Q1. What's the difference between a rule and a hook?**

<details><summary>Show answer</summary>

A **rule** is an always-follow guideline (what must be true). A **hook** is an
automatic action that fires on an event (something that happens by itself).
</details>

**Q2. Why does ECC organize rules into `common/` plus per-language folders?**

<details><summary>Show answer</summary>

So universal principles apply everywhere (`common/`), while language-specific
standards (Python, TypeScript, …) apply only when you're working in that language.
</details>

**Q3. Give one real example of what a hook can do.**

<details><summary>Show answer</summary>

Any of: block a bad action (e.g. prevent `console.log` in TypeScript), auto-format
code after writing, or save/restore session state.
</details>

**Q4. Why does ECC keep rules and hooks as committed files instead of personal
settings?**

<details><summary>Show answer</summary>

Because committed files travel with the repo — everyone who clones it (and every
cloud session) gets the same behavior. Personal/local settings don't travel.
</details>

### Hands-on exercise

Think of **one rule** you'd want an AI to always follow on your design-to-code work.
Write it as a single must-statement, e.g.:

> "Always include descriptive alt text for every image."

Keep it; in Chapter 8 you'll see where rules like this would live.

---

## Key terms

| Term | Plain meaning |
|------|---------------|
| Rule | An always-follow guideline |
| Hook | An automatic action triggered by an event |
| `.claude/settings.json` | Committed project config (hooks, settings) |
| Commit-the-config | The habit of committing config so it travels with the repo |

---

Next: connecting the AI to the **outside world** (MCP) and how ECC **remembers and
learns**.
**[Chapter 6 →](chapter-06-mcp-memory-learning.md)**
