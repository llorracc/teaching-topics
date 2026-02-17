# Workflow: Set up bibliography files for MyST

**Purpose:** Add BibTeX files to your ballpark directory and configure MyST to use them.

**External resources:**
- [The Submission (as.180.369)](https://github.com/llorracc/as.180.369/blob/main/materials/submission/README.md)

---

## ⚠️ Working directory

**You must be in:** `~/GitHub/econ-ark/ballpark`

**The .bib file goes in:** `models/We_Would_Like_In_Econ-ARK/[your-paper-folder]/`

Run this now:
```bash
cd ~/GitHub/econ-ark/ballpark && pwd
```

**Expected output:** Path ending in `/ballpark`

---

## Verify first

### 1. Verify you have a .bib file ready

You should have a `.bib` file from PaperPile (see [google-drive-paperpile-sync](google-drive-paperpile-sync.md)).

**Find your .bib file location:**
- **Mac:** Look in `~/Library/CloudStorage/GoogleDrive-[email]/My Drive/`
- **Windows/WSL:** This is tricky—see the copying instructions below

---

### 2. Verify your ballpark item directory exists

Run (replace `YourPaperFolder` with your actual folder name):
```bash
ls models/We_Would_Like_In_Econ-ARK/YourPaperFolder/
```

**Expected:** You see files like `README.md` or `*.ipynb`

---

## Steps

### A. Copy the PaperPile BibTeX file

#### Mac

```bash
# Navigate to your ballpark item
cd ~/GitHub/econ-ark/ballpark/models/We_Would_Like_In_Econ-ARK/YourPaperFolder/

# Copy the .bib file (adjust the source path to your actual location)
cp ~/Library/CloudStorage/GoogleDrive-*/My\ Drive/*.bib ./references.bib
```

#### Windows/WSL

Google Drive files are on the Windows filesystem. You need to access them through `/mnt/c/`:

```bash
# Navigate to your ballpark item
cd ~/GitHub/econ-ark/ballpark/models/We_Would_Like_In_Econ-ARK/YourPaperFolder/

# Find your Google Drive path (usually something like this)
# Replace 'YourUsername' with your Windows username
cp "/mnt/c/Users/YourUsername/Google Drive/My Library.bib" ./references.bib
```

**If you can't find the file:** See [_wsl-google-drive-access](_wsl-google-drive-access.md) for detailed instructions.

**If your path has spaces:** See [_paths-with-spaces](_paths-with-spaces.md) — you must use quotes around the path.

---

### B. Verify the copy worked

```bash
ls *.bib
```

**Expected:** Shows `references.bib` (or whatever you named it)

```bash
head -5 references.bib
```

**Expected:** Shows BibTeX entries (lines starting with `@article{` or similar)

---

### C. Create a BibTeX file for the paper itself (optional)

If you want a separate .bib file for just the paper you're working on:

1. Create a new file called `paper.bib`
2. Add a single BibTeX entry for your paper
3. You can generate this with ChatGPT:
   > "Generate a BibTeX entry for [paper title] by [authors]"

---

### D. Configure MyST to use the bib files

If your project uses MyST, modify `myst.yml` or the document frontmatter to include your bibliography:

```yaml
bibliography:
  - references.bib
  - paper.bib  # if you created this
```

Ask Cursor if you're unsure:
> "How do I add a bibliography to this MyST document?"
