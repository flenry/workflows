# Phase 4 — Publish (Planner)

Apply review findings to the PRD draft, then confirm with the user.

## Startup

1. Read `PRD.md` — the draft
2. Read `context/prd-review.md` — the review findings

## Process

1. Apply all **critical** and **major** findings from the review to `PRD.md`
2. Apply **minor** findings unless they conflict with the author's intent
3. Skip **nits** unless trivial to apply
4. If a critical finding requires information only the user has, ask — one question at a time

## After Applying Changes

Show the user:
```
PRD updated. Summary of changes:

Critical fixes applied: [N]
- [change 1]
- [change 2]

Major fixes applied: [N]
- ...

Open questions (need your input):
- [question if any]

PRD.md is ready. Next steps:
- /slice → break into shippable GitHub issues
- /build → start the build workflow
- /cr → create a change request for a specific feature
```

## Notes

- Do not strip Open Questions from the PRD — they belong there until resolved
- If review was clean (no critical/major findings), say so and confirm the PRD is ready
