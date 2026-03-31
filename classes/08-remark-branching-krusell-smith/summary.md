# Class 08: REMARK standards, branching, and Krusell–Smith — Summary

**Date:** 2026-03-24  
**Meeting:** 180.606 Topics — Part 2 (afternoon)  
**Source:** [Full meeting summary (Google Doc)](https://docs.google.com/document/d/1fn6bWCjnzw5xzXBBCiGipmrWwC6f5cY-3IsFYCkutac/edit)

---

## Overview

Class focused on student progress on computational economics papers (LaTeX, HARK, reproducibility), **REMARK** submission expectations, an expanded treatment of **branching** in dynamic programming (micro-DSOPs), and a substantive segment on the **Krusell–Smith** heterogeneous-agent model and **wealth inequality**.

---

## Key concepts

- **REMARK standards** — `reproduce.sh`, naming, documentation, and what “submission” means (fork request, student retains ownership).
- **Ballpark vs REMARK** — clarified: work that replicates belongs in the REMARK workflow; PR requests a maintainer fork of the student-owned repo.
- **Modular micro-DSOP framework** — portable stages for dynamic stochastic optimization problems.
- **Branching**
  - *Fan-out / fan-in (“recombinant”)* — temporary dispersion (e.g. employment state) with no lasting segmentation of value functions.
  - *Persistent (“garden of forking paths”)* — choices with irreversible or long-lived consequences (e.g. retirement).
  - **Modes** — stochastic, max, or logit (and room for custom modes).
- **Krusell–Smith** — aggregate shocks, idiosyncratic risk, forecasting aggregate capital with simple linear rules, iteration to fixed beliefs.
- **Wealth inequality** — limits of transitory shocks; role of permanent shocks and heterogeneous discount factors (dynasty draws).

---

## Questions raised (themes)

- What counts as adequate **numerical tolerance** for class demos vs publication?
- How should **branching** be represented when discrete choices have persistent effects?
- What does it take for a model’s wealth distribution to be **credible** relative to data?

---

## Takeaways

- **`reproduce.sh` is non-negotiable** for REMARK-style work: executable from project root and reproduces artifacts.
- **Standalone `.tex` for figures and tables** — edit and compile pieces without full-document rebuilds.
- **Rename repos/projects** from template names (e.g. HAFiscal) to **GitHub-ID–based** naming conventions.
- **Discounting as its own stage** — avoid embedding discounting inside stages in ways that imply **double discounting** (called out in entrepreneur example).
- **Abstract and generated files** — e.g. `abstract.txt` may be **output** of the reproduce pipeline, not the editable source; edit the true source in the paper.
- **Krusell–Smith insight** — agents need good forecasts of aggregates, not the full cross-section; simple linear rules in logs can achieve very high fit.
- **Benchmark HA models** often **understate top wealth** without richer income persistence or preference heterogeneity.

---

## 1. Student project progress and technical implementation

Students reported progress on diverse papers (monetary policy and EMs, fiscal multipliers / regional variation, event-study timing around central bank announcements, etc.). Emphasis on:

- Standalone LaTeX for each figure/table under the template’s `figures` (or analogous) structure.
- Verifying **`reproduce.sh`** from a **shell** (not only “it works in the IDE”).

### Q&A (excerpt)

- **Chris-JHU:** Can you view each table or figure as a standalone document?  
- **Carlos:** I’m not seeing a `.tex` for the figures.  
- **Chris-JHU:** Use the provided paper’s `.tex` as a pattern; build **one standalone file per figure** so you can iterate without recompiling the whole paper.  
- **Chris-JHU:** Is `reproduce.sh` working? Launch a terminal — REMARK means a **Unix** `reproduce.sh` in the root that reproduces the project.

---

## 2. REMARK repository standards and submission process

- Distinction between **ballpark** (aspirational / pre-replication) and **REMARK** (actual replication) was discussed; instructor adjusted guidance toward **REMARK** as the home for student-owned replication repos, with PR as a **request to fork** for publication.
- Expectations: naming, working reproduce script, original figure/table/equation, bibliography, AI-assisted critique where assigned, alignment with REMARK docs.
- **Next class:** plan to use **AI** to check submissions against assignment instructions and minimum REMARK standards.

### Q&A (excerpt)

- **Nathan:** HA Fiscal heritage vs ballpark PR — folder layout differs from a minimal ballpark.  
- **Chris-JHU:** Submit toward **REMARK**; design is author-owned; maintainers fork when ready.  
- **Siying:** PDF abstract doesn’t match what I edited.  
- **Chris-JHU:** **`abstract.txt` is generated** — find where the abstract lives in the LaTeX source.

---

## 3. Branching in dynamic programming models

Updated lecture notes on solving micro-DSOPs now include **branching**:

- **Recombinant** vs **persistent** paths, with examples (employment shock vs retirement).
- **Modes:** stochastic, max, logit.
- Students with branching in their ballpark papers: **revise Bellman/stage writeups** using the new notation.

### Q&A (excerpt)

- **Chris-JHU:** Why must discounting be its own stage?  
- **Ruby:** I merged discounting into “cons no shocks.”  
- **Chris-JHU:** That risks **double discounting** (e.g. young entrepreneur) — keep discounting in a proper separate stage.

---

## 4. Krusell–Smith heterogeneous-agent model

- Infinite horizon, idiosyncratic uninsurable risk, **good/bad aggregate states**, unemployment and AR(1) components for employed workers.
- **Fixed point in beliefs:** coefficients on log aggregate capital in forecasting rules; iterate until simulated aggregates match predictions (very high \(R^2\) in standard calibration).
- **HARK** workflow: calibration, agent types, production, equilibrium search.

### Q&A (excerpt)

- **Irem:** Tolerances smaller than 0.1% elsewhere — is 0.01 okay here?  
- **Chris-JHU:** Depends on purpose — fast classroom notebook vs journal submission; don’t claim **digits you don’t robustly obtain** across seeds/runs.

---

## 5. Wealth inequality in heterogeneous-agent models

- **Lorenz curves** — benchmark KS vs data (e.g. SCF): benchmark can look “too equal.”
- **Transitory vs permanent income** — permanent shocks widen targets and dispersion; still may miss the tail.
- **Heterogeneous discount rates** (e.g. dynasty draws across generations) — impatient dynasties decumulate; patient ones build the right tail.

---

## Action items (before next class)

- [ ] Working **`reproduce.sh`** that reproduces the paper from a clean shell.
- [ ] **Rename** project from template names to **GitHub ID + course code** convention.
- [ ] At least **one original** figure, table, and equation.
- [ ] **Standalone LaTeX** for figures and tables following the template layout.
- [ ] **REMARK-oriented PR** process per repo documentation; use AI to gap-check vs REMARK requirements.
- [ ] If your paper has **branching**, update the Bellman/stage decomposition using the **new micro-DSOP branching notes**.
- [ ] Prepare for **AI review** of compliance with assignment + REMARK minimum standards.
- [ ] Optional: think about a **~15 minute slide deck** on your project for a possible future session.

---

## Supplemental resources

- Revised **Solving micro-DSOPs** notes (with branching), course repo.
- **HARK** docs (e.g. `AgShockMarkovConsumerType` and related consumer types).
- **Krusell–Smith** implementation / REMARK materials on **econ-ark.org**.
- **REMARK** repository documentation (including AI-assisted compliance checks).
- **HA Fiscal** (or course) template illustrating standalone figure/table `.tex` files.
- **Cursor** / other assistants for LaTeX and Python debugging.
