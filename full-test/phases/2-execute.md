# Phase 2 — Execute Tests (Tester)

Adopt Tester's discipline: exhaustive, unbiased execution. You are not trying to prove the app works — you are trying to find where it doesn't.

## Startup

1. Read `progress/TEST-PLAN.md` — your execution checklist
2. Read `CLAUDE.md` — how to start the app, test commands, known issues

## Execution Order

### Step 1 — Environment Check

```bash
# Confirm env vars
cat .env.sample | grep -v "^#" | awk -F= '{print $1}'
# Check each is set in .env

# Confirm app starts
[app start command from CLAUDE.md]
```

If app fails to start: mark all tests as BLOCKED and skip to Phase 3.

### Step 2 — Existing Test Suite

Run the full existing test suite:
```bash
npx vitest run --pool=forks --poolOptions.forks.maxForks=2   # Vitest
npx jest --runInBand --forceExit                              # Jest
python -m pytest -x -q --no-header                           # pytest
```

Record: total, passed, failed, skipped.

### Step 3 — PRD Test Cases

Execute each test case in `TEST-PLAN.md` in order:
- Run the steps exactly as written
- Record the actual outcome (not what you expect)
- Note any deviation from expected outcome as a finding
- For frontend: use `agent-browser-axi` or `bowser` if available

### Step 4 — Exploratory

After running the plan, spend 5 minutes on exploratory testing:
- Try inputs the PRD didn't mention
- Try rapid sequences of actions
- Check error messages for quality and accuracy

## Output: progress/FINDINGS.md

```markdown
# Test Findings

*Executed: [date]*

## Environment
- App started: [yes/no]
- Env vars: [complete/missing: list]

## Existing Test Suite
- Total: [N] | Passed: [N] | Failed: [N] | Skipped: [N]
- Failing tests: [list]

## PRD Test Cases

### TC-001: [Name]
- Status: [PASS / FAIL / BLOCKED]
- Actual outcome: [what happened]
- Finding: [if FAIL/BLOCKED — what's wrong]

...

## Exploratory Findings
[Anything discovered outside the plan]

## Summary
- Total TC: [N] | Pass: [N] | Fail: [N] | Blocked: [N]
- Critical failures: [list]
- Blocking issues: [yes/no]
```
