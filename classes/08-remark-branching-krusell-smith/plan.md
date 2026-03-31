# Class 08: REMARK, branching & Krusell–Smith — Plan

**Unit:** [Research Skills](../../units/research-skills/) / [Contribution](../../units/contribution/)  
**Date:** 2026-03-24 (Tue)

---

## Pre-class assignments

Students arrive having completed: [Assignments for Class 08](../../assignments/for-class-08.md)

---

## Learning objectives

- **REMARK readiness:** `reproduce.sh` from a shell, GitHub-ID-based naming, telling **source** (e.g. LaTeX) from **generated** outputs (e.g. `abstract.txt`).
- **Submission semantics:** Ballpark vs REMARK; a **PR** as a request for a maintainer **fork** while the student **retains** the canonical repo.
- **Branching in micro-DSOPs:** Recombinant (fan-out / fan-in) vs persistent branching; stochastic / max / logit modes; **discounting as its own stage** (avoid double discounting).
- **Krusell–Smith:** Idiosyncratic and aggregate risk, forecasting aggregates, fixed point in belief coefficients, HARK workflow sketch.
- **Wealth inequality:** Lorenz curves vs data; transitory vs permanent shocks; heterogeneous discount factors (e.g. dynasty draws).

---

## In-class workflow

### 1. Project check-in — LaTeX, standalone floats, `reproduce.sh` (~25–35 min)

- Short updates: substance, LaTeX/figures/tables, automation.
- **Standalone-float check:** Each figure and table should compile from its own `.tex` under the template `figures/` (or equivalent).
- **REMARK check:** From repo root in a **terminal**, run `./reproduce.sh`—not only via IDE shortcuts.
- **Anticipated issues:** Missing per-float `.tex`; “reproduce works” without shell invocation. Steer using the course template / HAFiscal-style layout as the pattern.

### 2. REMARK vs ballpark; PRs; generated artifacts (~20–25 min)

- Contrast **ballpark** (pre-replication / exploratory) with **REMARK** (replication-ready, author-owned).
- State: PR to REMARK = maintainers **fork** your repo at a publication-ready point; you keep ownership.
- Walk a **minimum checklist:** naming, `reproduce.sh`, original figure/table/equation, bibliography, docs, AI critique if assigned.
- **Discussion prompts:** Repos that still look like full HAFiscal scaffolding; confusion when editing generated files (e.g. abstract) instead of LaTeX source.
- **Next time:** Mention that submissions will be reviewed (e.g. with **AI**) against assignment + REMARK expectations.

### 3. Branching in dynamic programming (~20–25 min)

- Teach **recombinant** branching (e.g. employment shock) where branches **recombine** after decisions.
- Contrast **persistent** branching (e.g. retirement) with parallel value tracks.
- Modes: **stochastic**, **max**, **logit**; note custom modes where useful.
- Students with branching in their papers: plan revisions to Bellman/stage writeups using the new notes.
- **Socratic check:** Why keep **discounting** out of “consumption, no shocks”? (Surface **double discounting** if someone folded it in—e.g. young entrepreneur example.)

### 4. Krusell–Smith — environment, beliefs, numerics (~25–30 min)

- Setup: infinite horizon, good/bad **aggregate** states, idiosyncratic risk (unemployment + employed AR(1)).
- Motivate **curse of dimensionality** for full distribution dynamics.
- **Krusell–Smith:** Forecast **log aggregate capital** with simple linear rules by aggregate state; iterate on coefficients until simulation matches beliefs (high \(R^2\) in standard calibrations).
- **HARK:** Calibration → types → production / aggregation → equilibrium search.
- **Numerics:** Tolerance depends on **purpose** (fast class notebook vs publication); do not claim precision that is not **robust** across seeds/runs.

### 5. Wealth inequality — model vs data (~15–20 min)

- **Lorenz curves:** 45° line, model, **SCF** (or comparable data).
- Transitory-only risk → often too little top wealth; **permanent shocks** widen dispersion; tail may still be thin.
- **Heterogeneous \(\beta\)** / dynasty draws: impatient dynasties decumulate; patient dynasties build the right tail.
- **Closing question:** When does your project require the wealth distribution to match the data?

### 6. Wrap-up (~5–10 min)

- Confirm **next-class** deliverables: working `reproduce.sh`, rename from template names, originals (figure, table, equation), standalone TeX, REMARK-oriented PR, branching revisions where relevant, prep for compliance review; optional short slide talk later.
- **Materials:** Revised **Solving micro-DSOPs** notes (branching); REMARK / econ-ark docs; HARK Krusell–Smith notebook or REMARK; template with standalone floats + `reproduce.sh`; optional live **Cursor** / LaTeX demo.
