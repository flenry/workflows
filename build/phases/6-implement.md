# Phase 6 — Implement with Eval Loop (Implementer + Evaluator)

Alternates between Implementer (implementation) and Evaluator (scoring) until score ≥ 8/10 or 5 iterations are reached.

---

## Loop Parameters

- **Max iterations**: 5
- **Pass threshold**: 8/10
- **Scoring rubric**: Correctness ×0.35 + Completeness ×0.30 + Code Quality ×0.20 + Design ×0.15

---

## Iteration Structure

Each iteration:
1. **Implementer** — implement (or fix critique from previous iteration)
2. **Evaluator** — score, produce critique
3. Check: if score ≥ 8 or iteration = 5 → exit loop

---

## Implementer — Implementation

Adopt Implementer's discipline: implement exactly what the spec says. No scope creep. No unsolicited improvements.

**Startup (first iteration)**:
1. Read `CLAUDE.md` — conventions are law
2. Read `PLAN.md` — this is your spec
3. Confirm tests from Phase 5 are present and failing

**Startup (subsequent iterations)**:
1. Read `progress/eval-[N].md` — the Evaluator's critique
2. Address every critical and major finding before re-submitting

**Rules**:
- One task at a time. Run tests after each.
- Follow the exact patterns shown in existing code. Do not introduce new patterns without a reason.
- If a task is ambiguous, read CLAUDE.md and existing code — the answer is there.
- Do not refactor adjacent code unless it directly blocks the task.

**After implementing each task**:
```bash
# Run tests (use low-memory flags)
npx vitest run --pool=forks --poolOptions.forks.maxForks=2
```

Report: tasks completed, tests passing/failing, blockers.

---

## Evaluator — Scoring

Adopt the Evaluator's discipline: ruthlessly honest. Never generous. A passing score means this is shippable.

**Startup**:
1. Read `CLAUDE.md` — review against project conventions
2. Read `PLAN.md` — evaluate against original intent, not current implementation
3. Run the full test suite

**Scoring Rubric**:

| Dimension | Weight | What it measures |
|-----------|--------|-----------------|
| Correctness | 0.35 | Tests pass, behaviour matches spec, no logic errors |
| Completeness | 0.30 | All tasks done, no stubs, no TODOs blocking functionality |
| Code Quality | 0.20 | Follows conventions, readable, no obvious smells |
| Design | 0.15 | Fits architecture, no over-engineering, interfaces are clean |

**Hard Caps** (override rubric score):
- Any failing test → max 4/10
- App/module won't start → max 2/10
- Stubs or incomplete tasks present → cannot score 8+

**Output format** (write to `progress/eval-[N].md`):

```markdown
# Evaluation — Iteration N

## SCORE: [X]/10

## Dimension Scores
- Correctness: [X]/10 × 0.35 = [weighted]
- Completeness: [X]/10 × 0.30 = [weighted]
- Code Quality: [X]/10 × 0.20 = [weighted]
- Design: [X]/10 × 0.15 = [weighted]

## Critical (must fix before next iteration)
- [finding: file:line — issue — fix direction]

## Major (should fix)
- ...

## Minor / Nit
- ...

## Test Results
[passed / failed / skipped counts]

## Verdict
[PASS — proceeding to Phase 7 / ITERATE — N iterations remaining]
```

---

## Loop Exit

**Score ≥ 8**: Print `Implementation complete. Score: [X]/10. Proceeding to Phase 7.`

**Max iterations reached (score < 8)**: Print:
```
Max iterations reached. Final score: [X]/10.
Remaining issues:
[list critical and major findings from final eval]

Recommend: review findings manually before proceeding to Phase 7.
```
Then ask the user: proceed to Phase 7, or fix issues first?
