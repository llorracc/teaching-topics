# Orchestrator: MyST Conversion

**Phase:** Skills  
**Time:** ~30 minutes

## Purpose

Convert your notebook to MyST format and configure bibliography integration.

**Note:** This orchestrator may be postponed to a later class.

---

## Prerequisites

- Notebook edited (from [Notebook Editing](04-notebook-editing.md))
- `.bib` files from PaperPile and LitMaps
- Bibliography Capture completed

---

## External resources

- **MyST & bibliography workflow:** [The Submission (as.180.369)](https://github.com/llorracc/as.180.369/blob/main/materials/submission/README.md)

---

## Workflow sequence

### 1. [Ask Cursor about a MyST extension](../workflows/ask-cursor-about-myst-extension.md)

Ask Cursor whether there is an extension for MyST Markdown and how to install it.

---

### 2. [Install MyST-Markdown extension](../workflows/install-myst-extension.md)

Install the MyST-Markdown VS Code extension for syntax highlighting and autocomplete.

---

### 3. [Install MyST (CLI)](../workflows/install-myst-cli.md)

Ask Cursor how to install MyST; follow the instructions.

**Deliverable:** `myst --version` works

---

### 4. [Convert notebook to MyST](../workflows/convert-notebook-to-myst.md)

Ask Cursor how to convert the notebook to a MyST document.

**Deliverable:** `.md` file created from notebook

---

### 5. [Set up bibliography files for MyST](../workflows/bibliography-setup-myst.md)

Copy PaperPile bib; create a bib for the paper itself; configure MyST to use both.

---

### 6. [Add a citation to the paper](../workflows/add-citation-to-paper.md)

Add a proper citation to the paper in your notebook/MyST document.

---

### 7. [Add LitMap image and subsequent-literature bib](../workflows/add-litmap-image-and-bib.md)

Download the LitMap image; add it to the MyST document; add the subsequent-literature bib.

---

### 8. [Add "Subsequent Literature" section (AI-assisted)](../workflows/ai-subsequent-literature-section.md)

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

[Contribution](06-contribution.md)
