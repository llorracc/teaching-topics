# Sequence Space Jacobians in HARK — Journey

A guided tour through HARK's SSJ documentation, tutorials, and examples,
ordered from conceptual foundations to full general-equilibrium applications.
Each tier builds on the previous; links point to rendered
[docs.econ-ark.org](https://docs.econ-ark.org) pages where available, with
GitHub source links for notebooks.

> **Source branch:** Notebook source links below point to the
> [PR #1750](https://github.com/econ-ark/HARK/pull/1750) branch
> (`main_improve-tm-vs-mc-sim-infra-and-examples`), which contains improved
> transition-matrix infrastructure and examples not yet merged to master.

> **Original paper:**
> Auclert, A., Bardóczy, B., Rognlie, M., & Straub, L. (2021).
> "Using the Sequence-Space Jacobian to Solve and Estimate
> Heterogeneous-Agent Models." *Econometrica*, 89(5), 2375–2408.
> [doi:10.3982/ECTA17434](https://doi.org/10.3982/ECTA17434)

All notebooks in Tiers 1–5 live under `examples/SequenceSpaceJacobians/`
from the HARK repo root.

---

## Tier 1 — Conceptual Introduction: What Is SSJ and Why?

*~15 min reading. No code to run; pure exposition.*

### `SSJ_explanation.ipynb` — The Sequence Space Jacobian (SSJ) Method

[Rendered notebook](https://docs.econ-ark.org/examples/SequenceSpaceJacobians/SSJ_explanation.html) |
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/SequenceSpaceJacobians/SSJ_explanation.ipynb)

Starts with the key contrast: Krusell-Smith (1997) uses a **state-space**
approach that approximates the model solution for every conceivable
combination of aggregate states — computationally expensive. The SSJ method
instead works in **sequence space**: it computes how aggregate outcomes
respond to an expected *path* of shocks, and Jacobian matrices become a
"sufficient statistic" for the macro dynamics.

Covers:

- Advantages of SSJ (3-second HANK models vs 15+ minutes; adding shocks is
  nearly free)
- MIT shocks and when the linearization is valid (aggregate shocks small
  relative to micro heterogeneity)
- A simplified Krusell-Smith model written as equilibrium conditions on
  sequences, linearized via the implicit function theorem
- The heterogeneous-agent Jacobian **F_r** and why the "Fake News"
  algorithm makes it fast

---

## Tier 2 — Prerequisite Machinery: Transition Matrices

*~20 min reading + optional hands-on. Transition-matrix methods are the
computational backbone that SSJ builds on.*

### `Transition_Matrix_Example.ipynb` — Transition Matrix vs Monte Carlo Methods

[Rendered notebook](https://docs.econ-ark.org/examples/SequenceSpaceJacobians/Transition_Matrix_Example.html) |
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/SequenceSpaceJacobians/Transition_Matrix_Example.ipynb)

Head-to-head comparison of Monte Carlo simulation and transition-matrix
(TM) propagation for heterogeneous-agent models, using
`NewKeynesianConsumerType`. Proceeds in three parts:

1. **Steady state** — solve, compute ergodic distribution by MC and TM,
   compare accuracy and precision
2. **Harmenberg neutral measure** — the reweighting trick that collapses a
   2D (m, p) grid to 1D, dramatically improving efficiency
3. **Perfect-foresight transition path** — compute the economy's nonlinear
   response to an anticipated interest-rate deviation, the building block
   for SSJ Jacobians

Prerequisite: familiarity with HARK's `AgentType` interface (solving,
simulating).

### `docs/guides/transition_matrix_methods.md` — Transition Matrix Methods Guide (reference)

[Guide on GitHub](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/docs/guides/transition_matrix_methods.md)

Comprehensive markdown reference covering single-state models, Markov
models, and Krusell-Smith GE. Includes a dedicated **"Sequence-Space
Jacobians (SSJ)"** section with `calc_jacobian` API, the Fake News
decomposition formula, diagnostic checklists, and common pitfalls.
Best used as a desk reference alongside the notebooks.

---

## Tier 3 — Hands-On SSJ Construction

*~30 min hands-on. Run code, plot Jacobian columns, compare methods.*

### `SSJ-tutorial.ipynb` — Making HA-SSJ Matrices with HARK

[Rendered notebook](https://docs.econ-ark.org/examples/SequenceSpaceJacobians/SSJ-tutorial.html) |
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/SequenceSpaceJacobians/SSJ-tutorial.ipynb)

The main tutorial. Walks through constructing HA-SSJ matrices using
`IndShockConsumerType.make_basic_SSJ()`:

- Set up an infinite-horizon agent
- Define grid specifications for assets and consumption
- Call `make_basic_SSJ()` and inspect the resulting T x T Jacobian
- Plot columns of the Jacobian (how aggregate capital at time t responds
  to an interest-rate change at time s)
- Verify results against manual impulse-response calculations

Prerequisite: Tier 1 (what an SSJ *is*) and basic familiarity with TM
concepts from Tier 2.

### `Jacobian_Example.ipynb` — Computing HA Sequence-Space Jacobians in HARK

[Rendered notebook](https://docs.econ-ark.org/examples/SequenceSpaceJacobians/Jacobian_Example.html) |
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/SequenceSpaceJacobians/Jacobian_Example.ipynb)

By William Du. Compares two approaches to producing the same Jacobian:

1. **`NewKeynesianConsumerType.calc_jacobian()`** — the Fake News algorithm
   from Auclert et al., implemented specifically for the NK consumer
2. **`IndShockConsumerType.make_basic_SSJ()`** — HARK's general-purpose
   constructor that works with *any* `AgentType` subclass

The figures overlay both methods; the differences are negligible, validating
the general constructor against the specialized one.

---

## Tier 4 — Advanced SSJ

*~20 min hands-on. Extends SSJ to richer models.*

### `SSJ-advanced-examples.ipynb` — Advanced Examples of HA-SSJ's

[Rendered notebook](https://docs.econ-ark.org/examples/SequenceSpaceJacobians/SSJ-advanced-examples.html) |
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/SequenceSpaceJacobians/SSJ-advanced-examples.ipynb)

Demonstrates SSJ with models beyond the vanilla `IndShockConsumerType`:

- **Alternative constructors** — swap in a HANK-style income process with
  wage rates, taxes, and unemployment
- **New shock parameters** — compute Jacobians with respect to wages, tax
  rates, or labor supply (not just `Rfree`)
- **`MarkovConsumerType`** — SSJ for agents facing discrete Markov state
  switches (e.g., employment/unemployment)

Prerequisite: Tier 3 (comfortable with `make_basic_SSJ` workflow).

---

## Tier 5 — General Equilibrium Applications

*~30 min hands-on. Full GE models combining HARK micro with SSJ macro.*

### `KS-HARK-presentation.ipynb` — Solving Krusell-Smith with HARK and SSJ

[Rendered notebook](https://docs.econ-ark.org/examples/SequenceSpaceJacobians/KS-HARK-presentation.html) |
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/SequenceSpaceJacobians/KS-HARK-presentation.ipynb)

By William Du. Solves the full Krusell-Smith (1998) model by combining:

- HARK's `NewKeynesianConsumerType` for the micro steady state and HA
  Jacobians
- The [`sequence_jacobian`](https://github.com/shade-econ/sequence-jacobian)
  toolkit's `simple` blocks for the firm side and market clearing
- `create_model()` to assemble the DAG and compute GE impulse responses

Shows calibration, steady-state computation, Jacobian extraction, and
impulse-response plots — the complete pipeline from micro to macro.

### `HANKFiscal_example.ipynb` — HARK + SSJ Toolkit: Fiscal HANK

[Rendered notebook](https://docs.econ-ark.org/examples/SequenceSpaceJacobians/HANKFiscal_example.html) |
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/SequenceSpaceJacobians/HANKFiscal_example.ipynb)

By William Du. Extends the KS presentation to a HANK model with fiscal
policy (government spending, taxes, transfers), building on the
[NBER SSJ Workshop (2022)](https://github.com/shade-econ/nber-workshop-2022)
fiscal-policy tutorial. Demonstrates the full
**HARK solves micro -> SSJ toolkit computes macro** workflow with a richer
policy environment.

Includes an `estimation/` subfolder with `model.py`, `routines.py`, and
`plots.py` for empirical impulse-response matching.

---

## Tier 6 — Monte Carlo vs Transition Matrix: End-to-End Comparisons

*~30 min hands-on. Three notebooks in `examples/MonteCarlovsTransitionMatrix/`
that systematically compare MC simulation with TM methods at increasing
levels of complexity — partial equilibrium, general equilibrium, and SSJ
validation. These are PR-branch-only notebooks (no rendered docs page yet).*

### `PE_MarkovConsumerType.ipynb` — Partial-Equilibrium MC vs TM for MarkovConsumerType

[Notebook source on GitHub](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/MonteCarlovsTransitionMatrix/PE_MarkovConsumerType.ipynb)

Head-to-head comparison of Monte Carlo (`symulate()` / `hystory`) and
transition-matrix methods for `MarkovConsumerType` in partial equilibrium.
Two parts of increasing difficulty:

1. **Serial unemployment (4-state Markov, 1D grid)** — builds the joint
   (m, j) transition matrix, computes the ergodic distribution, and
   compares MC vs TM time-series and cross-sectional distributions.
   Demonstrates sparsity, grid convergence, and degenerate-income
   edge cases.
2. **Varying PermGroFac on a 2D grid (5-state Markov)** — tackles the
   harder case where permanent-income growth differs across Markov states,
   requiring a 2D (m, p) distribution grid.

### `GE_KrusellSmith.ipynb` — General-Equilibrium MC vs TM: Krusell-Smith Economy

[Notebook source on GitHub](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/MonteCarlovsTransitionMatrix/GE_KrusellSmith.ipynb)

Extends the MC-vs-TM comparison to **general equilibrium** using HARK's
`CobbDouglasMarkovEconomy` (Krusell-Smith 1998). Two parts:

1. **TM with aggregate shocks** — solves the KS economy with standard MC,
   then builds per-state transition matrices at the steady state. Compares
   ergodic distributions and forward-propagates the TM through the same
   Markov shock sequence as MC, tracking aggregate capital trajectories.
2. **TM inside the KS loop** — uses `make_history_tm()` as a deterministic
   drop-in replacement for Monte Carlo within the KS solution algorithm
   itself: zero sampling noise, identical aggregate shock sequence.

Documents a known ~22% level mismatch between MC and TM aggregate
trajectories (high correlation but systematic offset), with discussion of
potential sources.

### `Validation_and_SSJ.ipynb` — TM Validation and Sequence-Space Jacobians

[Notebook source on GitHub](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/MonteCarlovsTransitionMatrix/Validation_and_SSJ.ipynb)

Two-part notebook using `MarkovConsumerType` with a symmetric 2-state
Markov chain:

1. **Part 1** — validates TM methods (`define_distribution_grid`,
   `calc_transition_matrix`, `calc_ergodic_dist`) against hand-built code
2. **Part 2** — computes SSJ Jacobians via the Fake News Algorithm, with
   finite-difference cross-checks

Useful as a self-contained validation exercise for anyone implementing SSJ
with Markov consumers.

---

## Appendix: Deep-Dive References

### `sims-about/` Notebook Progression

[Index README on GitHub](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/sims-about/README.md)

A 9-notebook sequence that builds transition-matrix intuition from scratch,
culminating in SSJ. Notebooks 2-4 and 6-9 are on the PR branch; notebooks
1 and 5 are on master pending renumbering.

| # | Notebook | Key idea |
|---|----------|----------|
| 1 | [`markov-tm-prototype.ipynb`](https://github.com/econ-ark/HARK/blob/master/sims-about/markov-tm-prototype.ipynb) | Hand-built 1D TM, MC vs TM, ergodic distribution |
| 2 | [`02-serial-unemployment-tm.ipynb`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/sims-about/02-serial-unemployment-tm.ipynb) | Scale to more Markov states |
| 3 | [`03-serial-growth-tm-2d.ipynb`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/sims-about/03-serial-growth-tm-2d.ipynb) | 2D (m,p) grid; reveals p-truncation problem |
| 4 | [`04-serial-growth-tm-harmenberg.ipynb`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/sims-about/04-serial-growth-tm-harmenberg.ipynb) | Neutral measure collapses back to 1D |
| 5 | [`tm-consolidation.ipynb`](https://github.com/econ-ark/HARK/blob/master/sims-about/tm-consolidation.ipynb) | Validates hand-built TM against HARK production code |
| 6 | [`06-agg-shock-markov-tm.ipynb`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/sims-about/06-agg-shock-markov-tm.ipynb) | TM with endogenous aggregate state (KS-style) |
| 7 | [`07-validate-markov-tm-methods.ipynb`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/sims-about/07-validate-markov-tm-methods.ipynb) | Validates `MarkovConsumerType` TM methods |
| 8 | [`08-tm-in-ks.ipynb`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/sims-about/08-tm-in-ks.ipynb) | TM forward propagation via `make_history_tm()` |
| 9 | [`09-markov-ssj.ipynb`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/sims-about/09-markov-ssj.ipynb) | **Sequence-space Jacobians via `calc_jacobian()`** |

Supporting: [`mathematical-framework.ipynb`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/sims-about/mathematical-framework.ipynb) (unified theory; Section 13
covers SSJ).

### Guides

- [`docs/guides/transition_matrix_methods.md`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/docs/guides/transition_matrix_methods.md) — Transition Matrix Methods
- [`docs/guides/krusell_smith.md`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/docs/guides/krusell_smith.md) — Krusell-Smith in HARK (includes SSJ integration sections)

### Source Code

| Module | Key symbols |
|--------|-------------|
| [`HARK/SSJutils.py`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/HARK/SSJutils.py) | `make_basic_SSJ_matrices`, `make_fake_news_matrices`, `calc_ssj_from_fake_news_matrices` |
| [`HARK/core.py`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/HARK/core.py) | `AgentType.make_basic_SSJ`, `AgentType.calc_impulse_response_manually` |
| [`HARK/ConsumptionSaving/ConsNewKeynesianModel.py`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/HARK/ConsumptionSaving/ConsNewKeynesianModel.py) | `NewKeynesianConsumerType.calc_jacobian` |
| [`HARK/simulator.py`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/HARK/simulator.py) | `fake_news_timing` flag for TM construction |

### External Resources

- **SSJ Toolkit**: https://github.com/shade-econ/sequence-jacobian
- **NBER Workshop 2022**: https://github.com/shade-econ/nber-workshop-2022 — tutorials and lecture slides by the SSJ authors
- **Annotated Bibliography**: [`sims-about/bibliography.md`](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/sims-about/bibliography.md) — ranked survey of population-simulation methods literature
