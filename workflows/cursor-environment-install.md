# Workflow: Install and activate the environment

**Purpose:** Install and activate the Python environment for the ballpark repo.

---

## ⚠️ Working directory

**You must be in:** `~/GitHub/econ-ark/ballpark` (the repo root)

**NOT:** `~/GitHub/econ-ark/ballpark/models/...` (a subdirectory)

Run this now:
```bash
cd ~/GitHub/econ-ark/ballpark && pwd
```

**Expected output:** `/home/.../GitHub/econ-ark/ballpark` or `/Users/.../GitHub/econ-ark/ballpark`

**Do not proceed until you see this output.**

---

## Verify first

### 1. Verify the environment exists

Run:
```bash
ls -d .venv/VENV-*
```

**Expected:** One or more directories like `.venv/VENV-Darwin-arm64` or `.venv/VENV-Linux-x86_64`

**If "No such file or directory":** 
- You may be in the wrong directory—check with `pwd`
- If you're in `ballpark` but no `.venv`, ask Cursor:
  > "How do I install the environment for this repo?"

---

## Steps

### 1. Identify your environment

Run:
```bash
ls .venv/
```

Note the folder name that matches your system:
- **Mac Apple Silicon:** `VENV-Darwin-arm64`
- **Mac Intel:** `VENV-Darwin-x86_64`
- **Linux/WSL:** `VENV-Linux-x86_64`

---

### 2. Activate the environment

Run (replacing `VENV-Darwin-arm64` with your actual folder name):
```bash
source .venv/VENV-Darwin-arm64/bin/activate
```

---

### 3. Verify activation

Run:
```bash
echo $VIRTUAL_ENV
```

**Expected:** Full path ending in `.venv/VENV-...`

**Additional check:** Your terminal prompt should now show `(VENV-...)` at the beginning.

---

## ⚠️ IMPORTANT: Activation is required before notebooks

**You must activate the environment before:**
- Opening Jupyter notebooks (so Cursor can find the kernel)
- Running any Python code in the repo
- Selecting a Python interpreter in Cursor

If you skip activation, Cursor won't be able to find the correct kernel.

**Correct order:**
1. `cd ~/GitHub/econ-ark/ballpark`
2. `source .venv/VENV-.../bin/activate`
3. Then open notebooks in Cursor
