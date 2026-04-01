# Sequence Space Jacobians in HARK — Journey

A guided path through HARK's SSJ documentation, tutorials, and examples.
Each tier builds on the previous, progressing from conceptual understanding
to hands-on Jacobian computation to full general-equilibrium applications.

All notebooks in Tiers 1–5 live under `examples/SequenceSpaceJacobians/`
from the HARK repo root unless otherwise noted.

> **Source branch:** Notebook source links below point to the
> [PR #1750](https://github.com/econ-ark/HARK/pull/1750) branch
> (`main_improve-tm-vs-mc-sim-infra-and-examples`), which contains improved
> transition-matrix infrastructure and examples not yet merged to master.

> **Original paper:**
> Auclert, A., Bardóczy, B., Rognlie, M., & Straub, L. (2021).
> "Using the Sequence-Space Jacobian to Solve and Estimate
> Heterogeneous-Agent Models." *Econometrica*, 89(5), 2375–2408.
> [doi:10.3982/ECTA17434](https://doi.org/10.3982/ECTA17434)

---

## Tier 1 — What Is SSJ and Why Should I Care?

*~15 min reading. No code to run; pure exposition.*

### `SSJ_explanation.ipynb` — The Sequence Space Jacobian Method

[Rendered notebook](https://docs.econ-ark.org/examples/SequenceSpaceJacobians/SSJ_explanation.html) |
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/SequenceSpaceJacobians/SSJ_explanation.ipynb)

The essential contrast: Krusell-Smith (1998) uses a **state-space**
approach — approximate the model solution for every conceivable
combination of aggregate states, which is computationally expensive.
The SSJ method works in **sequence space**: compute how aggregate outcomes
respond to an expected *path* of shocks, and Jacobian matrices become a
"sufficient statistic" for the macro dynamics.

Covers:

- Advantages of SSJ (3-second HANK models vs 15+ minutes)
- MIT shocks and when linearization is valid
- A simplified Krusell-Smith model written as equilibrium conditions on
  sequences, solved by linearization via the implicit function theorem
- The heterogeneous-agent Jacobian **F_r** and the Fake News algorithm
- Directed acyclic graphs (DAGs) for model structure
- Points to `KS-HARK-presentation.ipynb` (Tier 3) for the implementation

---

## Tier 2 — Compute Your First Jacobian

*~30 min hands-on. The "Hello World" of SSJ in HARK.*

### `SSJ-tutorial.ipynb` — Making HA-SSJ Matrices with HARK

[Rendered notebook](https://docs.econ-ark.org/examples/SequenceSpaceJacobians/SSJ-tutorial.html) |
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/SequenceSpaceJacobians/SSJ-tutorial.ipynb)

**This is the recommended starting point for hands-on work.** Uses the
general-purpose `make_basic_SSJ()` method on `IndShockConsumerType` — the
API that works with *any* `AgentType` subclass.

What you will learn:

- Set up an infinite-horizon agent and call `make_basic_SSJ()`
- Discover what model variables exist (via model files and
  `describe_constructors()`)
- Learn which parameters can be shock variables and why
- Inspect the resulting T x T Jacobian matrix
- Plot Jacobian columns (how aggregate capital at time t responds to an
  interest-rate change at time s)
- Understand permanent income normalization in the SSJ context
- Look under the hood: `initialize_sym()`, `make_transition_matrices()`,
  the `_simulator` attribute
- **Verify correctness**: `calc_impulse_response_manually()` computes
  impulse responses by brute force for a single horizon s, matching the
  corresponding column of the SSJ matrix

After this notebook you can compute a Jacobian for any HARK model and
have tools to verify the result.

---

## Tier 3 — From Partial Equilibrium to General Equilibrium

*~30 min hands-on. Full GE model combining HARK micro with the SSJ toolkit.*

Now that you know what a Jacobian *is* and how to compute one, this tier
shows the complete pipeline: calibrate a production economy, find the
steady state, extract Jacobians, plug into the
[`sequence_jacobian`](https://github.com/shade-econ/sequence-jacobian)
toolkit's DAG, and compute GE impulse responses and simulations.

### `KS-HARK-presentation.ipynb` — Solving Krusell-Smith with HARK and SSJ

[Rendered notebook](https://docs.econ-ark.org/examples/SequenceSpaceJacobians/KS-HARK-presentation.html) |
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/SequenceSpaceJacobians/KS-HARK-presentation.ipynb)

By William Du. Implements the model derived in `SSJ_explanation.ipynb`:

- **Calibration**: Cobb-Douglas production economy with steady-state
  targets for output, interest rate, and labor
- **HARK agent setup**: `NewKeynesianConsumerType` parameterized from
  `init_newkeynesian` defaults, overriding only the KS-specific values
- **Steady state**: calibrate the discount factor so desired asset
  holdings clear the capital market
- **Jacobians**: `calc_jacobian()` computes consumption and asset
  Jacobians with respect to wages and interest rates
- **GE impulse responses**: `sequence_jacobian`'s `simple` blocks for the
  firm side + `create_model()` to assemble the DAG
- **Simulation**: draw aggregate shocks, combine with Jacobians to
  produce simulated paths of output, capital, interest rates

Note: this notebook uses the older `calc_jacobian()` method specific to
`NewKeynesianConsumerType`. The general-purpose `make_basic_SSJ()` from
Tier 2 produces equivalent results (see Tier 6 for cross-validation).

---

## Tier 4 — Richer Partial-Equilibrium Models

*~20 min hands-on. Extends SSJ to models beyond vanilla IndShockConsumerType.*

### `SSJ-advanced-examples.ipynb` — Advanced Examples of HA-SSJ's

[Rendered notebook](https://docs.econ-ark.org/examples/SequenceSpaceJacobians/SSJ-advanced-examples.html) |
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/SequenceSpaceJacobians/SSJ-advanced-examples.ipynb)

Demonstrates the generality of `make_basic_SSJ()` with progressively
richer models:

- **Alternative constructors** — swap in a HANK-style income process
  (wages, taxes, unemployment) while keeping the same SSJ API
- **Labor on the intensive margin** — `LaborIntMargConsumerType`: agents
  choose hours, adding a labor-supply Jacobian
- **Markov unemployment dynamics** — `MarkovConsumerType` with persistent
  employment/unemployment transitions and state-dependent consumption
  functions
- **Portfolio choice** — risky vs safe assets; SSJ with respect to the
  equity premium

Each example follows the same pattern: set up the model, call
`make_basic_SSJ()`, plot and interpret.

---

## Tier 5 — Full HANK Application

*~30 min hands-on. The capstone: fiscal HANK with estimation.*

### `HANKFiscal_example.ipynb` — HARK + SSJ Toolkit: Fiscal HANK

[Rendered notebook](https://docs.econ-ark.org/examples/SequenceSpaceJacobians/HANKFiscal_example.html) |
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/SequenceSpaceJacobians/HANKFiscal_example.ipynb)

By William Du. Extends the KS model to a HANK economy with fiscal policy
(government spending, taxes, transfers), building on the
[NBER SSJ Workshop (2022)](https://github.com/shade-econ/nber-workshop-2022)
fiscal-policy tutorial. Demonstrates the full
**HARK solves micro -> SSJ toolkit computes macro** workflow with a richer
policy environment.

Includes an `estimation/` subfolder with `model.py`, `routines.py`, and
`plots.py` for empirical impulse-response matching.

---

## Tier 6 — Cross-Validation and MC-vs-TM Deep Dives

*Optional. For students who want to verify results or understand the
transition-matrix machinery underneath SSJ.*

### `Jacobian_Example.ipynb` — Cross-Validating Old and New SSJ Methods

[Rendered notebook](https://docs.econ-ark.org/examples/SequenceSpaceJacobians/Jacobian_Example.html) |
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/SequenceSpaceJacobians/Jacobian_Example.ipynb)

By William Du. Compares two approaches to the same Jacobian:

1. `NewKeynesianConsumerType.calc_jacobian()` — the Fake News algorithm
   implemented specifically for the NK consumer (used in Tier 3)
2. `IndShockConsumerType.make_basic_SSJ()` — the general constructor
   (used in Tier 2)

The figures overlay both; differences are negligible, confirming that the
general constructor matches the specialized one.

### `Transition_Matrix_Example.ipynb` — Transition Matrix vs Monte Carlo Methods

[Rendered notebook](https://docs.econ-ark.org/examples/SequenceSpaceJacobians/Transition_Matrix_Example.html) |
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/SequenceSpaceJacobians/Transition_Matrix_Example.ipynb)

Head-to-head comparison of Monte Carlo simulation and transition-matrix
(TM) propagation for `NewKeynesianConsumerType`. TM methods are the
computational backbone that SSJ builds on internally. Three parts:

1. **Steady state** — solve, compute ergodic distribution by MC and TM
2. **Harmenberg neutral measure** — the reweighting trick that collapses
   a 2D (m, p) grid to 1D
3. **Perfect-foresight transition path** — the building block for SSJ
   Jacobians

### `docs/guides/transition_matrix_methods.md` — TM Methods Guide (reference)

[Guide on GitHub](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/docs/guides/transition_matrix_methods.md)

Comprehensive markdown reference covering single-state models, Markov
models, and Krusell-Smith GE. Includes a **"Sequence-Space Jacobians"**
section with `calc_jacobian` API, the Fake News decomposition formula,
diagnostic checklists, and common pitfalls.

### Three `examples/MonteCarlovsTransitionMatrix/` notebooks

These systematically compare MC simulation with TM methods at increasing
complexity. All are PR-branch-only (no rendered docs page yet).

**`PE_MarkovConsumerType.ipynb`** — Partial-equilibrium MC vs TM for
`MarkovConsumerType`: 4-state Markov with 1D grid, then 5-state with
varying PermGroFac on a 2D grid.
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/MonteCarlovsTransitionMatrix/PE_MarkovConsumerType.ipynb)

**`GE_KrusellSmith.ipynb`** — General-equilibrium MC vs TM in the
Krusell-Smith economy. Uses `make_history_tm()` as a deterministic
drop-in for MC inside the KS solution loop.
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/MonteCarlovsTransitionMatrix/GE_KrusellSmith.ipynb)

**`Validation_and_SSJ.ipynb`** — TM validation against hand-built code,
then SSJ Jacobians via the Fake News Algorithm with finite-difference
cross-checks.
[Notebook source](https://github.com/econ-ark/HARK/blob/main_improve-tm-vs-mc-sim-infra-and-examples/examples/MonteCarlovsTransitionMatrix/Validation_and_SSJ.ipynb)

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
