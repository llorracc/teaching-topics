# Workflow: Git add, commit, and PR

**Purpose:** Stage your changes, commit them, and create a pull request.

---

## ⚠️ Working directory

**You must be in:** `~/GitHub/econ-ark/ballpark` (the repo root)

Run this now:
```bash
cd ~/GitHub/econ-ark/ballpark && pwd
```

**Expected output:** Path ending in `/ballpark`

**Do not proceed until you see this output.**

Git commands must be run from the repository root, not from a subdirectory.

---

## Verify first

### 1. Verify you're in a git repository

Run:
```bash
git status
```

**Expected:** Shows modified/staged files, branch name, etc.

**If "fatal: not a git repository":** You're in the wrong directory.

---

### 2. Verify you have changes to commit

```bash
git status
```

**Expected:** Shows files under "Changes not staged" or "Changes to be committed"

**If "nothing to commit, working tree clean":** You haven't made any changes yet, or you already committed them.

---

### 3. Verify you're on your own branch (not master)

```bash
git branch --show-current
```

**Expected:** Your branch name (e.g., `add-coauthor-yourname`)

**If you're on `master`:** Create a new branch first:
```bash
git checkout -b your-feature-branch
```

---

## Steps

### A. Review your changes

```bash
git diff
```

This shows what you've changed. Press `q` to exit.

---

### B. Stage your changes

```bash
git add .
```

Or stage specific files:
```bash
git add models/We_Would_Like_In_Econ-ARK/YourPaper/
```

---

### C. Commit

```bash
git commit -m "Add [your description of changes]"
```

---

### D. Push to your fork

```bash
git push origin your-branch-name
```

**If this is your first push for this branch:**
```bash
git push -u origin your-branch-name
```

---

### E. Create a pull request

1. Go to https://github.com/econ-ark/ballpark
2. You should see a banner: "Compare & pull request"
3. Click it and fill in the PR description
4. Click "Create pull request"

Or use the GitHub CLI:
```bash
gh pr create --title "Your PR title" --body "Description of changes"
```

---

## Alternative: Ask Cursor

You can also ask Cursor to help:
> "Git add and commit my changes, then create a pull request."

Cursor will guide you through the process.
