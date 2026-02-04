# Class 01: Git, WSL, ballpark intro — Summary

**Unit:** [Environment Setup](../../units/environment-setup/)  
**Date:** 2026-01-20 (Tue), 4:00–5:00pm ET

---

## Key links

- **Class notes (Google Doc):** https://docs.google.com/document/d/1Wy89QNwfUXMrn_e3EaxCGZVEtcM_bjJkKRSnuuScsHI/view
- **Econ-ARK ballpark:** https://github.com/econ-ark/ballpark

---

## What we did

- **Git & repo setup:** Create a working directory (e.g. "Lorac"), clone the course repo, use the correct GitHub URL. Ask when commands are unclear.
- **WSL orientation:** Git and tooling live in WSL; use the WSL file system, not the Windows one. `pwd` / `cd` to navigate. Install Git (and related tools) inside the WSL environment.
- **Econ-ARK / `reproduce.sh`:** Repos use a root-level `reproduce.sh` to build docs and run computations. Full runs can take 4–6 days; use the provided "min" targets for quick sanity checks.
- **UV environment:** Run `./reproduce.sh --env` and choose option 1 to install UV for a consistent environment across platforms.
- **Permissions & scripts:** `sudo chmod` for config dirs when needed; `~` for home, dotfiles for config. Exit code 0 = success, 1 = error. Use `./scriptname` to run scripts.
- **LaTeX & reproduce:** Install LaTeX (Windows/WSL: `texlive` + `texlive-latex-extra`; Mac: MacTeX). `reproduce.sh` compiles LaTeX and runs minimal computations.
- **Cursor:** Brief demo; Cursor is the course IDE. Department funding / licensing was mentioned.
- **Housekeeping:** 1Password over browser password managers; keep GitHub repos organized.

---

## Setup notes

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

## Conceptual notes

- **reproduce.sh:** Single entry point for building documents and reproducing results; use `--env` for environment setup, `docs` / `comp` for builds and runs.
- **WSL vs Windows:** Separate file systems; stick to WSL for course work.

---

## Open issues / common blockers

- Git "not found" or wrong context: install and run Git inside WSL, not Windows.
- Repo access: use the correct GitHub URL (instructor provided).
- Permissions: `sudo chmod` when the script can't write to config or output dirs.
