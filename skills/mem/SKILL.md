---
name: mem
description: Manage persistent memory — project context, session notes, cross-session knowledge retention
---

# Memory Manager

Maintain persistent knowledge across sessions. Remember what matters, forget what doesn't.

## Memory System

### File Locations

| File | Purpose | Lifetime |
|------|---------|----------|
| `MEMORY.md` (project) | Project context, rules, architecture | Cross-session |
| `notes.md` (session) | Free-form observations, quotes, questions | Per-session |
| `MEMORY.md` (global) | User preferences, cross-project patterns | All projects |

### What Goes Where

**MEMORY.md (Project):**
- Architecture decisions and rationale
- Coding conventions and rules
- Known patterns and anti-patterns
- Technology-specific guidance
- Durable facts that survive sessions

**notes.md (Session):**
- Quotes with lasting value
- Unresolved questions
- Cross-project observations
- Notes for future-self
- Context that won't fit in tasks

**MEMORY.md (Global):**
- User coding preferences
- Cross-project methodology rules
- Style preferences
- Tool preferences

## When to Write to Memory

### Write to MEMORY.md When:
- User states a project-level rule
- Architectural decision is made
- Durable fact discovered that spans sessions
- Pattern established that should persist

### Write to notes.md When:
- Interesting observation but not yet decided
- Quote worth remembering
- Question to revisit later
- Cross-project similarity noticed

### DON'T Write When:
- Task-specific details (use task progress)
- Temporary state (use checkpoint)
- Ephemeral debugging notes
- Things already in memory

## Reading Memory

Before re-exploring or re-deriving:

1. **Search memory** for relevant keywords
2. **Read MEMORY.md** for project context
3. **Check notes.md** for session observations
4. **Only then** explore codebase

## Memory Maintenance

### At Checkpoints:
- Review what was learned
- Promote durable facts to MEMORY.md
- Clean up notes.md (remove resolved items)

### Periodically:
- Review MEMORY.md for outdated info
- Remove entries no longer relevant
- Consolidate related entries

## Anti-Patterns

| Pattern | Problem |
|---------|---------|
| Not searching before exploring | Re-deriving known facts |
| Putting everything in MEMORY.md | Bloat, hard to find |
| Putting durable facts in notes.md | Lost at session end |
| Not writing decisions to memory | Repeated discussions |
| Storing task-specific details in memory | Noise, not signal |
