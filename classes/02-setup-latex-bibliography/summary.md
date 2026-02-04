# Class 02: Setup, LaTeX, bibliography — Summary

**Unit:** [Environment Setup](../../units/environment-setup/)  
**Date:** 2026-01-27 (Tue), 3:15–5:00pm ET

---

## Key links

- **Class notes (Google Doc):** https://docs.google.com/document/d/1sQP7PcduDzQjWA7kfin3RFRuZPpXQvj5NTJUe243Wvk/view
- **Econ-ARK ballpark:** https://github.com/econ-ark/ballpark
- **Econ-ARK HARK toolkit:** https://github.com/econ-ark/HARK

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
- If Cursor/WSL integration is flaky, install/launch Cursor from within WSL and ensure the WSL extension is installed in the right context.

### Cursor + Mac
- Confirm Cursor license / "education pro" status if features are missing.

### LaTeX
- Install a full LaTeX distribution:
  - **Mac:** MacTeX (2025 suggested in class)
  - **Windows (WSL):** `texlive` + `texlive-latex-extra`
- Install LaTeX Workshop in Cursor/VS Code to preview PDFs conveniently.

---

## Conceptual notes

- **Modular LaTeX:** A "main" file often just includes other `.tex` components; fragments (`.ltx`) won't compile standalone.
- **Bibliographies:** BibTeX is the common end-state; the workflow is (capture → export → compile).

---

## Student paper round (themes)

Common themes across student-selected papers:
- Heterogeneous agent models
- Monetary policy → housing markets (wealth effects, liquidity constraints, intertemporal substitution)
- Wealth inequality, tax progressivity, social mobility

---

## Open issues / common blockers

- Cursor licensing prompts (may ask for payment info even during free/edu trials).
- WSL confusion: editing files through Windows paths can cause permissions + toolchain weirdness.
- LaTeX missing packages: install a fuller distro rather than chasing individual packages one-by-one.
