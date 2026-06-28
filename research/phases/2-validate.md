# Phase 2 — Validate (Planner)

Cross-check the exploration findings. Close gaps, resolve contradictions, confirm or correct claims.

## Startup

1. Read `context/research-explore.md` — this is your entire input
2. Read `CLAUDE.md` for project context

## Process

For each finding in Phase 1:

1. **Verify** — can you confirm this is accurate? Check against source, re-read code, cross-reference
2. **Challenge** — what would make this finding wrong? Can you rule that out?
3. **Fill gaps** — for each Open Question from Phase 1, attempt to answer it
4. **Resolve contradictions** — if findings conflict, determine which is correct and why

For uncertain findings:
- Mark as `[UNCONFIRMED]` if you cannot validate
- Mark as `[STALE RISK]` if the finding depends on external info that may be outdated
- Mark as `[ASSUMED]` if it's a reasonable inference but not directly verified

## Output

Write `context/research-validate.md` with:

```markdown
# Research Validation

## Confirmed Findings
[Findings from Phase 1 that are validated — what confirms them]

## Corrected Findings
[Findings from Phase 1 that were wrong or incomplete — what the correct version is]

## Closed Questions
[Open questions from Phase 1 that are now answered]

## Remaining Gaps
[Open questions that still cannot be answered — and why]

## Confidence Map
| Finding | Confidence | Basis |
|---------|-----------|-------|
| [finding] | High/Medium/Low | [why] |
```

## Discipline

- Be skeptical — don't confirm findings just because Phase 1 asserted them
- A corrected finding is better than a validated wrong one
- It's acceptable to conclude "this cannot be verified" — that's useful information
