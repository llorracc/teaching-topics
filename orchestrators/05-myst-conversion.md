# Orchestrator: MyST Assembly

**Phase:** Skills  
**Time:** ~45 minutes

## Purpose

Create a multi-notebook MyST document that weaves together an intro, prior literature, the original notebook, and subsequent literature — with proper citations and a unified table of contents.

---

## Prerequisites

- `.bib` files from PaperPile (`references.bib`) and LitMaps (`subsequent-literature.bib`)
- `prior-literature.md` working document (from Assignment 030)
- `subsequent-literature-analysis.md` working document (from Assignment 040)
- **Environment set up** via `bash scripts/setup_env.sh` (which installs MyST CLI, jupytext, myst-parser, and the Cursor extension)

---

## Target structure

Four notebooks in TOC order, plus two .bib files:

| Order | Notebook | Content | .bib source |
|-------|----------|---------|-------------|
| 1 | `[name]_intro.ipynb` | Paper identity, original authors, student contributor | — |
| 2 | `[name]_prior-literature.ipynb` | Prior lit summary with MyST citations | `references.bib` |
| 3 | `[name].ipynb` | Original notebook (modified with citations, NOT converted) | `references.bib` |
| 4 | `[name]_subsequent-literature.ipynb` | Subsequent lit summary with MyST citations | `subsequent-literature.bib` |

---

## Workflow sequence

### 1. [Verify MyST tools](../workflows/verify-myst-tools.md)

Quick check that all MyST tools are installed. If `setup_env.sh` ran successfully, this should take under a minute.

**Deliverable:** `myst --version` works; MyST-Markdown extension visible in Cursor

---

### 2. [Create intro notebook](https://llorracc.github.io/workspace-course-topics/assignments/create-intro-notebook.html)

Create `[name]_intro.ipynb` with paper metadata: title, authors, year, original ballpark authors, and student contributor name.

**Deliverable:** `[name]_intro.ipynb` created

---

### 3. [Create prior-literature notebook](https://llorracc.github.io/workspace-course-topics/assignments/create-prior-literature-notebook.html)

Create `[name]_prior-literature.ipynb` from your `prior-literature.md` working document. Insert MyST citations (`{cite:t}` / `{cite:p}`) that resolve against `references.bib`.

**Deliverable:** `[name]_prior-literature.ipynb` with citations

---

### 4. [Create subsequent-literature notebook](https://llorracc.github.io/workspace-course-topics/assignments/create-subsequent-literature-notebook.html)

Create `[name]_subsequent-literature.ipynb` from your analysis. Insert MyST citations that resolve against `subsequent-literature.bib`.

**Deliverable:** `[name]_subsequent-literature.ipynb` with citations

---

### 5. [MyST assembly and configuration](https://llorracc.github.io/workspace-course-topics/assignments/myst-assembly-and-pr.html)

Add MyST citations to the original notebook. Create `myst.yml` with TOC (four notebooks) and bibliography (two .bib files).

**Deliverable:** `myst.yml` configured; original notebook has MyST citations

---

### 6. Verify build

Run `myst build` from the paper folder and confirm:
- Build completes without errors
- Citations resolve (no "undefined citation" warnings)
- HTML output shows rendered bibliography

---

## Checkpoint

Before proceeding, verify:
- [ ] Four notebooks exist in the paper folder
- [ ] `myst.yml` lists all four notebooks in the TOC
- [ ] `references.bib` and `subsequent-literature.bib` are in the paper folder
- [ ] `myst build` completes without errors
- [ ] Citations render correctly in the build output

---

## Next orchestrator

[Contribution](06-contribution.md)
