# Class 10 — Matsya — API keys, install, and Dolo Plus workflow

**Date:** April 7, 2026

**Recording:** Zoom cloud recording for **180.606 Topics — Part 2** (~1h 53m); link in the meeting-assets email from Zoom (Apr 7, 2026).

> **Note:** Based on Zoom’s AI meeting summary (with **Matzia** → **Matsya**, **EconArc** → **Econ-ARK**). Wording below is **edited for a neutral class record**; instructor **Q&A** lines are left as spoken. See [econ-ark/Matsya](https://github.com/econ-ark/Matsya).

---

## Meeting summary

### Overview

Class time focused on **setup and use** of **Matsya** (Econ-ARK CLI/API) together with **Anthropic API keys**, **Claude Code**, and **Cursor**, applied to students’ **ballpark** repositories. Matsya was presented as an AI assistant for modular dynamic programming and **Dolo Plus**-related notation.

### Key concepts

- **API keys:** Credentials for calling Claude (and similar) from the terminal or tools; distinct from browser chat.
- **Matsya:** Econ-ARK tool backed by a curated knowledge base; needs a **team-issued token** in addition to any Anthropic billing setup.
- **Dolo Plus:** Extension of Dolo-style YAML for describing models; Matsya can suggest or discuss specifications, which should still be **checked** like any generated draft.
- **Claude Code:** Anthropic’s CLI-oriented integration with Claude, used in parallel with Cursor.
- **WSL:** On Windows, installs and repos should live in the **Linux** filesystem if that is where the terminal and Cursor point.

### Questions the discussion raised

- How API access differs from chat-only use, and what that implies for cost and workflow.
- How Matsya and Dolo Plus relate to other macro computational tools (e.g. Dynare for representative-agent setups).
- How much to trust model summaries and YAML emitted by an LLM-backed tool.
- Prepaid billing and credit limits for API use.

### What students did (high level)

- Obtained Anthropic API access and exported keys in `.bashrc` / `.zshrc` (with awareness of reload and credit exhaustion).
- Installed **Claude Code** (including **Node.js** where needed) and **Matsya** via `pip` from GitHub; worked through **Python version** and path issues, including **WSL vs Windows** trees.
- Installed the **Claude Code** extension in **Cursor** and separated **Matsya token** vs **Anthropic** credentials.
- Practiced giving Matsya **explicit context** (e.g. notebook excerpts), since it does not see the repo unless provided.
- Tried Matsya on **ballpark** material toward **Dolo Plus**-style descriptions; reminder to **verify** outputs.

### Topic 1: API keys and shell config

Students used Anthropic’s console/dashboard to create an account, add a small credit balance, and create an API key. Emphasis: keys are **shown once**, should be stored safely, and billing is **prepaid** (calls stop when credits run out). Keys were added to shell startup files so they persist across sessions; changing those files requires **reloading** the shell or opening a new terminal.

### Topic 2: Install and environment

Install paths differed by OS (**Homebrew** on Mac, **WSL** on Windows). **Matsya** was installed with `pip` from the GitHub repo; missing **Node.js** and similar dependencies were resolved as they appeared. Windows users were reminded to **clone inside WSL** if that is the environment they use for development.

#### Relevant Q&A

Student: I cannot see the folders locally. Could it be because I am using WSL all the time?

Chris-JHU: Yes, actually. So you'll need to clone the thing inside the WSL file system.

### Topic 3: Cursor, Claude Code, credentials

Students added the Claude Code extension in Cursor and configured **both** the Anthropic API key and the **Matsya** token. The distinction was stressed: Matsya does **not** retain full project context between calls the way a long Composer thread might.

#### Relevant Q&A

Chris-JHU: You need to really bear in mind that Matsya is a completely external tool which does not have access to anything in the file system that you do not feed to it directly. Cursor's Composer remembers what you've done before, but every time you make a query to Matsya, you have to make sure that it has the context that it needs to answer your question.

### Topic 4: What Matsya is for

Matsya is positioned as a **helper** for modular DP / Bellman structure and **Dolo Plus** syntax, drawing on a **fixed** knowledge base rather than general web search. **Dolo Plus** builds on Dolo; Dynare remains the reference ecosystem for many RA models. Anything Matsya writes should be treated as a **draft** to review against the paper and your own judgment.

Students used **Composer** to paste or attach **notebook** material so Matsya had enough context to comment or suggest YAML-shaped output.

#### Relevant Q&A

Chris-JHU: What we're developing here is the new version of something like Dynare, but for heterogeneous agent models. One language that started doing that was a thing called Dolo, and we have added on to Dolo some important capabilities that it was missing, and that's why we have Dolo Plus now.

### Topic 5: Ballpark exercise

Students pointed Matsya at **ballpark** projects: describe the economic setup, probe unclear math, and experiment with **Dolo Plus**-style specifications. Prompts work best when **short and scoped**; large pastes slow things down and still need human editing.

#### Relevant Q&A

Chris-JHU: You will find that you can ask Matsya all sorts of questions, and it has a deep understanding of the math. So if there's anything about the paper when you read it that you had trouble understanding, ask Matsya to explain that concept or to help you understand what's going on.

### Follow-up assignment (germ — formalize in `assignments/` later)

**Timing:** *TBD* (e.g. due before Class 11); not yet on the course assignment index.

**Goal:** Use **Matsya** on your **ballpark** paper in a disciplined way: improve your own understanding of the dynamic program, and produce a **Dolo Plus-style draft** you can defend—not copy-paste truth.

**Do this:**

1. **Choose material** that actually has a Bellman / sequential problem. If your current ballpark is purely reduced-form or empirical, switch to a ballpark (or section of a paper) with an explicit dynamic optimization core for this exercise only.

2. **Configure access** (Anthropic API + Matsya token + `matsya configure`) so you can run queries from the terminal; use a **`--session`** tag tied to your project name so turns stay in context.

3. **Work in short, scoped prompts.** Paste or attach only the excerpt Matsya needs (e.g. timing paragraph + budget + Bellman statement). Ask it to clarify states, controls, shocks, information, and—when ready—to draft or revise **Dolo Plus** YAML. Avoid dumping whole PDFs or whole repos.

4. **Verify.** For at least one substantive Matsya answer, compare against the **source paper** and note what you changed or rejected and why (one short paragraph is enough).

**Turn in (sketch):** (a) the **session name** you used; (b) a **redacted** export or paste of **2–3 representative prompts** and the **corresponding answers** (remove tokens/secrets); (c) your latest **Dolo Plus draft** (or fragment) as a file in the ballpark repo or appendix; (d) the **verification** paragraph. *Exact format to be set when the assignment is published.*

### Supplemental resources

- Anthropic: console / dashboard for API keys and billing.
- Matsya: [github.com/econ-ark/Matsya](https://github.com/econ-ark/Matsya).
- Cursor + Claude Code extension docs.
- WSL docs (file paths, distros).
- Dolo / Dolo Plus documentation.

[View in Zoom](https://zoom.us/launch/hub?type=summary&mid=u3UJE0M%2BQoK%2BXAYuKSp6kw%3D%3D&origin=https%3A%2F%2Fzoom.us%2Fuser%2Fmeeting%2Fsummary%3FmeetingId%3Du3UJE0M%252BQoK%252BXAYuKSp6kw%253D%253D)

*AI can make mistakes. Review for accuracy.*

---

## Assignments in play (from Class 9)

Due before this class or ongoing — see [Assignments for Class 10](https://github.com/llorracc/teaching-topics/blob/main/assignments/for-class-10.md) (REMARK compliance self-assessment; SSJ tutorial exploration).
