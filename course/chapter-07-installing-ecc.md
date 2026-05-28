# Chapter 7 — Installing ECC

[← Chapter 6](chapter-06-mcp-memory-learning.md) · [Index](README.md) · Next: [Chapter 8 →](chapter-08-build-your-own.md)

---

## In plain words

You understand *what's* in ECC. Now: how do you actually *get it onto your machine*?
ECC offers **three paths**, from easiest to most hands-on. Think of it like
installing a font:

- **Plugin install** — like installing from an app's built-in store. Cleanest.
- **Manual install** — like downloading the font file and running an installer. Full
  control.
- **Minimal install** — like grabbing just the one weight you need. Lightweight.

> ⚠️ ECC's own warning: **don't mix paths.** Pick one and stick with it, or parts can
> collide. (Good life advice for installers in general.)

---

## How ECC actually does it

### Path 1 — Plugin install (recommended)

Inside Claude Code, you add ECC as a "marketplace," then install it:

```text
/plugin marketplace add https://github.com/affaan-m/ECC
/plugin install ecc@ecc
```

Then you copy in only the **rule** folders for languages you care about:

```bash
mkdir -p ~/.claude/rules/ecc
cp -r rules/common ~/.claude/rules/ecc/
cp -r rules/typescript ~/.claude/rules/ecc/   # add your language(s)
```

(`mkdir` = make a folder; `cp -r` = copy a folder and everything in it.)

### Path 2 — Manual install (full control)

```bash
git clone https://github.com/affaan-m/ECC.git
cd ECC
./install.sh --profile full     # macOS/Linux
.\install.ps1 --profile full    # Windows
```

(`cd` = "change directory," i.e. step into the folder. `./install.sh` runs the
included installer script.)

### Path 3 — Minimal (rules only, skip hooks)

```bash
./install.sh --profile minimal --target claude
```

After installing, ECC gives you workflows like `/ecc:plan "Add user auth"`,
the `tdd-workflow` skill, `/code-review`, `/build-fix`, and a desktop dashboard
(`npm run dashboard`) to browse everything visually.

---

## Git in this chapter — what & why

This chapter is **the** git chapter — two everyday commands you'll use forever.

**`git clone` — get the project the first time.**

```bash
git clone https://github.com/affaan-m/ECC.git
```

This downloads the whole repo (files **and** full history) into a new `ECC/` folder.
You run `clone` **once** per project. Notice Path 1 does this *for* you behind
`/plugin marketplace add` — the marketplace command fetches the repo so you don't
type `clone` yourself. Same idea, friendlier wrapper.

**`git pull` — get updates later.**

ECC ships weekly updates. To refresh your copy with the latest commits:

```bash
git pull
```

`pull` = "download new commits from GitHub and apply them to my copy." Use `clone`
**once** to get it; use `pull` **whenever** you want the newest version.

| Command | When | Plain meaning |
|---------|------|---------------|
| `git clone <url>` | First time | Download the whole repo |
| `git pull` | Anytime after | Fetch + apply the newest changes |
| `cd <folder>` | — | Step into a folder |
| `mkdir`, `cp -r` | — | Make a folder; copy a folder |

> **Why two different commands?** `clone` creates the local copy from nothing;
> `pull` updates a copy you already have. You can't `pull` what you haven't `clone`d
> yet, and you don't re-`clone` just to get updates.

---

## Check your understanding

**Q1. Which install path is recommended, and what two commands start it?**

<details><summary>Show answer</summary>

The **plugin install**: `/plugin marketplace add https://github.com/affaan-m/ECC`
then `/plugin install ecc@ecc`.
</details>

**Q2. What's the difference between `git clone` and `git pull`?**

<details><summary>Show answer</summary>

`git clone` downloads a repo for the **first time** (creating a local copy).
`git pull` **updates** a copy you already have with the newest commits.
</details>

**Q3. Why does ECC warn against mixing install paths?**

<details><summary>Show answer</summary>

Different paths can install overlapping pieces that collide or duplicate. Pick one
path and stick with it.
</details>

**Q4. In Path 1, you never type `git clone` yourself — why does the project still
end up on your machine?**

<details><summary>Show answer</summary>

`/plugin marketplace add` fetches the repo for you under the hood. It's a friendly
wrapper around the same clone idea.
</details>

### Hands-on exercise

You don't have to install ECC. Instead, **recognize the commands in the wild**: open
ECC's README on GitHub and find the install section. Match each command you see to
the table above — which line is the `clone`? Which would update it later?

---

## Key terms

| Term | Plain meaning |
|------|---------------|
| `git clone <url>` | Download a repo for the first time |
| `git pull` | Fetch and apply the newest commits |
| `cd` | Change into a folder |
| `mkdir` / `cp -r` | Make a folder / copy a folder recursively |
| Plugin marketplace | A friendly installer that clones the repo for you |

---

The finale: you'll **build your own first skill** in this repo and run the real
git workflow end to end.
**[Chapter 8 →](chapter-08-build-your-own.md)**
