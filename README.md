<p align="center">
  <img src="https://img.shields.io/badge/Skills-85-brightgreen?style=for-the-badge&labelColor=1a1a2e" alt="Skills">
  <img src="https://img.shields.io/badge/Agents-12-blue?style=for-the-badge&labelColor=1a1a2e" alt="Agents">
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge&labelColor=1a1a2e" alt="License">
  <img src="https://img.shields.io/github/stars/kazemcodes/skill-tree?style=for-the-badge&labelColor=1a1a2e&color=ff6b35" alt="Stars">
  <img src="https://img.shields.io/github/last-commit/kazemcodes/skill-tree?style=for-the-badge&labelColor=1a1a2e" alt="Last Commit">
  <img src="https://img.shields.io/badge/PRs-Welcome-brightgreen?style=for-the-badge&labelColor=1a1a2e" alt="PRs Welcome">
  <img src="https://img.shields.io/badge/Contributions-welcome-orange?style=for-the-badge&labelColor=1a1a2e" alt="Contributions">
</p>

<h1 align="center">Skill Tree</h1>

<p align="center">
  <strong>85 battle-tested skills across 15 domains.</strong><br>
  <em>Unlock your AI agent's full potential — one skill at a time.</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Architecture-5-blueviolet?style=flat-square" alt="Architecture">
  <img src="https://img.shields.io/badge/Backend-6-blueviolet?style=flat-square" alt="Backend">
  <img src="https://img.shields.io/badge/DevOps-8-blueviolet?style=flat-square" alt="DevOps">
  <img src="https://img.shields.io/badge/Security-9-blueviolet?style=flat-square" alt="Security">
  <img src="https://img.shields.io/badge/Testing-10-blueviolet?style=flat-square" alt="Testing">
  <img src="https://img.shields.io/badge/API-5-blueviolet?style=flat-square" alt="API">
  <img src="https://img.shields.io/badge/Workflow-10-blueviolet?style=flat-square" alt="Workflow">
  <img src="https://img.shields.io/badge/Git-5-blueviolet?style=flat-square" alt="Git">
  <img src="https://img.shields.io/badge/Ponytail-6-ff6b35?style=flat-square" alt="Ponytail">
  <img src="https://img.shields.io/badge/Firecrawl-1-0ea5e9?style=flat-square" alt="Firecrawl">
  <img src="https://img.shields.io/badge/Productivity-10-blueviolet?style=flat-square" alt="Productivity">
</p>

---

> **100+ skills. One repo. Your AI agent's skill tree — unlock the capabilities it's missing.**

> **If you find this useful, please give it a star!** It helps others discover the project and motivates us to keep adding more skills. Click the ⭐ button at the top right of this page.

---

## The Idea

Think of your AI agent like a character in a game. Out of the box, it has basic stats — it can write code, but it doesn't know *how* to write *good* code. It doesn't know your security practices, your testing preferences, or your architecture style.

**Skill Tree** is a collection of skills harvested from across the internet — open-source repos, community contributions, and battle-tested workflows — all unified into one place. Like a skill tree in an RPG, you pick and unlock the skills your agent needs to level up.

Each skill is a `SKILL.md` file that teaches your agent a specific capability. Drop it into your agent's skills directory and it instantly knows how to do that thing. No configuration. No boilerplate. Just competence.

```
  Your Agent                    Skill Tree
  ┌─────────────┐              ┌─────────────────────────────────────┐
  │  Level 1    │    ──►       │  Architecture · Backend · DevOps    │
  │  Basic Code │              │  Security · Testing · API · Git     │
  │  No context │              │  Ponytail · Firecrawl · Workflow    │
  └─────────────┘              └─────────────────────────────────────┘
                                  Drop skills in. Agent levels up.
```

---

## How It Works

```
Your Agent (Level 1)
  ├── + senior-architect      → now designs systems
  ├── + ponytail              → now writes minimal code
  ├── + tdd                   → now writes tests first
  ├── + senior-secops         → now thinks about security
  ├── + firecrawl             → now searches the web
  └── + ...85 skills total
```

Skills load **progressively**. At session start, the agent sees only each skill's name and description (~100 tokens). The full instructions load only when the agent decides the skill is relevant. This lets a single agent host 85+ skills without bloating its context window.

---

## Quick Install

**Find your agent — copy, paste, done:**

| Agent | Install Path | One-liner |
|-------|-------------|-----------|
| Claude Code | `~/.claude/skills/` | `cp -r skills/* ~/.claude/skills/` |
| MiMo Code | `~/.config/mimocode/skills/` | `cp -r skills/* ~/.config/mimocode/skills/` |
| OpenAI Codex | `~/.codex/skills/` | `cp -r skills/* ~/.codex/skills/` |
| Gemini CLI | `~/.gemini/skills/` | `cp -r skills/* ~/.gemini/skills/` |
| Cursor | `.cursor/rules/` | See [Cursor](#cursor) |
| Windsurf | `.windsurf/skills/` | `cp -r skills/* .windsurf/skills/` |
| Kilo Code | `.kilocode/rules/` | See [Kilo Code](#kilo-code) |
| OpenCode | `.opencode/skills/` | `cp -r skills/* .opencode/skills/` |
| Augment | `.augment/rules/` | See [Augment](#augment) |
| Hermes Agent | `~/.hermes/skills/` | `cp -r skills/* ~/.hermes/skills/ai-skills-hub/` |
| Mistral Vibe | `~/.vibe/skills/` | `cp -r skills/* ~/.vibe/skills/ai-skills-hub/` |
| Antigravity | `~/.gemini/antigravity/skills/` | See [Antigravity](#antigravity) |

### Claude Code

```bash
git clone https://github.com/kazemcodes/skill-tree.git
cd skill-tree
cp -r skills/* ~/.claude/skills/
```

### MiMo Code

```bash
git clone https://github.com/kazemcodes/skill-tree.git
cd skill-tree
cp -r skills/* ~/.config/mimocode/skills/
```

### OpenAI Codex

```bash
git clone https://github.com/kazemcodes/skill-tree.git
cd skill-tree
cp -r skills/* ~/.codex/skills/
```

### Gemini CLI

```bash
git clone https://github.com/kazemcodes/skill-tree.git
cd skill-tree
cp -r skills/* ~/.gemini/skills/
```

### Cursor

```bash
git clone https://github.com/kazemcodes/skill-tree.git
cd skill-tree
# Copy skills as .mdc rules
for skill in skills/*/SKILL.md; do
  name=$(basename $(dirname "$skill"))
  mkdir -p .cursor/rules
  cp "$skill" ".cursor/rules/${name}.mdc"
done
```

### Windsurf

```bash
git clone https://github.com/kazemcodes/skill-tree.git
cd skill-tree
mkdir -p .windsurf/skills
cp -r skills/* .windsurf/skills/
```

### Aider

```bash
git clone https://github.com/kazemcodes/skill-tree.git
cd skill-tree
# Aider reads from CONVENTIONS.md in project root
cat skills/*/SKILL.md > CONVENTIONS.md
```

### Kilo Code

```bash
git clone https://github.com/kazemcodes/skill-tree.git
cd skill-tree
mkdir -p .kilocode/rules
for skill in skills/*/SKILL.md; do
  name=$(basename $(dirname "$skill"))
  cp "$skill" ".kilocode/rules/${name}.md"
done
```

### OpenCode

```bash
git clone https://github.com/kazemcodes/skill-tree.git
cd skill-tree
mkdir -p .opencode/skills
cp -r skills/* .opencode/skills/
```

### Augment

```bash
git clone https://github.com/kazemcodes/skill-tree.git
cd skill-tree
mkdir -p .augment/rules
for skill in skills/*/SKILL.md; do
  name=$(basename $(dirname "$skill"))
  cp "$skill" ".augment/rules/${name}.md"
done
```

### Hermes Agent

```bash
git clone https://github.com/kazemcodes/skill-tree.git
cd skill-tree
mkdir -p ~/.hermes/skills/ai-skills-hub
cp -r skills/* ~/.hermes/skills/ai-skills-hub/
```

### Mistral Vibe

```bash
git clone https://github.com/kazemcodes/skill-tree.git
cd skill-tree
mkdir -p ~/.vibe/skills/ai-skills-hub
cp -r skills/* ~/.vibe/skills/ai-skills-hub/
```

### Antigravity

```bash
git clone https://github.com/kazemcodes/skill-tree.git
cd skill-tree
mkdir -p ~/.gemini/antigravity/skills/ai-skills-hub
cp -r skills/* ~/.gemini/antigravity/skills/ai-skills-hub/
```

### Universal (Any Agent)

```bash
git clone https://github.com/kazemcodes/skill-tree.git
cd skill-tree
# Copy any skill folder to your agent's skills directory
cp -r skills/my-skill /path/to/your/agent/skills/
```

---

## Skills Overview

**85 skills across 15 domains:**

### Engineering — Architecture & Design

| Skill | Source | Description |
|-------|--------|-------------|
| [senior-architect](skills/senior-architect/) | mattpocock/skills | Architecture design, system reviews, ADRs, tech stack evaluation, diagrams |
| [software-architecture](skills/software-architecture/) | mattpocock/skills | Clean Architecture, SOLID principles, design patterns |
| [codebase-design](skills/codebase-design/) | mattpocock/skills | Shared vocabulary for designing deep modules |
| [domain-modeling](skills/domain-modeling/) | mattpocock/skills | Build and sharpen a project's domain model |
| [improve-codebase-architecture](skills/improve-codebase-architecture/) | mattpocock/skills | Scan codebase for deepening opportunities |

### Engineering — Backend & Fullstack

| Skill | Source | Description |
|-------|--------|-------------|
| [senior-backend](skills/senior-backend/) | alirezarezvani/claude-skills | REST APIs, microservices, database architectures, auth flows |
| [senior-fullstack](skills/senior-fullstack/) | alirezarezvani/claude-skills | Fullstack toolkit — Next.js, FastAPI, MERN, Django |
| [senior-frontend](skills/senior-frontend/) | alirezarezvani/claude-skills | React, Next.js, TypeScript, Tailwind CSS |
| [database-designer](skills/database-designer/) | alirezarezvani/claude-skills | Database schemas, migrations, SQL vs NoSQL |
| [database-schema-designer](skills/database-schema-designer/) | alirezarezvani/claude-skills | ERD diagrams, schema normalization |
| [sql-database-assistant](skills/sql-database-assistant/) | alirezarezvani/claude-skills | Write SQL queries, optimize performance |

### Engineering — DevOps & Infrastructure

| Skill | Source | Description |
|-------|--------|-------------|
| [senior-devops](skills/senior-devops/) | alirezarezvani/claude-skills | CI/CD, infrastructure automation, containerization |
| [ci-cd-pipeline-builder](skills/ci-cd-pipeline-builder/) | alirezarezvani/claude-skills | Generate CI/CD pipelines from project stack |
| [aws-solution-architect](skills/aws-solution-architect/) | alirezarezvani/claude-skills | AWS serverless architectures, CloudFormation |
| [monorepo-navigator](skills/monorepo-navigator/) | alirezarezvani/claude-skills | Turborepo, Nx, pnpm workspaces |
| [observability-designer](skills/observability-designer/) | alirezarezvani/claude-skills | SLI/SLO design, golden-signals monitoring |
| [runbook-generator](skills/runbook-generator/) | alirezarezvani/claude-skills | Generate operational runbooks |
| [migration-architect](skills/migration-architect/) | alirezarezvani/claude-skills | Zero-downtime migration planning |
| [env-secrets-manager](skills/env-secrets-manager/) | alirezarezvani/claude-skills | Environment-variable hygiene, secrets safety |

### Engineering — Security

| Skill | Source | Description |
|-------|--------|-------------|
| [senior-secops](skills/senior-secops/) | alirezarezvani/claude-skills | Application security, vulnerability management, compliance |
| [senior-security](skills/senior-security/) | alirezarezvani/claude-skills | STRIDE threat modeling, DREAD risk scoring |
| [cloud-security](skills/cloud-security/) | alirezarezvani/claude-skills | Cloud infrastructure security assessment |
| [skill-security-auditor](skills/skill-security-auditor/) | alirezarezvani/claude-skills | Security audit for AI agent skills |
| [red-team](skills/red-team/) | alirezarezvani/claude-skills | Authorized red team engagements |
| [incident-commander](skills/incident-commander/) | alirezarezvani/claude-skills | Incident response framework |
| [incident-response](skills/incident-response/) | alirezarezvani/claude-skills | Security incident classification, triage |
| [threat-detection](skills/threat-detection/) | alirezarezvani/claude-skills | Threat hunting, IOC analysis |
| [ship-gate](skills/ship-gate/) | alirezarezvani/claude-skills | Pre-production audit |

### Engineering — Code Quality & Testing

| Skill | Source | Description |
|-------|--------|-------------|
| [code-reviewer](skills/code-reviewer/) | alirezarezvani/claude-skills | PR review automation |
| [pr-review-expert](skills/pr-review-expert/) | alirezarezvani/claude-skills | PR review — blast radius, security scan |
| [senior-qa](skills/senior-qa/) | alirezarezvani/claude-skills | Unit, integration, E2E tests |
| [tdd](skills/tdd/) | mattpocock/skills | Test-driven development |
| [tdd-guide](skills/tdd-guide/) | alirezarezvani/claude-skills | TDD across Jest, Pytest, JUnit, Vitest |
| [playwright-testing](skills/playwright-testing/) | alirezarezvani/claude-skills | Browser automation testing |
| [tech-debt-tracker](skills/tech-debt-tracker/) | alirezarezvani/claude-skills | Scan for technical debt, score severity |
| [superpowers](skills/superpowers/) | mattpocock/skills | TDD, clean architecture, YAGNI enforcement |
| [setup-pre-commit](skills/setup-pre-commit/) | alirezarezvani/claude-skills | Husky pre-commit hooks |
| [resolving-merge-conflicts](skills/resolving-merge-conflicts/) | alirezarezvani/claude-skills | Resolve git merge/rebase conflicts |

### Engineering — API & Integration

| Skill | Source | Description |
|-------|--------|-------------|
| [api-design-reviewer](skills/api-design-reviewer/) | alirezarezvani/claude-skills | REST API design review |
| [api-test-suite-builder](skills/api-test-suite-builder/) | alirezarezvani/claude-skills | Generate API tests, contract tests |
| [mcp-builder](skills/mcp-builder/) | alirezarezvani/claude-skills | Create MCP servers |
| [dependency-auditor](skills/dependency-auditor/) | alirezarezvani/claude-skills | Audit dependencies, vulnerabilities |
| [performance-profiler](skills/performance-profiler/) | alirezarezvani/claude-skills | CPU, memory, I/O profiling |

### Engineering — Workflow & Process

| Skill | Source | Description |
|-------|--------|-------------|
| [get-shit-done](skills/get-shit-done/) | mattpocock/skills | Execute tasks efficiently — parallelize, batch, ship |
| [subagent-dev](skills/subagent-dev/) | alirezarezvani/claude-skills | Execute tasks in parallel using subagents |
| [spec-driven-workflow](skills/spec-driven-workflow/) | alirezarezvani/claude-skills | Write specs before code |
| [to-prd](skills/to-prd/) | alirezarezvani/claude-skills | Turn conversation into a PRD |
| [to-issues](skills/to-issues/) | alirezarezvani/claude-skills | Break plan into independently-grabbable issues |
| [implement](skills/implement/) | alirezarezvani/claude-skills | Implement work based on a PRD |
| [triage](skills/triage/) | alirezarezvani/claude-skills | Move issues through triage state machine |
| [focused-fix](skills/focused-fix/) | alirezarezvani/claude-skills | Systematic deep-dive repair |
| [diagnosing-bugs](skills/diagnosing-bugs/) | alirezarezvani/claude-skills | Diagnosis loop for hard bugs |
| [root-cause-tracing](skills/root-cause-tracing/) | alirezarezvani/claude-skills | Trace errors to original trigger |

### Engineering — Git & Version Control

| Skill | Source | Description |
|-------|--------|-------------|
| [git-worktree-manager](skills/git-worktree-manager/) | alirezarezvani/claude-skills | Parallel feature work, branch isolation |
| [git-worktrees](skills/git-worktrees/) | alirezarezvani/claude-skills | Create isolated git worktrees |
| [git-guardrails-claude-code](skills/git-guardrails-claude-code/) | alirezarezvani/claude-skills | Block dangerous git commands |
| [finish-branch](skills/finish-branch/) | alirezarezvani/claude-skills | Complete development, present merge options |
| [changelog-generator](skills/changelog-generator/) | alirezarezvani/claude-skills | Create changelogs from git commits |

### Engineering — Codebase & Documentation

| Skill | Source | Description |
|-------|--------|-------------|
| [codebase-onboarding](skills/codebase-onboarding/) | alirezarezvani/claude-skills | Generate onboarding documentation |
| [prompt-engineering](skills/prompt-engineering/) | alirezarezvani/claude-skills | Chain-of-thought, few-shot, role prompting |

### Ponytail — Minimal Code Philosophy

| Skill | Source | Description |
|-------|--------|-------------|
| [ponytail](skills/ponytail/) | DietrichGebert/ponytail | Lazy senior dev mode — YAGNI, stdlib first, minimal code |
| [ponytail-review](skills/ponytail-review/) | DietrichGebert/ponytail | Over-engineering diff review |
| [ponytail-audit](skills/ponytail-audit/) | DietrichGebert/ponytail | Whole-repo over-engineering audit |
| [ponytail-debt](skills/ponytail-debt/) | DietrichGebert/ponytail | Harvest ponytail shortcut comments into ledger |
| [ponytail-gain](skills/ponytail-gain/) | DietrichGebert/ponytail | Benchmark impact scoreboard |
| [ponytail-help](skills/ponytail-help/) | DietrichGebert/ponytail | Quick-reference for ponytail commands |

### Firecrawl — Web Intelligence

| Skill | Source | Description |
|-------|--------|-------------|
| [firecrawl](skills/firecrawl/) | firecrawl.dev | Web search, scraping, interaction, and workflow deliverables |

### Productivity

| Skill | Source | Description |
|-------|--------|-------------|
| [grill-me](skills/grill-me/) | mattpocock/skills | Relentless interview to sharpen a plan |
| [grill-with-docs](skills/grill-with-docs/) | mattpocock/skills | Grilling session that creates docs |
| [grilling](skills/grilling/) | mattpocock/skills | Interview user about a plan or design |
| [handoff](skills/handoff/) | mattpocock/skills | Compact conversation into handoff document |
| [reflect](skills/reflect/) | mattpocock/skills | Mid-conversation reflection — zoom out |
| [capture](skills/capture/) | mattpocock/skills | Capture brain dumps into structured system |
| [context-compress](skills/context-compress/) | alirezarezvani/claude-skills | Compress and optimize context |
| [context-mode](skills/context-mode/) | alirezarezvani/claude-skills | Manage context windows efficiently |
| [mem](skills/mem/) | alirezarezvani/claude-skills | Manage persistent memory |
| [teach](skills/teach/) | alirezarezvani/claude-skills | Teach user a new skill or concept |

### Prompting & Meta

| Skill | Source | Description |
|-------|--------|-------------|
| [writing-great-skills](skills/writing-great-skills/) | mattpocock/skills | Reference for writing and editing skills |
| [skill-creator](skills/skill-creator/) | alirezarezvani/claude-skills | Create and manage agent skills |
| [ask-matt](skills/ask-matt/) | mattpocock/skills | Router — ask which skill fits your situation |

### Tech Evaluation

| Skill | Source | Description |
|-------|--------|-------------|
| [tech-stack-evaluator](skills/tech-stack-evaluator/) | alirezarezvani/claude-skills | Technology stack evaluation, TCO analysis |

---

## Skill Format

Every skill follows the same structure:

```
skills/
  my-skill/
    SKILL.md          # Required: frontmatter + instructions
    scripts/          # Optional: helper scripts (Python/Shell)
    references/       # Optional: domain knowledge files
    templates/        # Optional: document templates
```

### SKILL.md Template

```markdown
---
name: my-skill-name
description: One-line description the agent uses to decide when to load this skill
---

# My Skill Name

Detailed description of the skill's purpose.

## When to Use

- Use case 1
- Use case 2

## Instructions

Step-by-step guidance for the agent.

## Examples

Concrete before/after examples.
```

### Frontmatter Fields

| Field | Required | Description |
|-------|----------|-------------|
| `name` | Yes | Unique skill identifier (kebab-case) |
| `description` | Yes | One-line description — agent uses this to decide when to load |
| `disable-model-invocation` | No | If `true`, skill is only user-invoked (e.g. `/grill-me`) |

---

## How Skills Load

Skills use **progressive loading**:

1. **Session start** — agent sees only name + description (~100 tokens per skill)
2. **Task matching** — agent reads description to decide if skill is relevant
3. **Full load** — SKILL.md body loads only when activated (~5000 tokens max)
4. **On-demand** — scripts/, references/, templates/ load only when needed

This lets a single agent host 85+ skills without context bloat.

---

## Creating Your Own Skill

1. Create a folder under `skills/`:
   ```bash
   mkdir skills/my-new-skill
   ```

2. Add `SKILL.md` with frontmatter:
   ```markdown
   ---
   name: my-new-skill
   description: What this skill does and when to use it
   ---
   # My New Skill
   ## When to Use
   - When the user asks to...
   ## Instructions
   1. Step one
   2. Step two
   ```

3. Optionally add `scripts/`, `references/`, or `templates/` folders.

4. Test it by copying to your agent's skills directory.

---

## Sources

Skills in this tree are harvested from:

| Source | Skills | Description |
|--------|--------|-------------|
| [mattpocock/skills](https://github.com/mattpocock/skills) | 12 | Skills for real engineers — TDD, grilling, codebase design |
| [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) | 60+ | 345+ Claude Code skills across 17 domains |
| [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail) | 6 | Lazy senior dev philosophy — minimal code, YAGNI |
| [firecrawl.dev](https://github.com/firecrawl/skills) | 1 | Web intelligence — search, scrape, interact |

---

## Contributing

Contributions welcome! To add a skill:

1. Fork this repository
2. Create your skill under `skills/your-skill-name/`
3. Follow the [SKILL.md format](#skill-format)
4. Ensure `description` is clear enough for agents to auto-select
5. Submit a pull request

### Quality Checklist

- [ ] `SKILL.md` has valid YAML frontmatter with `name` and `description`
- [ ] `description` is specific enough for agent matching (not generic)
- [ ] Instructions are written for the agent, not the user
- [ ] Includes concrete examples where applicable
- [ ] No secrets, API keys, or sensitive data in any files
- [ ] Scripts are dependency-free (stdlib only) when possible

---

## License

MIT — see [LICENSE](LICENSE) for details.

---

<p align="center">
  <strong>Built for the AI coding agent ecosystem.</strong><br>
  Works with <strong>Claude Code</strong>, <strong>MiMo Code</strong>, <strong>OpenAI Codex</strong>, <strong>Gemini CLI</strong>, <strong>Cursor</strong>, <strong>Windsurf</strong>, <strong>Aider</strong>, and more.<br><br>
  <img src="https://img.shields.io/badge/Made_with-❤️-red?style=for-the-badge&labelColor=1a1a2e" alt="Made with love">
  <img src="https://img.shields.io/badge/Level_up_your_agent-Skill_Tree-brightgreen?style=for-the-badge&labelColor=1a1a2e" alt="Skill Tree">
</p>
