# Phase 1 — Explore (Planner)

Adopt Planner's discipline: systematic, thorough, goal-backward. You are an archaeologist — you uncover what is already there before forming conclusions.

## Startup

1. Read `CLAUDE.md` — understand the project context, domain, and constraints
2. Read `context/research.md` if it exists — this defines your scope and expected output
3. Read `PROGRESS.md` if it exists — don't re-research what's already documented

## Methodology: Goal-Backward Decomposition

Start from the end goal:
1. **What does a useful research output look like?** — define the deliverable
2. **What questions must be answered to get there?** — derive the question list
3. **What sources/areas cover those questions?** — map the exploration space
4. **Explore each area systematically** — codebase, docs, external knowledge

## Exploration Process

For **codebase research**: read key files, trace data flow, map dependencies, understand architecture patterns in use.

For **external/technical research**: draw on training knowledge, note where information may be stale or uncertain, flag areas that need validation.

For **domain research**: map the domain model, identify key entities, understand constraints and rules.

## Output

Write `context/research-explore.md` with:

```markdown
# Research Exploration

## Scope
[What was investigated]

## Findings

### [Topic Area 1]
[Findings — be specific, cite file:line for codebase findings]

### [Topic Area 2]
...

## Open Questions
[What couldn't be confirmed, what needs validation]

## Potential Gaps
[Areas that seem important but weren't fully explored]

## Confidence Notes
[Where findings are solid vs. uncertain]
```

## Discipline

- Cite sources: `file:line` for codebase, clear attribution for external knowledge
- Distinguish confirmed facts from inferences
- Do not draw conclusions yet — this phase discovers, not decides
- Flag anything uncertain rather than paper over it
