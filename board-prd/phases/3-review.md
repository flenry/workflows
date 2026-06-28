# Phase 3 — Architecture Review (Researcher + Reviewer)

Review the PRD for technical feasibility, architectural soundness, and completeness. Two passes.

## Startup

1. Read `PRD.md` — this is what you're reviewing
2. Read `CLAUDE.md` — understand the existing architecture and constraints

---

## Pass 1 — Researcher (Feasibility)

Ask: *Is this technically achievable given the stack and constraints?*

Check:
- Do the Technical Requirements conflict with the existing architecture?
- Are there known issues with the proposed approach (scaling, latency, consistency)?
- Are integration points realistic?
- Is the scope achievable without a rewrite of existing systems?

Output verdict per section:
- ✅ Approved
- ⚠️ Concern — note the risk, suggest mitigation
- ❌ Requires revision — explain why and what would make it approvable

---

## Pass 2 — Law (Completeness & Precision)

Ask: *Could a developer build this from the PRD as written?*

Check:
- Are any User Stories ambiguous? (Multiple valid interpretations = ambiguous)
- Are acceptance criteria missing or untestable?
- Are edge cases handled or explicitly deferred?
- Are Non-Goals specific enough to resolve disputes?
- Are Open Questions actually blocking, or could they be resolved by a developer?

Severity ratings:
- **critical** — developer cannot proceed without resolution
- **major** — will cause rework after build starts
- **minor** — should clarify but won't block
- **nit** — optional improvement

---

## Output

Write `context/prd-review.md`:

```markdown
# PRD Review

## Researcher — Feasibility Assessment

### Overall: [APPROVED / APPROVED WITH CONCERNS / REQUIRES REVISION]

[findings by section]

## Law — Completeness Review

### Critical
[items that block proceeding]

### Major
[items that will cause rework]

### Minor / Nit
[optional improvements]

## Required Changes Before Phase 4
[consolidated list of must-fix items]
```
