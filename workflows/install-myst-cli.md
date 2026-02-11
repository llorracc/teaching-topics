# Workflow: Install MyST (CLI)

**Purpose:** Install the MyST command-line tools for building and converting documents.

**Note:** If you ran `bash scripts/setup_env.sh` in the ballpark repo, the MyST CLI (`mystmd`) was installed automatically via npm, and `myst-parser` and `jupytext` were installed in the Python venv. Use this workflow only if you need to install manually or troubleshoot.

---

## Verify first

```bash
myst --version
jupytext --version
```

If both commands print version numbers, you're done.

---

## Manual install (if needed)

### MyST CLI (mystmd)

Requires node/npm:
```bash
npm install -g mystmd
```

### MyST parser (Python)

```bash
pip install myst-parser
```

### Jupytext (notebook-to-MyST converter)

```bash
pip install jupytext
```

---

## Troubleshooting

- **`npm: command not found`**: Install node first (`brew install node` on macOS, `sudo apt install nodejs npm` on Linux/WSL)
- **`myst` installed but not found**: Add npm's global bin to PATH: `export PATH="$(npm prefix -g)/bin:$PATH"`
