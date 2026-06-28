# workflows

Model-agnostic role-based workflow skills for AI-assisted development.

## Install

```bash
git clone git@github.com:flenry/workflows.git .claude/skills/workflows
```

Or installed automatically via [project-init](https://github.com/flenry/project-init).

## How It Works

Each workflow is a sequence of **phases**. Each phase is executed by adopting a **role** — a discipline with clear responsibilities and rules. One agent runs all phases sequentially, switching roles between them.

Roles are defined in [`ROLES.md`](ROLES.md). Read it to understand what each role does and what rules it must follow.

## Workflows

| Skill | What it does | Phases |
|-------|-------------|--------|
| `/chat` | Structured brainstorm — no implementation | Planner → Researcher |
| `/research` | Multi-pass research with validation | Planner explores → validates → Researcher synthesises |
| `/board-prd` | Thorough PRD with architecture review | Planner → Planner drafts → Researcher + Reviewer → Planner publishes |
| `/build` | Full TDD build with eval loop | Planner → Researcher → Reviewer → Planner → Tester → Implementer+Evaluator loop → Tester → Documenter |
| `/cr` | Scoped change request with PR | Planner → Implementer+Evaluator loop → Documenter |
| `/full-test` | PRD-driven QA with verdict | Planner → Tester → Planner verdict |

## Usage

### `/chat`
```
/chat should we use postgres or sqlite for this project?
```
Thinks through the decision with you. No code written.

### `/research`
```
/research how does STOCK Act disclosure filing work?
```
Produces `context/research.md` — a validated, synthesised research document.

### `/board-prd`
```
/board-prd
```
Interviews you, writes `PRD.md`, runs an architecture + completeness review, then publishes the final version.

### `/build`
```
/build implement the disclosure fetcher per PRD.md
```
Plans → writes failing tests → implements with self-evaluation loop (scores ≥ 8/10 to pass) → verifies → updates docs.

```
/build fast    # skip architecture review and docs phases
/build plan    # plan only, no implementation
```

### `/cr`
```
/cr add caching to the disclosure fetcher
```
Git hygiene → scoped plan → implements with eval loop (max 3 iterations) → creates PR.

```
/cr plan       # plan only
/cr implement  # implement only (assumes PLAN.md exists)
/cr pr         # create PR only
```

### `/full-test`
```
/full-test
```
Derives a test plan from `PRD.md`, runs the app and test suite, produces a verdict: **READY / NEEDS FIXES / BLOCKED**.

## Roles

| Role | Responsibility |
|------|---------------|
| **Planner** | Goal-backward decomposition, research, planning, synthesis |
| **Researcher** | Feasibility analysis, architecture review, knowledge synthesis |
| **Reviewer** | Severity-rated code and strategy review |
| **Tester** | Write failing tests first, verify after implementation |
| **Implementer** | Write source code to make tests pass, follow existing patterns |
| **Evaluator** | Score implementation 0–10 against rubric, produce critique |
| **Documenter** | Surgical updates to CLAUDE.md and README.md after builds |

See [`ROLES.md`](ROLES.md) for each role's full rules.

## Eval Loop

`/build` and `/cr` use a self-evaluation loop in the implementation phase:

1. Implementer writes code
2. Evaluator scores it (Correctness ×0.35 + Completeness ×0.30 + Code Quality ×0.20 + Design ×0.15)
3. If score < 8: Implementer fixes critique, loop repeats
4. If score ≥ 8 or max iterations reached: proceed

Hard caps: failing tests → max 4/10. App won't start → max 2/10. Stubs present → cannot score 8+.

## Output Files

| File | Written by |
|------|-----------|
| `PLAN.md` | `/build`, `/cr` |
| `PRD.md` | `/board-prd` |
| `context/research.md` | `/research` |
| `progress/TEST-PLAN.md` | `/full-test` |
| `progress/FINDINGS.md` | `/full-test` |
| `progress/handover/review.md` | `/full-test` |
| `progress/build-summary.md` | `/build` |
