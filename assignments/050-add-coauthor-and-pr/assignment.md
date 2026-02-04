# Assignment: Add Yourself as Coauthor and Create a Pull Request

**Due:** Before next class

**Prerequisite:** [Ballpark Paper Selection](../010-ballpark-paper-selection/assignment.md)

---

## Objective

1. Add yourself as a coauthor to your ballpark notebook
2. Create a pull request to the ballpark repository with this change

This is your first contribution to an open-source repository.

---

## Ask Cursor Throughout

Use Cursor as your advisor for Git commands. If you're unsure about any step:

> "I'm trying to [describe what you want to do]. What Git command should I use?"

For example:
- "I want to create a new branch for my changes"
- "I pushed to the wrong place, how do I fix it?"
- "What does this error message mean?"

---

## Prerequisites

Before starting, verify:
- [ ] You have completed the [pre-class checklist](../../workflows/_verify-pre-class.md)
- [ ] You can open your ballpark notebook in Cursor
- [ ] You have a GitHub account

---

## Part A: Fork the ballpark repository

If you haven't already forked ballpark:

1. Go to https://github.com/econ-ark/ballpark
2. Click **Fork** (top right)
3. Select your GitHub account as the destination
4. You now have your own copy at `https://github.com/YOUR-USERNAME/ballpark`

---

## Part B: Set up your fork as a remote

In your terminal:

```bash
cd ~/GitHub/econ-ark/ballpark

# Check current remotes
git remote -v

# Add your fork as a remote named "myfork"
git remote add myfork https://github.com/YOUR-USERNAME/ballpark.git

# Verify
git remote -v
```

**Expected:** You see both `origin` (econ-ark/ballpark) and `myfork` (your fork)

---

## Part C: Create a branch for your changes

```bash
# Make sure you're on master and up to date
git checkout master
git pull origin master

# Create a new branch for your changes
git checkout -b add-coauthor-YOURNAME
```

Replace `YOURNAME` with your actual name (no spaces, e.g., `add-coauthor-smith`).

---

## Part D: Add yourself as coauthor

1. Open Cursor from the ballpark directory:
   ```bash
   cd ~/GitHub/econ-ark/ballpark
   source .venv/VENV-*/bin/activate
   cursor .
   ```

2. Navigate to your ballpark paper's notebook:
   ```
   models/We_Would_Like_In_Econ-ARK/[YourPaperFolder]/[notebook].ipynb
   ```

3. Find the cell that lists authors (usually near the top)

4. Add yourself as a coauthor. The format varies, but typically:
   ```markdown
   **Authors:** Original Author(s), Your Name (JHU)
   ```
   
   Or if there's a structured author list:
   ```markdown
   - Original Author (Original Institution)
   - Your Name (Johns Hopkins University)
   ```

5. Save the notebook (Cmd+S or Ctrl+S)

---

## Part E: Commit your changes

In Cursor's terminal (or your regular terminal):

```bash
# Verify you're in ballpark and on your branch
pwd
git branch --show-current

# Stage your changes
git add models/We_Would_Like_In_Econ-ARK/[YourPaperFolder]/

# Commit
git commit -m "Add [Your Name] as coauthor to [Paper Name] ballpark"
```

Replace the bracketed items with your actual information.

---

## Part F: Push to your fork

```bash
git push myfork add-coauthor-YOURNAME
```

---

## Part G: Ask Cursor to review your changes

Before creating the PR, ask Cursor to check your work:

> "I'm about to create a pull request. Can you review my staged changes and tell me if anything looks wrong?"

In Cursor, you can also run `git diff --staged` to see exactly what you're about to commit.

---

## Part H: Create a pull request

1. Go to https://github.com/econ-ark/ballpark
2. You should see a banner: "Compare & pull request" for your recently pushed branch
3. Click it
4. Fill in the PR:
   - **Title:** "Add [Your Name] as coauthor to [Paper Name]"
   - **Description:** 
     ```
     Adding myself as a coauthor for the [Paper Name] ballpark entry.
     
     This is part of coursework for Economics research methods.
     ```
5. Click **Create pull request**

---

## Part I: Record your PR URL

Copy the URL of your pull request (e.g., `https://github.com/econ-ark/ballpark/pull/42`)

**Bring this URL to class** — you'll need to share it.

---

## Verification

Your PR is successful if:
- [ ] The PR appears on https://github.com/econ-ark/ballpark/pulls
- [ ] The PR shows your notebook change (adding yourself as coauthor)
- [ ] There are no merge conflicts

---

## Troubleshooting

**"Permission denied" when pushing:**
- Make sure you're pushing to `myfork`, not `origin`
- Verify your GitHub credentials are set up correctly

**"Branch already exists":**
- Use a different branch name, or delete the old branch:
  ```bash
  git branch -D add-coauthor-YOURNAME
  git checkout -b add-coauthor-YOURNAME
  ```

**"Can't find the notebook":**
- Make sure Cursor is open at the `ballpark` root (not a subdirectory)
- Navigate through: models → We_Would_Like_In_Econ-ARK → [your paper folder]

**"Merge conflicts":**
- This can happen if someone else edited the same file
- Ask for help in class — we'll resolve it together

---

## What happens next

Your PR will be reviewed. Once approved and merged, you'll officially be a contributor to the Econ-ARK ballpark repository!
