# Assignment: Prior Literature Summary

**Due:** Before next class  
**Time:** ~20-30 minutes

**Prerequisite:** [PaperPile Bibliography](../020-paperpile-bibliography/paperpile-bibliography.md) — you need your `.bib` file containing the papers your ballpark paper cites.

---

## Objective

Use AI to write a **1-2 paragraph summary** of the prior literature that your ballpark paper builds on.

---

## Why This Matters

Every paper builds on prior work. Understanding what came before helps you:
- Understand why the paper made the choices it did
- Identify the intellectual lineage of the ideas
- Write better context for your ballpark contribution

---

## Steps

### 1. Locate your PaperPile .bib file

Find the `.bib` file you exported from PaperPile. This contains the references from your ballpark paper — the papers IT cites.

---

### 2. Give it to AI with this prompt

Open Cursor (or another AI) and use this prompt:

> "Here is the bibliography (.bib file) from [paper title by authors, year]. These are the papers it cites. 
>
> Please write a 1-2 paragraph summary of the prior literature that this paper builds on. What were the key ideas, models, or findings from these cited papers that made this paper possible?
>
> [Paste your .bib file contents here]"

---

### 3. Iterate if needed

If the summary is too generic, ask follow-up questions:
- "Which of these papers were most foundational?"
- "What specific gap in the prior literature was this paper addressing?"
- "Can you be more specific about the methodological foundations?"

---

### 4. Save your summary

Save a file called `prior-literature.md`. This is a **working document** you'll use in Assignment 050 to prepare your PR — it won't be committed to the repo itself.

```markdown
# Prior Literature Summary: [Paper Title]

## The papers my ballpark paper cites

[1-2 paragraph summary from AI]

## Key foundational papers

- [Paper 1]: [One sentence on why it matters]
- [Paper 2]: [One sentence on why it matters]
- [Paper 3]: [One sentence on why it matters]
- [Paper 4]: [One sentence on why it matters]
- [Paper 5]: [One sentence on why it matters]
```

---

## Deliverable

A file named `prior-literature.md` containing:
- 1-2 paragraph summary of the prior literature
- 3-5 key foundational papers identified

**Keep this short.** This is background context, not a comprehensive literature review.

---

## Tips

1. **Use the .bib file directly.** The AI can parse BibTeX format and extract paper titles, authors, and years.

2. **1-2 paragraphs maximum.** Don't let the AI write a dissertation. If it gives you more, ask it to condense.

3. **Focus on intellectual lineage.** What ideas did your paper inherit? What methods did it build on?

---

## Next Step

After completing this, proceed to [Assignment 040: Subsequent Literature](../040-subsequent-literature/subsequent-literature.md).
