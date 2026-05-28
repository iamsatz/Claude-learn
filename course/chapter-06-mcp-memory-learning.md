# Chapter 6 — MCP, Memory & Continuous Learning

[← Chapter 5](chapter-05-rules-and-hooks.md) · [Index](README.md) · Next: [Chapter 7 →](chapter-07-installing-ecc.md)

---

## In plain words

So far every building block lives *inside* the AI's world. This chapter is about
reaching **outside** and about the AI **getting better over time**.

- **MCP** (Model Context Protocol) = a **standard plug** for connecting the AI to
  outside tools — GitHub, databases, deploy platforms, documentation lookups.
  *Design analogy:* Figma **plugins**. Figma is great alone, but a plugin lets it
  talk to Jira, Unsplash, or your content sheet. MCP is that plugin socket, but for
  AI assistants. (Fun fact: in *this very session* I have MCP connections to GitHub,
  a calendar, and email.)

- **Memory** = notes the AI **keeps between sessions** so it doesn't forget your
  project every time you return. *Analogy:* a project handoff doc that's always
  up to date.

- **Instincts / continuous learning** = ECC **watches your sessions, spots recurring
  patterns, and turns them into reusable skills automatically.** *Analogy:* noticing
  you always do the same 3 cleanup steps, then saving them as a one-click action.

---

## How ECC actually does it

- **MCP configs** live in `mcp-configs/`. ECC ships ready-made connections to common
  services (GitHub, Supabase, Vercel, Context7, and more). A practical tip from ECC:
  **keep under ~10 MCPs enabled per project** — each connection consumes some of the
  AI's limited attention ("context window"), so more isn't always better.

- **Memory persistence** uses **hooks** (from Chapter 5!) to save context at the end
  of a session and restore it at the start of the next. So the building blocks
  combine: a *hook* powers the *memory* feature.

- **Instincts & continuous learning**: special "Stop-phase" hooks extract patterns
  when a session ends, then **cluster related patterns into new skills.** ECC v2 adds
  *confidence scoring* (how sure it is a pattern is real) and *evolution tracking*
  (how a pattern changes over time). In short: **ECC turns experience into new
  skills, automatically.**

Notice the beautiful loop: hooks feed memory and instincts → instincts become skills
→ skills make the AI better → which produces more experience to learn from.

---

## Git in this chapter — what & why

**Concept: _versioning_ your connections and settings (don't hand-configure).**

MCP connections are described in **config files** that ECC keeps in `mcp-configs/`
and commits to the repo. Why store them as committed files instead of clicking
buttons to set them up each time?

1. **Reproducible** — anyone who clones gets the exact same connections. No "works on
   my machine" mystery.
2. **Reviewable** — a connection change shows up as a diff in a commit, so others can
   see (and approve) what the AI can reach.
3. **Revertable** — if a config breaks something, git lets you go back to the last
   good version.

This is the same lesson as Chapter 5, applied to integrations: **describe it in a
file, commit the file.** Configuration-as-committed-files is a core professional
habit — it makes setups shareable, auditable, and undoable.

> Security note ECC echoes: more connections = more access. Commit only what you need,
> and review changes. Git makes that review possible.

---

## Check your understanding

**Q1. In one line, what is MCP for?**

<details><summary>Show answer</summary>

It's a standard way to connect the AI to outside tools (GitHub, databases, deploy
platforms, etc.) — like a plugin socket.
</details>

**Q2. Why does ECC suggest keeping under ~10 MCPs enabled per project?**

<details><summary>Show answer</summary>

Each connection consumes some of the AI's limited context window/attention, so too
many can crowd out the actual work.
</details>

**Q3. Which earlier building block powers ECC's memory feature?**

<details><summary>Show answer</summary>

Hooks — they save context at session end and restore it at the next start.
</details>

**Q4. Name two benefits of storing MCP connections as committed config files.**

<details><summary>Show answer</summary>

Any two of: reproducible (everyone gets the same setup), reviewable (changes show as
diffs), revertable (you can roll back a bad config).
</details>

### Hands-on exercise

List **two outside tools** you'd love an AI to connect to for your design work
(e.g. Figma, Google Drive, a font library, Jira). For each, write one sentence on
*what you'd ask it to do.* This is how you'd later decide which MCP connections to add.

---

## Key terms

| Term | Plain meaning |
|------|---------------|
| MCP | A standard way to connect the AI to outside tools |
| Context window | The AI's limited "attention"; connections consume it |
| Memory persistence | Saving/restoring context across sessions (via hooks) |
| Instincts / continuous learning | Auto-extracting patterns into new skills |
| Config-as-committed-files | Storing setups as files in the repo, not by hand |

---

Time to actually get ECC running — the three **install paths** and the git commands
behind them.
**[Chapter 7 →](chapter-07-installing-ecc.md)**
