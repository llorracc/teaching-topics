# Class 09 — HARK and SSJ

**Date:** March 31, 2026

---

## Part 1: REMARK Progress Reviews

Individual student projects were reviewed, with feedback on structure,
reproducibility, and workflow. Common themes across all reviews:

### Recurring guidance

- **`reproduce.sh` must work continuously.** Every commit should leave the
  script in a runnable state. Don't break it and fix it later.
- **Commit frequently** with detailed, AI-generated commit messages.
- **Interact with the repository exclusively through AI or terminal**
  (Cursor, command line) — not by manually editing files in a file browser.
- **Standalone LaTeX subfiles** for every figure and table: each `.tex`
  subfile must compile independently.
- **Rename REMARK repositories** to follow the required naming scheme
  (`GitHubID-606`).
- **Rewrite abstracts and main text** to create an independent summary of
  the replicated work, not copied verbatim from the original paper.

### Project-specific issues raised

- Converting Jupyter notebooks to executable formats (use `ipython` for
  `.ipynb` or convert to `.py`) so `reproduce.sh` can run them.
- When a template repository (e.g., HA Fiscal) exists, re-clone it as a
  clean reference and make incremental changes rather than replacing entire
  sections at once.
- Setting up `.gitignore` properly to exclude upstream template content
  from repository pushes.
- Using orchestrator files in the `reproduce/` directory to coordinate
  multi-step code execution.
- Translating MATLAB and Stata code to Python to eliminate proprietary
  software dependencies.
- Organizing multi-document projects: choosing between stage-breakdown
  documents vs. Jupyter notebooks, consulting AI for file naming conventions.
- Submitting pull requests to the REMARK repository (not ballpark).

---

## Part 2: The Sequence Space Jacobian (SSJ) Method

### Overview

The lecture introduced the Sequence Space Jacobian (SSJ) method for
solving heterogeneous agent models. SSJ represents a major breakthrough
of the last 7–8 years, reducing solution time from ~15 minutes (traditional
Krusell-Smith state-space method) to ~3 seconds, making dynamic
macroeconomic simulations with heterogeneous agents practical for policy
analysis.

### Key concepts

- **Sequence space vs state space.** The state-space method (Krusell-Smith
  1998) forecasts based on state variables like aggregate capital, searching
  over forecasting rules until finding a rational expectations equilibrium.
  The SSJ method instead computes a dynamic future *path* such that if
  everyone believed it, it would actually occur — analogous to perfect
  foresight solutions in the Ramsey model.

- **Jacobian matrices as sufficient statistics.** Small changes in
  aggregate variables (interest rates, wages) produce aggregate responses
  that can be characterized linearly, even though individual optimization
  remains complex. The Jacobian matrices capture first-order responses to
  one-off changes at every future horizon.

- **Approximate aggregation.** Heterogeneous agent models can be
  represented in aggregated form, but this does *not* mean their dynamics
  match representative agent models. The wealth distribution remains
  relatively stable in response to small aggregate shocks, enabling linear
  approximation of aggregate dynamics.

- **Fake News Algorithm.** Exploits the fact that responses scale linearly
  across time horizons: the response to a shock 20 periods ahead is a
  scaled version of the response at horizon 21, 22, etc. Only the scaling
  factors need to be computed, not each horizon independently.

- **Directed Acyclic Graphs (DAGs).** Visual representations of model
  structure: exogenous productivity shock and capital feed into firms, which
  generate prices (R, W) for heterogeneous agents. Agents' saving decisions
  must clear the asset market. DAGs clarify the circular nature of general
  equilibrium and extend naturally to more complex models.

### Important questions and answers

**Q:** If we're only looking at shocks that hardly change the wealth
distribution, why use heterogeneous agent models? What can this capture
that a representative agent model cannot?

**A:** This is still a framework where the marginal propensity to consume
can be 30–50%. For fiscal policy analysis like stimulus checks, you get
very different answers. Krusell and Smith initially seemed to suggest
heterogeneous agents didn't matter much, but later realized this was wrong
and introduced the term "approximate aggregation." Just because you can
represent the aggregated model doesn't mean its dynamics are the same as a
representative agent model. Monetary policy effects are also quite
different, especially for populations without much wealth who are exposed to
interest rate changes through adjustable rate mortgages or car loans.

---

**Q:** The example about one variable (the Fed funds rate) sounds like
scenario analysis where we set priors about multiple shocks simultaneously,
and the aggregated shock is their combination based on some prior.

**A:** That's exactly right. In practice, it's complicated enough to think
about one kind of shock at a time. To the extent we don't have compelling
cases for how shocks covary, there's nothing conceptually wrong with a
whole package of shocks, but people don't tend to do that because there's
not much confidence in the paths you might choose for all variables at once.

**Follow-up Q:** In the econometrics literature, this is more like a
Bayesian perspective — forming priors based on history, not
forward-looking expectations.

**A:** Bayesian structural macro models are about people forming rational
beliefs about future aggregate dynamics and updating based on incoming news.
However, there's reason for skepticism about Bayesian macroeconomics: you
have to be sure you know the right model of how the economy works, or at
least the model all agents believe. If people believe different models,
there's no reason to give the imprimatur of science to mathematics based on
false premises. Bayesians have a blind spot for the enormous problem that
you can only know how to update if you know the correct model.

---

**Q:** When I think about heterogeneous New Keynesian models, I remember
Ricardian equivalence failing when we taxed agents. What kind of equation
should fail so that heterogeneous agent modeling makes sense?

**A:** The crucial deviation from representative agent models is
uncertainty. Individual people are subject to income shocks and can't buy
insurance policies guaranteeing a fixed income regardless of employment.
That's not the world we live in due to moral hazard, adverse selection, and
anti-slavery laws. This missing market for complete insurance, combined with
either productivity shocks or borrowing constraints, is all you need.
Borrowing constraints and uncertainty about future income are very closely
related and have similar effects.

---

**Q:** I don't fully understand why we are looking at the effect of a
*future* shock. If we are expecting some future shock, it's not a shock
anymore.

**A:** Excellent point — the literature has done a very bad job choosing
terminology. People loosely refer to predictable changes in future variables
as "shocks" even though they are not shocks. We want these calculations
because history shows the path of short-term interest rates is fairly
predictable when the Fed goes through a rate cycle. When the economy is on
one of those paths, you have a prediction of what rates will do, and you
feed that prediction into the Jacobian apparatus to see the combined effect.
There are two different kinds of experiments often conflated: true MIT
shocks where nobody had any idea beforehand, versus changes in the
anticipated future path relative to what people previously expected.
Carefully distinguishing these two is essential.

### Computational demonstration

The lecture walked through the KS-HARK-presentation notebook, which
solves the Krusell-Smith model by combining:

- HARK's `NewKeynesianConsumerType` for the micro steady state and
  heterogeneous-agent Jacobians
- The `sequence_jacobian` toolkit's `simple` blocks for the firm side
  and market clearing
- `create_model()` to assemble the DAG and compute GE impulse responses

Key results demonstrated:

- **Steady-state calibration**: finding the discount factor that makes
  agents' desired asset holdings equal the capital stock implied by the
  production economy.
- **Impulse responses**: for a temporary positive wage shock, consumption
  spikes then gradually decays. For a wage shock anticipated 20 quarters
  ahead, consumption increases immediately but peaks when the increase
  occurs. For anticipated interest rate increases, agents increase saving
  beforehand to benefit from higher returns.
- **Simulated paths**: sequences of shocks cause the economy to constantly
  fluctuate. Income moves one-for-one with productivity; capital is more
  sluggish; interest rates reflect both capital and productivity, producing
  jagged patterns.

### Limitations discussed

- The SSJ method breaks down for large shocks that significantly change the
  wealth distribution (e.g., S&P 500 falling 56% in the Great Recession or
  89% in the Great Depression).
- The field lacks good general-purpose solution methods for models with such
  large shocks, partly because we lack justification for how expectations
  change under enormous shocks.
- The assumption that people optimally adjust behavior for tiny anticipated
  aggregate changes is philosophically questionable — but this concern
  applies equally to the state-space approach. Given two methods with
  identical assumptions but one solvable in 3 seconds vs 15 minutes, the
  choice is clear.
- SSJ tools have not been widely used outside heterogeneous agent macro,
  representing an arbitrage opportunity for microeconomists studying
  industry dynamics and other markets with aggregate equilibria and
  micro-heterogeneity.

---

## Assignments

- Continue learning about the SSJ toolkit; additional assignments for the
  next class will be sent separately.
- Review the
  [SSJ journey document](journey-for-HARK-SSJ-material.md)
  and the notebooks it references.
