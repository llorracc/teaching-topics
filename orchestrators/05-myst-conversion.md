# Orchestrator: MyST Conversion

**Phase:** Skills  
**Time:** ~30 minutes

## Purpose

Convert your notebook to MyST format and configure bibliography integration.

---

## Prerequisites

- Notebook edited (from [Notebook Editing](https://llorracc.github.io/workspace-course-topics/orchestrators/04-notebook-editing.html))
- `.bib` files from PaperPile and LitMaps
- Bibliography Capture completed
- **Environment set up** via `bash scripts/setup_env.sh` (which installs MyST CLI, jupytext, myst-parser, and the Cursor extension)

---

## Workflow sequence

### 1. [Verify MyST tools](https://llorracc.github.io/workspace-course-topics/workflows/verify-myst-tools.html)

Quick check that all MyST tools are installed. If `setup_env.sh` ran successfully, this should take under a minute.

**Deliverable:** `myst --version`, `jupytext --version` both work; MyST-Markdown extension visible in Cursor

---

### 2. [Convert notebook to MyST](https://llorracc.github.io/workspace-course-topics/workflows/convert-notebook-to-myst.html)

Use jupytext to convert your `.ipynb` to MyST Markdown.

**Deliverable:** `.md` file created from notebook

---

### 3. [Set up bibliography files for MyST](https://llorracc.github.io/workspace-course-topics/workflows/bibliography-setup-myst.html)

Copy PaperPile bib; create a bib for the paper itself; configure MyST to use both.

---

### 4. [Add a citation to the paper](https://llorracc.github.io/workspace-course-topics/workflows/add-citation-to-paper.html)

Add a proper citation to the paper in your notebook/MyST document.

---

### 5. [Add LitMap image and subsequent-literature bib](https://llorracc.github.io/workspace-course-topics/workflows/add-litmap-image-and-bib.html)

Download the LitMap image; add it to the MyST document; add the subsequent-literature bib.

---

### 6. [Add "Subsequent Literature" section (AI-assisted)](https://llorracc.github.io/workspace-course-topics/workflows/ai-subsequent-literature-section.html)

Use AI to generate a summary of citing papers.

---

## Checkpoint

Before proceeding, verify:
- [ ] MyST CLI is installed
- [ ] Notebook is converted to `.md`
- [ ] Bibliography is configured in `myst.yml`
- [ ] Citations render correctly

---

## Next orchestrator

[Contribution](https://llorracc.github.io/workspace-course-topics/orchestrators/06-contribution.html)
