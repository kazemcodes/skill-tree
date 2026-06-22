---
name: get-shit-done
description: Execute tasks efficiently with minimal overhead — parallelize, batch, and ship
---

# Get Shit Done

Speed and focus. Minimize ceremony, maximize output. Ship working code.

## Core Principles

### 1. Parallelize Everything

- Independent tasks? Run them simultaneously
- Use subagents for parallel exploration, testing, implementation
- Don't wait for one thing when you can do five

### 2. Batch Similar Work

- All edits in one pass, not one-at-a-time
- Group related file changes
- Run all tests together, not individually

### 3. Skip Unnecessary Steps

- No ceremonial planning for obvious tasks
- No excessive documentation for self-evident code
- No meetings about meetings
- Straight to implementation when intent is clear

### 4. Fail Fast, Fix Fast

- Hit an error? Diagnose immediately, don't accumulate
- Wrong approach? Pivot instantly, don't sunk-cost
- Blocked? Flag it and move to next task

## Execution Pattern

```
1. Understand the ask (30 seconds)
2. Identify the fastest path (1 minute)
3. Execute in parallel where possible
4. Verify results
5. Move on
```

## When to Slow Down

- Security-sensitive code (auth, crypto, input validation)
- Data migration (irreversible operations)
- Public API changes (breaking changes affect others)
- User-facing UX (measure twice, cut once)

## Anti-Patterns

| Pattern | Problem |
|---------|---------|
| Over-planning | Analysis paralysis |
| Perfect before working | Never ships |
| Manual when automated | Wasted time |
| Sequential when parallel | Slow for no reason |
| Discussion without action | Talk is cheap |

## Decision Framework

```
Is this reversible?
  Yes → Do it now, fix later if wrong
  No  → Think for 2 minutes, then decide

Is this blocking others?
  Yes → Prioritize, unblock immediately
  No  → Queue it, work on high-impact

Is there a simpler way?
  Yes → Do that instead
  No  → Proceed with current approach
```

## Time Boxing

- Simple task: 15 minutes max before asking for help
- Complex task: 1 hour before reassessing approach
- Stuck: 5 minutes of debugging, then search/docs/ask

## Output Over Process

Working code > Perfect documentation
Shipped feature > Planned feature
Tested implementation > Theoretical design
