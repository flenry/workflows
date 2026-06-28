# Phase 1 — Plan (Planner)

Git hygiene first, then plan the change.

## Git Hygiene

Before any planning:
```bash
git fetch origin
git status           # confirm clean working tree
git pull --ff-only   # get latest
git checkout -b cr/[feature-name]   # new branch for this CR
```

If working tree is dirty, stop and report. Do not plan on a dirty tree.

## Planning

Adopt Planner's goal-backward discipline (same as `/build` Phase 1), but scoped to the change request:

1. Read `CLAUDE.md` — conventions, existing patterns
2. Read `PROGRESS.md` if it exists — what's already done?
3. Understand the change: what exactly is changing, and why?
4. Identify the blast radius: what existing code is affected?
5. Write `PLAN.md`

## PLAN.md for a CR

```markdown
# CR: [Change Name]

## Change Summary
[One paragraph: what changes, what stays the same, why]

## Blast Radius
[Files and systems affected by this change]

## Tasks

### Task 1: [Name]
- **What**: [specific change]
- **Acceptance**: [testable criterion]
- **Risk**: [what could go wrong]

...

## Rollback Plan
[How to revert if this change causes problems]

## Out of Scope
[What this CR explicitly does not change]
```

## Scope Check

If the task list grows beyond ~5 tasks or touches more than 3 subsystems, flag it:
```
⚠ This CR is larger than expected. Consider using /build instead for better structure.
Proceed with CR? [yes/no]
```
