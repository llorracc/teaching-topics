# Class 04: MyST Modernization and PR Review — Plan

**Unit:** [Research Skills](../../units/research-skills/) / [Contribution](../../units/contribution/)  
**Date:** TBD

---

## Pre-class assignments (completed BEFORE class)

You should arrive with:

| # | Assignment | Deliverable |
|---|------------|-------------|
| 025 | [Literature Context & Improvements](../../assignments/025-ai-paper-deep-dive/assignment.md) | `literature-and-improvements.md` + **PR URL** |
| 030 | [Subsequent Literature](../../assignments/030-subsequent-literature/assignment.md) | `subsequent-literature.bib` |
| 040 | [AI Literature Analysis](../../assignments/040-ai-literature-analysis/assignment.md) | `subsequent-literature-analysis.md` |

**You have already:**
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

### Part 1: PR Review (~30 min)

1. **Share PR URLs** — Each student shares their PR from Assignment 025
2. **Peer review** — Review 2-3 other students' PRs:
   - Are the literature sections well-written?
   - Are the improvement suggestions implemented?
   - Any issues with the changes?
3. **Discuss common patterns** — What worked well? What needs improvement?

---

### Part 2: MyST Modernization (~45 min)

Now we modernize the ballpark items using MyST:

| # | Workflow | Description |
|---|----------|-------------|
| 1 | [Install MyST-Markdown extension](../../workflows/install-myst-extension.md) | VS Code extension for syntax highlighting |
| 2 | [Install MyST (CLI)](../../workflows/install-myst-cli.md) | Command-line tool for building documents |
| 3 | [Convert notebook to MyST](../../workflows/convert-notebook-to-myst.md) | Convert `.ipynb` to `.md` format |
| 4 | [Set up bibliography for MyST](../../workflows/bibliography-setup-myst.md) | Configure `myst.yml` to use .bib files |
| 5 | [Add citations in MyST syntax](../../workflows/add-citation-to-paper.md) | Add proper `{cite}` references |

See orchestrator: [05-myst-conversion](../../orchestrators/05-myst-conversion.md)

---

### Part 3: Update PRs (~15 min)

After MyST conversion:
1. Stage new changes: `git add .`
2. Commit: `git commit -m "Convert to MyST format"`
3. Push to update PR: `git push myfork [branch-name]`
4. Verify PR shows MyST conversion

---

## Key resources

- **MyST documentation:** https://mystmd.org
- **Orchestrator:** [05-myst-conversion](../../orchestrators/05-myst-conversion.md)
- **as.180.369 materials:** [The Submission](https://github.com/llorracc/as.180.369/blob/main/materials/submission/README.md)

---

## Assignment after this class

You will create your **own ballpark objects** for new papers (details TBD).
