# Class 04: MyST Modernization — Plan

**Unit:** [Research Skills](https://llorracc.github.io/workspace-course-topics/units/research-skills/unit.html) / [Contribution](https://llorracc.github.io/workspace-course-topics/units/contribution/unit.html)  
**Date:** TBD

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

**You have already:**
- Forked the ballpark repo and run `setup_env.sh`
- Added yourself as coauthor
- Added prior and subsequent literature sections
- Created and submitted a Pull Request

---

## Learning objectives

- **MyST conversion:** Convert notebooks to MyST format for modern document building
- **Bibliography integration:** Configure MyST to use .bib files for citations

---

## In-class workflow

### Verify tools (~5 min)

Quick check that everyone's setup is working:

1. [Verify MyST tools](https://llorracc.github.io/workspace-course-topics/workflows/verify-myst-tools.html) — confirm `myst --version`, `jupytext --version`, and the Cursor extension
2. If anything is missing, re-run `bash scripts/setup_env.sh` or follow the manual install workflows

---

### Part 1: MyST Conversion and Bibliography (~50 min)

Now we modernize the ballpark items using MyST. Since tools are already installed, we jump straight to conversion:

| # | Workflow | Description |
|---|----------|-------------|
| 1 | [Convert notebook to MyST](https://llorracc.github.io/workspace-course-topics/workflows/convert-notebook-to-myst.html) | Convert `.ipynb` to `.md` format using jupytext |
| 2 | [Set up bibliography for MyST](https://llorracc.github.io/workspace-course-topics/workflows/bibliography-setup-myst.html) | Configure `myst.yml` to use .bib files |
| 3 | [Add citations in MyST syntax](https://llorracc.github.io/workspace-course-topics/workflows/add-citation-to-paper.html) | Add proper `{cite}` references |
| 4 | [Add LitMap image and bib](https://llorracc.github.io/workspace-course-topics/workflows/add-litmap-image-and-bib.html) | Add citation map visualization |
| 5 | [AI "Subsequent Literature" section](https://llorracc.github.io/workspace-course-topics/workflows/ai-subsequent-literature-section.html) | AI-assisted summary of citing papers |

See orchestrator: [05-myst-conversion](https://llorracc.github.io/workspace-course-topics/orchestrators/05-myst-conversion.html)

---

### Part 2: Update PRs (~15 min)

After MyST conversion:
1. Stage new changes: `git add .`
2. Commit: `git commit -m "Convert to MyST format"`
3. Push to update PR: `git push origin <branch-name>`
4. Verify PR shows MyST conversion

---

## Key resources

- **MyST documentation:** https://mystmd.org
- **Orchestrator:** [05-myst-conversion](https://llorracc.github.io/workspace-course-topics/orchestrators/05-myst-conversion.html)
- **as.180.369 materials:** [The Submission](https://github.com/llorracc/as.180.369/blob/main/materials/submission/README.md)

---

## Assignments for next class

Complete before the next class: [Assignments for Class 05](../../assignments/for-class-05.md)
