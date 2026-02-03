# Workflow: Set up bibliography files for MyST

**Purpose:** Add BibTeX files to your ballpark directory and configure MyST to use them.

**External resources:**
- [The Submission (as.180.369)](https://github.com/llorracc/as.180.369/blob/main/materials/submission/README.md)

---

## Steps

### A. Copy the PaperPile BibTeX file

1. Copy the `.bib` file exported from PaperPile into your ballpark directory.

### B. Create a BibTeX file for the paper itself

1. Create a new `.bib` file containing **only** the reference to the paper you are working on.
   - You can export just that entry from PaperPile, or create it manually / with AI assistance.

### C. Tell MyST about both bib files

1. Modify the MyST configuration (e.g. `myst.yml` or the document frontmatter) so it knows about **both** bib files:
   - The PaperPile bibliography (citations from the paper).
   - The single-entry bib file for the paper itself.
