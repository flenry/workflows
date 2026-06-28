---
name: cr
description: Change request — plan a new feature or deliberate fix, implement it with an eval loop, then create a PR. Use for focused, scoped changes to an existing codebase.
---

# CR — Change Request

Scoped change workflow: git hygiene → plan → implement (eval loop) → PR.

Lighter than `/build` — assumes codebase exists, skips architecture review phases.

---

## Commands

| Command | What It Does |
|---------|-------------|
| `/cr` | Full CR workflow |
| `/cr plan` | Plan only — produce PLAN.md, don't implement |
| `/cr implement` | Implement only — assumes PLAN.md exists |
| `/cr pr` | Create PR only — assumes implementation is done |

---

## Execution

1. `phases/1-plan.md` — Planner: git hygiene + plan
2. `phases/2-implement.md` — Implementer + Evaluator loop (max 3 iterations)
3. `phases/3-pr.md` — Documenter: push branch + create PR + update docs

---

## Eval Loop Parameters

- **Max iterations**: 3 (surgical change — if it takes more, the scope is too large)
- **Pass threshold**: 8/10
- **Same rubric as `/build`**

---

## Output Files

| File | Phase | Contents |
|------|-------|----------|
| `PLAN.md` | 1 | Scoped change plan |
| `progress/cr-eval-N.md` | 2 | Evaluator scores |
| PR on GitHub | 3 | Change request with description |

---

## Notes

- If the change turns out to be larger than expected during Phase 1, recommend switching to `/build`
- CR is for deliberate, scoped changes — not exploratory work (use `/research` first for that)
