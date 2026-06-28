# Phase 8 — Documentation (Documenter) — optional

Adopt Documenter's discipline: update living documentation after every build cycle. Surgical updates only — read existing docs first, modify only what changed.

## Startup

1. Read all build phase outputs to understand what was built and what decisions were made
2. Read existing `CLAUDE.md`, `README.md` (if they exist) — only update what changed
3. Read `PLAN.md` — what was the intent?

## What to Update

**CLAUDE.md** — AI-first reference:
- New architectural patterns or conventions introduced
- New dependencies added and why
- New environment variables or configuration
- Anything a future agent needs to know to work in this codebase

**README.md** — Human-facing:
- New setup steps
- New commands
- Changed behaviour in existing features

**Do NOT**:
- Rewrite sections that didn't change
- Add commentary about what was built in this session (that belongs in git history)
- Document implementation details that are obvious from the code

## Fast Mode

Skip this phase if `/build fast` was invoked.

## Output

Write `progress/build-summary.md`:

```markdown
# Build Summary

## What Was Built
[Feature name, brief description]

## Key Decisions
[Architecture choices made, trade-offs accepted]

## Files Changed
[List of modified files]

## Docs Updated
- CLAUDE.md: [yes/no — what changed]
- README.md: [yes/no — what changed]

## Final Score
[From Phase 6 eval]
```

Print: `Build complete. Summary written to progress/build-summary.md`
