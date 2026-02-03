# Class 02: Setup, LaTeX, bibliography — Summary

**Unit:** [Environment Setup](../../units/environment-setup/unit.md)  
**Date:** 2026-01-27

---

## What we did

- **Got everyone moving toward a reproducible computational setup** (Cursor + WSL where relevant; avoid Windows-path issues; confirm license status).
- **Walked the repo + LaTeX build structure:** Modular documents, subfiles, why multiple compilation passes matter, and how to get a clean PDF build loop.
- **Introduced bibliography workflow for this course:** BibTeX as the output target; PaperPile as the capture tool.
- **Student paper round:** Quick intros of selected "ballpark" papers to map interests + potential replication targets.

---

## Setup notes

### Cursor + Windows (WSL)
- Work **inside WSL** (Unix paths). If you see Windows-style paths (backslashes), you're not in the right place.
- If Cursor/WSL integration is flaky, install/launch Cursor from within WSL.

### Cursor + Mac
- Confirm Cursor license / "education pro" status if features are missing.

### LaTeX
- Install a full LaTeX distribution.
- Install LaTeX Workshop in Cursor/VS Code to preview PDFs conveniently.

---

## Conceptual notes

- **Modular LaTeX:** A "main" file often just includes other `.tex` components; fragments (`.ltx`) won't compile standalone.
- **Bibliographies:** BibTeX is the common end-state; the workflow is (capture → export → compile).

---

## Assignment

**Due before Class 03:** [PaperPile bibliography](../../assignments/020-paperpile-bibliography/assignment.md)

---

## Resources

- **Econ-ARK ballpark:** https://github.com/econ-ark/ballpark
- **Econ-ARK HARK:** https://github.com/econ-ark/HARK
