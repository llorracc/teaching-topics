# Assignments for Class 05

Complete before arriving at Class 05.

---

## Terminology

Throughout this document, **BALLPARK** refers to your paper's folder name inside the ballpark repository (e.g. `OptimumDebt`, `HKMOHousingChannelMP`, `OpenHA`). All notebook filenames use this as a prefix.

---

## How This Assignment Works

Each step below has a matching **AI prompt**. You give the prompt to Cursor (or another AI), it does the work, and then you **check the result** before moving on.

You do not need to do the steps by hand — the AI handles the mechanics. Your job is to:
1. Give the AI the right prompt
2. Verify that the output looks correct
3. Fix anything that looks wrong before moving on

### Which AI model to use

- For **mechanical steps** (copying files, fixing typos, creating `myst.yml`, committing): the free "auto" model in Cursor works fine.
- For steps that require **real knowledge of economics literature** — especially creating the prior-literature and subsequent-literature notebooks — the free model produces noticeably weaker results. For those steps, switch to a premium model:
  - **Claude Opus 4.6**
  - **ChatGPT 5.3**

Try running the literature steps with the free model first, then re-run them with a premium model so you can see the difference. This comparison is itself a useful learning experience — it shows you when model choice matters and when it doesn't.

---

## Step 0: Get on your branch

You already have a fork and a PR branch from your earlier ballpark work. **Do not** create a new fork or branch — use the one you already have.

```bash
cd ~/GitHub/<your-username>/ballpark
```

If you don't remember your branch name, list your branches:

```bash
git branch          # the one with * is your current branch
```

Or check https://github.com/YOUR-USERNAME/ballpark → "Branches" tab.

Switch to your PR branch and pull the latest changes:

```bash
git checkout <your-PR-branch>
git pull origin <your-PR-branch>
```

> **If you get stuck with any Git command**, ask Cursor: *"I'm trying to [describe what you want to do]. What Git command should I use?"*

---

## Step 1: Create the summary notebook by copying

Make a **copy** of the Jupyter notebook that summarizes the paper and name the copy `BALLPARK_summary.ipynb`.

**Example:** If your folder is `AHLifeCycleExpenditure` and the original notebook is `WangT-AHLifeCycleExpenditure.ipynb`:

```bash
cd models/We-Would-Like-In-Econ-ARK/AHLifeCycleExpenditure/
cp WangT-AHLifeCycleExpenditure.ipynb AHLifeCycleExpenditure_summary.ipynb
```

You now have:
- `WangT-AHLifeCycleExpenditure.ipynb` (original — leave this unchanged)
- `AHLifeCycleExpenditure_summary.ipynb` (your copy — all your work goes here)

---

## Step 2: Convert slideshows (if needed)

The original notebook might be a Jupyter slideshow. Run the conversion prompt on your **copy** — it will do nothing if the notebook is not a slideshow.

Ask your AI:

> Apply the [convert-slideshow-to-notebook](https://llorracc.github.io/workspace-course-topics/assignments/prompts/convert-slideshow-to-notebook.html) prompt to the ballpark `BALLPARK`.

(Replace `BALLPARK` with your actual folder name, e.g. `AHLifeCycleExpenditure`.)

**What to check:** Open `BALLPARK_summary.ipynb`. It should read as a normal document, not a slide deck. If you see slide metadata, ask the AI to try again.

---

## Step 3: Create the intro notebook

Ask your AI:

> Apply the [coauthor-and-intro-notebook](https://llorracc.github.io/workspace-course-topics/assignments/prompts/coauthor-and-intro-notebook.html) prompt to the ballpark `BALLPARK`.

**What to check:** Open `BALLPARK_intro.ipynb`. Verify it contains:
- The paper's full title, authors, year, and venue
- The name of the original ballpark contributor (the student who made the earlier PR)
- Your name and today's date as "Updated by"

> **Note:** The sub-assignment page [Create Intro Notebook](https://llorracc.github.io/workspace-course-topics/assignments/create-intro-notebook.html) has additional background. You can skip its "Part A: Fork and set up" section — you already did that for your original PR.

---

## Step 4: Create the prior-literature notebook

**This step benefits from a premium AI model** (Opus 4.6 or ChatGPT 5.3).

Ask your AI:

> Apply the [prior-literature-notebook](https://llorracc.github.io/workspace-course-topics/assignments/prompts/prior-literature-notebook.html) prompt to the ballpark `BALLPARK`.

This will create `self.bib` (a BibTeX entry for the subject paper itself), `references.bib` (prior literature), and `BALLPARK_prior-literature.ipynb`.

**What to check:** Open the notebook and verify:
- It discusses at least 3-5 papers from the reference list
- Citations use `{cite:t}` or `{cite:p}` syntax with keys that match entries in `references.bib` or `self.bib`
- `self.bib` contains exactly one entry — for the paper your ballpark is about
- The subject paper does **not** also appear in `references.bib`

> **If you already have `references.bib`** from earlier PaperPile work, the AI should use it. If you don't have one yet, the AI will create it — but the result will be better with a premium model.

---

## Step 5: Create the subsequent-literature notebook

**This step also benefits from a premium AI model.**

Ask your AI:

> Apply the [subsequent-literature-notebook](https://llorracc.github.io/workspace-course-topics/assignments/prompts/subsequent-literature-notebook.html) prompt to the ballpark `BALLPARK`.

This will create `subsequent-literature.bib` and `BALLPARK_subsequent-literature.ipynb`.

**What to check:** Open the notebook and verify:
- It discusses papers that **cite** your ballpark paper (not the other way around)
- Citations use `{cite:t}` or `{cite:p}` syntax with keys matching `subsequent-literature.bib` or `self.bib`

> **If you already have `subsequent-literature.bib`** from earlier LitMaps work, the AI should use it. If you don't, the AI will create it — again, a premium model will do a better job.

---

## Step 6: Enhance the summary notebook with MyST citations and cross-references

Ask your AI:

> Apply the [myst-citations-in-original](https://llorracc.github.io/workspace-course-topics/assignments/prompts/myst-citations-in-original.html) prompt to the ballpark `BALLPARK`.

**What to check:** Open `BALLPARK_summary.ipynb` and verify:
- Typos and grammar errors have been fixed (without rewriting the original prose)
- There is exactly one `#` heading (the document title); sections use `##`, subsections `###`
- Papers mentioned inline have MyST citation tags
- There are clickable Markdown links to the companion notebooks (e.g. `[Prior Literature](BALLPARK_prior-literature.ipynb)`)
- Any HTML `<img>` tags have been replaced with Markdown image syntax

---

## Step 7: Create `myst.yml` and verify the build

Ask your AI:

> Apply the [myst-build-and-review](https://llorracc.github.io/workspace-course-topics/assignments/prompts/myst-build-and-review.html) prompt to the ballpark `BALLPARK`.

**What to check:**
- `myst.yml` exists in your paper folder and lists all four notebooks and all three `.bib` files
- `myst build` completes without errors
- No "undefined citation" warnings

---

## Step 8: Review, commit, and push

Ask your AI:

> Apply the [commit-and-push](https://llorracc.github.io/workspace-course-topics/assignments/prompts/commit-and-push.html) prompt to the ballpark `BALLPARK`.

Or do it yourself:

```bash
git add .
git commit -m "Add four-notebook MyST assembly with citations and TOC"
git push origin <your-PR-branch>
```

Since you already have an open PR from this branch, **pushing updates it automatically** — no new PR is needed.

**What to check:** Go to your PR on GitHub (e.g. `https://github.com/econ-ark/ballpark/pull/XX`) and verify that the PR now shows all your new files.

---

## Step 9: Record your PR URL

Copy your PR URL (e.g. `https://github.com/econ-ark/ballpark/pull/42`).

**Bring this URL to class** — you'll need to share it.

---

## What Your Folder Should Look Like When You're Done

```
OptimumDebt/
├── OptimumDebt.ipynb                          ← original (unchanged)
├── OptimumDebt_summary.ipynb                  ← your copy (edited)
├── OptimumDebt_intro.ipynb                    ← new
├── OptimumDebt_prior-literature.ipynb         ← new
├── OptimumDebt_subsequent-literature.ipynb    ← new
├── self.bib                                   ← new (the subject paper)
├── references.bib                             ← prior literature
├── subsequent-literature.bib                  ← subsequent literature
└── myst.yml                                   ← new (TOC + bibliography config)
```

---

## Reference: Key Concepts

### `self.bib`

A file containing a single BibTeX entry for the subject paper itself (the paper your ballpark entry is about). This is separate from `references.bib`, which holds the prior literature.

### `myst.yml`

```yaml
version: 1

project:
  title: "[Paper Title] — Ballpark Entry"
  bibliography:
    - self.bib
    - references.bib
    - subsequent-literature.bib
  toc:
    - file: BALLPARK_intro.ipynb
    - file: BALLPARK_prior-literature.ipynb
    - file: BALLPARK_summary.ipynb
    - file: BALLPARK_subsequent-literature.ipynb

site:
  title: "[Paper Title] — Ballpark Entry"
```

### Quality standards for the summary notebook

- Fix any obvious typos or grammar errors in the existing text
- Heading hierarchy: single `#` for the title, `##` for sections, `###` for subsections
- Cross-references to companion notebooks must be clickable Markdown links, e.g. `[Prior Literature](BALLPARK_prior-literature.ipynb)` — not just bold text
- Replace HTML `<img>` tags with Markdown image syntax using descriptive alt text

### Attribution

The `_intro.ipynb` notebook is the **single source of truth** for who contributed. Put your "Updated by" line there and only there.

### Reference example

See the completed Benhabib_et_al_2019 entry as a model of the finished product:
https://github.com/econ-ark/ballpark/tree/master/models/We-Would-Like-In-Econ-ARK/Benhabib_et_al_2019

---

## Troubleshooting

**Citations don't resolve:**
- The citation key must match an entry in `self.bib`, `references.bib`, or `subsequent-literature.bib` exactly (case-sensitive)
- Verify all three `.bib` files are listed in `myst.yml` under `project: bibliography:`

**`myst build` fails:**
- Ensure MyST CLI is installed: `myst --version`
- Run from the correct directory (your paper folder, not the repo root)
- Re-run `bash scripts/setup_env.sh` if needed

**"Permission denied" when pushing:**
- Make sure you're pushing to **your fork**, not to `econ-ark/ballpark`
- Check `git remote -v` — `origin` should point to your fork

**Push rejected ("non-fast-forward"):**
- Someone may have updated the branch. Try:
  ```bash
  git pull --rebase origin <your-PR-branch>
  git push origin <your-PR-branch>
  ```

**Branch or remote confusion:**
- Run `git remote -v` and `git branch --show-current` to see where you are
- Ask Cursor: *"My git remote -v shows [paste output]. Am I pushing to the right place?"*

---

## If You Get Stuck

**Ask Cursor AI.** Describe what you're trying to do in plain English. If the free "auto" model gives a poor answer, try **Claude Opus 4.6** or **ChatGPT 5.3**. If two models agree, the answer is probably correct.

---

## Final Deliverable

**Your PR URL.** Push all changes to your existing PR branch — no new PR needed. Bring the URL to class.
