# Class 10: Job market guest & Matsya workshop — Plan

**Unit:** [Research Skills](../../units/research-skills/) / [Contribution](../../units/contribution/)  
**Date:** April 7, 2026

---

## Pre-class assignments

Students were expected to have worked on (assigned in Class 9): [Assignments for Class 10](../../assignments/for-class-10.md)

- [Ask AI to assess REMARK compliance](https://llorracc.github.io/workspace-course-topics/assignments/ask-ai-to-assess-remark-compliance.html)
- [Explore the SSJ tutorial notebook](https://llorracc.github.io/workspace-course-topics/assignments/explore-ssj-tutorial.html)

*(Class time did not center on collecting these; they remain due per the assignment pages.)*

---

## Learning objectives

- Hear how **job-market / vacancy data** (e.g. EJM postings) can be used in research and what **data-sharing constraints** apply when posting materials publicly.
- Install and configure **programmatic Claude** (API key, shell, prepaid billing mental model).
- Install **Claude Code** (with dependencies such as **Node.js** where needed) and **Matsya** from the econ-ark repo.
- Use **Cursor** (Composer + context) to feed **ballpark** notebooks to Matsya and move toward a **Dolo Plus**-style description of a **Bellman** problem.
- Understand **WSL vs. native paths** for Windows users and that **Matsya is context-external** (unlike Composer’s threaded memory).

---

## In-class workflow

### 1. Guest lecture — labor market / job postings (~first block)

- Guest (**Kyung Woong Koh**, JHU Economics): presentation on work involving **job postings** / market-side evidence (e.g. **EJM**).
- **Discussion:** what can and cannot be placed in a **public GitHub repo** (permissions, data use).
- **Follow-up:** instructor to obtain **slides** (and later a **repo URL** if sharing is cleared) for linking from course materials.

---

### 2. Matsya workshop — API keys and environment (~main block)

- **Claude API:** create/top up credits, generate key, **store once** (keys are not shown again), add `export` lines to **`.bashrc` / `.zshrc`**, **reload shell** or open a new terminal.
- **Billing model:** prepaid credits; tool **stops** when balance is exhausted until replenished.
- **Platform notes:** **Mac** (e.g. Homebrew) vs **Windows** — work **inside WSL**; clone and open the project from the **Linux filesystem** so IDE and terminal agree.

---

### 3. Install Claude Code and Matsya

- Install **Node.js** if needed for Claude Code.
- **`pip install`** Matsya from [econ-ark/Matsya](https://github.com/econ-ark/Matsya) (or follow current README).
- Install **Claude Code** and the **Cursor** extension; set **Anthropic** and any **Matsya-specific** env vars as documented.

---

### 4. Cursor + Matsya on the ballpark

- Open the **ballpark** repo in Cursor; add **notebooks / files** to Composer context.
- **Emphasize:** each Matsya query must include **enough context** (e.g. “the notebook”) — Matsya does **not** auto-read the whole repo.
- Use Matsya to: **explain** hard passages, **check** Bellman structure, and **draft** **Dolo Plus** specifications where the paper has a clear dynamic problem.
- **If** the chosen ballpark is **purely empirical** with no Bellman problem, **switch** to a paper that has an explicit dynamic program for this exercise.

---

### 5. Wrap-up and next steps

- Reinforce **repo hygiene** and directory layout for reproducibility.
- **Next:** iterate on ballpark text and math with Matsya; monitor **API usage**; submit improved ballpark + Dolo Plus direction per ongoing assignment messaging (see course announcements).

---

## Reference links

- Anthropic Claude console / dashboard (API keys, billing)
- [econ-ark/Matsya](https://github.com/econ-ark/Matsya) README
- Cursor — Claude Code extension
- Dolo / Dolo Plus documentation
