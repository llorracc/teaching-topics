# Workflow: Launch Cursor in the ballpark directory

**Purpose:** Open Cursor with the ballpark repo as your workspace.

---

## ⚠️ Working directory

**You must be in:** `~/GitHub/econ-ark/ballpark`

Run this now:
```bash
cd ~/GitHub/econ-ark/ballpark && pwd
```

**Expected output:** `/home/.../GitHub/econ-ark/ballpark` or `/Users/.../GitHub/econ-ark/ballpark`

**Do not proceed until you see this output.**

---

## Why this matters

When you run `cursor .` from a directory, Cursor opens with that directory as the workspace root. If you run `cursor .` from the wrong directory (e.g., `models/` or your home directory), Cursor will be in the wrong context and many things won't work correctly:
- The Python environment won't be found
- File paths in notebooks will be wrong
- Git operations will fail or behave unexpectedly

---

## Verify first

### 1. Verify terminal context

Run:
```bash
echo $HOME
```

**Expected:** `/home/...` (Linux/WSL) or `/Users/...` (Mac)

**If you see `C:\...`:** You're in Windows context. See [_verify-terminal-context](_verify-terminal-context.md).

---

### 2. Verify Cursor CLI is installed

Run:
```bash
which cursor
```

**Expected:** A path like `/usr/local/bin/cursor` or similar

**If "cursor not found":** 
- Open Cursor manually (from Applications or Start menu)
- In Cursor: Cmd+Shift+P (Mac) or Ctrl+Shift+P (Windows) → "Shell Command: Install 'cursor' command in PATH"
- Restart your terminal

---

## Steps

1. Navigate to ballpark:
   ```bash
   cd ~/GitHub/econ-ark/ballpark
   ```

2. **Confirm you're in the right place:**
   ```bash
   pwd
   ```
   You must see `ballpark` at the end of the path.

3. Launch Cursor:
   ```bash
   cursor .
   ```

4. **Verify Cursor opened correctly:**
   - Look at the Explorer panel (left side)
   - The ROOT folder should be named `ballpark`
   - You should see files like `README.md`, `models/`, `.venv/` at the top level
   - If you see `We_Would_Like_In_Econ-ARK` at the top level, you're in the wrong directory

---

## If Cursor opens in wrong context (Windows)

If Cursor shows Windows paths or PowerShell terminal:

1. In Cursor: Ctrl+Shift+P → "Remote-WSL: Reopen Folder in WSL"
2. Or: Close Cursor, ensure you're in WSL terminal, then run `cursor .` again
