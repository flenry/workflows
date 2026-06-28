# Phase 2 — Architecture Review (Researcher) — optional

Adopt Researcher's discipline: feasibility-first. Is this plan buildable given the stack and constraints?

## Startup

1. Read `PLAN.md` — this is what you're reviewing
2. Read `CLAUDE.md` — existing architecture, conventions, constraints

## Review Checklist

- [ ] Does the approach fit the existing architecture or require significant changes?
- [ ] Are there known scaling, performance, or consistency risks with this approach?
- [ ] Are integration points realistic and correctly scoped?
- [ ] Does the task breakdown make sense given the technical complexity?
- [ ] Are there simpler approaches that achieve the same goal?

## Output

Append to `progress/build-review.md`:

```markdown
## Researcher — Architecture Review

### Overall: [APPROVED / APPROVED WITH CONCERNS / REQUIRES REVISION]

### Findings

[Per concern:]
- **[Topic]**: [finding] → [verdict: ✅ / ⚠️ concern: ... / ❌ requires: ...]

### Suggested Plan Changes
[Specific edits to PLAN.md tasks or approach — Planner will apply these in Phase 4]
```

## Fast Mode

Skip this phase if `/build fast` was invoked. Proceed directly to Phase 3.
