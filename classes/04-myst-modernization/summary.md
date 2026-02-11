# Class 04: MyST Modernization and PR Review — Summary

**Unit:** [Research Skills](../../units/research-skills/) / [Contribution](../../units/contribution/)  
**Date:** 2026-02-10 (Tue)  
**Sessions:** Part 1 (12:00–1:00pm) + Part 2 (3:15–5:00pm)

---

## Overview

This class focused on the fork-based PR workflow and MyST modernization of ballpark notebooks. In Part 1, we reviewed students' fork status, corrected a common mistake (cloning vs. forking), and sent assignment reminders. In Part 2, we walked through the MyST toolchain: installing the MyST-Markdown extension in Cursor, verifying the MyST CLI and parser, installing jupytext, and converting a Jupyter notebook to MyST Markdown format.

---

## Progress against plan

The [Class 04 plan](plan.md) has three parts. We completed Part 2 (MyST conversion demo) and set up the groundwork for Parts 1 and 3:

| Part | Activity | Status | Notes |
|------|----------|--------|-------|
| 1 | PR Review | Partial | Checked student fork status; PRs to be reviewed asynchronously |
| 2 | MyST Modernization | ✓ Done | Full demo: extension install, jupytext, notebook conversion |
| 3 | Update PRs | Pending | Students to push MyST-converted work to their forks |

---

## Part 1: Fork Workflow and Assignments (12:00–1:00pm)

### Assignment reminder

Sent a reminder email to all 11 students about Class 04 assignments:
- Assignment 030: Prior Literature (~20–30 min)
- Assignment 040: Subsequent Literature (~45–60 min)
- Assignment 050: Integration + PR (~60–90 min)

**Main deliverable:** Pull Request URL, to bring to class.

### Fork vs. clone clarification

A key issue surfaced: the instructor (and likely some students) had **cloned** the econ-ark/ballpark repo directly instead of **forking** it first. This matters because:
- A **clone** of econ-ark/ballpark only lets you pull; you can't push or open PRs to it (no write access).
- A **fork** creates your own copy on GitHub (e.g. `llorracc/ballpark`), which you can push to and then open PRs from.

**Resolution:** Checked GitHub for existing forks. No fork found for the instructor (`llorracc`). The fix:
1. Fork on GitHub (click Fork at https://github.com/econ-ark/ballpark)
2. Point the existing local clone at the fork:
   ```bash
   git remote rename origin upstream
   git remote add origin https://github.com/YOUR-USERNAME/ballpark.git
   git push -u origin master
   ```

### Student fork status

Checked the econ-ark/ballpark fork list on GitHub. Students who have already forked:

| GitHub User | Student | Fork Created |
|-------------|---------|-------------|
| Calbafa | Carlos Alba | Feb 10 |
| nathanrobino | Nathan Robino | Feb 10 |
| rzheng2112 | Rudan Zheng | Feb 10 |
| jliu226 | Jianhong Liu | Feb 9 |
| jzhan476 | Jiaxuan Zhang | Feb 9 |
| iremdesdemir | Irem Desdemir | Feb 9 |

Students not yet confirmed as having forked: Tianshi Wang, Yuchen Wang, Emma Ma, Siying Li, Benjamin Stagoff-Belfort.

---

## Part 2: MyST Modernization (3:15–5:00pm)

### Step 1: Install MyST-Markdown extension in Cursor

The [MyST-Markdown extension](https://marketplace.visualstudio.com/items?itemName=ExecutableBookProject.myst-highlight) provides syntax highlighting, directive/role autocomplete, and enhanced preview for MyST files.

**Issue encountered:** Cursor uses the Open VSX marketplace, not the VS Code Marketplace. The extension isn't available by ID in Cursor:
```
cursor --install-extension ExecutableBookProject.myst-highlight
# → Extension 'executablebookproject.myst-highlight' not found.
```

**Workaround — manual `.vsix` install:**
```bash
# Download the .vsix file
curl -L "https://ExecutableBookProject.gallery.vsassets.io/_apis/public/gallery/publisher/ExecutableBookProject/extension/myst-highlight/latest/assetbyname/Microsoft.VisualStudio.Services.VSIXPackage" -o ~/Downloads/myst-highlight.vsix

# Install in Cursor
cursor --install-extension ~/Downloads/myst-highlight.vsix
```

Or: Cmd+Shift+P → "Extensions: Install from VSIX..." → select the downloaded file.

### Step 2: Verify MyST CLI and parser

Both were already installed:
- **`myst` CLI** (mystmd): v1.6.0 at `/usr/local/bin/myst` — installed via npm
- **`myst-parser`** (Python): v4.0.1 — the Sphinx extension for parsing MyST

For fresh installs:
```bash
npm install -g mystmd        # CLI
pip install myst-parser      # Python parser
```

### Step 3: Install jupytext

Jupytext converts between `.ipynb` and MyST Markdown (`.md`) formats:
```bash
pip install jupytext         # Installed v1.19.1
```

### Step 4: Convert notebook to MyST Markdown

Demonstrated conversion on `HKMOHousingChannelMP`:
```bash
cd ~/GitHub/llorracc/ballpark/models/We-Would-Like-In-Econ-ARK/HKMOHousingChannelMP
jupytext --to myst HKMOHousingChannelMP.ipynb
```

This created `HKMOHousingChannelMP.md` (8.6 KB) with:
- MyST/jupytext YAML front matter
- Code cells as ` ```{code-cell} ` directives
- Markdown cells preserved as-is
- Round-trippable back to `.ipynb` via `jupytext --to ipynb`

### Steps 5–6: Bibliography and citations (not yet covered)

Configuring `myst.yml` for `.bib` files and adding `{cite}` references will be covered in the next session or done by students as part of their assignments.

---

## Key issues encountered

### Cursor marketplace limitation
- Cursor uses Open VSX, not the Microsoft VS Code Marketplace
- Some VS Code extensions (including MyST-Markdown) must be manually installed via `.vsix` download
- This is a known Cursor limitation documented at https://www.cursor.com/en/how-to-install-extension

### Fork vs. clone confusion
- Multiple students (and the instructor) initially cloned econ-ark/ballpark directly
- Without a fork, students cannot push branches or open PRs
- Fix: fork on GitHub first, then update the local remote

### Teaching-topics repo sync
- The teaching-topics repo needed a force-merge to sync local with remote:
  ```bash
  git fetch origin && git reset --hard origin/main
  ```

---

## Key takeaways

1. **Fork first, then clone:** Always fork a repo you plan to contribute to, then clone your fork
2. **MyST-Markdown extension** needs manual `.vsix` install in Cursor (not available via marketplace search)
3. **jupytext** is the bridge between `.ipynb` and MyST `.md` — install it and use `jupytext --to myst`
4. **MyST CLI and parser** are separate tools: `mystmd` (npm) builds documents, `myst-parser` (pip) integrates with Sphinx
5. **Converted `.md` files** are round-trippable back to `.ipynb` and can be version-controlled more cleanly than notebooks

---

## Remaining for next class

- Students complete Assignments 030, 040, and 050
- Students who haven't forked ballpark need to do so
- Configure `myst.yml` for bibliography support
- Add `{cite}` references in MyST syntax
- Push MyST-converted notebooks to forks and open PRs

---

## Assignment

Complete before next class:
1. **Assignment 030:** Prior Literature (`prior-literature.md`)
2. **Assignment 040:** Subsequent Literature (`subsequent-literature.bib` + analysis)
3. **Assignment 050:** Integration + PR (**PR URL** — main deliverable)

See: [Assignments for Class 04](../../assignments/index.md)

---

## Resources

- **Econ-ARK ballpark:** https://github.com/econ-ark/ballpark
- **Teaching topics:** https://github.com/llorracc/teaching-topics
- **MyST documentation:** https://mystmd.org
- **Jupytext documentation:** https://jupytext.readthedocs.io
- **MyST-Markdown extension:** https://marketplace.visualstudio.com/items?itemName=ExecutableBookProject.myst-highlight
- **Cursor extension install guide:** https://www.cursor.com/en/how-to-install-extension
