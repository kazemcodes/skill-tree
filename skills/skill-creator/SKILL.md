---
name: skill-creator
description: Create, edit, and manage MiMo Code agent skills with proper SKILL.md format
---

# Skill Creator

Helps you create new MiMo Code agent skills or modify existing ones.

## When to Use

- Creating a new skill from scratch
- Editing an existing skill's instructions
- Debugging why a skill isn't loading
- Converting instructions into a reusable skill

## Skill Structure

Every skill lives in a folder with a `SKILL.md` file:

```
.mimocode/skills/
  my-skill/
    SKILL.md          # Required: frontmatter + instructions
    supporting-files  # Optional: examples, templates, scripts
```

## SKILL.md Template

```markdown
---
name: skill-name
description: One-line description the agent uses to decide when to load this skill
---

# Skill Title

## When to Use

- Condition 1
- Condition 2

## Instructions

Step-by-step guidance for the agent.

## Examples

Concrete before/after examples.

## Constraints

What the skill must NOT do.
```

## Frontmatter Rules

| Field | Required | Notes |
|-------|----------|-------|
| `name` | Yes | Lowercase, hyphens allowed. This is how agents reference it. |
| `description` | Yes | Agent sees this before loading. Be specific. |
| `hidden` | No | `true` = loaded but not shown in available skills list |

## Naming Conventions

- Use lowercase with hyphens: `git-release`, `code-review`, `tdd`
- Keep names short and predictable (2-3 words max)
- Avoid underscores or camelCase

## Writing Good Descriptions

The description is the ONLY signal the agent sees before choosing to load your skill. Make it count.

**Good:** "Create consistent releases and changelogs from merged PRs"
**Bad:** "A helpful skill for releases"

**Good:** "Review pull requests for security vulnerabilities and code quality"
**Bad:** "Code review"

## Placement Options

| Path | Scope |
|------|-------|
| `.mimocode/skills/` | Project-local |
| `~/.config/mimocode/skills/` | Global (all projects) |
| `.claude/skills/` | Compatibility (also works) |

## Debugging

If your skill doesn't appear:

1. File must be named exactly `SKILL.md` (all caps)
2. Frontmatter must have both `name` and `description`
3. Check `permission` settings in `mimocode.json` — `deny` hides skills
4. Duplicate names: last loaded wins (check for conflicts)

## Example: Creating a Skill

```bash
# 1. Create the folder
mkdir -p .mimocode/skills/code-review

# 2. Write SKILL.md
cat > .mimocode/skills/code-review/SKILL.md << 'EOF'
---
name: code-review
description: Review code changes for bugs, security issues, and style violations
---

# Code Review

## When to Use

- After writing new code
- Before committing changes
- When asked to review a PR

## Process

1. Read the diff
2. Check for security issues (injection, auth bypass, secrets)
3. Check for logic errors
4. Check for style consistency
5. Report findings with file:line references
EOF
```
