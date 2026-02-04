# Assignment: Subsequent Literature

**Due:** Before next class  
**Time:** ~45-60 minutes

**Prerequisite:** You selected your ballpark paper in [Assignment 010](../010-ballpark-paper-selection/ballpark-paper-selection.md).

---

## Objective

1. Use **LitMaps** to find papers that CITE your ballpark paper
2. Export as `.bib`
3. Use **AI** to analyze where the field has gone

---

## Part A: Find Citing Papers with LitMaps

### 1. Sign in to LitMaps

Go to https://www.litmaps.com (free account is sufficient).

### 2. Find your ballpark paper

Search by title or author. Add it as the **seed article**.

### 3. Discover citing papers

Click **Discover**. You want papers **citing** your paper (forward/newer), not papers cited by it (backward/older).

### 4. Add citing papers to your map

Select 20-50 relevant citing papers. Prioritize highly cited and recent papers.

### 5. Export as BibTeX

Click export → BibTeX → Save as `subsequent-literature.bib`

---

## Part B: AI Analysis

### 6. Give the .bib to AI

Open Cursor and use this prompt:

> "Here are papers that have cited [your ballpark paper title]:
>
> [Paste your subsequent-literature.bib]
>
> Please analyze: What research directions emerged? What's cutting-edge now? Which 3-5 papers are most important for understanding where this field is heading?"

### 7. Iterate

Push deeper:
- "What gaps remain in this literature?"
- "What would a researcher need to know to contribute here?"

### 8. Save your analysis

Save as `subsequent-literature-analysis.md`:

```markdown
# Subsequent Literature Analysis: [Paper Title]

## Papers that cite my ballpark paper

I found [X] papers in LitMaps.

## What the subsequent literature tells us

[2-3 paragraphs: research directions, cutting-edge topics, open questions]

## Most important subsequent papers

1. [Paper]: [Why important]
2. [Paper]: [Why important]
3. [Paper]: [Why important]
```

---

## Troubleshooting

- **Can't find paper:** Try DOI or exact title
- **No citing papers:** Paper may be recent — document this
- **Too many papers:** Be selective — quality over quantity

---

## If You Get Stuck

**Ask Cursor AI.** If the "auto" model is inadequate, try **Claude Opus 4.5** or **ChatGPT 5.2**. If both agree, the answer is probably correct.

---

## Next Step

[Assignment 050: Integration and PR](../050-integration-and-pr/integration-and-pr.md)
