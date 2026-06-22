---
name: finish-branch
description: Complete development work — verify tests, present merge/PR/discard options, clean up worktree and branch
---

# Finish Branch

Guide completion of development work with structured options.

## When to Use

- Implementation is complete
- All tests pass
- Ready to integrate or discard work

## Process

### Step 1: Verify Tests

```bash
npm test / cargo test / pytest / go test ./...
```

**Tests fail?** Stop. Fix before proceeding.

### Step 2: Detect Environment

```bash
GIT_DIR=$(cd "$(git rev-parse --git-dir)" 2>/dev/null && pwd -P)
GIT_COMMON=$(cd "$(git rev-parse --git-common-dir)" 2>/dev/null && pwd -P)
```

### Step 3: Present Options

**Normal repo or named-branch worktree:**

```
Implementation complete. What would you like to do?

1. Merge back to <base-branch> locally
2. Push and create a Pull Request
3. Keep the branch as-is (I'll handle it later)
4. Discard this work

Which option?
```

**Detached HEAD (3 options):**

```
1. Push as new branch and create a Pull Request
2. Keep as-is (I'll handle it later)
3. Discard this work
```

### Step 4: Execute

| Option | Action |
|--------|--------|
| **1. Merge locally** | Checkout base → pull → merge → verify tests → cleanup worktree → delete branch |
| **2. Create PR** | Push branch (`git push -u origin <branch>`) — keep worktree alive for PR iteration |
| **3. Keep as-is** | Report preserved state, no cleanup |
| **4. Discard** | Confirm with typed "discard" → remove worktree → force-delete branch |

### Step 5: Cleanup (Options 1 & 4 only)

```bash
# From main repo root
git worktree remove <worktree-path>
git worktree prune
```

## Rules

- Verify tests before presenting options
- Get typed confirmation for discard
- Don't clean up worktree for Option 2 (PR needs it)
- Don't run `git worktree remove` from inside the worktree
- Always `cd` to main repo root first
