---
name: prompt-engineering
description: Apply prompt engineering techniques — chain-of-thought, few-shot, role prompting, structured output, and Anthropic best practices
---

# Prompt Engineering

Craft effective prompts for LLMs using proven techniques.

## When to Use

- Writing system prompts for agents
- Designing few-shot examples
- Structuring outputs from LLMs
- Improving prompt quality

## Core Techniques

### Role Prompting

```
You are a senior security engineer reviewing code for vulnerabilities.
Focus on OWASP Top 10 issues. Be specific about line numbers.
```

### Chain-of-Thought

```
Think through this step by step:
1. What is the input?
2. What rules apply?
3. What is the output?
```

### Few-Shot

```
Convert these natural language queries to SQL:

Q: "Show all users who signed up this week"
A: SELECT * FROM users WHERE created_at >= DATE('now', '-7 days')

Q: "Find orders over $100"
A: SELECT * FROM orders WHERE amount > 100

Q: "List active subscriptions"
A: 
```

### Structured Output

```
Respond in this exact JSON format:
{
  "summary": "one line summary",
  "issues": [{"severity": "high|medium|low", "file": "path", "description": "..."}],
  "recommendation": "what to do"
}
```

## Anthropic Best Practices

1. **Be specific** — "Write a Python function that..." not "Write some code"
2. **Use XML tags** — `<instructions>`, `<example>`, `<context>` for structure
3. **Provide examples** — Show, don't just tell
4. **Set constraints** — "Respond in under 100 words"
5. **Use delimiters** — Separate context from instructions clearly

## Anti-Patterns

| Pattern | Problem |
|---------|---------|
| Vague instructions | Model guesses intent |
| No examples | Inconsistent output format |
| Too many constraints | Model can't satisfy all |
| Ambiguous "good" | No way to measure success |
| Mixing languages | Confusing instructions |

## Output Control

```
# Force specific format
Respond ONLY with valid JSON. No explanation, no markdown.

# Limit length
In exactly 3 bullet points...

# Require citations
Cite sources with [Source: URL] format.
```
