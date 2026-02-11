# Workflow: Git fetch/pull on ballpark

**Purpose:** Update your local ballpark clone to the latest version.

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

## Verify first

### 1. Verify terminal context

Run:
```bash
echo $HOME
```

**Expected:** `/home/...` (Linux/WSL) or `/Users/...` (Mac)

**If you see `C:\...`:** You're in Windows context. See [verify terminal context](https://llorracc.github.io/workspace-course-topics/workflows/verify-terminal-context.html).

---

### 2. Verify ballpark exists

Run:
```bash
ls ~/GitHub/econ-ark/ballpark
```

**Expected:** List of files including `README.md`, `models/`, etc.

**If "No such file or directory":** You need to clone ballpark first:
```bash
mkdir -p ~/GitHub/econ-ark
cd ~/GitHub/econ-ark
git clone https://github.com/econ-ark/ballpark.git
```

---

## Steps

Once all verifications pass:

1. Ensure you're in the ballpark directory:
   ```bash
   cd ~/GitHub/econ-ark/ballpark
   ```

2. Fetch and pull the latest changes:
   ```bash
   git fetch origin
   git pull origin master
   ```

3. Confirm success:
   ```bash
   git log -1 --oneline
   ```
   
   **Expected:** Shows the most recent commit (should be recent if updates were pulled).
