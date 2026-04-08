# Class 10 — Matsya — API keys, install, and Dolo Plus workflow

**Date:** April 7, 2026

**Recording:** Zoom cloud recording for **180.606 Topics — Part 2** (~1h 53m); link in the meeting-assets email from Zoom (Apr 7, 2026).

> **Note:** Based on Zoom’s AI meeting summary (with **Matzia** → **Matsya**, **EconArc** → **Econ-ARK**). Wording below is **edited for a neutral class record**; instructor **Q&A** lines are left as spoken. See [econ-ark/Matsya](https://github.com/econ-ark/Matsya).

---

## Meeting summary

### Overview

Class time focused on **setup and use** of **Matsya** (Econ-ARK CLI/API) together with **Anthropic API keys**, **Claude Code**, and **Cursor**, applied to students’ **ballpark** repositories. Matsya was presented as a **narrow** assistant for modular dynamic programming and **Dolo Plus**-related notation—not as a full substitute for established heterogeneous-agent solution stacks, but as something to consult for structure and syntax alongside your normal editor and LLM workflow.

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

#### Relevant Q&A

Josh: Is it set up to automatically reload, or do you have to reload it manually?

Chris-JHU: Yes, you have to reload it manually. It will tell you when you run out of money, and it won't work until you put some more money in.

### Topic 2: Install and environment

Install paths differed by OS (**Homebrew** on Mac, **WSL** on Windows). **Matsya** was installed with `pip` from the GitHub repo; missing **Node.js** and similar dependencies were resolved as they appeared. Windows users were reminded to **clone inside WSL** if that is the environment they use for development.

#### Relevant Q&A

Student: I cannot see the folders locally. Could it be because I am using WSL all the time?

Chris-JHU: Yes, actually. So you'll need to clone the thing inside the WSL file system.

### Topic 3: Cursor, Claude Code, credentials

Students added the Claude Code extension in Cursor and configured **both** the Anthropic API key and the **Matsya** token. The distinction was stressed: Matsya does **not** retain full project context between calls the way a long Composer thread might.

#### Relevant Q&A

Chris-JHU: You need to really bear in mind that Matsya is a completely external tool which does not have access to anything in the file system that you do not feed to it directly. Cursor's Composer remembers what you've done before, but every time you make a query to Matsya, you have to make sure that it has the context that it needs to answer your question.

### Supplement: Matsya server-side sessions (post-class clarification)

Topic 3 is about **repo** access: Matsya still does **not** read your disk. Separately, the **Matsya CLI/API** supports **named sessions** (`--session` / `session=` in Python). When you reuse the **same session name** across calls, the **server** stores prior Q&A so **follow-up Matsya queries** can build on earlier turns. That is **not** the same as Cursor’s thread memory—it is **Matsya’s** logged conversation. Session traffic is **persisted** for continuity and for **research / improving the tool**; see [Data logging and consent](https://github.com/econ-ark/Matsya/blob/main/README.md#data-logging-and-consent). If a session grows very long, queries may **slow down** or **time out**; you can drop `--session` for a one-off or **start a new session name**.

**Student-facing detail (from Matsya team guidance, Apr 2026):** Please use your own **`MATSYA_ANTHROPIC_KEY`** when you can so routine calls do not rely only on the shared Econ-ARK key; starting balances on the order of **\$5–\$10** are enough to begin. Expect **roughly tens of seconds to a few minutes** per Matsya response—it is meant as a **careful DP specialist**, not a fast generic chatbot. A useful modeling pattern: ask for **dolo-plus YAML** first, then ask for the **math writeup** from that YAML, to pin down states, controls, and timing before prose.

### Topic 4: What Matsya is for

Matsya is positioned as a **helper** for modular DP / Bellman structure and **Dolo Plus** syntax, drawing on a **fixed** knowledge base rather than general web search. **Dolo Plus** builds on Dolo; Dynare remains the reference ecosystem for many RA models. Anything Matsya writes should be treated as a **draft** to review against the paper and your own judgment.

Students used **Composer** to paste or attach **notebook** material so Matsya had enough context to comment or suggest YAML-shaped output.

#### Relevant Q&A

Chris-JHU: What we're developing here is the new version of something like Dynare, but for heterogeneous agent models. One language that started doing that was a thing called Dolo, and we have added on to Dolo some important capabilities that it was missing, and that's why we have Dolo Plus now.

### Topic 5: Ballpark exercise

Students pointed Matsya at **ballpark** projects: describe the economic setup, probe unclear math, and experiment with **Dolo Plus**-style specifications. Prompts work best when **short and scoped**; large pastes slow things down and still need human editing.

#### Relevant Q&A

Chris-JHU: You will find that you can ask Matsya all sorts of questions, and it has a deep understanding of the math. So if there's anything about the paper when you read it that you had trouble understanding, ask Matsya to explain that concept or to help you understand what's going on.

### Follow-up assignment

Due before Class 11: see **[Assignments for Class 11](https://github.com/llorracc/teaching-topics/blob/main/assignments/for-class-11.md)** — Anthropic key setup (#131), **named Matsya session** workflow (#132), and ballpark / Dolo Plus draft (#130). Run roster: [`teaching-topics/run.md`](https://github.com/llorracc/teaching-topics/blob/main/run.md).

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
