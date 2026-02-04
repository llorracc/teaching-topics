# Assignment: AI Analysis of Cutting-Edge Topics

**Due:** Before next class

**Prerequisite:** [Subsequent Literature Bibliography](../040-litmaps-subsequent-citations/assignment.md) — you must have `subsequent-literature.bib` completed first.

---

## Objective

Use AI to analyze the papers that cite your ballpark paper and characterize the **current cutting-edge topics** in this research area.

---

## Purpose

You now have a bibliography of papers that cite your ballpark paper. But a list of papers isn't the same as understanding where the field is heading. In this assignment, you'll use AI to help you synthesize this literature and identify the research frontier.

---

## Steps

### 1. Gather information from your .bib file

Open `subsequent-literature.bib` and extract the key information:
- Paper titles
- Authors
- Publication years
- Abstracts (if included)

If your .bib file doesn't include abstracts, you can:
- Look up abstracts on Google Scholar
- Use the abstracts shown in LitMaps
- Focus on titles if abstracts aren't available (but note this in your analysis)

---

### 2. Prepare your prompt

Ask an AI (Cursor, ChatGPT, Claude) to analyze the citing papers. Provide context about your ballpark paper and the citing papers.

**Example prompt structure:**

> "I'm studying a paper about [brief description of your ballpark paper — its main contribution, methodology, findings].
>
> Since its publication, the following papers have cited it:
>
> [Paste titles and abstracts, or provide the .bib file content]
>
> Based on these citing papers, please help me understand:
> 1. What are the main research directions that have emerged from this paper?
> 2. What are the cutting-edge topics currently being explored?
> 3. What methodological advances have been made?
> 4. What open questions or debates exist in this literature?
> 5. Which 3-5 papers seem most important for understanding where this field is heading, and why?"

---

### 3. Document the AI interaction

Create a file called `subsequent-literature-analysis.md` with the following structure:

```markdown
# Subsequent Literature Analysis

## My Ballpark Paper

**Title:** [Full title of your ballpark paper]
**Authors:** [Original authors]
**Year:** [Publication year]
**Main contribution:** [1-2 sentences on what this paper contributed]

---

## The Prompt I Used

[Paste your exact prompt here — this helps us understand what context you provided]

---

## AI Response

[Paste the AI's full response]

---

## My Reflection

### Themes I expected
[Did the AI identify research directions you anticipated?]

### Surprises
[Anything unexpected in the AI's analysis?]

### Agreement/Disagreement
[Do you agree with the AI's assessment of the most important papers? Why or why not?]

### What I want to explore further
[Based on this analysis, what aspects of the literature would you want to dig deeper into?]

### Limitations of this analysis
[What might the AI have missed? What would require reading the actual papers to understand?]
```

---

### 4. Iterate if needed

If the AI's first response isn't helpful:
- Refine your prompt with more specific context
- Try a different AI
- Ask follow-up questions

Document what you changed and why in your analysis file.

---

## Deliverable

A file named `subsequent-literature-analysis.md` containing:
1. Context about your ballpark paper
2. The prompt you used
3. The AI's response
4. Your thoughtful reflection on the analysis

**Bring this file to class** — we will discuss what you learned.

---

## Grading Criteria

| Criterion | What we're looking for |
|-----------|------------------------|
| **Context provided** | Did you give the AI enough information about your ballpark paper and the citing papers? |
| **Thoughtful prompting** | Did you ask specific, focused questions? |
| **Critical engagement** | Does your reflection show you thought carefully about whether the AI's output makes sense? |
| **Insight** | Did you learn something about where this research area is heading? |
| **Intellectual honesty** | Did you acknowledge limitations and uncertainties? |

---

## Troubleshooting

**"AI response seems generic":**
- Provide more specific context (abstracts, not just titles)
- Mention the specific field or methodology
- Ask follow-up questions to get more depth

**"AI got something wrong":**
- This is valuable to document! Note what was wrong and why you think so
- Ask the AI to reconsider with additional information
- Your critical engagement is part of the assignment

**"I only have a few citing papers":**
- That's fine — work with what you have
- You might ask the AI to also identify related recent work that *should* be citing this paper

---

## Tips for Success

1. **More context = better AI output.** Include abstracts when possible, and describe your ballpark paper's contribution clearly.

2. **Be specific.** "Cutting-edge topics in heterogeneous agent models of wealth inequality" is better than "what's new in economics."

3. **Push back on the AI.** If something seems wrong or superficial, ask for clarification or alternative perspectives.

4. **Your reflection matters most.** The goal isn't just to get AI output — it's to develop your own understanding of the literature. The reflection section is where you demonstrate learning.

5. **Acknowledge uncertainty.** It's better to say "I'm not sure if the AI is right about X" than to accept everything uncritically.
