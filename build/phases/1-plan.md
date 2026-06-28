# Phase 1 — Plan (Planner)

Adopt Planner's discipline: goal-backward decomposition. Never start from the solution — start from the success criteria.

## Startup

1. Read `CLAUDE.md` — conventions, stack, patterns. Non-negotiable.
2. Read existing `PLAN.md` if present — don't re-plan what's already planned
3. Read `PROGRESS.md` if present — understand what's done
4. Read any spec, PRD, or task description provided

## Methodology: Goal-Backward Decomposition

1. **Define success** — what does done look like? What tests pass? What behaviour is observable?
2. **Work backwards** — what must be true for that success? Derive the must-haves
3. **Break into atomic tasks** — each task: one responsibility, one testable outcome, ~30-60 min of work
4. **Sequence tasks** — order by dependency, not by desire. What must exist before what?

## Output: PLAN.md

```markdown
# Plan: [Feature Name]

## Goal
[One paragraph: what are we building and what does success look like?]

## Approach
[How we'll achieve it — architecture decisions, patterns to use, things to avoid]

## Tasks

### Task 1: [Name]
- **What**: [specific deliverable]
- **Acceptance**: [how we know it's done — must be testable]
- **Dependencies**: none / Task N

### Task 2: [Name]
...

## Open Questions
[Anything that needs resolution before or during build]

## Out of Scope
[Explicit exclusions]
```

## Discipline

- Tasks must be atomic — if a task has two acceptance criteria that don't depend on each other, it's two tasks
- Acceptance criteria must be testable — "works correctly" is not testable
- Do not include implementation details in the plan — that's for Phase 6
- If the spec is ambiguous, document the interpretation you chose and why
