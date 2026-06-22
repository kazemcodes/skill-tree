# AI Skills Hub

[![Skills](https://img.shields.io/badge/Skills-78-brightgreen?style=for-the-badge)](#skills-overview)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

> **78 production-ready AI agent skills** — reusable instruction packages that give coding agents domain expertise they don't have out of the box. Works with **Claude Code**, **MiMo Code**, **OpenAI Codex**, **Gemini CLI**, **Cursor**, and more.

---

## What Are AI Skills?

AI Skills are modular instruction packages that teach an agent how to handle a specific class of tasks. Each skill is a folder containing a `SKILL.md` file with YAML frontmatter (name, description) and Markdown instructions, optionally bundled with scripts, references, and assets.

Skills load **progressively**. At session start, the agent sees only each skill's name and description (~100 tokens). The full SKILL.md body loads only when the agent decides the skill is relevant. This lets a single agent host hundreds of skills without bloating its context window.

### Skills vs Agents vs Personas

| Concept | Purpose | Scope | Example |
|---------|---------|-------|---------|
| **Skills** | How to execute a task | Single domain | "Follow these steps for TDD" |
| **Agents** | What task to do | Single domain | "Run a security audit" |
| **Personas** | Who is thinking | Cross-domain | "Think like a startup CTO" |

---

## Quick Install

### Claude Code

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/ai-skills-hub.git
cd ai-skills-hub

# Copy skills to your Claude Code directory
cp -r skills/* ~/.claude/skills/
```

### MiMo Code

```bash
# Copy skills to MiMo Code directory
cp -r skills/* ~/.config/mimocode/skills/
```

### Manual Installation

```bash
git clone https://github.com/YOUR_USERNAME/ai-skills-hub.git
# Copy any skill folder to your agent's skills directory
```

---

## Skills Overview

**78 skills across 14 domains:**

### Engineering — Architecture & Design

| Skill | Description |
|-------|-------------|
| [senior-architect](skills/senior-architect/) | Architecture design, system reviews, ADRs, tech stack evaluation, diagrams (Mermaid/PlantUML/ASCII) |
| [software-architecture](skills/software-architecture/) | Clean Architecture, SOLID principles, design patterns — evaluate trade-offs and recommend decisions |
| [codebase-design](skills/codebase-design/) | Shared vocabulary for designing deep modules — interfaces, seams, testability |
| [domain-modeling](skills/domain-modeling/) | Build and sharpen a project's domain model, record architectural decisions |
| [improve-codebase-architecture](skills/improve-codebase-architecture/) | Scan codebase for deepening opportunities, visual HTML report, grill through picks |

### Engineering — Backend & Fullstack

| Skill | Description |
|-------|-------------|
| [senior-backend](skills/senior-backend/) | REST APIs, microservices, database architectures, auth flows, security hardening |
| [senior-fullstack](skills/senior-fullstack/) | Fullstack toolkit — Next.js, FastAPI, MERN, Django scaffolding, code quality analysis |
| [senior-frontend](skills/senior-frontend/) | React, Next.js, TypeScript, Tailwind CSS — components, performance, accessibility |
| [database-designer](skills/database-designer/) | Database schemas, data migrations, query optimization, SQL vs NoSQL decisions |
| [database-schema-designer](skills/database-schema-designer/) | ERD diagrams, schema normalization, table relationships, schema migrations |
| [sql-database-assistant](skills/sql-database-assistant/) | Write SQL queries, optimize performance, generate migrations, explore schemas |

### Engineering — DevOps & Infrastructure

| Skill | Description |
|-------|-------------|
| [senior-devops](skills/senior-devops/) | CI/CD, infrastructure automation, containerization, cloud platforms (AWS/GCP/Azure) |
| [ci-cd-pipeline-builder](skills/ci-cd-pipeline-builder/) | Generate CI/CD pipelines from detected project stack — GitHub Actions, GitLab CI |
| [aws-solution-architect](skills/aws-solution-architect/) | AWS serverless architectures, CloudFormation, Lambda, API Gateway, DynamoDB |
| [monorepo-navigator](skills/monorepo-navigator/) | Turborepo, Nx, pnpm workspaces — cross-package impact analysis, remote caching |
| [observability-designer](skills/observability-designer/) | SLI/SLO design, golden-signals monitoring, alert optimization, dashboards |
| [runbook-generator](skills/runbook-generator/) | Generate operational runbooks — deployment, incident response, maintenance workflows |
| [migration-architect](skills/migration-architect/) | Zero-downtime migration planning, compatibility validation, rollback strategies |
| [env-secrets-manager](skills/env-secrets-manager/) | Environment-variable hygiene, secrets safety, leak detection, rotation readiness |

### Engineering — Security

| Skill | Description |
|-------|-------------|
| [senior-secops](skills/senior-secops/) | Application security, vulnerability management, compliance (SOC2/PCI-DSS/HIPAA/GDPR) |
| [senior-security](skills/senior-security/) | STRIDE threat modeling, DREAD risk scoring, data-flow-diagram threat analysis |
| [cloud-security](skills/cloud-security/) | Cloud infrastructure security — IAM escalation, S3 exposure, security groups, IaC gaps |
| [skill-security-auditor](skills/skill-security-auditor/) | Security audit and vulnerability scanner for AI agent skills before installation |
| [red-team](skills/red-team/) | Authorized red team engagements, attack path analysis, offensive security simulations |
| [incident-commander](skills/incident-commander/) | Incident response framework — severity classification, timeline, post-incident review |
| [incident-response](skills/incident-response/) | Security incident classification, triage, escalation paths, forensic evidence collection |
| [threat-detection](skills/threat-detection/) | Threat hunting, IOC analysis, behavioral anomaly detection, MITRE ATT&CK mapping |
| [ship-gate](skills/ship-gate/) | Pre-production audit — security, database, deployment, code quality, AI/LLM, dependencies |

### Engineering — Code Quality & Testing

| Skill | Description |
|-------|-------------|
| [code-reviewer](skills/code-reviewer/) | PR review automation — complexity analysis, SOLID violations, code smells, review reports |
| [pr-review-expert](skills/pr-review-expert/) | PR review — blast radius analysis, security scan, coverage delta |
| [senior-qa](skills/senior-qa/) | Unit tests, integration tests, E2E tests — Jest, React Testing Library, Playwright, MSW |
| [tdd](skills/tdd/) | Test-driven development — red-green-refactor loop, integration tests |
| [tdd-guide](skills/tdd-guide/) | TDD across Jest, Pytest, JUnit, Vitest, Mocha — test writing, coverage, mocks |
| [playwright-testing](skills/playwright-testing/) | Browser automation testing — verify UI, capture screenshots, debug |
| [tech-debt-tracker](skills/tech-debt-tracker/) | Scan for technical debt, score severity, track trends, remediation plans |
| [superpowers](skills/superpowers/) | Enforce TDD, clean architecture, YAGNI, evidence-based development |
| [setup-pre-commit](skills/setup-pre-commit/) | Husky pre-commit hooks — lint-staged, Prettier, type checking, tests |
| [resolving-merge-conflicts](skills/resolving-merge-conflicts/) | Resolve in-progress git merge/rebase conflicts |

### Engineering — API & Integration

| Skill | Description |
|-------|-------------|
| [api-design-reviewer](skills/api-design-reviewer/) | REST API design review — linting, breaking-change detection, design scorecards |
| [api-test-suite-builder](skills/api-test-suite-builder/) | Generate API tests, integration test suites, contract tests |
| [mcp-builder](skills/mcp-builder/) | Create MCP servers — Python FastMCP, TypeScript MCP SDK |
| [dependency-auditor](skills/dependency-auditor/) | Audit dependencies — vulnerabilities, license conflicts, safe-upgrade paths |
| [performance-profiler](skills/performance-profiler/) | Node.js, Python, Go profiling — CPU, memory, I/O bottlenecks, flamegraphs |

### Engineering — Workflow & Process

| Skill | Description |
|-------|-------------|
| [get-shit-done](skills/get-shit-done/) | Execute tasks efficiently — parallelize, batch, ship |
| [subagent-dev](skills/subagent-dev/) | Execute independent tasks in parallel using subagents |
| [spec-driven-workflow](skills/spec-driven-workflow/) | Write specs before code, define acceptance criteria, plan before implementation |
| [to-prd](skills/to-prd/) | Turn conversation into a PRD and publish to issue tracker |
| [to-issues](skills/to-issues/) | Break plan/spec/PRD into independently-grabbable issues |
| [implement](skills/implement/) | Implement work based on a PRD or set of issues |
| [triage](skills/triage/) | Move issues through a state machine of triage roles |
| [focused-fix](skills/focused-fix/) | Systematic deep-dive repair across all files and dependencies |
| [diagnosing-bugs](skills/diagnosing-bugs/) | Diagnosis loop for hard bugs and performance regressions |
| [root-cause-tracing](skills/root-cause-tracing/) | Trace errors back to original trigger — find root cause, not symptom |

### Engineering — Git & Version Control

| Skill | Description |
|-------|-------------|
| [git-worktree-manager](skills/git-worktree-manager/) | Parallel feature work — branch isolation, port allocation, env sync |
| [git-worktrees](skills/git-worktrees/) | Create isolated git worktrees for feature work |
| [git-guardrails-claude-code](skills/git-guardrails-claude-code/) | Block dangerous git commands (push, reset --hard, clean) before execution |
| [finish-branch](skills/finish-branch/) | Complete development — verify tests, present merge/PR/discard options |
| [changelog-generator](skills/changelog-generator/) | Create user-facing changelogs from git commits |

### Engineering — Codebase & Documentation

| Skill | Description |
|-------|-------------|
| [codebase-onboarding](skills/codebase-onboarding/) | Analyze codebase, generate onboarding documentation for engineers |
| [prompt-engineering](skills/prompt-engineering/) | Chain-of-thought, few-shot, role prompting, structured output, Anthropic best practices |

### Productivity

| Skill | Description |
|-------|-------------|
| [grill-me](skills/grill-me/) | Relentless interview to sharpen a plan or design |
| [grill-with-docs](skills/grill-with-docs/) | Grilling session that also creates docs (ADRs, glossary) as we go |
| [grilling](skills/grilling/) | Interview user relentlessly about a plan or design |
| [handoff](skills/handoff/) | Compact conversation into a handoff document for another agent |
| [reflect](skills/reflect/) | Mid-conversation reflection — zoom out, reassess direction, assumptions, bias |
| [capture](skills/capture/) | Capture chaotic brain dumps into structured, actionable system |
| [context-compress](skills/context-compress/) | Compress and optimize context — summarize, layer by relevance, preserve critical facts |
| [context-mode](skills/context-mode/) | Manage context windows efficiently — summarize, compress, preserve across sessions |
| [mem](skills/mem/) | Manage persistent memory — project context, session notes, cross-session knowledge |
| [teach](skills/teach/) | Teach user a new skill or concept within the workspace |

### Prompting & Meta

| Skill | Description |
|-------|-------------|
| [writing-great-skills](skills/writing-great-skills/) | Reference for writing and editing skills — vocabulary and principles |
| [skill-creator](skills/skill-creator/) | Create, edit, and manage MiMo Code agent skills with proper SKILL.md format |
| [ask-matt](skills/ask-matt/) | Ask which skill or flow fits your situation — a router skill |

### Tech Evaluation

| Skill | Description |
|-------|-------------|
| [tech-stack-evaluator](skills/tech-stack-evaluator/) | Technology stack evaluation — TCO analysis, security assessment, ecosystem health |

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

This lets a single agent host 78+ skills without context bloat.

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

## Related Projects

| Project | Description |
|---------|-------------|
| [mattpocock/skills](https://github.com/mattpocock/skills) | Skills for real engineers — TDD, grilling, codebase design |
| [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) | 345+ Claude Code skills across 17 domains |
| [ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) | Curated list of 1000+ Claude skills and plugins |
| [anthropics/skills](https://github.com/anthropics/skills) | Official Anthropic skills repository |

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

**Built for the AI coding agent ecosystem.** Works with Claude Code, MiMo Code, OpenAI Codex, Gemini CLI, Cursor, Windsurf, Aider, and more.
