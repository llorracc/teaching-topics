# Workflow: Install MyST-Markdown extension in Cursor

**Purpose:** Install the MyST-Markdown VS Code extension for syntax highlighting, autocomplete, and preview.

**Note:** Cursor's extension marketplace is separate from VS Code's and may not include this extension. If searching "MyST" in Cursor returns nothing, use the manual install method below.

---

## Option A: Search in Cursor (may not work)

1. In Cursor, open the Extensions panel (View → Extensions, or `Cmd+Shift+X` / `Ctrl+Shift+X`).
2. Search for **MyST-Markdown**.
3. If found, install the extension by **ExecutableBookProject** (`ExecutableBookProject.myst-highlight`).

---

## Option B: Manual VSIX install (if search fails)

1. Go to the VS Code Marketplace page:  
   https://marketplace.visualstudio.com/items?itemName=ExecutableBookProject.myst-highlight
2. Click **"Download Extension"** (under Resources on the right side) to get the `.vsix` file.
3. In Cursor: Extensions panel → click the `...` menu (top right) → **"Install from VSIX..."**
4. Select the downloaded `.vsix` file.
5. Reload Cursor if prompted.

---

## Option C: Command line install (may work)

```bash
cursor --install-extension ExecutableBookProject.myst-highlight
```

---

## What this gives you

- Extended syntax highlighting for MyST directives and roles.
- Hover information and autocomplete for MyST syntax.
- Enhanced preview rendering.
- Code snippets for roles and directives.
