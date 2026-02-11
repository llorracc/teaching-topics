# Workflows index

Atomic, reusable in-class workflow steps. Each workflow is a standalone document that can be referenced by orchestrators.

---

## ⚠️ Before you start any workflow

1. **Check your working directory** — Most workflows require you to be in your ballpark fork (e.g. `~/GitHub/<your-username>/ballpark`)
2. **Complete verification steps** — Each workflow has a "Verify first" section at the top
3. **Windows users:** Ensure you're in WSL/Ubuntu, not Windows

**Quick check:**
```bash
cd ~/GitHub/<your-username>/ballpark && pwd
```

---

## Reference documents

These are not workflows, but reference material for common issues:

- [Verify terminal context](https://llorracc.github.io/workspace-course-topics/workflows/verify-terminal-context.html) — Ensures correct filesystem and directory
- [Pre-class verification checklist](https://llorracc.github.io/workspace-course-topics/workflows/verify-pre-class.html) — **Complete before each class**
- [Paths with spaces](https://llorracc.github.io/workspace-course-topics/workflows/paths-with-spaces.html) — How to handle paths containing spaces or special characters
- [WSL Google Drive access](https://llorracc.github.io/workspace-course-topics/workflows/wsl-google-drive-access.html) — Windows: accessing Google Drive files from WSL

---

## Git

- [Git fetch/pull on ballpark](git-fetch-pull-ballpark.md) — Working dir: `ballpark/`
- [Git add, commit, and PR](git-commit-and-pr.md) — Working dir: `ballpark/`

## PaperPile & LitMaps

- [PaperPile setup and sharing](paperpile-setup-and-sharing.md) — Browser-based
- [Google Drive sync for PaperPile](google-drive-paperpile-sync.md) — Browser + filesystem ⚠️ Includes BibTeX Export
- [LitMaps import and visualize](litmaps-import-and-visualize.md) — Browser-based

## Cursor & environment

- [Launch Cursor in ballpark](launch-cursor-in-ballpark.md) — Working dir: `ballpark/` ⚠️ Critical
- [Install the environment (via Cursor)](cursor-environment-install.md) — Working dir: `ballpark/`

## Jupyter notebooks

- [Open Jupyter notebook in Cursor](jupyter-notebook-in-cursor.md) — Cursor root: `ballpark/` ⚠️ Critical
- [Add yourself as coauthor](add-coauthor-to-notebook.md)

## MyST

- [Ask Cursor about a MyST extension](ask-cursor-about-myst-extension.md)
- [Install MyST-Markdown extension](install-myst-extension.md)
- [Install MyST (CLI)](install-myst-cli.md)
- [Verify MyST tools](https://llorracc.github.io/workspace-course-topics/workflows/verify-myst-tools.html)
- ~~Convert notebook to MyST~~ — replaced by the [four-notebook MyST assembly](https://llorracc.github.io/workspace-course-topics/orchestrators/05-myst-conversion.html)

## Bibliography

- [Set up bibliography files for MyST](bibliography-setup-myst.md) — Working dir: `ballpark/`
- [Add a citation to the paper](add-citation-to-paper.md)
- [Add LitMap image and subsequent-literature bib](add-litmap-image-and-bib.md)

## AI-assisted

- [Add "Subsequent Literature" section (AI-assisted)](ai-subsequent-literature-section.md)
