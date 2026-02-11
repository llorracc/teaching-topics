# Orchestrator: Contribution

**Phase:** Artifacts  
**Time:** ~15 minutes

## Purpose

Create a pull request with your changes to the ballpark repository.

---

## Prerequisites

- Changes made to your notebook (at minimum: added yourself as coauthor)
- GitHub account
- Fork of ballpark repository

---

## Ask Cursor to Review

Before creating the PR:
> "I'm about to create a pull request. Can you review my staged changes and tell me if anything looks wrong?"

---

## Workflow sequence

### 1. Fork the repository (if not already done)

1. Go to https://github.com/econ-ark/ballpark
2. Click **Fork**
3. Add your fork as a remote:
   ```bash
   git remote add myfork https://github.com/YOUR-USERNAME/ballpark.git
   ```

---

### 2. Create a branch

```bash
git checkout -b add-coauthor-YOURNAME
```

---

### 3. [Git add, commit, and PR](https://llorracc.github.io/workspace-course-topics/workflows/git-commit-and-pr.html)

Stage changes, commit, and create a pull request for your modifications.

**Key steps:**
1. Stage: `git add models/We_Would_Like_In_Econ-ARK/[YourPaperFolder]/`
2. Commit: `git commit -m "Add [Your Name] as coauthor to [Paper Name]"`
3. Push: `git push myfork add-coauthor-YOURNAME`
4. Create PR on GitHub

**Deliverable:** PR URL (e.g., `https://github.com/econ-ark/ballpark/pull/42`)

---

## Checkpoint

Your PR is successful if:
- [ ] The PR appears on https://github.com/econ-ark/ballpark/pulls
- [ ] The PR shows your notebook change
- [ ] There are no merge conflicts

---

## Assignment

This orchestrator completes:
- [Assignment 050: Add Coauthor + PR](https://llorracc.github.io/workspace-course-topics/assignments/add-coauthor-and-pr.html)

---

## What happens next

Your PR will be reviewed. Once approved and merged, you'll officially be a contributor to the Econ-ARK ballpark repository!
