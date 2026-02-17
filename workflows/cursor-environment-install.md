# Workflow: Install and activate the environment

**Purpose:** Install all tools and Python dependencies for the ballpark repo using the automated setup script.

---

## Recommended: Run setup_env.sh

The ballpark repo includes a comprehensive setup script that installs everything you need in one command.

### 1. Navigate to the ballpark repo root

```bash
cd ~/GitHub/<your-username>/ballpark && pwd
```

**Expected output:** `/home/.../GitHub/<your-username>/ballpark` or `/Users/.../GitHub/<your-username>/ballpark`

**Do not proceed until you see this output.**

---

### 2. Run the setup script

```bash
bash scripts/setup_env.sh
```

This installs:
- **Homebrew** (macOS, if missing)
- **node/npm** (if missing)
- **uv** (if missing)
- **Python 3.12** (via uv)
- **Python venv** with all dependencies (econ-ark, jupyter, jupytext, myst-parser, ...)
- **mystmd CLI** (globally, via npm)
- **MyST-Markdown Cursor extension** (via .vsix download)

The script prints a summary with version numbers when finished.

---

### 3. Activate the environment

After the script completes, activate the virtual environment it created:

```bash
source .venv-$(uname -s | tr '[:upper:]' '[:lower:]')-$(uname -m)/bin/activate
```

Or identify your environment manually:

```bash
ls .venv-*/
```

And activate the one matching your platform:
- **Mac Apple Silicon:** `source .venv-darwin-arm64/bin/activate`
- **Mac Intel:** `source .venv-darwin-x86_64/bin/activate`
- **Linux/WSL:** `source .venv-linux-x86_64/bin/activate`

---

### 4. Verify activation

```bash
echo $VIRTUAL_ENV
```

**Expected:** Full path ending in `.venv-...`

Your terminal prompt should now show `(.venv-...)` at the beginning.

---

## Fallback: Manual setup

If `setup_env.sh` fails, you can set up manually:

1. Install uv: `curl -LsSf https://astral.sh/uv/install.sh | sh`
2. Create venv: `uv venv --python 3.12 .venv-$(uname -s | tr '[:upper:]' '[:lower:]')-$(uname -m)`
3. Install deps: `UV_PROJECT_ENVIRONMENT=.venv-... uv sync --python 3.12`
4. Install mystmd: `npm install -g mystmd`
5. Install extension: See [Install MyST-Markdown extension](install-myst-extension.md)

## ⚠️ IMPORTANT: Activation is required before notebooks

**You must activate the environment before:**
- Opening Jupyter notebooks (so Cursor can find the kernel)
- Running any Python code in the repo
- Selecting a Python interpreter in Cursor

**Correct order:**
1. `cd ~/GitHub/<your-username>/ballpark`
2. `source .venv-.../bin/activate`
3. Then open notebooks in Cursor
