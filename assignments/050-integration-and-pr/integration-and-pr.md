# Assignment: Integration and Pull Request

**Due:** Before next class  
**Time:** ~60-90 minutes

**Prerequisites:** 
- [Assignment 030](../030-prior-literature/prior-literature.md) — `prior-literature.md`
- [Assignment 040](../040-subsequent-literature/subsequent-literature.md) — `subsequent-literature.bib` + `subsequent-literature-analysis.md`

---

## Objective

1. Ask AI to propose revisions integrating your literature analysis
2. Implement the revisions
3. Add yourself as coauthor
4. Create a Pull Request

---

## Part A: Ask AI for Revisions

### 1. Open your ballpark item

```bash
cd ~/GitHub/econ-ark/ballpark
ls models/We_Would_Like_In_Econ-ARK/[YourPaperFolder]/
```

Open the notebook and review the existing content.

### 2. Ask AI to propose revisions

Use this prompt:

> "I'm improving a ballpark item for [paper title]. Here's what I have:
>
> **Current ballpark content:** [Paste notebook content]
>
> **Prior literature summary:** [Paste prior-literature.md]
>
> **Subsequent literature analysis:** [Paste subsequent-literature-analysis.md]
>
> Propose specific revisions: where to add Prior Literature section, Subsequent Literature section, and any other improvements."

### 3. Save proposed revisions

Create `proposed-revisions.md`:

```markdown
# Proposed Revisions: [Paper Title]

## Prior Literature section to add
[Text]

## Subsequent Literature section to add
[Text]

## Other improvements
[List]
```

---

## Part B: Implement and Create PR

### 4. Fork ballpark (once) and set up remotes

**You are not a collaborator on `econ-ark/ballpark`.** To make a PR, you will:
1. Fork `econ-ark/ballpark` to your GitHub account
2. Push your changes to your fork
3. Open a PR from your fork back to `econ-ark/ballpark`

If you haven't already forked ballpark:

1. Go to https://github.com/econ-ark/ballpark
2. Click **Fork**
3. Select your GitHub account as the destination

Now, in your terminal (from your local `ballpark` clone):

```bash
cd ~/GitHub/econ-ark/ballpark

# Check your current remotes
git remote -v

# Add your fork as a remote named "myfork"
git remote add myfork https://github.com/YOUR-USERNAME/ballpark.git

# Verify
git remote -v
```

**Expected:** You see both:
- `origin` (the upstream `econ-ark/ballpark`)
- `myfork` (your fork)

### 5. Create a branch

```bash
git checkout master
git pull origin master
git checkout -b improve-[paper-name]-[yourname]
```

**Stuck on git?** Ask Cursor AI — paste any error messages.

### 6. Make your changes

```bash
source .venv/bin/activate
cursor .
```

In Cursor, open the notebook and:
1. Add yourself as coauthor
2. Add Prior Literature section
3. Add Subsequent Literature section
4. Implement other improvements

Save the notebook.

### 7. Stage and verify

```bash
git add models/We_Would_Like_In_Econ-ARK/[YourPaperFolder]/
git diff --staged
```

Ask Cursor: "Can you review my staged changes?"

### 8. Commit and push (to your fork)

```bash
git commit -m "Add literature context to [Paper Name]"
git push myfork improve-[paper-name]-[yourname]
```

### 9. Create Pull Request (from your fork)

1. Go to your fork on GitHub: `https://github.com/YOUR-USERNAME/ballpark`
2. You should see a banner offering to create a PR for your recently pushed branch. Click **Compare & pull request**.
3. Make sure the PR target is:
   - **base repository:** `econ-ark/ballpark`
   - **base branch:** `master`
   - **head repository:** `YOUR-USERNAME/ballpark`
   - **compare branch:** `improve-[paper-name]-[yourname]`
4. Title: "Add literature context to [Paper Name]"
5. Description: What you added + your name as coauthor
6. Click **Create pull request**

### 10. Record your PR URL

Copy the URL (e.g., `https://github.com/econ-ark/ballpark/pull/42`)

**Bring this URL to class.**

---

## Deliverable

**Your PR URL** — this is what gets reviewed in class.

---

## Tips

1. **Don't copy-paste AI blindly.** Review and edit.
2. **Keep sections concise.** Prior lit: 1-2 paragraphs. Subsequent lit: 2-3 paragraphs.
3. **Verify citations.** AI can hallucinate paper titles.

---

## If You Get Stuck

**Ask Cursor AI.** If the "auto" model is inadequate, try **Claude Opus 4.5** or **ChatGPT 5.2**. If both agree, the answer is probably correct.
