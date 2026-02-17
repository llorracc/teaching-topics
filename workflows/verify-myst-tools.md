# Workflow: Verify MyST tools are installed

**Purpose:** Quick checklist to confirm all MyST-related tools are working before starting MyST conversion work.

**Time:** < 1 minute (if `setup_env.sh` ran successfully)

---

## Checklist

Run each command and confirm it prints a version number:

### 1. MyST CLI

```bash
myst --version
```

**Expected:** A version like `v1.6.0` or higher.

**If missing:** `npm install -g mystmd` (see [Install MyST CLI](install-myst-cli.md))

---

### 2. Jupytext

```bash
jupytext --version
```

**Expected:** A version like `1.19.1` or higher.

**If missing:** `pip install jupytext` (or re-run `bash scripts/setup_env.sh`)

---

### 3. MyST-Markdown Cursor extension

1. Open the Extensions panel in Cursor (`Cmd+Shift+X` / `Ctrl+Shift+X`).
2. Search your installed extensions for **MyST**.
3. Confirm **MyST-Markdown** by ExecutableBookProject is installed.

**If missing:** See [Install MyST-Markdown extension](install-myst-extension.md)

---

## All good?

If all three checks pass, you're ready to proceed with the [MyST Assembly orchestrator](../orchestrators/05-myst-conversion.md).

If any tool is missing, the fastest fix is to re-run the setup script from the ballpark repo root:
```bash
cd ~/GitHub/<your-username>/ballpark
bash scripts/setup_env.sh
```
