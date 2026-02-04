# Class 04: MyST Modernization and PR Review — Plan

**Unit:** [Research Skills](../../units/research-skills/) / [Contribution](../../units/contribution/)  
**Date:** TBD

---

## Pre-class assignments (required BEFORE class)

You should arrive with these completed:

| # | Assignment | Deliverable |
|---|------------|-------------|
| 025 | [Literature Context & Improvements](../../assignments/025-ai-paper-deep-dive/assignment.md) | `literature-and-improvements.md` + **PR URL** |
| 030 | [Subsequent Literature](../../assignments/030-subsequent-literature/assignment.md) | `subsequent-literature.bib` |
| 040 | [AI Literature Analysis](../../assignments/040-ai-literature-analysis/assignment.md) | `subsequent-literature-analysis.md` |

**Critical:** Assignment 025 requires submitting a Pull Request BEFORE class.

---

## Learning objectives

- **Review PRs:** Give and receive feedback on each other's Pull Requests
- **MyST conversion:** Convert notebooks to MyST format
- **Bibliography integration:** Configure MyST to use .bib files for citations
- **Modern tooling:** Use MyST CLI and extensions for document building

---

## In-class workflow

### Part 1: PR Review (~30 min)

1. **Share PR URLs** — Each student shares their PR from Assignment 025
2. **Peer review** — Review 2-3 other students' PRs:
   - Are the literature sections well-written?
   - Are improvement suggestions implemented?
   - Any issues with the changes?
3. **Discuss common patterns** — What worked well? What needs improvement?

---

### Part 2: MyST Modernization (~60 min)

These are the steps we didn't complete in Class 03:

| # | Workflow | Description |
|---|----------|-------------|
| 9 | [Ask Cursor about MyST extension](../../workflows/ask-cursor-about-myst-extension.md) | Ask Cursor whether there's a MyST extension |
| 10 | [Install MyST-Markdown extension](../../workflows/install-myst-extension.md) | Install VS Code extension for syntax highlighting |
| 11 | [Install MyST (CLI)](../../workflows/install-myst-cli.md) | Install the MyST command-line tool |
| 12 | [Convert notebook to MyST](../../workflows/convert-notebook-to-myst.md) | Convert `.ipynb` to `.md` format |
| 13 | [Set up bibliography files](../../workflows/bibliography-setup-myst.md) | Configure `myst.yml` to use .bib files |
| 14 | [Add citation to the paper](../../workflows/add-citation-to-paper.md) | Add proper citations in MyST syntax |
| 15 | [Add LitMap image and bib](../../workflows/add-litmap-image-and-bib.md) | Add visualization and subsequent-literature.bib |
| 16 | [AI "Subsequent Literature" section](../../workflows/ai-subsequent-literature-section.md) | Use AI to generate summary of citing papers |

See orchestrator: [05-myst-conversion](../../orchestrators/05-myst-conversion.md)

---

### Part 3: Update PRs (~20 min)

After MyST modernization:
1. Stage new changes: `git add .`
2. Amend commit or create new commit
3. Push to update PR
4. Verify PR shows MyST conversion

---

## Key resources

- **MyST documentation:** https://mystmd.org
- **Orchestrator:** [05-myst-conversion](../../orchestrators/05-myst-conversion.md)
- **as.180.369 materials:** [The Submission](https://github.com/llorracc/as.180.369/blob/main/materials/submission/README.md)

---

## Assignment after this class

You will create your **own ballpark objects** for new papers (details TBD).
