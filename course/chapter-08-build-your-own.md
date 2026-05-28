# Chapter 8 — Build Your Own (Capstone)

[← Chapter 7](chapter-07-installing-ecc.md) · [Index](README.md)

---

## In plain words

This is the chapter you've been building toward. You'll **create your own skill** —
just like the 249 in ECC — and then walk the **full git workflow** that real
contributors use: *branch → commit → push → pull request.*

You're a designer, so we'll build a designer's skill: **`brand-checker`** — a card
that tells the AI how to review a design (or design-to-code work) against brand and
accessibility basics. Adapt the wording to your own brand anytime.

> You won't break anything. Git is *designed* so experiments are safe and undoable.

---

## Part A — Write the skill

A skill is a folder with a `SKILL.md` inside (remember Chapter 3). Here's a complete,
beginner-friendly example you can copy into a file at
`skills/brand-checker/SKILL.md` in this repo:

```markdown
---
name: brand-checker
description: Use when reviewing a UI design or front-end for brand and accessibility basics.
---

# Brand Checker

When reviewing a design or UI code, check these in order and report what passes
and what fails:

1. Color contrast: body text meets WCAG AA (4.5:1). Flag anything lower.
2. Never pure black (#000000) for text — use the brand near-black instead.
3. Headings use the brand display font; body uses the brand text font.
4. Every image has descriptive alt text.
5. Tap targets are at least 44x44px on mobile.
6. Spacing follows an 8px scale (4/8/16/24/32...).

End with a short checklist: each item marked PASS or FIX, with a one-line reason
for any FIX.
```

That's a real skill. The **description** says *when* the AI should grab it; the
**body** is your house style. Anyone (including the AI) can now apply your standards
consistently.

> Want it to be *your* brand? Swap the fonts, colors, and rules for your own. That's
> the whole point — a skill captures *your* taste once.

---

## Part B — The git workflow, step by step

Now we save it the professional way. Each step has a one-line "why."

### 1. Make a branch — a safe workspace

```bash
git checkout -b add-brand-checker-skill
```

**Why:** a *branch* is a parallel copy where you can work without disturbing the main
version (like a "draft" artboard). `checkout -b` creates one and switches to it.
The name describes the work.

### 2. Create the file

Add the `SKILL.md` shown above at `skills/brand-checker/SKILL.md`.
(Use any text editor, or ask me to create it for you.)

### 3. Stage it — choose what to snapshot

```bash
git add skills/brand-checker/SKILL.md
```

**Why:** `add` selects which changes go into the next snapshot — like picking the
layers you want to export.

### 4. Commit — take the labeled snapshot

```bash
git commit -m "Add brand-checker skill"
```

**Why:** `commit` saves the snapshot with a message explaining *why*. Future-you will
thank present-you.

### 5. Push — upload to GitHub

```bash
git push -u origin add-brand-checker-skill
```

**Why:** `push` sends your local commits up to GitHub so they exist beyond your
machine and others can see them. `-u origin <branch>` links your branch to GitHub the
first time.

### 6. Open a Pull Request — propose the change

On GitHub, click **"Compare & pull request."**

**Why:** a *pull request (PR)* says "please review and add my branch to the main
project." It's where teammates comment before the change is **merged** (accepted) into
`main`. This is exactly how ECC's contributors add new agents, skills, and rules —
the README literally says *"contribute via pull request."*

### The whole loop, at a glance

```
branch  →  edit  →  add  →  commit  →  push  →  pull request  →  merge
 (safe     (make    (pick   (snapshot  (upload  (propose +       (accepted
  space)    change)  files)  + label)   it)      review)          into main)
```

---

## Git in this chapter — what & why (summary)

| Command | What it does | Why you do it |
|---------|--------------|---------------|
| `git checkout -b <name>` | Make + switch to a branch | Work safely without touching `main` |
| `git add <file>` | Stage changes | Choose what goes in the snapshot |
| `git commit -m "..."` | Save a labeled snapshot | Record the change + the reason |
| `git push -u origin <name>` | Upload to GitHub | Share it; back it up off your machine |
| Pull Request | Propose + review | Let others approve before merging |
| Merge | Accept into `main` | Make the change official |

---

## Check your understanding

**Q1. Put these in order:** commit, push, branch, pull request, add.

<details><summary>Show answer</summary>

branch → add → commit → push → pull request. (Edit the file between branch and add.)
</details>

**Q2. Why work on a branch instead of directly on `main`?**

<details><summary>Show answer</summary>

A branch is a safe, parallel workspace — you can experiment freely without affecting
the main version, and others can review before it's merged.
</details>

**Q3. What's the difference between `commit` and `push`?**

<details><summary>Show answer</summary>

`commit` saves a snapshot **locally** (on your computer). `push` uploads your commits
to **GitHub** so they exist remotely and others can see them.
</details>

**Q4. What is a pull request, in your own words?**

<details><summary>Show answer</summary>

A proposal to add your branch's changes into the main project, with a review step
where others can comment before it's merged. It's how ECC accepts contributions.
</details>

### Hands-on exercise (the real one!)

Actually create your first skill in **this** repo:

1. Create the file `skills/brand-checker/SKILL.md` with the content from Part A
   (edit the fonts/colors to your own brand).
2. Run the git steps in Part B — or just ask me: *"create the brand-checker skill and
   commit it"* and I'll do steps 2–5 with you, explaining as we go.
3. Congratulations — you've authored a skill exactly like the ones in ECC. 🎉

---

## Where to go next

- **Make a second skill** for another part of your workflow (a `handoff-notes` skill,
  an `icon-export` skill — anything you do repeatedly).
- **Read one real ECC skill** on GitHub to see how pros phrase descriptions.
- **Revisit Chapter 5** and try writing a *rule*, then Chapter 6 to imagine an *MCP*
  connection (e.g. to a font library).
- When you're ready, we can turn your skills into a tiny plugin — your **own** mini
  version of ECC.

You started knowing none of these words. Now you can read ECC, explain its parts,
follow its git workflow, and build your own tools. That's the whole journey. 👏

[← Back to the index](README.md)
