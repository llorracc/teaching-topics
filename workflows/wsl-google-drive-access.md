# Reference: Accessing Google Drive from WSL (Windows)

**Purpose:** How Windows users can access Google Drive files from within WSL.

---

## The challenge

Google Drive for Desktop syncs files to your **Windows** filesystem (e.g., `C:\Users\YourName\Google Drive\`), not to your WSL/Linux filesystem.

When you're working in WSL, you can't use Windows-style paths directly.

---

## The solution: Use /mnt/c/

WSL provides access to Windows drives through `/mnt/`:
- `C:\` becomes `/mnt/c/`
- `D:\` becomes `/mnt/d/`

---

## Converting paths

| Windows path | WSL path |
|--------------|----------|
| `C:\Users\Alice\Google Drive\file.bib` | `/mnt/c/Users/Alice/Google Drive/file.bib` |
| `C:\Users\Bob\My Documents\paper.pdf` | `/mnt/c/Users/Bob/My Documents/paper.pdf` |

**Steps:**
1. Replace `C:\` with `/mnt/c/`
2. Replace all `\` with `/`
3. Keep the rest of the path the same
4. Add quotes if the path contains spaces

---

## Finding your Google Drive path

1. In Windows File Explorer, navigate to your Google Drive folder
2. Click in the address bar to see the full path
3. It will look something like: `C:\Users\YourName\Google Drive\My Library.bib`
4. Convert using the rules above

---

## Example: Copying a .bib file from Google Drive

```bash
# In WSL terminal, navigate to your ballpark paper
cd ~/GitHub/econ-ark/ballpark/models/We_Would_Like_In_Econ-ARK/YourPaper/

# Copy the file (note the quotes due to spaces)
cp "/mnt/c/Users/YourName/Google Drive/My Library.bib" ./references.bib
```

---

## Troubleshooting

**"No such file or directory":**
- Double-check the Windows username in the path
- Verify the file exists in Windows File Explorer
- Make sure you converted backslashes to forward slashes
- Ensure quotes are around the entire path

**File has a cloud icon in Windows:**
- The file may not be downloaded yet (Google Drive streams files)
- In Windows: right-click → "Make available offline"
- Wait for download to complete, then try again in WSL
