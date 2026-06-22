---
name: context-compress
description: Compress and optimize context usage — summarize verbose outputs, layer information by relevance, preserve critical facts across sessions
---

# Context Compress

Maximize signal, minimize noise in context windows.

## When to Use

- Context window approaching limits
- Starting session with prior work
- Large codebase exploration consuming tokens
- Need to preserve decisions across checkpoints

## Strategies

### 1. Summarize Aggressively

```
Bad:  Full stack trace (50 lines)
Good: "TypeError at src/api.ts:42 — missing null check on response.data.user"

Bad:  Entire file read (500 lines)
Good: "File has 200 lines, key function at line 85-120, uses X pattern"

Bad:  Running every test individually
Good: "All 47 tests pass, coverage at 82%"
```

### 2. Layer Information

```
Critical (always keep):
  - Current task goal
  - Active blockers
  - Key architectural decisions
  - Modified file paths

Important (summarize when needed):
  - Prior decisions and rationale
  - Test results
  - Exploration findings

Ephemeral (drop when tight):
  - Full file contents (re-read on demand)
  - Verbose command output
  - Intermediate search results
```

### 3. Use Memory System

- Store durable facts in `MEMORY.md`
- Use `notes.md` for session observations
- Reference memory instead of re-deriving
- Search memory before re-exploring

### 4. Parallel Context via Subagents

- Spawn subagents for heavy exploration
- Each gets clean context
- Synthesize findings, not raw output
- Don't pass full conversation to every subagent

## Token Budget

| Content | Cost |
|---------|------|
| Full file (500 lines) | ~2000 tokens |
| Command output (100 lines) | ~400 tokens |
| Subagent prompt | ~500 tokens |
| Checkpoint summary | ~800 tokens |

**Rule:** If reading it twice, summarize it once.

## Session Handoff

When context is tight:

1. Write findings to `notes.md` or task progress
2. Summarize what's done and what's next
3. Reference specific file paths and line numbers
4. Start fresh session with focused prompt

## Anti-Patterns

| Pattern | Problem |
|---------|---------|
| Reading full files unnecessarily | Burns tokens |
| Re-deriving from memory | Wastes context |
| Passing full conversation to subagents | Redundant |
| Keeping verbose output | Noisy |
| Not summarizing at checkpoints | Loses critical info |
