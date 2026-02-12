# Assignments for Class 05

Complete before arriving at Class 05.

---

## Before You Start: Initial Steps

Do these **first**, on the same branch you used to open your original PR.

### 1. Start on your PR branch

Work in **your fork** on the branch you used to make your original ballpark PR. Do not create a new branch.

```bash
cd ~/GitHub/<your-username>/ballpark
git checkout <your-PR-branch>
git pull origin <your-PR-branch>
```

### 2. Create the summary notebook by copying

Before doing any other assignment work, make a **copy** of the Jupyter notebook that summarizes the paper and name the copy using the pattern `[directory-name]_summary.ipynb`.

**Example:** If your ballpark folder is `AHLifeCycleExpenditure` and the original notebook is `WangT-AHLifeCycleExpenditure.ipynb`, create a copy named `AHLifeCycleExpenditure_summary.ipynb` in the same folder. So you have:
- `AHLifeCycleExpenditure/WangT-AHLifeCycleExpenditure.ipynb` (original, unchanged)
- `AHLifeCycleExpenditure/AHLifeCycleExpenditure_summary.ipynb` (your copy — this is the one you will edit in the assignments)

You can copy the file in your file manager or in the terminal, e.g.:
```bash
cd models/We-Would-Like-In-Econ-ARK/[YourPaperFolder]/
cp [original-notebook].ipynb [directory-name]_summary.ipynb
```

### 3. Convert slideshows to a regular notebook (if needed)

If the original notebook is a **Jupyter slideshow** (e.g. it was built with RISE or has slide metadata), use an AI to run the [convert-slideshow-to-notebook](https://llorracc.github.io/workspace-course-topics/assignments/prompts/convert-slideshow-to-notebook.html) prompt on your **copy** (`[directory-name]_summary.ipynb`), not on the original. For example:

> Apply the convert-slideshow-to-notebook.md prompt to the ballpark `AHLifeCycleExpenditure`.

If the notebook was not a slideshow, the AI will report that no conversion was needed.

Once you have `[directory-name]_summary.ipynb` (and, if applicable, converted from slideshow format), the rest of the instructions below apply.

---

## Naming Convention

When you're done, your ballpark folder should contain four notebooks, all
sharing the same base name (the folder name). For example, if your folder
is `OptimumDebt`, you will produce:

| File | Purpose |
|------|---------|
| `OptimumDebt_intro.ipynb` | Paper metadata and attribution |
| `OptimumDebt_prior-literature.ipynb` | Prior literature with citations |
| `OptimumDebt_summary.ipynb` | Main summary notebook |
| `OptimumDebt_subsequent-literature.ipynb` | Subsequent literature with citations |

Plus three `.bib` files (`self.bib`, `references.bib`, `subsequent-literature.bib`) and a `myst.yml`.

---

## Key Concepts

### `self.bib`

Create a file called `self.bib` containing a single BibTeX entry for the
subject paper itself (the paper your ballpark entry is about). This is
separate from `references.bib`, which holds the prior literature.

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
    - file: [name]_intro.ipynb
    - file: [name]_prior-literature.ipynb
    - file: [name]_summary.ipynb
    - file: [name]_subsequent-literature.ipynb

site:
  title: "[Paper Title] — Ballpark Entry"
```

### Quality Standards for the Summary Notebook

- Fix any obvious typos or grammar errors in the existing text
- Heading hierarchy: single `#` for the title, `##` for sections, `###` for subsections
- Cross-references to companion notebooks must be clickable Markdown links,
  e.g. `[Prior Literature]([name]_prior-literature.ipynb)` — not just bold text
- Replace HTML `<img>` tags with Markdown image syntax using descriptive alt text

### Attribution

The `_intro.ipynb` notebook is the **single source of truth** for who
contributed. Put your "Updated by" line there and only there.

---

## Reference Example

See the completed Benhabib_et_al_2019 entry as a model of the finished product:
https://github.com/econ-ark/ballpark/tree/master/models/We-Would-Like-In-Econ-ARK/Benhabib_et_al_2019

---

## Assignment Steps

The detailed step-by-step instructions are here:

https://llorracc.github.io/workspace-course-topics/assignments/myst-assembly-and-pr.html

| Assignment | Deliverable |
|------------|-------------|
| [Create Intro Notebook](https://llorracc.github.io/workspace-course-topics/assignments/create-intro-notebook.html) | `[name]_intro.ipynb` |
| [Create Prior-Literature Notebook](https://llorracc.github.io/workspace-course-topics/assignments/create-prior-literature-notebook.html) | `self.bib` + `[name]_prior-literature.ipynb` + citations |
| [Create Subsequent-Literature Notebook](https://llorracc.github.io/workspace-course-topics/assignments/create-subsequent-literature-notebook.html) | `[name]_subsequent-literature.ipynb` + citations |
| [MyST Assembly + PR](https://llorracc.github.io/workspace-course-topics/assignments/myst-assembly-and-pr.html) | Four notebooks + `self.bib` + `myst.yml` + **PR URL** |

The first three create the companion notebooks. The MyST Assembly step weaves
everything together, applies quality fixes to the summary notebook, and produces the PR.

---

## IMPORTANT: How to Execute the Assignment

The [MyST Assembly + PR](https://llorracc.github.io/workspace-course-topics/assignments/myst-assembly-and-pr.html) page has numbered steps (Step 1, Step 2, ... Step 11).
**You can and should execute these by feeding each step to an AI in
Cursor, one at a time.** For example, type a prompt like:

> Execute Step 1 of
> `https://llorracc.github.io/workspace-course-topics/assignments/myst-assembly-and-pr.html`
> for the ballpark `OptimumDebt`.

After each step completes, **check whether it succeeded** before moving
on to the next. Look at the files the AI created or modified. If something
looks wrong, ask it to fix the problem before proceeding.

### Free AI vs. Premium AI

For mechanical steps (fixing typos, creating `myst.yml`, committing),
the free "auto" AI model in Cursor will work fine.

For steps that require **real knowledge of economics literature** — especially
creating the prior-literature and subsequent-literature notebooks — the free
model will produce noticeably weaker results. For those steps, use one of the
premium models:

- **Claude Opus 4.6**
- **ChatGPT 5.3**

Try running the literature steps with the free "auto" model first, then
re-run them with a premium model so you can see the difference in quality.
This comparison is itself a useful learning experience — it shows you when
model choice matters and when it doesn't.

---

## Final Deliverable

**Your PR URL.** Bring it to class.

Push all changes to your existing PR branch — no new PR needed.
