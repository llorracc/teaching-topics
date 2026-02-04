# Assignment: AI-Assisted Literature Context and Improvement Suggestions

**Due:** Before next class

**Prerequisite:** [Ballpark Paper Selection](../010-ballpark-paper-selection/assignment.md) — you must have chosen a paper.

---

## Objective

Use AI to create content that **extends** the existing ballpark item:
1. A summary of the **prior literature** leading up to the paper
2. A summary of the **subsequent literature** that builds on it
3. Specific suggestions for **improving the current ballpark content**

The existing ballpark items summarize the paper itself. Your job is to provide the **context** that's missing.

---

## Why This Matters

In the next class, we will:
- Upgrade existing ballpark items using MyST and modern bibliographical tools
- Create pull requests to improve ballpark objects
- Eventually **create your own ballpark objects**

This assignment gives you material to add to the ballpark and teaches you how to use AI to identify improvements.

---

## Steps

### Part 1: Prior Literature Summary

The existing ballpark item explains what the paper does, but not **what came before it**.

Ask the AI:

> "I'm studying [paper title] by [authors], published in [year]. What prior literature does this paper build on? What were the key papers, models, and ideas that made this work possible? Please give me a 2-3 paragraph summary suitable for someone who wants to understand the intellectual lineage of this paper."

Then iterate:
- "What was the state of the field immediately before this paper?"
- "What specific gap or limitation was this paper addressing?"
- "Are there 3-5 key papers I should cite as foundational?"

**Deliverable:** A "Prior Literature" section (2-3 paragraphs) that could be added to the ballpark item.

---

### Part 2: Subsequent Literature Summary

Ask the AI:

> "What has happened in this research area since [paper title] was published? What papers have cited it, and what directions have they taken? Please give me a 2-3 paragraph summary of the subsequent literature and the current state of this research area."

Then iterate:
- "What aspects of this paper have been most influential?"
- "Have there been important extensions, critiques, or replications?"
- "What are the current cutting-edge topics in this area?"
- "What open questions remain?"

**Deliverable:** A "Subsequent Literature" section (2-3 paragraphs) that could be added to the ballpark item.

---

### Part 3: Review the Current Ballpark Content

Now look at the **actual ballpark item** for your paper (or a similar one if yours doesn't exist yet).

1. Open the ballpark repository: https://github.com/econ-ark/ballpark
2. Navigate to `models/We_Would_Like_In_Econ-ARK/` and find your paper's folder
3. Read through the existing notebook content

Then ask the AI:

> "Here is the current content of a ballpark item for [paper title]:
>
> [Paste the key content from the notebook]
>
> Based on what you know about this paper and its literature, what specific improvements would you suggest? Consider:
> - Accuracy of the summary
> - Missing context or caveats
> - Opportunities to add code demonstrations
> - Bibliography improvements
> - Clarity of explanation"

**Deliverable:** A list of 3-5 specific, actionable improvement suggestions.

---

## Document Your Work

Create a file called `literature-and-improvements.md`:

```markdown
# Literature Context and Improvements: [Paper Title]

## Paper Information

**Title:** [Full title]
**Authors:** [Names]
**Year:** [Publication year]
**Ballpark location:** `models/We_Would_Like_In_Econ-ARK/[folder name]/`

---

## Part 1: Prior Literature

[Your 2-3 paragraph summary of the prior literature]

### Key foundational papers
- [Paper 1]: [Brief explanation of relevance]
- [Paper 2]: [Brief explanation of relevance]
- [Paper 3]: [Brief explanation of relevance]

---

## Part 2: Subsequent Literature

[Your 2-3 paragraph summary of the subsequent literature]

### Current state of the field
[1 paragraph on where things stand now]

---

## Part 3: Improvement Suggestions

### Current ballpark content reviewed
[Brief description of what's currently in the ballpark item]

### Suggested improvements

1. **[Improvement 1]:** [Specific, actionable suggestion]

2. **[Improvement 2]:** [Specific, actionable suggestion]

3. **[Improvement 3]:** [Specific, actionable suggestion]

[Add more as needed]

---

## AI Tools Used

**Model(s):** [Which AI model(s) did you use?]

**Key prompts that worked well:**
[Note any prompts that gave particularly good results]
```

---

## Deliverable

A file named `literature-and-improvements.md` containing:
1. Prior literature summary (ready to add to ballpark)
2. Subsequent literature summary (ready to add to ballpark)
3. Specific improvement suggestions for the current content

**Bring this file to class** — we will use it when upgrading ballpark items.

---

## Tips for Success

1. **Use a frontier AI model** (Claude Opus 4.5 or GPT-5.2) for better literature knowledge.

2. **The summaries should be additive.** Don't repeat what's already in the ballpark — add context that's missing.

3. **Be specific in your improvement suggestions.** "Make it better" is not helpful. "Add a code cell demonstrating the Euler equation" is.

4. **Verify citations.** AI can hallucinate paper titles. If you cite specific papers, try to verify they exist.

---

## Part 4: Create Your Pull Request (BEFORE CLASS)

Once you have completed your literature summaries and improvement suggestions, **implement them and submit a Pull Request before class**.

### Steps:

1. **Fork the ballpark repository** (if you haven't already)
   - Go to https://github.com/econ-ark/ballpark
   - Click **Fork**

2. **Create a branch for your changes**
   ```bash
   cd ~/GitHub/econ-ark/ballpark
   git checkout master
   git pull origin master
   git checkout -b improve-[paper-name]-[yourname]
   ```

3. **Make your changes to the notebook**
   - Open the notebook in Cursor
   - Add yourself as a coauthor (in the authors section)
   - Add your "Prior Literature" section
   - Add your "Subsequent Literature" section
   - Implement any other improvements you proposed

4. **Commit and push**
   ```bash
   git add models/We_Would_Like_In_Econ-ARK/[YourPaperFolder]/
   git commit -m "Add literature context and improvements to [Paper Name]"
   git push myfork improve-[paper-name]-[yourname]
   ```

5. **Create the Pull Request**
   - Go to https://github.com/econ-ark/ballpark
   - Click "Compare & pull request"
   - Title: "Add literature context to [Paper Name]"
   - Description: Briefly describe what you added

6. **Record your PR URL** — bring it to class

---

## Deliverables (BEFORE CLASS)

| Deliverable | Description |
|-------------|-------------|
| `literature-and-improvements.md` | Your AI-assisted analysis document |
| **Pull Request URL** | PR with your changes to the ballpark |

**Both are required before class.**

---

## In Class

We will:
- Review each other's PRs
- Discuss the improvements
- Learn additional techniques for modernizing ballpark items
