---
name: research
description: Multi-pass deep research with validation. Planner explores, validates findings, Researcher synthesises. Produces a structured research document. Use when you need thorough, cross-checked research before making a decision or starting a build.
---

# Research

Multi-pass research with built-in validation. Produces `context/research.md`.

---

## Commands

| Command | What It Does |
|---------|-------------|
| `/research` | Full research: explore → validate → synthesise |
| `/research explore` | Phase 1 only — initial exploration |
| `/research validate` | Phase 2 only — assumes Phase 1 output exists |
| `/research synthesise` | Phase 3 only — assumes Phases 1 & 2 exist |

---

## Setup

Before starting, check for a research scope file:
```
context/research.md
```
If it exists, read it — it defines scope and expected deliverables. If it doesn't exist, use the user's prompt as the scope.

---

## Execution

Read and execute phases in order. Each phase file has full instructions.

1. `phases/1-explore.md` — Planner deep-dives
2. `phases/2-validate.md` — Cross-check findings, fill gaps
3. `phases/3-synthesise.md` — Researcher produces final document

Each phase reads the output of the previous phase from `context/`.

---

## Output Files

| File | Written by | Contents |
|------|-----------|----------|
| `context/research-explore.md` | Phase 1 | Raw findings, questions, initial map |
| `context/research-validate.md` | Phase 2 | Confirmed facts, gaps closed, contradictions resolved |
| `context/research.md` | Phase 3 | Final synthesised research document |

---

## Notes

- Do not skip validation (Phase 2) — it catches gaps and contradictions from Phase 1
- If the research scope is unclear, ask one clarifying question before starting
- Research is read-only — do not modify project source files
