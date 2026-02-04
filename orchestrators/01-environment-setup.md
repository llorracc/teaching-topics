# Orchestrator: Environment Setup

**Phase:** Tools  
**Time:** ~15 minutes

## Purpose

Get everyone's local environment ready before starting substantive work.

---

## Prerequisites

- Git installed and configured
- Cursor installed
- ballpark repo cloned to `~/GitHub/econ-ark/ballpark`

---

## Workflow sequence

### 1. [Git fetch/pull on ballpark](../workflows/git-fetch-pull-ballpark.md)

Make sure everyone has the latest code before we begin.

**Deliverable:** `git status` shows "Your branch is up to date"

---

### 2. [Launch Cursor in ballpark](../workflows/launch-cursor-in-ballpark.md)

Open Cursor with the ballpark repo as your workspace.

**Deliverable:** Cursor opens with `ballpark` as the root folder

---

### 3. [Install the environment (via Cursor)](../workflows/cursor-environment-install.md)

Ask Cursor how to install the environment; execute the steps.

**Deliverable:** `.venv/VENV-*` directory exists and activates successfully

---

### 4. [Open Jupyter notebook in Cursor](../workflows/jupyter-notebook-in-cursor.md)

Navigate to your ballpark directory and open your notebook in Cursor.

**Deliverable:** Notebook opens and kernel is selected from "Python Environments"

---

## Checkpoint

Before proceeding, verify:
- [ ] ballpark repo is up to date
- [ ] Cursor is open at the ballpark root
- [ ] Environment is installed and activated
- [ ] Your notebook opens and runs cells

---

## Next orchestrator

[Bibliography Capture](02-bibliography-capture.md)
