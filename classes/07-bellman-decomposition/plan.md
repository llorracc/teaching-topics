# Class 07: Bellman decomposition — Plan

**Unit:** [Research Skills](../../units/research-skills/)  
**Date:** 2026-03-10 (Tue)

---

## Pre-class assignments

Students arrive having completed: [Assignments for Class 07](../../assignments/for-class-07.md)

---

## Learning objectives

- **Stage–perch architecture:** Express a multi-control (or multi-stage) Bellman problem using **arrival**, **decision**, and **continuation** perches.
- **Canonical tables:** Produce stage decompositions in the **standard table format** used in class and in the Imai–Keane templates.
- **State and shocks:** Track **state variables** (including vector notation across perches) and place **shocks between perches**, not inside a perch.
- **Economics of controls:** Distinguish choices that belong in one stage vs another (e.g. **consumption** mapping to **next-period assets** vs treating assets as a separate “choice”).
- **Discrete branches:** When the paper has **discrete alternatives** (e.g. entrepreneur vs worker), add explicit **branch** logic and **separate value expressions** per branch before the max/choice step.
- **Notebook hygiene:** Use consistent **LaTeX math** in Jupyter (**`$...$`**, avoid stray **`$$`** / bracket clutter that breaks rendering).

---

## In-class workflow

### 1. Check-in and assignment alignment (~10–15 min)

- Confirm everyone has a **qualifying paper** (multi-control or natural multi-stage structure) and a **notebook repo path** (ballpark or fork).
- Reiterate the **template sources:** SMD Sections **12–13**, **Imai–Keane** one-stage vs two-stage notebooks.

### 2. Canonical stage table — board or shared example (~20–25 min)

- Walk through a **reference decomposition** (student exemplar or instructor walkthrough).
- Emphasize **three perch columns** and **what moves** from arrival → decision → continuation.

### 3. Office-hours style — PRs and notebooks (~35–45 min)

Rotate through common issues reflected in student work:

- **Notebook in PR:** Stages breakdown notebook lives in **ballpark** (or agreed repo path) with a **clear filename** (e.g. includes “stages” / “bellman”).
- **Math formatting:** Fix **double dollars**, unnecessary brackets, and align equation blocks so the notebook is readable in GitHub and locally.
- **Tables:** Vector notation for states across perches; explicit tracking of **state updates** at each perch boundary.
- **Economic clarity:** Match the instructor’s **canonical table**; clarify text so **consumption** implies **next-period assets** rather than treating assets as a separate parallel “choice.”
- **Discrete choice:** **Occupational or other branches** — add a **branch stage**, **separate value expressions** per discrete alternative, document how the **argmax** across branches works, keep the **class table template**.

### 4. Shocks and timing (~10–15 min)

- Rule: **shocks realize between perches**, not “inside” a perch in the writeup.
- Short examples of correct vs confusing wording.

### 5. Wrap-up (~5–10 min)

- **Housekeeping:** e.g. Zoom screen sharing for next session if needed.
- **Next deliverables:** point to **[Bellman revision and next steps](https://llorracc.github.io/workspace-course-topics/assignments/bellman-revision-and-remark-next.html)** / Class 08 themes as appropriate.
- **Optional deep links:** [Part 1 summary Doc](https://docs.google.com/document/d/1wApPp-LGVXTVCXrEG-U52DGwIE5mImcntZ7Cu9-NXG8/edit), [Part 2 summary Doc](https://docs.google.com/document/d/1q-mFqxKZoJngKTqD5TA493xkA9g-uXMneX__mPLXiHw/edit) (for students who want the raw Zoom-generated notes).

---

## Materials to have open

- **SolvingMicroDSOPs** Sections **12–13** and **Imai–Keane** example notebooks.
- Student **ballpark PRs** or shared **stage notebooks** under review.
- **[Bellman stage decomposition](https://llorracc.github.io/workspace-course-topics/assignments/bellman-stage-decomposition.html)** assignment text for rubric language.
