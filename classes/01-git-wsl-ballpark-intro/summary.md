# Class 01: Git, WSL, ballpark intro — Summary

**Unit:** [Environment Setup](../../units/environment-setup/unit.md)  
**Date:** 2026-01-20

---

## What we did

- **Git & repo setup:** Create a working directory, clone the course repo, use the correct GitHub URL.
- **WSL orientation:** Git and tooling live in WSL; use the WSL file system, not the Windows one. `pwd` / `cd` to navigate.
- **Econ-ARK / `reproduce.sh`:** Repos use a root-level `reproduce.sh` to build docs and run computations. Full runs can take 4–6 days; use the provided "min" targets for quick sanity checks.
- **UV environment:** Run `./reproduce.sh --env` and choose option 1 to install UV for a consistent environment across platforms.
- **LaTeX & reproduce:** Install LaTeX (Windows/WSL: `texlive` + `texlive-latex-extra`; Mac: MacTeX).
- **Cursor:** Brief demo; Cursor is the course IDE.

---

## Setup checklist

### Git & WSL (Windows)
- Install and use Git **inside WSL**. Don't mix Windows and WSL paths.
- Work in the WSL file system; use `pwd` and `cd` to confirm you're in the right place.

### LaTeX
- **Mac:** MacTeX (2025)
- **Windows (WSL):** `sudo apt-get update && sudo apt install texlive texlive-latex-extra`

### Repo / reproduce.sh
- Clone the course repo into a dedicated directory.
- Run `./reproduce.sh --env` and install UV (option 1). Then:
  - `./reproduce.sh docs main` — build the docs
  - `./reproduce.sh comp min` — run minimal computations

---

## Assignment

**Due before Class 02:** [Ballpark paper selection](../../assignments/010-ballpark-paper-selection/assignment.md)

---

## Resources

- **Econ-ARK ballpark:** https://github.com/econ-ark/ballpark
