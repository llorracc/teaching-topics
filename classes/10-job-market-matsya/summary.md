# Class 10 — Job market guest lecture and Matsya workshop

**Date:** April 7, 2026

**Recording:** Zoom cloud recording for **180.606 Topics — Part 2** (~1h 53m); link and transcript are in the meeting-assets email from Zoom (Apr 7, 2026). *(AI-generated meeting summary below; verify against recording.)*

---

## Part 1: Guest presentation — labor market / job postings

Kyung Woong Koh (PhD candidate, JHU Economics) presented in class and shared slides afterward. The thread referenced **EJM (European Job Market)** data on job postings and whether those data could be released in a **public GitHub repository** — pending confirmation with EJM personnel.

*Instructor follow-up:* Slides were requested for archiving and linking from the course materials; any public repo URL will be added here once sharing is cleared.

---

## Part 2: Matsya — API keys, install, and Dolo Plus workflow

> **Note:** Zoom’s auto-summary spells the tool “Matzia”; course materials use **Matsya** ([econ-ark/Matsya](https://github.com/econ-ark/Matsya)).

### Overview

Hands-on session on turning **programmatic AI** (Claude API) and **Matsya** into part of the research stack: obtaining API keys, shell configuration, installing **Claude Code** and Matsya, and using Matsya inside **Cursor** to read ballpark notebooks and work toward **Dolo Plus** representations of Bellman problems.

### Concepts and tools

- **API keys** — one-time visibility, prepaid billing, export in `.bashrc` / `.zshrc` for persistent use.
- **Matsya** — economics-focused assistant for heterogeneous-agent / Bellman-style models (course framing: HA analogue to tools like Dynare for RA models).
- **Dolo Plus** — extended model-description language building on Dolo for HA models.
- **Claude Code** — CLI / IDE integration (requires Node.js, etc.).
- **WSL** — Windows users need clones and tooling **inside** the Linux filesystem, not only on the Windows side.

### Q&A (sanitized)

- **Reloading shell config after API changes:** Environment changes to login files require reloading the shell (or opening a new terminal); usage stops when credits are exhausted until you add more.
- **WSL and “not seeing folders”:** If the project lives under WSL, clone and open the repo from the **WSL path** so Cursor and the terminal agree on the workspace.
- **Matsya vs. Cursor Composer:** Matsya does **not** see the project unless you paste or attach context each time — unlike Composer, it has no implicit memory of prior turns.

### Takeaways

- Students set up **Claude API** billing and keys and wired them into the shell.
- **Claude Code** + **Matsya** install paths were walked through (Mac/Homebrew vs. WSL).
- **Cursor** integration: Composer used to feed notebooks to Matsya for math/Bellman discussion and Dolo Plus drafts.
- Reinforced **repo layout** and that ballpark projects should include a **Bellman / dynamic problem** if the goal is a Dolo Plus specification.

### Suggested next steps (from Zoom summary)

- Use Matsya on your **ballpark** project: clarify math, improve descriptions, and request a **Dolo Plus** spec where applicable.
- If the original ballpark was purely empirical with no Bellman problem, pick a paper that has a clear dynamic program.
- Monitor **API credit** balance while iterating.

### Supplemental pointers

- Anthropic Claude console / dashboard for API keys and billing.
- Matsya repository README and install instructions.
- Cursor + Claude Code extension.
- Dolo / Dolo Plus documentation for syntax.

---

## Assignments in play (from Class 9)

Due before this class or ongoing — see [Assignments for Class 10](https://github.com/llorracc/teaching-topics/blob/main/assignments/for-class-10.md) (REMARK compliance self-assessment; SSJ tutorial exploration).
