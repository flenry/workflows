# Phase 1 — Context Gathering (Planner)

Understand everything needed to write a good PRD before writing a single word of it.

## Startup

1. Read `CLAUDE.md` — project context, domain, existing architecture
2. Read existing `PRD.md` if it exists — is this an update or a new PRD?
3. Read `PROGRESS.md` if it exists — what's already been built?
4. Read any existing specs or planning docs in the project

## What to Gather

Ask the user (one question at a time, only if not already clear from context):

1. **What is this?** — feature name and one-sentence description
2. **Why now?** — what's the motivation or trigger?
3. **Who is it for?** — which users, what are their goals?
4. **What does success look like?** — measurable outcome
5. **What's out of scope?** — what are we explicitly NOT doing?
6. **Any hard constraints?** — technical, timeline, compliance

Skip questions already answered by `CLAUDE.md`, existing docs, or the user's initial prompt.

## Output

Write `context/prd-context.md`:

```markdown
# PRD Context

## Feature / Project Name
[name]

## Motivation
[why this, why now]

## Target Users
[who and what they need]

## Success Criteria
[measurable outcomes]

## Known Constraints
[hard limits]

## Explicit Non-Goals
[what we're not doing]

## Open Questions
[anything still unclear that will affect the PRD]
```
