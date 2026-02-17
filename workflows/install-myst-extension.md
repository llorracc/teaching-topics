# Workflow: Install MyST-Markdown extension in Cursor

**Purpose:** Install the MyST-Markdown VS Code extension for syntax highlighting, autocomplete, and preview.

**Note:** If you ran `bash scripts/setup_env.sh` in the ballpark repo, the extension may already be installed automatically. Use this workflow only if you need to install it manually or troubleshoot.

---

## Verify first

Check if the extension is already installed:

1. In Cursor, open the Extensions panel (`Cmd+Shift+X` / `Ctrl+Shift+X`).
2. Search for **MyST** in the installed extensions.
3. If **MyST-Markdown** by ExecutableBookProject is listed, you're done.

---

## Option A: Manual VSIX install (recommended fallback)

Cursor's marketplace is separate from VS Code's and may not include this extension. Download and install the `.vsix` file directly:

1. Download the extension:
   ```bash
   curl -L "https://ExecutableBookProject.gallery.vsassets.io/_apis/public/gallery/publisher/ExecutableBookProject/extension/myst-highlight/latest/assetbyname/Microsoft.VisualStudio.Services.VSIXPackage" -o /tmp/myst-highlight.vsix
   ```
2. Install in Cursor:
   - Extensions panel → click the `...` menu (top right) → **"Install from VSIX..."**
   - Select `/tmp/myst-highlight.vsix`
3. Reload Cursor if prompted.

Or from the command line (if Cursor CLI is on PATH):

```bash
cursor --install-extension /tmp/myst-highlight.vsix
```

---

## Option B: Search in Cursor (may not work)

1. Open the Extensions panel (`Cmd+Shift+X` / `Ctrl+Shift+X`).
2. Search for **MyST-Markdown**.
3. If found, install the extension by **ExecutableBookProject** (`ExecutableBookProject.myst-highlight`).

---

## What this gives you

- Extended syntax highlighting for MyST directives and roles.
- Hover information and autocomplete for MyST syntax.
- Enhanced preview rendering.
- Code snippets for roles and directives.
