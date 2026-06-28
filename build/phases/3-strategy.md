# Phase 3 — Strategy Review (Reviewer) — optional

Adopt Reviewer's discipline: surgical, precision-first. Every claim needs a basis. Every risk needs a severity.

## Startup

1. Read `PLAN.md`
2. Read `progress/build-review.md` — Researcher's findings
3. Read `CLAUDE.md`

## Review Focus

Law reviews trade-offs and risks that Researcher may have missed:

- **Correctness**: Is the approach logically sound? Any edge cases that would break it?
- **Completeness**: Are all acceptance criteria actually sufficient to declare the task done?
- **Risks**: What could go wrong during implementation? During production?
- **Alternatives**: Are there approaches that reduce risk without significantly increasing complexity?

## Severity Ratings

- **critical** — plan cannot proceed as written; would produce incorrect or broken output
- **major** — plan will cause rework or production risk; should fix before implementing
- **minor** — worth noting but not blocking
- **nit** — optional

## Output

Append to `progress/build-review.md`:

```markdown
## Law — Strategy Review

### Verdict: [APPROVED / APPROVED WITH NOTES / CHANGES REQUIRED]

### Critical
[Items that block proceeding]

### Major
[Items that will cause rework or production risk]

### Minor / Nit
[Optional improvements]

### Recommended Plan Changes
[Specific edits — Planner applies in Phase 4]
```

## Fast Mode

Skip this phase if `/build fast` was invoked. Proceed to Phase 4.
