# Assignment: Integration and Pull Request

**Due:** Before next class  
**Time:** ~60-90 minutes

**Prerequisites:** 
- [Assignment 030: Prior Literature](../030-prior-literature/prior-literature.md) — `prior-literature.md`
- [Assignment 040: Subsequent Literature](../040-subsequent-literature/subsequent-literature.md) — `subsequent-literature.bib` + `subsequent-literature-analysis.md`

---

## Objective

1. Ask AI to propose revisions that integrate your prior and subsequent literature analysis with the existing ballpark content
2. Implement the revisions
3. Add yourself as coauthor
4. Create a Pull Request

---

## Part A: Review Current Ballpark Content

### 1. Open the current ballpark item in your local clone

In your terminal:

```bash
cd ~/GitHub/econ-ark/ballpark
ls models/We_Would_Like_In_Econ-ARK/[YourPaperFolder]/
```

Open the notebook file and read through the existing content.

---

### 2. Identify what's there vs. what's missing

The current ballpark item probably has:
- A summary of what the paper does
- Maybe some code demonstrating the model

What's likely missing (what YOU will add):
- Prior literature context
- Subsequent literature context
- Updated/improved explanation

**Reminder:** You selected your ballpark item in [Assignment 010](../010-ballpark-paper-selection/ballpark-paper-selection.md). Navigate to that folder in your clone of the ballpark repo.

---

## Part B: Ask AI to Propose Revisions

### 3. Give AI the full context

Use this prompt:

> "I'm improving a ballpark item for [paper title]. Here's what I have:
>
> **Current ballpark content:**
> [Paste the key content from the notebook]
>
> **Prior literature summary I wrote:**
> [Paste your prior-literature.md]
>
> **Subsequent literature analysis I wrote:**
> [Paste your subsequent-literature-analysis.md]
>
> Please propose specific revisions to the ballpark item that:
> 1. Add a 'Prior Literature' section summarizing what came before
> 2. Add a 'Subsequent Literature' section summarizing what came after
> 3. Improve the existing content to better connect with this context
> 4. Suggest any other improvements (clarity, accuracy, code demonstrations)
>
> Be specific about what to add and where."

---

### 4. Document the proposed revisions

Create `proposed-revisions.md`:

```markdown
# Proposed Revisions: [Paper Title]

## What the AI suggested

### Prior Literature section to add
[The text to add]

### Subsequent Literature section to add
[The text to add]

### Other improvements suggested
1. [Improvement 1]
2. [Improvement 2]
3. [Improvement 3]

## What I will implement
[Your decisions about which suggestions to use]
```

---

## Part C: Implement and Create PR

### 5. Navigate to the ballpark repository

```bash
cd ~/GitHub/econ-ark/ballpark
```

---

### 6. Get latest changes and create a branch

```bash
git checkout master
git pull origin master
git checkout -b improve-[paper-name]-[yourname]
```

---

### 7. Activate the environment and open in Cursor

```bash
source .venv/bin/activate
cursor .
```

---

### 8. Make your changes

Open the notebook in Cursor and:
1. **Add yourself as coauthor** (in the authors section)
2. **Add your Prior Literature section**
3. **Add your Subsequent Literature section**
4. **Implement other improvements** you decided on

Save the notebook.

---

### 9. Stage your changes

```bash
git add models/We_Would_Like_In_Econ-ARK/[YourPaperFolder]/
```

---

### 10. Verify before committing

Review what you're about to commit:

```bash
git diff --staged
```

Ask Cursor to review your staged changes:

> "Can you review my staged changes and tell me if anything looks wrong?"

---

### 11. Commit and push

```bash
git commit -m "Add literature context and improvements to [Paper Name]"
git push origin improve-[paper-name]-[yourname]
```

---

### 12. Create the Pull Request

1. Go to https://github.com/econ-ark/ballpark
2. Click "Compare & pull request" (should appear after you push)
3. Title: "Add literature context to [Paper Name]"
4. Description:

> This PR adds:
> - Prior Literature section (context on foundational papers)
> - Subsequent Literature section (what the field has done since)
> - [Any other improvements]
>
> Adds [Your Name] as coauthor.

5. Click **Create pull request**

---

### 13. Record your PR URL

Copy the PR URL (e.g., `https://github.com/econ-ark/ballpark/pull/42`)

**Bring this URL to class.**

---

## Deliverables (BEFORE CLASS)

| Deliverable | Description |
|-------------|-------------|
| `proposed-revisions.md` | Working document with AI-suggested revisions (keep for your records) |
| **PR URL** | Your Pull Request to econ-ark/ballpark — this is what gets reviewed |

**The PR is the main deliverable.** Bring your PR URL to class.

---

## In Class

We will:
- Review each other's PRs
- Discuss the improvements
- Learn MyST modernization techniques

---

## Tips

1. **Don't just copy-paste AI output.** Review and edit for accuracy and style.

2. **Keep sections concise.** Prior lit: 1-2 paragraphs. Subsequent lit: 2-3 paragraphs.

3. **Verify citations.** AI can hallucinate paper titles. Spot-check important references.
