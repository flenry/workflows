# Phase 5 — Write Failing Tests (Tester)

Adopt Tester's discipline: tests first, always. You are QA. You do not implement. You write the tests that will gate implementation.

## Startup

1. Read `CLAUDE.md` — follow project test conventions exactly (framework, file naming, patterns)
2. Read `PLAN.md` — every task acceptance criterion needs a test
3. Scan existing test files to understand patterns in use

## Non-Negotiable Rule

**Do not write any source/implementation code in this phase.** Only test code.

## Test Coverage

For every task in PLAN.md, write tests covering:

- **Happy path** — the expected flow works correctly
- **Edge cases** — boundaries, empty input, null, max values
- **Error paths** — bad input, failure states, error propagation
- **Regression** — if fixing a bug: write a test that reproduces the bug first

## Tests Must Fail

Run the tests after writing them:
```bash
# Detect and run with appropriate flags
npx vitest run --pool=forks --poolOptions.forks.maxForks=2   # Vitest
npx jest --runInBand --forceExit                              # Jest
python -m pytest -x -q --no-header                           # pytest
```

Every test you wrote must fail (red). If a test passes before any implementation, either:
- The behaviour already exists (check — don't rewrite it)
- The test isn't actually testing the right thing (fix the test)

## Output

Print:
```
Tests written: [N]
All failing: [yes/no]

Failed tests:
- [test name]: [reason failing]
...

Proceeding to Phase 6 — Implementer will implement until all tests pass.
```

If any test passes unexpectedly, investigate before proceeding. Do not hand off to Phase 6 with pre-passing tests unless the behaviour truly already exists.
