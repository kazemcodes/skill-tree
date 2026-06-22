---
name: changelog-generator
description: Create user-facing changelogs from git commits — categorize changes, translate technical language to customer-friendly release notes
---

# Changelog Generator

Transform technical git commits into polished, user-friendly changelogs.

## When to Use

- Preparing release notes for a new version
- Creating weekly/monthly product update summaries
- Writing changelog entries for app store submissions
- Generating update notifications

## Process

1. **Scan Git History**: Analyze commits between versions or time periods
2. **Categorize Changes**: Group into features, improvements, bug fixes, breaking changes, security
3. **Translate Technical → User-Friendly**: Convert developer commits to customer language
4. **Filter Noise**: Exclude internal commits (refactoring, tests, CI)
5. **Format Professionally**: Clean, structured changelog entries

## Usage Examples

```
Create a changelog from commits since last release
Generate changelog for all commits from the past week
Create release notes for version 2.5.0
Create a changelog for all commits between March 1 and March 15
```

## Output Format

```markdown
# Updates - Week of March 10, 2024

## ✨ New Features

- **Team Workspaces**: Create separate workspaces for different projects.
- **Keyboard Shortcuts**: Press ? to see all available shortcuts.

## 🔧 Improvements

- **Faster Sync**: Files now sync 2x faster across devices
- **Better Search**: Search now includes file contents, not just titles

## 🐛 Fixes

- Fixed issue where large images wouldn't upload
- Resolved timezone confusion in scheduled posts

## ⚠️ Breaking Changes

- API v1 endpoints removed — migrate to v2 (see migration guide)

## 🔒 Security

- Updated authentication to prevent session fixation
```

## Categories

| Category | Icon | What Goes Here |
|----------|------|----------------|
| New Features | ✨ | User-facing new functionality |
| Improvements | 🔧 | Enhancements to existing features |
| Fixes | 🐛 | Bug fixes that affect users |
| Breaking Changes | ⚠️ | Changes that require user action |
| Security | 🔒 | Security patches and hardening |

## Tips

- Run from git repository root
- Specify date ranges for focused changelogs
- Review and adjust before publishing
- Save output to CHANGELOG.md
- Filter out: "refactor", "test", "ci", "chore", "style" commits
