# Phase 2 — Implement with Eval Loop (Implementer + Evaluator)

Same loop structure as `/build` Phase 6, but max 3 iterations.

---

## Loop Parameters

- **Max iterations**: 3
- **Pass threshold**: 8/10
- **Rubric**: Correctness ×0.35 + Completeness ×0.30 + Code Quality ×0.20 + Design ×0.15

---

## Implementer — Implementation

Adopt Implementer's discipline:

1. Read `CLAUDE.md` and `PLAN.md`
2. Write tests for the change first (if not already present)
3. Implement each task, run tests after each
4. Do not touch code outside the blast radius defined in PLAN.md

**CR-specific rule**: Be surgical. A CR is not an opportunity to refactor adjacent code. If you see something that needs fixing outside scope, note it in `progress/cr-notes.md` and leave it.

---

## Evaluator — Scoring

Same rubric and hard caps as `/build` Phase 6.

Write score to `progress/cr-eval-[N].md` using same format.

**CR-specific check**:
- [ ] Change stays within declared blast radius (no scope creep)
- [ ] Rollback plan is still valid given the implementation

---

## Loop Exit

Same as `/build` Phase 6. If max iterations reached without passing, report and ask user.

On pass: `Implementation complete. Score: [X]/10. Proceeding to PR phase.`
