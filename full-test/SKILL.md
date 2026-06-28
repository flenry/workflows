---
name: full-test
description: PRD-driven QA — derive a test plan from PRD.md, run the app and tests, produce a verdict. Use before shipping or after a build to get an independent quality assessment.
---

# Full Test

PRD-driven QA workflow: derive test plan → execute → verdict.

Independent of the build process — treats the app as a black box and verifies it against the PRD.

---

## Commands

| Command | What It Does |
|---------|-------------|
| `/full-test` | Full QA: derive plan → execute → verdict |
| `/full-test plan` | Phase 1 only — produce TEST-PLAN.md |
| `/full-test run` | Phase 2 only — execute existing TEST-PLAN.md |
| `/full-test verdict` | Phase 3 only — produce verdict from existing FINDINGS.md |

---

## Execution

1. `phases/1-test-plan.md` — Planner: derive test plan from PRD
2. `phases/2-execute.md` — Tester: run app + tests + write PRD-derived tests
3. `phases/3-verdict.md` — Planner: analyse findings, write verdict

---

## Output Files

| File | Phase | Contents |
|------|-------|----------|
| `progress/TEST-PLAN.md` | 1 | Structured test plan derived from PRD |
| `progress/FINDINGS.md` | 2 | Test results, failures, screenshots |
| `progress/handover/test.md` | 3 | What passed |
| `progress/handover/review.md` | 3 | Verdict: READY / NEEDS FIXES / BLOCKED |

---

## Verdict Levels

- **READY** — all PRD requirements verified, no blocking issues
- **NEEDS FIXES** — non-blocking issues found; can ship with known limitations
- **BLOCKED** — critical failures; do not ship

---

## Notes

- This skill is read-only for source code — it tests, doesn't fix
- If issues are found, use `/cr` or `/build` to address them
- Can be run against any app that has a `PRD.md`
