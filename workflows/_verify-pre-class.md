# Pre-Class Verification Checklist

**Purpose:** Verify your environment is ready BEFORE class. Complete all checks and fix any issues.

**Bring to class:** Be prepared to demonstrate each verification step if asked.

---

## 1. Terminal context (Windows users especially)

Run:
```bash
echo $SHELL
```

**Expected:** `/bin/bash` or `/bin/zsh`

**If wrong:** You're in Windows PowerShell. Type `wsl` to enter Ubuntu.

---

## 2. Ballpark repository exists

Run:
```bash
ls ~/GitHub/econ-ark/ballpark/README.md
```

**Expected:** Shows the file path (no error)

**If "No such file":** Clone the repo:
```bash
mkdir -p ~/GitHub/econ-ark
cd ~/GitHub/econ-ark
git clone https://github.com/econ-ark/ballpark.git
```

---

## 3. Ballpark is up to date

Run:
```bash
cd ~/GitHub/econ-ark/ballpark && git pull origin master
```

**Expected:** "Already up to date" or shows files updated

**If error about uncommitted changes:** Ask for help or run `git stash` first.

---

## 4. Environment exists

Run:
```bash
ls ~/GitHub/econ-ark/ballpark/.venv/
```

**Expected:** Shows `VENV-Darwin-arm64/` or `VENV-Linux-x86_64/` (depends on your system)

**If empty or missing:** The environment needs to be created. Ask Cursor:
> "How do I install the Python environment for this repo?"

---

## 5. Environment activates successfully

Run:
```bash
cd ~/GitHub/econ-ark/ballpark
source .venv/VENV-*/bin/activate
echo $VIRTUAL_ENV
```

**Expected:** Path ending in `.venv/VENV-...`

**If error:** The environment may be corrupted. Ask for help.

---

## 6. Cursor launches from ballpark

Run:
```bash
cd ~/GitHub/econ-ark/ballpark
cursor .
```

**Expected:** Cursor opens with `ballpark` as the root folder in Explorer

**If "cursor: command not found":** Open Cursor manually, then: Cmd+Shift+P → "Shell Command: Install 'cursor' command in PATH"

---

## 7. PaperPile account exists with papers

Go to https://paperpile.com and sign in.

**Expected:** You see bibliography entries for your ballpark paper

**If empty:** You need to add references. Ask an AI:
> "I need to create a BibTeX file for the references in [paper title]. What's the most efficient way?"

---

## 8. PaperPile connected to JHU Libraries

In PaperPile: Settings → Proxy Connection

**Expected:** Johns Hopkins University is selected and "Test Connection" succeeds

**If not connected:** Select Johns Hopkins University and test the connection.

---

## 9. Google Drive installed and syncing

**Mac:** Look for Google Drive icon in menu bar  
**Windows:** Look for Google Drive icon in system tray

**Expected:** Icon is visible; your Gmail account is connected

**If not installed:** Download from https://www.google.com/drive/download/

---

## 10. BibTeX Export Workflow configured in PaperPile

In PaperPile: Click profile icon (top right) → Workflows and Integrations

**Expected:** You see a BibTeX Export workflow listed

**If missing:** Click "Add Workflow" → "BibTeX Export" → Source: My Library → Destination: Google Drive → Finish

---

## Summary

| Check | Status |
|-------|--------|
| 1. Terminal context | ☐ |
| 2. Ballpark exists | ☐ |
| 3. Ballpark up to date | ☐ |
| 4. Environment exists | ☐ |
| 5. Environment activates | ☐ |
| 6. Cursor launches | ☐ |
| 7. PaperPile has papers | ☐ |
| 8. PaperPile → JHU | ☐ |
| 9. Google Drive installed | ☐ |
| 10. BibTeX Export configured | ☐ |

**All boxes checked?** You're ready for class.

**Any failures?** Fix them before class, or arrive early to get help.
