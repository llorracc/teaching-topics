# Instructor reference — Matsya sessions under pseudonym `Petty`

> **Not a student assessment.** This file documents the instructor's own use of Matsya during Class-11 preparation. It is retained alongside the student assessments for reference — the instructor's session behavior on an in-house paper (HAFiscal) and on the course's worked example (Benhabib) is useful context for anyone interpreting the student assessments in this directory.

**Source:** Matsya server session logs (instructor-reviewed)

## Sessions observed

- `topics-example-benhabib2019` — 1 turn — 0.3 KB — single-sentence "what is a perch" test
- `topics-instructor-benhabib2019-matsya-demo` — 4 turns — 21.0 KB — Benhabib-style lifecycle model decomposition (the course worked example)
- `benhabib_et_al_2019` — 1 turn — 0.4 KB — "instructor/course workflow" session-open acknowledgement
- `HAFiscal` — 2 turns — 32.9 KB — HAFiscal household YAML (Carroll, Crawley, Frankovic, Tretvoll — the instructor's own paper)
- `HAFiscal-Latest` — 2 turns — 46.4 KB — HAFiscal focused spec parse (instructor's own paper)

## Purpose and character of each session

**Benhabib sessions.** Small-scale pedagogical demonstrations of perch decomposition on a toy lifecycle model. The 4-turn `topics-instructor-benhabib2019-matsya-demo` session is the canonical course worked example; its artifacts (bellman excerpt, SMD-polished markdown, interior-period dolo-plus YAML, prompt files, interaction log) are committed at [`workspace-course-topics/artifacts/matsya-workflow-example-benhabib-2019/`](https://github.com/llorracc/workspace-course-topics/tree/main/artifacts/matsya-workflow-example-benhabib-2019). That session was the reference that several students emulated.

**HAFiscal sessions.** Instructor-quality stress tests of Matsya's ability to handle a large, feature-rich household Bellman — normalization, splurge, Markov employment states, perpetual-youth mortality. `HAFiscal-Latest` turn 1 supplies a detailed focused spec and asks Matsya only to parse-and-confirm in perch notation; `HAFiscal` turn 1 produces a full dolo-plus YAML with explicit flags on the three awkward features (splurge, $\hat\Gamma^{1-\gamma}$ normalization, $(1-D)$ mortality discount). These sessions test Matsya's behavior under realistic research loads, not pedagogical ones.

## Observations relevant to student grading

1. **Session-memory limitation is real.** The `HAFiscal` turn 2 explicitly acknowledged "I do not have the original critique items … in my retrieved context. I am reconstructing." Students who hit similar context-retrieval failures were doing something the instructor's own sessions also hit; this is Matsya's behavior, not a student defect.

2. **Context-size ceiling is real.** The instructor's `prompt-02-stage-decomposition.txt` paste failed with a 504 timeout after 120 seconds and was recovered by `prompt-02b-short.txt`. Students who reported similar timeouts and recovered with shorter prompts were tracking the same failure mode the worked example documents.

3. **Benhabib interior-YAML known defects.** The committed worked-example YAML has `a` appearing in both `prestate` and `poststates` blocks (notebook's $a$-double-role leaking through). Students imitating the worked example may have reproduced this. It is a known issue, not a student-introduced error.

## Relationship to the ballpark repository

The Benhabib worked example was **not** submitted as a pull request against `econ-ark/ballpark`. Its artifacts live only under `workspace-course-topics/artifacts/…`. Students who looked for the worked example inside the Benhabib ballpark directory would not have found a completed formalization layer there — that is an instructor-side follow-up and is noted as such in the ballpark entry's [`AGENTS.md`](https://github.com/llorracc/ballpark/blob/master/models/We-Would-Like-In-Econ-ARK/Benhabib_et_al_2019/AGENTS.md) (once the ballpark PRs #1–#3 land).
