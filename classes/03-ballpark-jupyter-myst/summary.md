# Class 03: Ballpark, Jupyter, MyST — Summary

**Unit:** [Research Skills](https://llorracc.github.io/workspace-course-topics/units/research-skills/unit.html)  
**Date:** 2026-02-03 (Tue)  
**Sessions:** Part 1 (12:00–1:00pm) + Part 2 (3:15–5:00pm)

---

## Overview

This class focused on setting up computational environments for economic research: updating ballpark, configuring PaperPile with JHU libraries, syncing to Google Drive, activating virtual environments, opening Jupyter notebooks in Cursor, and creating literature maps with Litmaps.

---

## Progress against plan

The [planned orchestrator](https://llorracc.github.io/workspace-course-topics/orchestrators/ballpark-jupyter-myst-bibliography.html) has 17 steps. We completed steps 1–7 and partially step 13:

| # | Workflow | Status | Notes |
|---|----------|--------|-------|
| 1 | [Git fetch/pull on ballpark](https://llorracc.github.io/workspace-course-topics/workflows/git-fetch-pull-ballpark.html) | ✓ Done | PR #39 (modernize-uv-env) was merged; everyone pulled updates |
| 2 | [PaperPile setup and sharing](https://llorracc.github.io/workspace-course-topics/workflows/paperpile-setup-and-sharing.html) | ✓ Done | Connected to JHU libraries via proxy, ran Auto Update |
| 3 | [Google Drive sync for PaperPile](https://llorracc.github.io/workspace-course-topics/workflows/google-drive-paperpile-sync.html) | ✓ Done | Installed Google Drive, configured PaperPile sync |
| 4 | [LitMaps import and visualize](https://llorracc.github.io/workspace-course-topics/workflows/litmaps-import-and-visualize.html) | ✓ Done | Imported .bib, explored citation maps (hit free tier limits) |
| 5 | [Launch Cursor in ballpark](https://llorracc.github.io/workspace-course-topics/workflows/launch-cursor-in-ballpark.html) | ✓ Done | Used `cursor .` from terminal |
| 6 | [Install the environment](https://llorracc.github.io/workspace-course-topics/workflows/cursor-environment-install.html) | ✓ Done | Activated `.venv` with `source` command |
| 7 | [Open Jupyter notebook in Cursor](https://llorracc.github.io/workspace-course-topics/workflows/jupyter-notebook-in-cursor.html) | ✓ Done | Selected Python environment kernel, ran cells |
| 8 | [Add yourself as coauthor](https://llorracc.github.io/workspace-course-topics/workflows/add-coauthor-to-notebook.html) | Pending | |
| 9 | [Ask Cursor about MyST extension](https://llorracc.github.io/workspace-course-topics/workflows/ask-cursor-about-myst-extension.html) | Pending | |
| 10 | [Install MyST-Markdown extension](https://llorracc.github.io/workspace-course-topics/workflows/install-myst-extension.html) | Pending | |
| 11 | [Install MyST (CLI)](https://llorracc.github.io/workspace-course-topics/workflows/install-myst-cli.html) | Pending | |
| 12 | [Convert notebook to MyST](https://llorracc.github.io/workspace-course-topics/workflows/convert-notebook-to-myst.html) | Pending | |
| 13 | [Set up bibliography files](https://llorracc.github.io/workspace-course-topics/workflows/bibliography-setup-myst.html) | Partial | Set up PaperPile export workflow; copied .bib to ballpark |
| 14 | [Add citation to the paper](https://llorracc.github.io/workspace-course-topics/workflows/add-citation-to-paper.html) | Pending | |
| 15 | [Add LitMap image and bib](https://llorracc.github.io/workspace-course-topics/workflows/add-litmap-image-and-bib.html) | Pending | |
| 16 | [AI "Subsequent Literature" section](https://llorracc.github.io/workspace-course-topics/workflows/ai-subsequent-literature-section.html) | Pending | |
| 17 | [Git add, commit, and PR](https://llorracc.github.io/workspace-course-topics/workflows/git-commit-and-pr.html) | Pending | |

---

## Part 1: Setup and PaperPile (12:00–1:00pm)

### Teaching-topics repo introduction
- Introduced the new [teaching-topics](https://github.com/llorracc/teaching-topics) public repo
- Showed class summaries from previous sessions generated from AI Companion
- Each class now has a plan document in addition to summaries

### Git fetch/pull on ballpark
Everyone navigated to their local ballpark repo and pulled the latest changes:
```bash
cd ~/GitHub/econ-ark/ballpark
git fetch origin
git checkout master
git pull origin master
```

**Note:** For students who hadn't cloned ballpark yet:
```bash
mkdir -p ~/GitHub/econ-ark
cd ~/GitHub/econ-ark
git clone https://github.com/econ-ark/ballpark.git
cd ballpark
```

### PaperPile setup
1. **Connect to JHU libraries:**
   - Settings → Proxy Connection → Johns Hopkins University
   - Use "EZProxy" connection type
   - Test connection to verify

2. **Update bibliography metadata:**
   - Select All papers
   - More → Auto Update (retrieves journal, volume, pages, abstract)
   - More → Find PDFs Online (downloads available papers through Hopkins)

3. **Pro tip from students:** Use ChatGPT to generate BibTeX files from reference lists:
   > "Give me a BibTeX file for all references in [paper name]"
   
   Then import the .bib file into PaperPile.

### Google Drive setup
1. Download Google Drive for desktop: https://www.google.com/drive/download/
2. Add your Gmail account
3. Configure selective sync (don't sync everything—just course materials)

### PaperPile → Google Drive sync
1. In PaperPile: Settings → Data and Files → Cloud Storage
2. Select Google Drive
3. This makes bibliography files accessible on your local computer

---

## Part 2: Environments and Litmaps (3:15–5:00pm)

### Virtual environment activation

The ballpark repo includes a pre-configured environment. To activate:
```bash
ls -lash                                    # Find the .venv folder
source .venv/VENV-Darwin-arm64/bin/activate  # Mac Apple Silicon
# or
source .venv/VENV-Linux-x86_64/bin/activate  # Linux/WSL
```

The environment name depends on your OS/architecture:
- `VENV-Darwin-arm64` — Mac Apple Silicon
- `VENV-Darwin-x86_64` — Mac Intel
- `VENV-Linux-x86_64` — Linux/WSL

### Opening Jupyter notebooks in Cursor

1. Launch Cursor from the ballpark directory: `cursor .`
2. File → Open → navigate to `models/We_Would_Like_In_Econ-ARK/`
3. Open the `.ipynb` file
4. Select kernel: Python Environments → choose the `.venv` environment
5. Run All to execute the notebook

### WSL troubleshooting (Windows users)

**Critical:** Always work inside WSL, not Windows paths.

**Symptoms of wrong context:**
- Path shows `C:\Users\...` instead of `/home/username/...`
- PowerShell prompt instead of bash prompt

**Fix:**
```bash
# From PowerShell, enter WSL:
wsl

# Navigate to your GitHub folder:
cd ~/GitHub/econ-ark/ballpark

# Launch Cursor from WSL:
cursor .
```

**Cursor WSL extension:** If Cursor opens in Windows context, install the WSL extension and use "Reopen in WSL" command.

### Copying bibliography to ballpark

1. Navigate to your chosen ballpark paper:
   ```bash
   cd ~/GitHub/econ-ark/ballpark/models/We_Would_Like_In_Econ-ARK/
   cd [your-paper-folder]
   ```

2. Find your .bib file path (Mac):
   - In Finder, navigate to Google Drive → PaperPile folder
   - Ctrl-click → hold Option → "Copy as Pathname"

3. Copy the file:
   ```bash
   cp "/path/to/your/bibliography.bib" .
   ```
   
   **Note:** Use quotes if the path contains spaces.

### PaperPile export workflow

To get a continuously-synced .bib file:
1. In PaperPile: click profile icon → Workflows and Integrations
2. Add BibTeX Export
3. Source: select your paper folder
4. Destination: Google Drive
5. Click "Open in Google Drive" to verify

### Litmaps

1. Go to https://www.litmaps.com and log in
2. Import → Choose File → select your .bib file
3. Click "Explore Related Articles"
4. Add articles to your litmap (shows both cited and citing papers)

**Limitation:** Free accounts limited to ~50 articles per map

---

## Key issues encountered

### Cross-platform challenges
- **WSL path confusion:** Students accidentally working in Windows file system instead of WSL
- **Cursor context:** Need to launch Cursor from within WSL terminal, not Windows
- **Google Drive paths:** Windows users need special handling to access Google Drive from WSL

### Common mistakes
- Not activating the virtual environment before selecting kernel
- Opening Cursor from wrong directory (models/ instead of ballpark/)
- Missing the PaperPile export workflow step (needed for .bib sync)

### Student solutions
- Using ChatGPT to generate BibTeX files from reference lists
- Manual import of .bib files when auto-sync didn't work

---

## Key takeaways

1. **Virtual environments** ensure consistent software dependencies—always activate before work
2. **WSL discipline:** Windows users must stay in WSL context (Linux paths, bash shell)
3. **PaperPile workflow:** Requires explicit export setup for .bib file sync
4. **Litmaps** shows both backward (cited) and forward (citing) citations
5. **Ask AI for help:** When stuck, describe your problem to Cursor/ChatGPT

---

## Remaining for next class

Steps 8–17 of the [orchestrator](https://llorracc.github.io/workspace-course-topics/orchestrators/ballpark-jupyter-myst-bibliography.html):
- Add yourself as coauthor to notebook
- Install MyST extension and CLI
- Convert notebook to MyST
- Configure bibliography for MyST
- Add citations and LitMap visualization
- AI-assisted "Subsequent Literature" section
- Git commit and PR

---

## Assignment

Instructor will email revised assignment. Continue working with selected ballpark items.

See: [AI revision with prompt tracking](https://llorracc.github.io/workspace-course-topics/assignments/ai-revision-with-prompt-tracking.html)

---

## Resources

- **Econ-ARK ballpark:** https://github.com/econ-ark/ballpark
- **Teaching topics:** https://github.com/llorracc/teaching-topics
- **PaperPile:** https://paperpile.com
- **Litmaps:** https://www.litmaps.com
- **as.180.369 materials:**
  - [The Setup](https://github.com/llorracc/as.180.369/blob/main/materials/setup/README.md) — PaperPile & LitMaps intro
  - [The Pitch](https://github.com/llorracc/as.180.369/blob/main/materials/pitch/README.md) — PaperPile sharing, LitMaps deeper dive
