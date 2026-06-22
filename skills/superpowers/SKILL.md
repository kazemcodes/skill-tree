---
name: superpowers
description: Enforce TDD, clean architecture, YAGNI, and evidence-based development from the Superpowers framework
---

# Superpowers

Based on [obra/superpowers](https://github.com/obra/superpowers). Non-negotiable engineering discipline.

## TDD — Iron Law

```
NO PRODUCTION CODE WITHOUT A FAILING TEST FIRST
```

Write code before test? **Delete it. Start over. No exceptions.**

### RED → GREEN → REFACTOR

1. **RED**: Write one failing test. Watch it fail. Confirm failure message is expected.
2. **GREEN**: Write minimal code to pass. Don't add features, don't refactor.
3. **REFACTOR**: Clean up while keeping tests green.

### Rules

- Watch EVERY test fail before implementing
- If test passes immediately → you're testing existing behavior → fix the test
- Write minimal code to pass. Nothing extra.
- After green: remove duplication, improve names, extract helpers
- "Tests after achieve the same goals" is FALSE

### Red Flags — Delete and Restart

- Code before test
- Test passes immediately
- "I'll test after"
- "Too simple to test"
- "Keep as reference"
- "TDD is dogmatic"

## Clean Architecture

- Break systems into smaller units with one clear purpose
- Communication through well-defined interfaces
- Each unit: what does it do, how do you use it, what does it depend on?
- Follow existing codebase patterns — never introduce alien abstractions
- **No stubs or placeholder code in production**

## YAGNI (You Aren't Gonna Need It)

- Remove unnecessary features ruthlessly
- Don't add error handling for scenarios that can't happen
- Don't add feature flags or backwards-compatibility shims
- Three similar lines > premature abstraction

## Evidence Over Claims

- Verify before declaring success
- Run tests and confirm — don't assume
- When stuck: write wished-for API, write assertion first
- "Manually tested" ≠ comprehensive

## Anti-Patterns

| Pattern | Why It's Wrong |
|---------|---------------|
| Writing code before tests | Violates iron law |
| Test passes immediately | Testing existing behavior |
| Mocking without understanding | Hides real dependencies |
| "I'll test after" | Proves nothing |
| Over-engineering | Violates YAGNI |

## Verification Checklist

Before marking done:

- [ ] Every new function has a test
- [ ] Watched each test fail before implementing
- [ ] Each test failed for expected reason
- [ ] Wrote minimal code to pass
- [ ] All tests pass
- [ ] Output pristine (no errors/warnings)
- [ ] Tests use real code (mocks only if unavoidable)
- [ ] Edge cases covered
