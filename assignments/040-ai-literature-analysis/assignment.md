# Assignment: AI Analysis of Cutting-Edge Topics

**Due:** Before next class

**Prerequisite:** [Subsequent Literature](../030-subsequent-literature/assignment.md) — you must have `subsequent-literature.bib` completed first.

---

## Objective

Use AI to analyze the papers that cite your ballpark paper and characterize the **current cutting-edge topics** in this research area.

**You will compare two AI experiences:**
1. A "free" (auto-selected) AI — iterating through multiple prompts
2. A frontier AI (Claude Opus 4.5 or ChatGPT 5.2) — for deeper analysis

---

## Purpose

You now have a bibliography of papers that cite your ballpark paper. But a list of papers isn't the same as understanding where the field is heading. In this assignment, you'll use AI to help you synthesize this literature and identify the research frontier.

You'll also learn an important skill: **iterative prompting**. The first answer an AI gives is rarely the best. By refining your prompts and pushing for deeper analysis, you can get substantially better results.

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

## Part A: Analysis with a Free AI (Iterative Prompting)

### 2. Start with Cursor's default AI

In Cursor, open the chat panel (Cmd+L on Mac, Ctrl+L on Windows). By default, Cursor uses "Auto" mode which selects a free or lower-cost model.

**Verify you're in Auto mode:** Look at the model selector at the bottom of the chat panel. It should say "Auto" or show a model name — don't change it yet.

---

### 3. Send your initial prompt

**Example initial prompt:**

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

### 4. Iterate — don't accept the first answer

⚠️ **Important:** The first answer you get is rarely the best. Push the AI to go deeper.

**Send follow-up prompts to refine the analysis:**

- "Can you be more specific about the methodological advances? What exactly changed?"
- "You mentioned [topic X]. What's the current debate or disagreement in that area?"
- "Which of these directions seems most promising? Why?"
- "Are there any gaps in this literature that no one seems to be addressing?"
- "What would a graduate student need to know to contribute to this literature?"

**Keep iterating until you feel you've reached a reasonably complete picture.** This might take 3-5 follow-up prompts.

Document your entire conversation — all prompts and responses.

---

## Part B: Deeper Analysis with a Frontier AI

### 5. Switch to a frontier AI model

Now you'll compare by using a more capable model.

**How to switch AI models in Cursor:**

1. In the chat panel, look at the **bottom of the panel** for the model selector
2. Click on it (it may say "Auto" or show a model name)
3. Select one of these frontier models:
   - **claude-4-opus** (Anthropic's most capable model)
   - **gpt-5.2** (OpenAI's most capable model)
4. If you don't see these options, click "More models..." to see the full list

**Note:** Frontier models may require a Cursor Pro subscription or have usage limits. If you can't access them in Cursor, you can use:
- https://claude.ai (for Claude Opus 4.5 — requires free account)
- https://chat.openai.com (for ChatGPT 5.2 — may require subscription)

---

### 6. Ask the frontier AI for deeper analysis

**Don't just repeat your original prompt.** Start by summarizing what you learned from the free AI, then ask for more:

> "I've been analyzing the subsequent literature citing [your ballpark paper]. Here's what I've learned so far:
>
> [Summarize your key findings from Part A]
>
> I'd like your help going deeper:
> 1. What aspects of this analysis might be incomplete or oversimplified?
> 2. Are there important nuances or debates that a surface-level analysis would miss?
> 3. What would be the most promising **next steps** for someone wanting to contribute to this literature?
> 4. If you were advising a graduate student, what specific research question would you suggest they pursue?
> 5. What data, methods, or theoretical frameworks would be most valuable for advancing this field?"

Document this conversation as well.

---

### 7. Document your complete analysis

Create a file called `subsequent-literature-analysis.md` with the following structure:

```markdown
# Subsequent Literature Analysis

## My Ballpark Paper

**Title:** [Full title of your ballpark paper]
**Authors:** [Original authors]
**Year:** [Publication year]
**Main contribution:** [1-2 sentences on what this paper contributed]

---

## Part A: Free AI Analysis (Auto/Default Model)

### Initial Prompt
[Paste your first prompt]

### Initial Response
[Paste the AI's response]

### Follow-up Prompt 1
[Your refinement question]

### Response 1
[AI's response]

### Follow-up Prompt 2
[Your next refinement question]

### Response 2
[AI's response]

[Continue for all follow-up prompts...]

### Summary of Part A Findings
[What did you conclude from the free AI? Key themes, directions, important papers]

---

## Part B: Frontier AI Analysis (Claude Opus 4.5 / GPT-5.2)

**Model used:** [Which frontier model did you use?]

### Prompt
[Your prompt to the frontier AI]

### Response
[The frontier AI's response]

### Follow-up (if any)
[Any additional questions and responses]

---

## Comparison and Reflection

### How did the free AI vs. frontier AI compare?
[Was the frontier AI's analysis deeper? More accurate? Different in perspective?]

### What did iterative prompting teach you?
[How did the responses improve as you refined your questions?]

### Key insights about the research frontier
[What did you learn about where this literature is heading?]

### Proposed next steps
[Based on the frontier AI's suggestions, what research directions seem most promising?]

### Limitations of this analysis
[What might the AIs have missed? What would require reading the actual papers?]
```

---

## Deliverable

A file named `subsequent-literature-analysis.md` containing:
1. Context about your ballpark paper
2. **Part A:** Your full conversation with the free AI (all prompts and responses)
3. **Part B:** Your conversation with the frontier AI
4. **Comparison:** Your reflection on how the two compared and what you learned

**Bring this file to class** — we will discuss what you learned.

---

## Grading Criteria

| Criterion | What we're looking for |
|-----------|------------------------|
| **Context provided** | Did you give the AI enough information about your ballpark paper and the citing papers? |
| **Iterative prompting** | Did you refine and improve your prompts, not just accept the first answer? |
| **Model comparison** | Did you use both a free and frontier AI, and thoughtfully compare them? |
| **Critical engagement** | Does your reflection show you thought carefully about whether the AI's outputs make sense? |
| **Next steps identified** | Did you come away with concrete ideas about research directions? |
| **Intellectual honesty** | Did you acknowledge limitations and uncertainties? |

---

## Troubleshooting

**"AI response seems generic":**
- Provide more specific context (abstracts, not just titles)
- Mention the specific field or methodology
- Ask follow-up questions to get more depth
- This is exactly why iterative prompting matters — push for specifics

**"AI got something wrong":**
- This is valuable to document! Note what was wrong and why you think so
- Ask the AI to reconsider with additional information
- Your critical engagement is part of the assignment

**"I only have a few citing papers":**
- That's fine — work with what you have
- You might ask the AI to also identify related recent work that *should* be citing this paper

**"I can't find the frontier models in Cursor":**
- Click the model selector at the bottom of the chat panel
- Look for "More models..." or scroll down in the list
- If you don't have access, use the web interfaces:
  - Claude Opus 4.5: https://claude.ai
  - ChatGPT 5.2: https://chat.openai.com

**"The free AI and frontier AI gave similar answers":**
- Try asking the frontier AI more challenging questions
- Ask it to critique or extend what the free AI said
- Document this similarity — it's a valid finding

---

## Tips for Success

1. **More context = better AI output.** Include abstracts when possible, and describe your ballpark paper's contribution clearly.

2. **Be specific.** "Cutting-edge topics in heterogeneous agent models of wealth inequality" is better than "what's new in economics."

3. **Don't accept the first answer.** The whole point of iterative prompting is to push past surface-level responses. If the AI gives you a generic answer, ask "Why?" or "Can you be more specific?"

4. **Save your best questions for the frontier AI.** After learning from the free AI, you'll know better questions to ask. Use that knowledge.

5. **Push back on the AI.** If something seems wrong or superficial, ask for clarification or alternative perspectives.

6. **Your reflection matters most.** The goal isn't just to get AI output — it's to develop your own understanding of the literature. The comparison section is where you demonstrate learning.

7. **Acknowledge uncertainty.** It's better to say "I'm not sure if the AI is right about X" than to accept everything uncritically.
