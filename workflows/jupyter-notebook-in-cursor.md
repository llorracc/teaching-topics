# Workflow: Open Jupyter notebook in Cursor

**Purpose:** Navigate to your ballpark notebook and open it within Cursor.

---

## ⚠️ Working directory (Cursor workspace root)

**Cursor must have been opened from:** `~/GitHub/<your-username>/ballpark`

**How to check:** Look at the Explorer panel (left side of Cursor). The root folder should be `ballpark`, not `models` or a paper name.

**If Cursor shows the wrong root:**
1. Close Cursor
2. In terminal: `cd ~/GitHub/econ-ark/ballpark && cursor .`

---

## ⚠️ Common mistake

Opening Cursor from a subdirectory like `models/We_Would_Like_In_Econ-ARK/SomeProject/` will cause problems:
- The `.venv` environment won't be found (it's at the repo root)
- Relative paths in notebooks will be wrong
- You won't be able to select the correct kernel

**Always open Cursor from the `ballpark` directory itself, then navigate to notebooks within Cursor.**

---

## Verify first

### 1. Verify the environment is activated

In Cursor's terminal, run:
```bash
echo $VIRTUAL_ENV
```

**Expected:** A path containing `.venv-...`

**If empty or no output:** You haven't activated the environment. Complete [cursor-environment-install](cursor-environment-install.md) first.

---

### 2. Verify your prompt shows the environment

Look at your terminal prompt in Cursor.

**Expected:** Prompt starts with `(VENV-Darwin-arm64)` or similar

**If not visible:** Run the activation command:
```bash
source .venv-$(uname -s | tr '[:upper:]' '[:lower:]')-$(uname -m)/bin/activate
```

---

### 3. Verify Cursor's workspace root

In the Explorer panel, the top-level folder should be `ballpark`.

**If it shows something else:**
1. File → Open Folder
2. Navigate to `~/GitHub/econ-ark/ballpark`
3. Click Open

---

## Steps

### 1. Navigate to your notebook in Cursor's Explorer

In the left sidebar, expand:
```
ballpark/
  └── models/
      └── We_Would_Like_In_Econ-ARK/
          └── [your-paper-folder]/
              └── [your-notebook].ipynb
```

Click on the `.ipynb` file to open it.

---

### 2. Select the kernel

When prompted "Select Kernel":
1. **Click "Python Environments"** — this is the correct option
2. Look for your `.venv-...` environment (usually at the TOP of the list)
3. Select it

**Common mistake:** Clicking "Jupyter Kernel" or "Select Another Kernel" instead. These options usually don't find your environment. Always start with **"Python Environments"**.

**If the environment doesn't appear:**
- You likely didn't activate before opening Cursor
- Close Cursor
- In terminal: `cd ~/GitHub/<your-username>/ballpark && source .venv-$(uname -s | tr '[:upper:]' '[:lower:]')-$(uname -m)/bin/activate && cursor .`
- Try opening the notebook again

---

### 3. Verify the kernel is correct

Look at the top-right of the notebook (next to "Run All").

**Expected:** Shows `VENV-Darwin-arm64` or your environment name

---

### 4. Run the notebook

Click "Run All" to execute all cells.

---

## Troubleshooting

**"Kernel not found" or can't find Python environment:**
1. Check that Cursor is open at the `ballpark` root (not a subdirectory)
2. Check that you activated the environment before opening Cursor
3. Close Cursor, activate environment, reopen from `ballpark` directory

**Windows: Environment shows but fails to start:**
- You may have Cursor in Windows mode instead of WSL mode
- Use Ctrl+Shift+P → "Remote-WSL: Reopen Folder in WSL"
