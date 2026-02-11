# Class 04: MyST Modernization — Plan

**Unit:** [Research Skills](https://llorracc.github.io/workspace-course-topics/units/research-skills/unit.html) / [Contribution](https://llorracc.github.io/workspace-course-topics/units/contribution/unit.html)  
**Date:** 2026-02-10 (Tue)

---

## Pre-class assignments

Students arrive having completed: [Assignments for Class 04](../../assignments/for-class-04.md)

---

## Pre-class setup

### Fork and environment

1. **Fork** econ-ark/ballpark to your own GitHub account (do NOT just clone it)
2. Clone **your fork**: `git clone https://github.com/<your-username>/ballpark.git`
3. Run the setup script from the repo root:
   ```bash
   cd ~/GitHub/<your-username>/ballpark
   bash scripts/setup_env.sh
   ```
   This installs all tools: Homebrew, node/npm, uv, Python venv (with jupytext and myst-parser), mystmd CLI, and the MyST-Markdown Cursor extension.

**Important — Fork vs. Clone:** If you cloned econ-ark/ballpark directly, you won't be able to push or open PRs. You must fork first, then either re-clone your fork or update your remote:
```bash
git remote rename origin upstream
git remote add origin https://github.com/<your-username>/ballpark.git
```

**Prerequisites** (completed in Classes 01–03):
- Forked the ballpark repo and run `setup_env.sh`
- Added yourself as coauthor in your notebook
- Created prior-literature and subsequent-literature materials

---

## Learning objectives

- **MyST assembly:** Create a multi-notebook MyST document with TOC and bibliography
- **Bibliography integration:** Configure `myst.yml` to use .bib files for citations across multiple notebooks

---

## In-class workflow

### Verify tools (~5 min)

Quick check that everyone's setup is working:

1. [Verify MyST tools](https://llorracc.github.io/workspace-course-topics/workflows/verify-myst-tools.html) — confirm `myst --version`, `jupytext --version`, and the Cursor extension
2. If anything is missing, re-run `bash scripts/setup_env.sh` or follow the manual install workflows

---

### Part 1: Four-Notebook MyST Assembly (~50 min)

Instead of converting the notebook to a markdown file, we create three new notebooks and weave them together with the original via a MyST table of contents:

| # | Step | Description |
|---|------|-------------|
| 1 | [Create intro notebook](https://llorracc.github.io/workspace-course-topics/assignments/create-intro-notebook.html) | Paper identity, original authors, student contributor |
| 2 | [Create prior-literature notebook](https://llorracc.github.io/workspace-course-topics/assignments/create-prior-literature-notebook.html) | Prior lit summary with `{cite}` references against `references.bib` |
| 3 | [Create subsequent-literature notebook](https://llorracc.github.io/workspace-course-topics/assignments/create-subsequent-literature-notebook.html) | Subsequent lit summary with `{cite}` references against `subsequent-literature.bib` |
| 4 | [MyST assembly](https://llorracc.github.io/workspace-course-topics/assignments/myst-assembly-and-pr.html) | Add citations to original notebook; create `myst.yml` TOC + bibliography config |
| 5 | Verify build | Run `myst build`; confirm citations resolve and bibliography renders |

The four notebooks in TOC order:

1. `[name]_intro.ipynb` — paper metadata
2. `[name]_prior-literature.ipynb` — prior literature with citations
3. `[name].ipynb` — original notebook (modified with citations, NOT converted)
4. `[name]_subsequent-literature.ipynb` — subsequent literature with citations

See orchestrator: [05-myst-conversion](https://llorracc.github.io/workspace-course-topics/orchestrators/05-myst-conversion.html)

---

### Part 2: Update PRs (~15 min)

After assembly:
1. Stage new changes: `git add .`
2. Commit: `git commit -m "Add four-notebook MyST assembly"`
3. Push to update PR: `git push origin <branch-name>`
4. Verify PR shows the four-notebook structure

---

## Key resources

- **MyST documentation:** https://mystmd.org
- **MyST Citations:** https://mystmd.org/guide/citations
- **Orchestrator:** [05-myst-conversion](https://llorracc.github.io/workspace-course-topics/orchestrators/05-myst-conversion.html)

---

## Assignments for next class

Complete before the next class: [Assignments for Class 05](../../assignments/for-class-05.md)
