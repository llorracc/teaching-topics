# Class 04: MyST Modernization — Plan

**Unit:** [Research Skills](https://llorracc.github.io/workspace-course-topics/units/research-skills/unit.html) / [Contribution](https://llorracc.github.io/workspace-course-topics/units/contribution/unit.html)  
**Date:** TBD

---

## Pre-class assignments

Students arrive having completed: [Assignments for Class 04](../../assignments/for-class-04.md)

---

## Learning objectives

- **MyST assembly:** Create a multi-notebook MyST document with TOC and bibliography
- **Bibliography integration:** Configure `myst.yml` to use .bib files for citations across multiple notebooks

---

## In-class workflow

### Part 1: Four-Notebook MyST Assembly (~45 min)

Instead of converting the notebook to a markdown file, we create three new notebooks and weave them together with the original via a MyST table of contents:

| # | Step | Description |
|---|------|-------------|
| 1 | [Create intro notebook](https://llorracc.github.io/workspace-course-topics/assignments/create-intro-notebook.html) | Paper identity, original authors, student contributor |
| 2 | [Create prior-literature notebook](https://llorracc.github.io/workspace-course-topics/assignments/create-prior-literature-notebook.html) | Prior lit summary with `{cite}` references against `references.bib` |
| 3 | [Create subsequent-literature notebook](https://llorracc.github.io/workspace-course-topics/assignments/create-subsequent-literature-notebook.html) | Subsequent lit summary with `{cite}` references against `subsequent-literature.bib` |
| 4 | [MyST assembly](https://llorracc.github.io/workspace-course-topics/assignments/myst-assembly-and-pr.html) | Add citations to original notebook; create `myst.yml` TOC + bibliography config |
| 5 | Verify build | Run `myst build`; confirm citations resolve and bibliography renders |

The four notebooks in TOC order:

1. `[name]_intro.ipynb` — paper metadata and attribution (SST)
2. `[name]_prior-literature.ipynb` — prior literature with citations
3. `[name]_summary.ipynb` — original notebook (typos fixed, heading hierarchy, MyST citations, cross-reference links)
4. `[name]_subsequent-literature.ipynb` — subsequent literature with citations

See orchestrator: [05-myst-conversion](https://llorracc.github.io/workspace-course-topics/orchestrators/05-myst-conversion.html)

---

### Part 2: Update PRs (~15 min)

After assembly:
1. Stage new changes: `git add .`
2. Commit: `git commit -m "Add four-notebook MyST assembly"`
3. Push to update PR: `git push myfork [branch-name]`
4. Verify PR shows the four-notebook structure

---

## Key resources

- **MyST documentation:** https://mystmd.org
- **MyST Citations:** https://mystmd.org/guide/citations
- **Orchestrator:** [05-myst-conversion](https://llorracc.github.io/workspace-course-topics/orchestrators/05-myst-conversion.html)

---

## Assignments for next class

Complete before the next class: [Assignments for Class 05](../../assignments/for-class-05.md)
