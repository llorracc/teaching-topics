# Assignment: AI-Assisted Paper Deep Dive

**Due:** Before next class

**Prerequisite:** [Ballpark Paper Selection](../010-ballpark-paper-selection/assignment.md) — you must have chosen a paper.

---

## Objective

Use AI tools to develop a **deep understanding** of your chosen paper:
- What the paper itself contributes
- The prior literature it builds on
- The subsequent literature that cites it
- The current state of this research area

By the end of this assignment, you should be able to explain this paper and its place in the literature to someone unfamiliar with the topic.

---

## Why This Matters

In the next class, we will learn how to:
- Upgrade existing ballpark items using MyST and modern bibliographical tools
- Prepare pull requests to modernize ballpark objects
- **Create your own ballpark objects** to add to the roster

This deep dive prepares you to create a high-quality ballpark entry for your paper. You can't write a good summary of a paper's contribution if you don't understand both the paper and its context.

---

## Can I Change My Paper?

Yes. If you've discovered that your original choice isn't a good fit, you may switch to a different paper. But **you must complete this deep dive for SOME paper** that you would be glad to see fully replicated in Econ-ARK.

If you switch papers, briefly note why in your submission.

---

## Steps

### 1. Start with the paper itself

Open Cursor and ask:

> "I'm studying a paper titled [full title]. The authors are [names] and it was published in [year/journal]. Can you help me understand:
> 1. What is the main research question this paper addresses?
> 2. What methodology or model does it use?
> 3. What are the key findings or contributions?
> 4. Why is this paper important to the field?"

**Iterate.** If the AI's response is too general, ask follow-up questions:
- "Can you be more specific about the methodology?"
- "What assumptions does the model make?"
- "What data does it use?"
- "How does this differ from previous approaches?"

---

### 2. Understand the prior literature

Ask the AI:

> "What prior literature does this paper build on? What were the key papers and ideas that made this work possible?"

Then dig deeper:
- "What was the state of the field before this paper?"
- "What problem or gap in the literature was this paper trying to address?"
- "Were there competing approaches? How does this paper's approach differ?"

---

### 3. Understand the subsequent literature

Ask the AI:

> "What has happened in this research area since this paper was published? What papers have cited it, and what directions have they taken?"

Then explore:
- "What aspects of this paper have been most influential?"
- "Have there been extensions, critiques, or replications?"
- "What's the current cutting-edge in this area?"
- "Are there open questions that remain unresolved?"

---

### 4. Synthesize: The paper's place in the literature

Ask the AI:

> "If I had to explain this paper to someone unfamiliar with the field, how would you summarize:
> 1. What problem it solves
> 2. How it fits into the broader literature
> 3. Why it matters today"

---

### 5. Identify what a good replication would need

Ask the AI:

> "If someone wanted to create a computational replication of this paper for teaching purposes, what would be the essential elements to include? What aspects of the model or analysis would be most valuable to implement?"

This helps you think about what your future ballpark object should contain.

---

## Document Your Work

Create a file called `paper-deep-dive.md` with the following structure:

```markdown
# Paper Deep Dive: [Paper Title]

## Paper Information

**Title:** [Full title]
**Authors:** [Names]
**Year:** [Publication year]
**Journal/Venue:** [Where published]

---

## Part 1: Understanding the Paper

### My prompts and AI responses

[Document your key prompts and the AI's responses]

### My summary of the paper's contribution

[In your own words, what does this paper contribute?]

---

## Part 2: Prior Literature

### Key papers this builds on

[List 3-5 key prior papers and briefly explain their relevance]

### The gap this paper addresses

[What was missing before this paper?]

---

## Part 3: Subsequent Literature

### How this paper has been influential

[What directions has the field taken since?]

### Current state of this research area

[Where is the field now?]

---

## Part 4: Synthesis

### The paper's place in the literature

[Your 2-3 paragraph synthesis of how this paper fits into the broader story]

### What a good replication would include

[What elements would be essential for a ballpark entry?]

---

## Part 5: Reflection

### What I learned from using AI for this

[Was the AI helpful? Where did it struggle? What did you have to verify or dig deeper on?]

### Am I keeping this paper or switching?

[If switching, briefly explain why]
```

---

## Deliverable

A file named `paper-deep-dive.md` containing:
1. Documentation of your AI-assisted exploration
2. Your synthesis of the paper's contribution and context
3. Your reflection on the process

**Bring this file to class** — we will discuss what you learned and use it as the foundation for creating ballpark objects.

---

## Tips for Success

1. **Use a frontier AI model** for this assignment. The depth of analysis benefits from more capable models (Claude Opus 4.5 or GPT-5.2). See [Assignment 040](../040-ai-literature-analysis/assignment.md) for how to switch models in Cursor.

2. **Don't just accept the first answer.** Iterate. Push for specifics. Ask "why?" and "how?"

3. **Verify key claims.** AI can hallucinate citations or mischaracterize papers. If something seems important, try to verify it.

4. **Your synthesis matters.** The AI can give you information, but YOU need to synthesize it into a coherent understanding.

5. **Think about replication.** As you learn about the paper, think about what would make a good computational demonstration. What's the core insight that could be illustrated with code?

---

## Looking Ahead

After this assignment, you'll be ready to:
- Modernize existing ballpark items (in-class)
- Create your own ballpark object (next assignment)
- Contribute to the Econ-ARK repository
