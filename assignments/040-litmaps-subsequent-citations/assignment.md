# Assignment: Subsequent Literature Analysis

**Due:** Before next class

---

## Objective

1. Create a BibTeX file containing papers that have **cited** your ballpark paper
2. Use AI to analyze these citing papers and characterize the **current cutting-edge topics** in this research area

---

## Part A: Build the Subsequent Literature Bibliography

### Background

Your ballpark paper was published at some point in the past. Since then, other researchers have cited it. These **citing papers** represent the "subsequent literature" — work that builds on, extends, or responds to your paper.

### Free account limitations

LitMaps free accounts have limits:
- **2 maps** total
- **100 articles per map**
- **20 search inputs**

This is sufficient for this assignment if you work strategically.

### Steps

#### 1. Sign in to LitMaps

Go to https://www.litmaps.com and sign in (or create a free account).

#### 2. Import your ballpark paper's bibliography

1. Click **Import** (top left)
2. Select the .bib file you exported from PaperPile
3. Click **Import**

#### 3. Find your specific ballpark paper

1. In LitMaps, use the search bar to find your ballpark paper by title or author
2. If it doesn't appear in search, check "My Articles"

#### 4. Create a LitMap focused on citing papers

1. Click **New Litmap**
2. Add your ballpark paper as the **seed article**
3. Click **Discover** to find related articles

#### 5. Filter for CITING papers only

LitMaps shows both:
- Papers **cited by** your paper (backward citations — older)
- Papers **citing** your paper (forward citations — newer)

**You want only the forward citations.**

To filter:
1. Citing papers appear to the RIGHT of your seed paper in the visualization
2. Only add articles with publication dates AFTER your ballpark paper

#### 6. Add citing papers to your map

Prioritize:
- Highly cited papers
- Recent papers (last 3-5 years)
- Papers directly relevant to your ballpark topic

Focus on the most relevant 20-50 papers.

#### 7. Export as BibTeX

1. Click the **download/export icon**
2. Select **BibTeX** format
3. Save as `subsequent-literature.bib`

---

## Part B: AI-Assisted Analysis of Cutting-Edge Topics

### Purpose

Use AI to help you understand what the current research frontier looks like in the area of your ballpark paper.

### Steps

#### 1. Prepare your prompt

Ask an AI (Cursor, ChatGPT, Claude) to analyze the citing papers. Provide context:

> "I'm studying [brief description of your ballpark paper]. Here are the titles and abstracts of papers that have cited it since publication:
>
> [Paste titles and abstracts from your subsequent-literature.bib, or provide the .bib file directly]
>
> Based on these citing papers, please help me understand:
> 1. What are the main research directions that have emerged from this paper?
> 2. What are the cutting-edge topics currently being explored?
> 3. What methodological advances have been made?
> 4. What open questions or debates exist in this literature?
> 5. Which 3-5 papers seem most important for understanding where this field is heading?"

#### 2. Document the AI interaction

Create a file called `subsequent-literature-analysis.md` with:

```markdown
# Subsequent Literature Analysis: [Your Ballpark Paper Title]

## The Prompt I Used

[Paste your exact prompt here]

## AI Response

[Paste the AI's response]

## My Reflection

[Your own thoughts on the AI's analysis:
- Did the AI identify themes you expected?
- Anything surprising?
- Do you agree with the AI's assessment of the most important papers?
- What would you want to explore further?]
```

#### 3. Iterate if needed

If the AI's first response isn't helpful, refine your prompt and try again. Document what you changed and why.

---

## Deliverables

1. **`subsequent-literature.bib`** — BibTeX file of papers citing your ballpark paper
2. **`subsequent-literature-analysis.md`** — Your AI-assisted analysis including:
   - The prompt you used
   - The AI's response
   - Your reflection on the analysis

**Bring both files to class** — we will discuss what you learned.

---

## Grading Criteria

Your analysis will be evaluated on:
- **Completeness:** Did you identify relevant citing papers?
- **Thoughtful prompting:** Did you give the AI enough context to be helpful?
- **Critical engagement:** Does your reflection show you thought critically about the AI's output?
- **Insight:** Did you learn something about where this research area is heading?

---

## Troubleshooting

**"Can't find my ballpark paper in LitMaps":**
- Try searching by DOI
- Try the exact title
- Some working papers may not be indexed

**"No citing papers found":**
- Your paper may be very recent
- Document this and ask the AI to help identify related recent work instead

**"AI response seems generic or wrong":**
- Provide more specific context (abstracts, not just titles)
- Ask follow-up questions to dig deeper
- Try a different AI

---

## Tips for Success

1. **More context = better AI output.** Include abstracts, not just titles.

2. **Be specific in your prompt.** "Cutting-edge topics in heterogeneous agent macroeconomics" is better than "what's new in economics."

3. **Push back on the AI.** If something seems wrong, ask for clarification or alternative perspectives.

4. **Your reflection matters.** The goal isn't just to get AI output — it's to develop your understanding of the literature.
