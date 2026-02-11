# Class 04: MyST Modernization and PR Review — Plan

**Unit:** [Research Skills](../../units/research-skills/) / [Contribution](../../units/contribution/)  
**Date:** TBD

---

## Pre-class setup (completed BEFORE class)

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

### Assignments

You should arrive with:

| # | Assignment | Deliverable |
|---|------------|-------------|
| 025 | [Literature Context & Improvements](../../assignments/025-ai-paper-deep-dive/assignment.md) | `literature-and-improvements.md` + **PR URL** |
| 030 | [Subsequent Literature](../../assignments/030-subsequent-literature/assignment.md) | `subsequent-literature.bib` |
| 040 | [AI Literature Analysis](../../assignments/040-ai-literature-analysis/assignment.md) | `subsequent-literature-analysis.md` |

**You have already:**
- Forked the ballpark repo and run `setup_env.sh`
- Added yourself as coauthor
- Added prior and subsequent literature sections
- Created and submitted a Pull Request
- Exported citing papers from LitMaps
- Analyzed the literature with AI

---

## Learning objectives

- **Review PRs:** Give and receive feedback on each other's Pull Requests
- **MyST conversion:** Convert notebooks to MyST format for modern document building
- **Bibliography integration:** Configure MyST to use .bib files for citations

---

## In-class workflow

### Verify tools (~5 min)

Quick check that everyone's setup is working:

1. [Verify MyST tools](../../workflows/verify-myst-tools.md) — confirm `myst --version`, `jupytext --version`, and the Cursor extension
2. If anything is missing, re-run `bash scripts/setup_env.sh` or follow the manual install workflows

---

### Part 1: PR Review (~30 min)

1. **Share PR URLs** — Each student shares their PR from Assignment 025
2. **Peer review** — Review 2-3 other students' PRs:
   - Are the literature sections well-written?
   - Are the improvement suggestions implemented?
   - Any issues with the changes?
3. **Discuss common patterns** — What worked well? What needs improvement?

---

### Part 2: MyST Conversion and Bibliography (~50 min)

Now we modernize the ballpark items using MyST. Since tools are already installed, we jump straight to conversion:

| # | Workflow | Description |
|---|----------|-------------|
| 1 | [Convert notebook to MyST](../../workflows/convert-notebook-to-myst.md) | Convert `.ipynb` to `.md` format using jupytext |
| 2 | [Set up bibliography for MyST](../../workflows/bibliography-setup-myst.md) | Configure `myst.yml` to use .bib files |
| 3 | [Add citations in MyST syntax](../../workflows/add-citation-to-paper.md) | Add proper `{cite}` references |
| 4 | [Add LitMap image and bib](../../workflows/add-litmap-image-and-bib.md) | Add citation map visualization |
| 5 | [AI "Subsequent Literature" section](../../workflows/ai-subsequent-literature-section.md) | AI-assisted summary of citing papers |

See orchestrator: [05-myst-conversion](../../orchestrators/05-myst-conversion.md)

---

### Part 3: Update PRs (~15 min)

After MyST conversion:
1. Stage new changes: `git add .`
2. Commit: `git commit -m "Convert to MyST format"`
3. Push to update PR: `git push origin <branch-name>`
4. Verify PR shows MyST conversion

---

## Key resources

- **MyST documentation:** https://mystmd.org
- **Orchestrator:** [05-myst-conversion](../../orchestrators/05-myst-conversion.md)
- **as.180.369 materials:** [The Submission](https://github.com/llorracc/as.180.369/blob/main/materials/submission/README.md)

---

## Assignment after this class

You will create your **own ballpark objects** for new papers (details TBD).
