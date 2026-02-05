# Compound Engineering

The core philosophy is **80% planning & review, 20% execution** — each unit of work makes the next one easier.

## The Main Workflow Cycle

```
Brainstorm → Plan → Work → Review → Compound → Repeat
```

## 5 Core Workflow Commands

| Command | Phase | Purpose |
|---------|-------|---------|
| `/workflows:brainstorm` | Explore | Clarify WHAT to build through dialogue, outputs a brainstorm doc |
| `/workflows:plan` | Plan | Research-driven implementation plan (never writes code), runs parallel research agents |
| `/workflows:work` | Execute | Follow the plan with task tracking, incremental commits, auto-creates PR |
| `/workflows:review` | Review | Runs 10-14 specialized agents in parallel for exhaustive code review |
| `/workflows:compound` | Learn | Document the solution so next similar problem takes 2 min instead of 30 |

## Typical Flow

1. **`/workflows:brainstorm "add user auth"`** — explores approaches, captures decision in `docs/brainstorms/`
2. **`/workflows:plan`** — auto-detects the brainstorm, runs research agents, creates plan in `docs/plans/`
3. **`/workflows:work docs/plans/2026-02-04-feat-auth-plan.md`** — breaks plan into tasks, implements, commits incrementally, creates PR
4. **`/workflows:review 42`** — parallel agent review of PR #42, creates prioritized findings (P1 blocks merge)
5. **`/workflows:compound`** — captures what you learned in `docs/solutions/`

## Utility Commands

- `/deepen-plan` — enhance a plan with more research
- `/plan_review` — get multi-agent feedback on a plan
- `/resolve_pr_parallel` — resolve PR review comments in parallel
- `/resolve_todo_parallel` — resolve todos in parallel
- `/lfg` — quick start ("let's go!")
- `/triage` — prioritize issues
- `/changelog` — generate changelogs

## 5 Agents

The agents are invoked automatically by the workflow commands — you generally don't call them directly. They include specialized reviewers (security, performance, architecture, simplicity) and researchers (repo patterns, best practices, framework docs).

| Agent | Purpose |
|-------|---------|
| design | UI/design iteration and implementation review |
| docs | Documentation generation (e.g. README writing) |
| research | Repository analysis, best practices, framework docs |
| review | Code review with multiple specialized perspectives |
| workflow | Bug reproduction, linting, PR comments, spec analysis |

## Key Principles

- **Parallel over sequential** — agents run simultaneously
- **Incremental commits** — commit after each logical unit, not at the end
- **Never code during plan/compound** — those phases are pure analysis
- **Document everything** — solutions compound over time

## Documentation Artifacts

| Directory | Created By | Purpose |
|-----------|-----------|---------|
| `docs/brainstorms/` | `/workflows:brainstorm` | Explored ideas and decisions |
| `docs/plans/` | `/workflows:plan` | Actionable implementation plans |
| `docs/solutions/` | `/workflows:compound` | Solved problems for fast future lookup |
