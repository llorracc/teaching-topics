# Unit: Environment Setup

## Overview

This unit covers getting the development environment working: Git, WSL, Homebrew, Cursor, the ballpark repo (fork and clone), and the full toolchain installed by `scripts/setup_env.sh`.

By the end of this unit, you should have:
- A working Git + WSL (Windows) or Git + terminal (Mac) setup
- Homebrew installed (macOS) with node/npm
- Cursor configured as your IDE with the MyST-Markdown extension
- The ballpark repo **forked** to your GitHub account and cloned locally
- The environment set up via `bash scripts/setup_env.sh`, which provides:
  - Python virtual environment with all dependencies (econ-ark, jupyter, jupytext, myst-parser)
  - MyST CLI (`myst --version` works)
  - Jupytext (`jupytext --version` works)
  - MyST-Markdown Cursor extension installed
- Selected a ballpark paper of interest

---

## Phase: Tools

This unit represents the **Tools** phase of the course:
- **Phase 1 (Tools):** Environment Setup ← _You are here_
- **Phase 2 (Skills):** Research Skills
- **Phase 3 (Artifacts):** Contribution

---

## Classes in this unit

| Class | Topic | Status |
|-------|-------|--------|
| [01](../../classes/01-git-wsl-ballpark-intro/) | Git, WSL, ballpark intro | Completed |
| [02](../../classes/02-setup-latex-bibliography/) | Setup, LaTeX, bibliography | Completed |

---

## Assignments in this unit

| # | Assignment | Deliverable |
|---|------------|-------------|
| 010 | [Ballpark Paper Selection](https://llorracc.github.io/workspace-course-topics/assignments/ballpark-paper-selection-and-presentation.html) | Paper choice + presentation |

---

## Environment setup (single command)

Once you have the ballpark repo forked and cloned, run:
```bash
cd ~/GitHub/<your-username>/ballpark
bash scripts/setup_env.sh
```

This installs Homebrew (macOS), node/npm, uv, Python 3.12, all Python dependencies, the mystmd CLI, and the MyST-Markdown Cursor extension. See [Install the environment](https://llorracc.github.io/workspace-course-topics/workflows/cursor-environment-install.html) for details.

---

## Key resources

- **Econ-ARK ballpark:** https://github.com/econ-ark/ballpark
- **Methods course Git intro:** [Start Learning Git](https://github.com/ccarrollATjhuecon/Methods/blob/main/Assignments/00_Start-Learning-Git/Start-Learning-Git.md)
