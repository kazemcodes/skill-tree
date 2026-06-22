---
name: software-architecture
description: Apply Clean Architecture, SOLID principles, and design patterns — evaluate trade-offs and recommend architectural decisions
---

# Software Architecture

Apply proven architectural patterns. Make informed trade-off decisions.

## When to Use

- Designing new systems or major features
- Evaluating architectural trade-offs
- Refactoring toward better separation of concerns
- Reviewing system design decisions
- Choosing between patterns (microservices vs monolith, etc.)

## Core Principles

### SOLID

| Principle | Meaning |
|-----------|---------|
| **S**ingle Responsibility | One reason to change |
| **O**pen/Closed | Open for extension, closed for modification |
| **L**iskov Substitution | Subtypes must be substitutable |
| **I**nterface Segregation | Many specific interfaces > one general |
| **D**ependency Inversion | Depend on abstractions, not concretions |

### Clean Architecture Layers

```
┌─────────────────────────────┐
│     Entities (Domain)       │  ← Business objects
├─────────────────────────────┤
│   Use Cases (Application)   │  ← Business rules
├─────────────────────────────┤
│  Interface Adapters         │  ← Controllers, Gateways
├─────────────────────────────┤
│  Frameworks & Drivers       │  ← DB, Web, UI
└─────────────────────────────┘
```

**Rule:** Dependencies point inward. Outer layers know about inner layers, never reverse.

### Key Patterns

| Pattern | When to Use |
|---------|-------------|
| **Repository** | Abstract data access behind interface |
| **Use Case** | Encapsulate business logic |
| **Strategy** | Multiple algorithms, swap at runtime |
| **Observer** | Decouple event producers from consumers |
| **Facade** | Simplify complex subsystems |
| **Factory** | Complex object creation logic |

## Decision Framework

```
1. What is the core domain logic?
   → Isolate in entities/use cases

2. What are the external dependencies?
   → Push to boundaries, depend on interfaces

3. What changes most often?
   → Keep it replaceable

4. What is the team's expertise?
   → Prefer patterns they know

5. What are the performance constraints?
   → Don't over-architect for scale you don't have
```

## Anti-Patterns

| Pattern | Problem |
|---------|---------|
| God class | One class does everything |
| Anemic domain model | Entities with only getters/setters |
| Dependency hell | Circular dependencies |
| premature abstraction | Abstract before patterns emerge |
| Big ball of mud | No clear architecture at all |

## When to Choose What

**Monolith first:**
- Small team (< 5 engineers)
- Early product stage
- Simple domain

**Modular monolith:**
- Medium team, growing complexity
- Want modularity without distributed overhead

**Microservices:**
- Large team, independent deploy needed
- Different scaling requirements per service
- Mature domain with clear boundaries
