---
name: build
description: Full TDD build workflow — plan, tests, implement with self-evaluation loop, docs. Use when building a new feature or project from a spec. Produces tested, documented, production-ready code.
---

# Build

Full TDD workflow: plan → architecture review → strategy → synthesise → tests → implement (eval loop) → verify → docs.

Adapted from the role-based workflow's `build` chain. Each phase adopts a specialist role with its own discipline.

---

## Commands

| Command | What It Does |
|---------|-------------|
| `/build` | Full workflow from planning through docs |
| `/build plan` | Phase 1-4 only — produce PLAN.md, don't implement |
| `/build implement` | Phases 5-7 — assumes PLAN.md exists |
| `/build fast` | Skip optional phases (architecture review, docs) |

---

## Execution

Read and execute phases in order. Do not skip phases unless using a subcommand.

1. `phases/1-plan.md` — Planner: deep planning → PLAN.md
2. `phases/2-architecture.md` — Researcher: feasibility review *(optional in fast mode)*
3. `phases/3-strategy.md` — Law: trade-off and risk analysis *(optional in fast mode)*
4. `phases/4-synthesise.md` — Planner: incorporate feedback → final PLAN.md + task list
5. `phases/5-tests.md` — Tester: write all failing tests first
6. `phases/6-implement.md` — Implementer + Evaluator loop: implement until score ≥ 8
7. `phases/7-verify.md` — Tester: full suite verification
8. `phases/8-docs.md` — Documenter: update CLAUDE.md, README.md *(optional in fast mode)*

---

## Output Files

| File | Phase | Contents |
|------|-------|----------|
| `PLAN.md` | 1, 4 | Task breakdown, approach, acceptance criteria |
| `progress/build-review.md` | 2-3 | Architecture + strategy findings |
| `progress/eval-N.md` | 6 | Evaluator score per iteration |
| `progress/build-summary.md` | 8 | What was built, decisions made |

---

## Eval Loop Parameters

- **Max iterations**: 5
- **Pass threshold**: 8/10
- **Scoring rubric**: Correctness ×0.35 + Completeness ×0.30 + Code Quality ×0.20 + Design ×0.15
- **Hard caps**: Failing tests → max 4/10. App won't start → max 2/10. Stubs present → cannot score 8+.

---

## Notes

- Never start Phase 6 (implement) without confirmed failing tests from Phase 5
- If the spec is unclear, clarify before Phase 1 — one question, then proceed
- Phases 2 and 3 are optional in fast mode but strongly recommended for production work
