---
name: root-cause-tracing
description: Trace errors deep in execution back to their original trigger — find the root cause, not just the symptom
---

# Root Cause Tracing

When errors occur deep in execution, trace back to find the original trigger.

## When to Use

- Error message is far from actual cause
- Intermittent failures with no obvious trigger
- Stack trace leads through framework code
- Multiple related failures cascading
- "Something broke" but unclear what

## Process

### 1. Capture the Error State

```
What is the error message?
What is the stack trace?
When does it occur (always, sometimes, under load)?
What changed recently?
```

### 2. Trace Backwards

Follow the error upstream:

```
Error at Layer A
  ← caused by bad input from Layer B
    ← caused by unexpected state from Layer C
      ← caused by missing initialization in Layer D (ROOT CAUSE)
```

**Techniques:**
- **Binary search**: Comment out half the code path, does error still occur?
- **Last known good**: Find when it last worked, diff that commit
- **Data flow**: Follow the data from input to error point
- **Timing**: Add logging at each layer, narrow the window

### 3. Identify Root Cause Categories

| Category | Signs |
|----------|-------|
| **State** | Race condition, stale data, missing initialization |
| **Input** | Unexpected null, wrong type, boundary value |
| **Configuration** | Wrong env var, missing dependency, version mismatch |
| **Logic** | Off-by-one, wrong condition, missing case |
| **Integration** | API changed, timeout, permission denied |

### 4. Verify Root Cause

```
Can you reproduce with this root cause?
If you fix ONLY this, does everything work?
Are there other paths that trigger the same root cause?
```

### 5. Fix and Prevent

- Fix root cause, not symptom
- Add test that catches this specific failure
- Consider if similar patterns exist elsewhere

## Techniques

### Binary Search Bisection

```bash
# Find the commit that introduced the bug
git bisect start
git bisect bad          # current commit
git bisect good <hash>  # last known working

# For each commit, test if bug exists
git bisect run npm test
```

### Strategic Logging

```python
# Add trace points
def process(data):
    logger.debug(f"process input: {data}")
    result = validate(data)
    logger.debug(f"validate result: {result}")
    return transform(result)
```

### State Snapshots

```python
# Capture state at boundaries
state_before = snapshot(system)
result = operation()
state_after = snapshot(system)
diff = compare(state_before, state_after)
```

## Common Root Causes

| Symptom | Likely Root Cause |
|---------|-------------------|
| "Cannot read property of undefined" | Missing initialization or wrong order |
| Intermittent 500 errors | Race condition or resource exhaustion |
| Works in dev, fails in prod | Environment difference |
| Slow then crashes | Memory leak or connection pool exhaustion |
| Works for small data, fails for large | Missing pagination or timeout |

## Red Flags

**Don't:**
- Fix symptoms without finding cause
- Assume first error is the root cause
- Skip reading the full stack trace
- Ignore "works on my machine" — investigate why

**Do:**
- Read error message completely
- Follow stack trace to origin
- Check what changed recently
- Verify fix resolves the actual root cause
