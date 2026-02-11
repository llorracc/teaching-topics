# Verification: Terminal Context

**Purpose:** Ensure your terminal is in the correct filesystem context before proceeding with any workflow.

**Windows users:** You must be in WSL/Ubuntu, not Windows PowerShell.

---

## Verification steps

### 1. Check your shell

Run:
```bash
echo $SHELL
```

**Expected output:** `/bin/bash` or `/bin/zsh`

**If you see nothing or an error:** You are likely in PowerShell. Open a terminal and type `wsl` to enter Ubuntu.

---

### 2. Check your home directory

Run:
```bash
echo $HOME
```

**Expected output:** `/home/yourusername` (Linux/WSL) or `/Users/yourusername` (Mac)

**NOT expected:** `C:\Users\...` or any path with backslashes

---

### 3. Check your current path format

Run:
```bash
pwd
```

**Expected:** Path starting with `/` (e.g., `/home/alice/GitHub/econ-ark/ballpark`)

**NOT expected:** Path starting with `C:` or containing backslashes

---

## If verification fails (Windows users)

1. Open a new terminal
2. Type `wsl` and press Enter
3. You should see your prompt change (often to `username@machine:~$`)
4. Run the verifications again

Once all verifications pass, proceed with the workflow.

---

## Common mistake: Wrong directory

Many workflows require you to be in a specific directory (usually `~/GitHub/econ-ark/ballpark`).

**Check your current directory:**
```bash
pwd
```

**Navigate to ballpark if needed:**
```bash
cd ~/GitHub/econ-ark/ballpark
```

Being in the wrong directory is one of the most common causes of errors. Always verify your location before running commands.
