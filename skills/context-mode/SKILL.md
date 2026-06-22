---
name: context-mode
description: Manage context windows efficiently — summarize, compress, and preserve critical information across sessions
---

# Context Mode

Optimize context usage. Keep what matters, compress what doesn't, preserve across sessions.

## When to Use

- Context window getting full
- Starting a new session with prior work
- Need to preserve decisions across checkpoints
- Large codebase exploration consuming tokens

## Context Management Strategies

### 1. Summarize Aggressively

Replace verbose output with concise summaries:

```
Bad:  Full stack trace with 50 lines
Good: "TypeError at src/api.ts:42 — missing null check on response.data.user"

Bad:  Entire file content read
Good: "File has 200 lines, key function at line 85-120, uses X pattern"

Bad:  Running every test individually
Good: "All 47 tests pass, coverage at 82%"
```

### 2. Layer Information

Organize context by relevance:

```
Critical (always keep):
- Current task goal
- Active blockers
- Key architectural decisions
- File paths of modified files

Important (summarize when needed):
- Prior conversation decisions
- Test results
- Code exploration findings

Ephemeral (drop when context tight):
- Full file contents (re-read on demand)
- Verbose command output
- Intermediate search results
```

### 3. Use Memory System

- Store durable facts in `MEMORY.md`
- Use `notes.md` for cross-session observations
- Reference memory instead of re-deriving
- Search memory before re-exploring

### 4. Parallel Context via Subagents

- Spawn subagents for heavy exploration
- Each subagent gets clean context
- Synthesize findings, not raw output
- Don't pass full conversation to every subagent

## Checkpoint Discipline

At checkpoint time, ensure these are captured:

1. **What was accomplished** (not what was attempted)
2. **Key decisions** and their rationale
3. **Current state** of modified files
4. **Blockers** and how to resolve them
5. **Next action** (specific, not vague)

## Token Budget Awareness

| Content | Approximate Cost |
|---------|-----------------|
| Full file read (500 lines) | ~2000 tokens |
| Command output (100 lines) | ~400 tokens |
| Subagent prompt | ~500 tokens |
| Checkpoint summary | ~800 tokens |

**Rule of thumb:** If you're reading it twice, summarize it once.

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
| Passing full conversation to subagents | Redundant context |
| Keeping verbose command output | Noisy, hard to parse |
| Not summarizing at checkpoints | Loses critical info |
