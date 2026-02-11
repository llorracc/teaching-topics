# Workflow: PaperPile setup and sharing

**Purpose:** Set up PaperPile, connect to JHU libraries, and populate your bibliography.

---

## Verify first

### 1. Verify you have a PaperPile account

Go to https://paperpile.com and sign in.

**Expected:** You can access your PaperPile library.

**If no account:** Create one at https://paperpile.com (free trial or paid).

---

### 2. Verify you have papers in your library

In PaperPile, check "My Library" or "All Papers".

**Expected:** You see the bibliography entries for your ballpark paper.

**If empty:** You need to add your bibliography first. See the next section.

---

## Populating your bibliography

Adding references one-by-one is tedious. Before doing that, **ask an AI for help**:

> "I need to create a BibTeX file containing all the references from [paper title]. What's the most efficient way to do this?"

Try asking:
- Cursor (in your chat panel)
- ChatGPT
- Claude

The AI may suggest approaches you hadn't considered. This is a skill you'll use throughout your research career: when facing a tedious task, ask whether there's a more efficient approach.

**After you have a .bib file:** Import it into PaperPile via File → Import.

---

## Steps

### 1. Connect to JHU Libraries

1. In PaperPile: click **Settings** (gear icon, bottom left)
2. Select **Proxy Connection**
3. Choose **Johns Hopkins University**
4. Click **Test Connection** to verify

**Expected:** "Connection successful" or similar message

This enables PaperPile to download PDFs through Hopkins library access.

---

### 2. Update metadata

1. In your library, click **Select All** (checkbox at top)
2. Click **More** → **Auto Update**
3. Wait for the update to complete

This retrieves journal names, volume numbers, page numbers, abstracts, etc.

---

### 3. Find PDFs

1. With papers still selected, click **More** → **Find PDFs Online**
2. Wait for the search to complete

Some PDFs may not be found—this is normal. Hopkins access improves the success rate.

---

### 4. Create a folder for your ballpark paper (optional)

1. Right-click in the left sidebar → **New Folder**
2. Name it after your ballpark paper (e.g., "SSJ2021")
3. Drag your bibliography entries into this folder

This keeps your ballpark bibliography organized separately from other papers.

---

## ⚠️ Next step: Set up BibTeX Export

**Important:** Completing this workflow does NOT automatically create a .bib file on your computer. You must proceed to the next workflow to set up the BibTeX Export.

**Proceed to:** [google-drive-paperpile-sync](google-drive-paperpile-sync.md)

This will guide you through:
1. Connecting Google Drive
2. **Setting up "Workflows and Integrations" → BibTeX Export** (the step that creates your .bib file)
