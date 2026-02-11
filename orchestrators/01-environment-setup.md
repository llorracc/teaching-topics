# Orchestrator: Environment Setup

**Phase:** Tools  
**Time:** ~15 minutes

## Purpose

Get everyone's local environment ready before starting substantive work. The ballpark repo includes a comprehensive setup script (`scripts/setup_env.sh`) that installs all required tools automatically.

---

## Prerequisites

- Git installed and configured
- Cursor installed
- ballpark repo **forked** to your GitHub account, then cloned to `~/GitHub/<your-username>/ballpark`

**Important:** You need a **fork**, not just a clone of econ-ark/ballpark. Fork first at https://github.com/econ-ark/ballpark, then clone your fork.

---

## Workflow sequence

### 1. [Git fetch/pull on ballpark](https://llorracc.github.io/workspace-course-topics/workflows/git-fetch-pull-ballpark.html)

Make sure everyone has the latest code before we begin.

**Deliverable:** `git status` shows "Your branch is up to date"

---

### 2. Run the setup script

From the ballpark repo root, run:
```bash
cd ~/GitHub/<your-username>/ballpark
bash scripts/setup_env.sh
```

This single command:
- Installs Homebrew (macOS, if missing)
- Installs node/npm (if missing)
- Installs uv (if missing)
- Creates a platform-specific Python virtual environment
- Installs all Python dependencies (including jupytext and myst-parser)
- Installs the mystmd CLI globally
- Installs the MyST-Markdown extension in Cursor (if Cursor CLI is on PATH)

**Deliverable:** Script prints a summary with version numbers for all tools.

---

### 3. [Launch Cursor in ballpark](https://llorracc.github.io/workspace-course-topics/workflows/launch-cursor-in-ballpark.html)

Open Cursor with the ballpark repo as your workspace.

**Deliverable:** Cursor opens with `ballpark` as the root folder

---

### 4. Activate the environment and open a notebook

Activate the environment created by the setup script:
```bash
source .venv-$(uname -s | tr '[:upper:]' '[:lower:]')-$(uname -m)/bin/activate
```

Then open your notebook in Cursor. See [Open Jupyter notebook in Cursor](https://llorracc.github.io/workspace-course-topics/workflows/jupyter-notebook-in-cursor.html) for details.

**Deliverable:** Notebook opens and kernel is selected from "Python Environments"

---

## Checkpoint

Before proceeding, verify:
- [ ] ballpark repo is up to date
- [ ] `setup_env.sh` completed successfully (all tools show version numbers)
- [ ] Cursor is open at the ballpark root
- [ ] Environment is activated
- [ ] Your notebook opens and runs cells
- [ ] `myst --version` and `jupytext --version` both work

---

## Next orchestrator

[Bibliography Capture](https://llorracc.github.io/workspace-course-topics/orchestrators/02-bibliography-capture.html)
