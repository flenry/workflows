---
name: board-prd
description: Write or update PRD.md via a structured board process. Gathers context, drafts the PRD, runs an architecture review, then publishes. Use when you want a thorough, reviewed PRD rather than a quick draft.
---

# Board PRD

Structured PRD creation: context gathering → draft → architecture review → publish.

---

## Commands

| Command | What It Does |
|---------|-------------|
| `/board-prd` | Full process: gather → draft → review → publish |
| `/board-prd draft` | Skip context gathering, go straight to draft |
| `/board-prd review` | Review an existing `PRD.md` |
| `/board-prd update` | Update an existing PRD with new information |

---

## Execution

Read and execute phases in order.

1. `phases/1-context.md` — Planner gathers context
2. `phases/2-draft.md` — Planner writes PRD.md
3. `phases/3-review.md` — Researcher/Reviewer architecture review
4. `phases/4-publish.md` — finalise and confirm with user

---

## Output Files

| File | Written by | Contents |
|------|-----------|----------|
| `PRD.md` | Phase 2, finalised in Phase 4 | Full product requirements document |
| `context/prd-review.md` | Phase 3 | Architecture review findings |

---

## PRD Structure

The PRD.md produced by this skill follows this format:

```markdown
# PRD: [Feature/Project Name]

## Overview
[1-2 paragraph summary: what, why, who]

## Problem Statement
[What problem does this solve? For whom? Why now?]

## Goals
[Measurable outcomes — what success looks like]

## Non-Goals
[Explicit scope exclusions — prevents scope creep]

## User Stories
[As a [user], I want [capability] so that [outcome]]

## Technical Requirements
[Architecture constraints, integration points, performance requirements]

## Open Questions
[Unresolved decisions that need input before build]

## Out of Scope (Future)
[Things that came up but are deferred]
```
