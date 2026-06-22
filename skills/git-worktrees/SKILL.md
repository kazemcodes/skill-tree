---
name: git-worktrees
description: Create isolated git worktrees for feature work — protects current branch, enables parallel development
---

# Git Worktrees

Create isolated workspaces for feature work without stashing or switching branches.

## When to Use

- Starting new feature while current work is in-progress
- Need to test on main without losing local changes
- Parallel development on multiple features
- Hotfix while feature branch is dirty

## Process

### Step 0: Detect Existing Isolation

```bash
GIT_DIR=$(cd "$(git rev-parse --git-dir)" 2>/dev/null && pwd -P)
GIT_COMMON=$(cd "$(git rev-parse --git-common-dir)" 2>/dev/null && pwd -P)
```

If `GIT_DIR != GIT_COMMON` → already in a worktree. Skip creation.

### Step 1: Create Worktree

```bash
# Check if .worktrees is gitignored
git check-ignore -q .worktrees 2>/dev/null

# Create worktree
git worktree add .worktrees/feature-name -b feature-name

# Enter it
cd .worktrees/feature-name
```

### Step 2: Setup

```bash
# Auto-detect and install dependencies
[ -f package.json ] && npm install
[ -f Cargo.toml ] && cargo build
[ -f requirements.txt ] && pip install -r requirements.txt
[ -f go.mod ] && go mod download
```

### Step 3: Verify Baseline

```bash
# Run tests to ensure clean start
npm test / cargo test / pytest / go test ./...
```

## Cleanup

```bash
# From main repo root
git worktree remove .worktrees/feature-name
git worktree prune
git branch -d feature-name
```

## Quick Reference

| Situation | Action |
|-----------|--------|
| Already in worktree | Skip creation |
| `.worktrees/` exists | Use it (verify gitignored) |
| Neither exists | Create `.worktrees/`, add to .gitignore |
| Permission error | Work in current directory instead |
| Tests fail at baseline | Report failures, ask whether to proceed |

## Rules

- Always verify `.worktrees/` is in .gitignore before creating
- Always run baseline tests
- Don't create nested worktrees
- Don't remove worktrees you didn't create
