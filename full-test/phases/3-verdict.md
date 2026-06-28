# Phase 3 — Verdict (Planner)

Adopt Planner's discipline: clear-eyed synthesis. Produce an honest verdict the team can act on.

## Startup

1. Read `PRD.md` — the original requirements
2. Read `progress/FINDINGS.md` — the test results

## Analysis

For each finding:
- Map it to a PRD requirement (or note it's outside scope)
- Classify severity:
  - **critical** — PRD requirement completely unmet, data loss risk, security issue, or app crashes
  - **major** — PRD requirement partially met, significantly degraded experience
  - **minor** — cosmetic, edge case, or enhancement opportunity
  - **info** — observation with no action required

## Verdict Decision

- **READY**: No critical or major findings. Minor issues noted.
- **NEEDS FIXES**: Major findings present but no critical. Can ship with known limitations documented.
- **BLOCKED**: Any critical finding present. Do not ship.

## Output Files

### progress/handover/test.md — What Passed

```markdown
# What's Working

*From full-test on [date]*

## Passing Requirements
[List PRD requirements that are fully satisfied]

## Passing Tests
[Existing test suite: N/N, PRD tests: N/N]
```

### progress/handover/review.md — Verdict

```markdown
# QA Verdict: [READY / NEEDS FIXES / BLOCKED]

*Full-test on [date]*

## Summary
[2-3 sentences: what was tested, what was found, recommendation]

## Critical Issues
[List — must fix before shipping]

## Major Issues
[List — should fix, can ship with these known]

## Minor Issues
[List — note for backlog]

## Recommended Next Steps
- READY → ship or do one more review pass
- NEEDS FIXES → /cr for each major issue, then re-run /full-test
- BLOCKED → /build or /cr for critical issues before re-testing
```

## Print to User

```
QA Verdict: [READY / NEEDS FIXES / BLOCKED]

Critical: [N] | Major: [N] | Minor: [N]

Full report: progress/handover/review.md
```
