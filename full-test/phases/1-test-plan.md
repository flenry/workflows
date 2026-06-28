# Phase 1 — Derive Test Plan (Planner)

Adopt Planner's discipline. Derive a comprehensive test plan from the PRD — do not copy the PRD, translate it into testable scenarios.

## Startup

1. Read `PRD.md` — this is your source of truth
2. Read `CLAUDE.md` — understand the stack, how to run the app, test framework in use
3. Detect app type:
   - CLI → how to invoke, expected output
   - Backend API → endpoints, request/response contracts
   - Frontend → key user flows, component behaviour
   - Fullstack → combination of above
4. Check env vars: are all required vars present? (check `.env.sample` vs `.env`)

## What to Derive

For each User Story or requirement in the PRD, produce at least:
- **Happy path test** — the expected flow works
- **Edge case test** — boundary conditions, empty states, limits
- **Error test** — invalid input, failure states, error messages

For non-functional requirements (performance, accessibility):
- Define what "passing" looks like concretely (e.g., "page loads in < 2s")
- Note if not testable in this environment

## Output: progress/TEST-PLAN.md

```markdown
# Test Plan

*Derived from PRD.md — [date]*

## App Type
[CLI / Backend / Frontend / Fullstack]

## Environment Check
- [ ] All required env vars present
- [ ] App starts successfully
- [ ] Test framework available

## Test Cases

### TC-001: [Requirement Name] — Happy Path
- **PRD reference**: [section]
- **Setup**: [preconditions]
- **Steps**: [numbered steps]
- **Expected**: [specific, observable outcome]

### TC-002: [Requirement Name] — Edge Case
...

### TC-003: [Requirement Name] — Error Case
...

## Out of Scope
[Requirements that cannot be tested in this environment and why]
```
