# Phase 7 — Verify (Tester)

Adopt Tester's discipline: final QA gate. Run the full suite. Trust nothing.

## Startup

1. Read `CLAUDE.md` — test conventions
2. Read `PLAN.md` — acceptance criteria to verify against

## Process

1. Run the full test suite:
   ```bash
   npx vitest run --pool=forks --poolOptions.forks.maxForks=2   # Vitest
   npx jest --runInBand --forceExit                              # Jest
   python -m pytest -x -q --no-header                           # pytest
   ```

2. For each task in PLAN.md, confirm its acceptance criteria are satisfied

3. Check for regressions — compare against any existing tests that were passing before Phase 5

## Pass Criteria

- All tests written in Phase 5 pass
- No regressions in pre-existing tests
- Every task acceptance criterion is satisfied

## If Tests Fail

Do not proceed to Phase 8. Return to Phase 6 with a clear summary of what's failing.

## Output

Print:
```
Verification complete.

Tests: [N passed] / [N total]
Regressions: [none / list]
Acceptance criteria: [N/N satisfied]

[VERIFIED — proceeding to Phase 8]
  or
[FAILED — returning to Phase 6: [list failing tests]]
```
