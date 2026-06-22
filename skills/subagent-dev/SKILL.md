---
name: subagent-dev
description: Execute independent tasks in parallel using subagents — dispatch fresh agent per task with review between iterations
---

# Subagent-Driven Development

Dispatch fresh subagent per task for fast, isolated execution with quality gates.

## When to Use

- 3+ independent issues to investigate
- Implementation plan with independent tasks
- Need parallel execution without context pollution
- Multiple test failures across different files

## Sequential Execution

For tightly coupled tasks that must run in order:

```
For each task:
  1. Dispatch implementation subagent
  2. Review output
  3. Fix issues if found
  4. Mark complete, move to next
```

## Parallel Execution

For independent tasks (different files, subsystems):

```
1. Identify independent domains
2. Dispatch one agent per domain
3. Review all results
4. Verify no conflicts
5. Run full test suite
```

## Subagent Prompt Template

```markdown
You are implementing [TASK] from [PLAN].

Your job:
1. Read the requirements carefully
2. Implement exactly what's specified
3. Write tests (TDD if specified)
4. Verify implementation works
5. Commit your work
6. Report back

Constraints:
- Don't change code outside your scope
- Follow existing patterns
- Use project's test framework

Report: What you implemented, tests run, files changed, any issues.
```

## Review After Each Agent

```markdown
Review the changes from the last subagent:
- Check for correctness
- Verify tests pass
- Look for scope creep
- Check code quality
- Report issues by severity: Critical/Important/Minor
```

## Rules

- **Fresh subagent per task** — no context pollution
- **Review between tasks** — catch issues early
- **Don't parallelize coupled tasks** — conflicts will occur
- **Stop on blockers** — don't guess, ask
- **Verify full test suite** — after all agents complete

## When NOT to Use

- Tasks are tightly coupled
- Need full system context to understand
- Exploratory debugging (don't know what's broken)
- Agents would edit same files
