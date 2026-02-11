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

### 1. [Git fetch/pull on ballpark](https://llorracc.github.io/workspace-course-topics/workflows/git-fetch-pull-ballpark.html)
Make sure everyone has the latest code before we begin.

### 2. [PaperPile setup and sharing](https://llorracc.github.io/workspace-course-topics/workflows/paperpile-setup-and-sharing.html)
Connect to JHU libraries; create and share folders; verify shared content.

### 3. [Google Drive sync for PaperPile](https://llorracc.github.io/workspace-course-topics/workflows/google-drive-paperpile-sync.html)
Get PaperPile files available locally via Google Drive.

### 4. [LitMaps import and visualize](https://llorracc.github.io/workspace-course-topics/workflows/litmaps-import-and-visualize.html)
Import bib from PaperPile; create a map showing papers that cite your paper.

### 5. [Launch Cursor in ballpark](https://llorracc.github.io/workspace-course-topics/workflows/launch-cursor-in-ballpark.html)
Open Cursor with the ballpark repo as your workspace.

### 6. [Install the environment](https://llorracc.github.io/workspace-course-topics/workflows/cursor-environment-install.html)
Run `bash scripts/setup_env.sh` to install all tools and dependencies.

### 7. [Open Jupyter notebook in Cursor](https://llorracc.github.io/workspace-course-topics/workflows/jupyter-notebook-in-cursor.html)
Navigate to your ballpark directory and open your notebook in Cursor.

### 8. [Add yourself as coauthor](https://llorracc.github.io/workspace-course-topics/workflows/add-coauthor-to-notebook.html)
Add your name to the notebook; save and close.

### 9. [Verify MyST tools](https://llorracc.github.io/workspace-course-topics/workflows/verify-myst-tools.html)
Confirm that `myst`, `jupytext`, and the MyST-Markdown Cursor extension are installed (they should be from step 6). See [troubleshooting](https://llorracc.github.io/workspace-course-topics/workflows/install-myst-extension.html) if anything is missing.

### 10. [Convert notebook to MyST](https://llorracc.github.io/workspace-course-topics/workflows/convert-notebook-to-myst.html)
Use jupytext to convert the notebook to a MyST Markdown document.

### 11. [Set up bibliography files for MyST](https://llorracc.github.io/workspace-course-topics/workflows/bibliography-setup-myst.html)
Copy PaperPile bib; create a bib for the paper itself; configure MyST to use both.

### 12. [Add a citation to the paper](https://llorracc.github.io/workspace-course-topics/workflows/add-citation-to-paper.html)
Add a proper citation to the paper in your notebook/MyST document.

### 13. [Add LitMap image and subsequent-literature bib](https://llorracc.github.io/workspace-course-topics/workflows/add-litmap-image-and-bib.html)
Download the LitMap image; add it to the MyST document; add the subsequent-literature bib.

### 14. [Add "Subsequent Literature" section (AI-assisted)](https://llorracc.github.io/workspace-course-topics/workflows/ai-subsequent-literature-section.html)
Use AI to generate a summary of citing papers.

### 15. [Git add, commit, and PR](https://llorracc.github.io/workspace-course-topics/workflows/git-commit-and-pr.html)
Stage changes, commit, and create a pull request for your modifications.

---

## Assignment after this session

See [AI revision with prompt tracking](https://llorracc.github.io/workspace-course-topics/assignments/ai-revision-with-prompt-tracking.html)
