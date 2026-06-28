# Phase 3 — Create PR (Documenter)

Adopt Documenter's discipline: clean handoff. The PR description must let any reviewer understand the change without reading the code.

## Startup

1. Read `PLAN.md` — what was intended
2. Read `progress/cr-eval-[final].md` — what was actually built and what the score was
3. Read `CLAUDE.md` — any PR conventions (branch naming, labels, etc.)

## Git

```bash
git add -p        # stage changes interactively — never `git add .`
git commit -m "[type]: [concise description of change]"
git push -u origin cr/[feature-name]
```

Commit message format:
- `feat:` new feature
- `fix:` bug fix
- `refactor:` no behaviour change
- `chore:` tooling, deps, config

## Create PR

Use `gh-axi` if available (preferred), otherwise `gh`:

```bash
gh-axi pr create \
  --title "[CR]: [feature name]" \
  --body "$(cat pr-body.md)"
```

PR body template (write to `pr-body.md` first, then use it):

```markdown
## What

[1-2 sentences: what changed]

## Why

[motivation — what problem does this solve?]

## How

[approach taken — key decisions, trade-offs]

## Test Plan

- [ ] [specific thing to test]
- [ ] [edge case to verify]
- [ ] [regression to check]

## Blast Radius

[Files changed, systems affected]

## Eval Score

[X]/10 — [brief summary of evaluator findings]
```

## Doc Updates

If the change introduces new conventions, env vars, or patterns:
- Update `CLAUDE.md` (AI-first reference) — surgically, only what changed
- Update `README.md` if user-facing behaviour changed

## Output

Print: `PR created: [URL]`
