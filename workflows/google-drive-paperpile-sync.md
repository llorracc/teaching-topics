# Workflow: Google Drive sync for PaperPile

**Purpose:** Make your PaperPile bibliography files accessible on your local computer via Google Drive.

---

## ⚠️ Critical: Two separate steps required

Connecting PaperPile to Google Drive is **not enough** to get a .bib file. You must also set up a **BibTeX Export Workflow**. These are two different things:

1. **Cloud Storage connection** (Settings → Data and Files) — stores PDFs in Google Drive
2. **BibTeX Export Workflow** (Profile → Workflows and Integrations) — creates the .bib file ⬅️ **This is what you need!**

Many students miss step 2 and wonder why they don't have a .bib file.

---

## Verify first

### 1. Verify Google Drive is installed

**Mac:** Look for Google Drive icon in menu bar (top right)

**Windows:** Look for Google Drive icon in system tray (bottom right)

**If not installed:** Download from https://www.google.com/drive/download/

---

### 2. Verify your Gmail account is connected

Click the Google Drive icon → check that your Gmail account appears.

**If not connected:**
1. Click Google Drive icon → **Add Account**
2. Sign in with your Gmail account (the one linked to PaperPile)

---

## Steps

### 1. Connect PaperPile to Google Drive (for PDF storage)

1. In PaperPile: click **Settings** (gear icon, bottom left)
2. Go to **Data and Files**
3. Scroll down to **Cloud Storage**
4. Select **Google Drive**

This enables PaperPile to store PDFs in your Google Drive. **But this does NOT create a .bib file.**

---

### 2. ⚠️ Set up BibTeX Export Workflow (REQUIRED for .bib file)

**This is the critical step that creates a .bib file you can use locally.**

1. In PaperPile: click your **profile icon** (top right — NOT the Settings gear!)
2. Select **Workflows and Integrations** from the dropdown
3. Click **Add Workflow**
4. Choose **BibTeX Export**
5. Configure:
   - **Source:** Select "My Library" or your specific ballpark folder
   - **Destination:** Select **Google Drive**
6. Click **Finish**
7. Click **Open File in Google Drive** to verify the .bib file was created

**Common mistake:** Looking for this in Settings. It's NOT in Settings — it's under your profile icon → Workflows and Integrations.

---

### 3. Verify the .bib file appears locally

1. Open Finder (Mac) or File Explorer (Windows)
2. Navigate to your Google Drive folder
3. Look for the .bib file (e.g., `My Library.bib` or `[FolderName].bib`)

**Expected:** You see a `.bib` file with your bibliography.

**If the file has a cloud icon:** Right-click → "Make available offline" (or "Download")

---

### 4. Note the path to your .bib file

You'll need this path later to copy the file to your ballpark directory.

**Mac:** Ctrl-click the file → hold Option → "Copy as Pathname"

**Windows:** Click in the address bar → copy the path

---

## Troubleshooting

**Can't find the .bib file:**
- Did you set up the BibTeX Export Workflow (Step 2)? This is the most common issue.
- Check Workflows and Integrations → your workflow should show "Last run: ..."
- The file may be at the root of your Google Drive, not in a PaperPile subfolder
- Search your Google Drive folder for `*.bib`

**File shows cloud icon, won't open:**
- Right-click → Make available offline
- Wait for download to complete (cloud icon should disappear)

**"Workflows and Integrations" not visible:**
- Make sure you're clicking your **profile icon** (top right), not Settings (bottom left)
- The profile icon is usually your photo or initials

---

## Next step

Once you have the .bib file locally, you can copy it to your ballpark directory using [bibliography-setup-myst](bibliography-setup-myst.md).
