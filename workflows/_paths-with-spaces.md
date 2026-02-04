# Reference: Paths with Spaces or Special Characters

**Purpose:** Guidance for handling file paths that contain spaces, commas, or other special characters.

---

## The problem

Unix/Linux terminals interpret spaces as separators between arguments. If your path contains spaces, the command will fail:

```bash
# WRONG - terminal thinks these are two separate arguments
cp /Users/me/Google Drive/My Library.bib .
```

---

## The solution: Use quotes

Wrap the entire path in double quotes:

```bash
# CORRECT
cp "/Users/me/Google Drive/My Library.bib" .
```

---

## Common paths with spaces

| Source | Typical path | Has spaces? |
|--------|--------------|-------------|
| Google Drive (Mac) | `/Users/.../Google Drive/...` | Yes ("Google Drive") |
| Google Drive (Windows/WSL) | `/mnt/c/Users/.../Google Drive/...` | Yes |
| PaperPile export | `My Library.bib` | Yes ("My Library") |
| Some paper folders | `Author et al 2021/` | Yes |

---

## Quick rule

**If in doubt, always use quotes around paths.**

It never hurts to quote a path that doesn't need it, but failing to quote a path that does need it will cause errors.

---

## Special characters to watch for

These characters also require quoting:
- Spaces: `My File.txt`
- Commas: `Smith, Jones 2021.bib`
- Parentheses: `Paper (draft).pdf`
- Ampersands: `Tom & Jerry.txt`

---

## Example: Copying a .bib file

```bash
# Navigate to your ballpark paper directory
cd ~/GitHub/econ-ark/ballpark/models/We_Would_Like_In_Econ-ARK/YourPaper/

# Copy the .bib file (with quotes because of spaces)
cp "/Users/yourname/Library/CloudStorage/GoogleDrive-you@gmail.com/My Drive/My Library.bib" ./references.bib
```
