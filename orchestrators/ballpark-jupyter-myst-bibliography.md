# Orchestrator: Ballpark editing, Jupyter, MyST, and bibliography

**Unit:** ballpark-jupyter-myst-bibliography

## Overview

This session takes students from an updated ballpark fork through PaperPile/LitMaps setup, Jupyter editing, MyST conversion, bibliography configuration, and a PR.

**Note:** MyST tools (CLI, jupytext, Cursor extension) are installed automatically by `scripts/setup_env.sh` during environment setup. This orchestrator assumes they are already available.

---

## External resources (as.180.369)

- **PaperPile & LitMaps intro:** [The Setup](https://github.com/llorracc/as.180.369/blob/main/materials/setup/README.md)
- **PaperPile sharing, LitMaps deeper dive:** [The Pitch](https://github.com/llorracc/as.180.369/blob/main/materials/pitch/README.md)
- **MyST & bibliography workflow:** [The Submission](https://github.com/llorracc/as.180.369/blob/main/materials/submission/README.md)

---

## Workflow sequence

### 1. [Git fetch/pull on ballpark](../workflows/git-fetch-pull-ballpark.md)
Make sure everyone has the latest code before we begin.

### 2. [PaperPile setup and sharing](../workflows/paperpile-setup-and-sharing.md)
Connect to JHU libraries; create and share folders; verify shared content.

### 3. [Google Drive sync for PaperPile](../workflows/google-drive-paperpile-sync.md)
Get PaperPile files available locally via Google Drive.

### 4. [LitMaps import and visualize](../workflows/litmaps-import-and-visualize.md)
Import bib from PaperPile; create a map showing papers that cite your paper.

### 5. [Launch Cursor in ballpark](../workflows/launch-cursor-in-ballpark.md)
Open Cursor with the ballpark repo as your workspace.

### 6. [Install the environment](../workflows/cursor-environment-install.md)
Run `bash scripts/setup_env.sh` to install all tools and dependencies.

### 7. [Open Jupyter notebook in Cursor](../workflows/jupyter-notebook-in-cursor.md)
Navigate to your ballpark directory and open your notebook in Cursor.

### 8. [Add yourself as coauthor](../workflows/add-coauthor-to-notebook.md)
Add your name to the notebook; save and close.

### 9. [Verify MyST tools](../workflows/verify-myst-tools.md)
Confirm that `myst`, `jupytext`, and the MyST-Markdown Cursor extension are installed (they should be from step 6). See [troubleshooting](../workflows/install-myst-extension.md) if anything is missing.

### 10. [Convert notebook to MyST](../workflows/convert-notebook-to-myst.md)
Use jupytext to convert the notebook to a MyST Markdown document.

### 11. [Set up bibliography files for MyST](../workflows/bibliography-setup-myst.md)
Copy PaperPile bib; create a bib for the paper itself; configure MyST to use both.

### 12. [Add a citation to the paper](../workflows/add-citation-to-paper.md)
Add a proper citation to the paper in your notebook/MyST document.

### 13. [Add LitMap image and subsequent-literature bib](../workflows/add-litmap-image-and-bib.md)
Download the LitMap image; add it to the MyST document; add the subsequent-literature bib.

### 14. [Add "Subsequent Literature" section (AI-assisted)](../workflows/ai-subsequent-literature-section.md)
Use AI to generate a summary of citing papers.

### 15. [Git add, commit, and PR](../workflows/git-commit-and-pr.md)
Stage changes, commit, and create a pull request for your modifications.

---

## Assignment after this session

See [AI revision with prompt tracking](../assignments/ai-revision-with-prompt-tracking.md)
