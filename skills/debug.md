---
name: debug
description: Systematic debugging — use the scientific method to find bugs, no guessing, step-by-step root cause analysis
---

# Systematic Debugging

Find the root cause using a scientific approach. No guessing. Every step must be evidence-based.

## Core Principles

- No "let me just try changing this" — every change must be based on a clear hypothesis
- No skipping steps — follow the steps in order
- Record every finding — avoid going in circles

## Steps

### 1. Understand the problem

Ask the user:
> What's the problem? You can describe what's happening, paste the error message, or tell me which feature isn't working.

Collect:
- Error messages (full logs or screenshots)
- When it started happening
- What changed before it started
- What the expected behavior is

### 2. Reproduce the problem

- Find the relevant code files, read and understand the context
- Try to reproduce the issue (run the code, run tests)
- Confirm the problem exists and record the reproduction steps

If it can't be reproduced, tell the user and ask for more information. Do not guess at a fix for an unreproduced issue.

### 3. Identify the root cause

- Based on the error and code logic, form a hypothesis
- Use the smallest possible test to confirm or rule out the hypothesis (add logs, breakpoints, unit tests)
- If the first hypothesis is wrong, record why and form the next one
- Narrow down until the root cause is found

Log format:
```
Hypothesis 1: xxx
Verification: xxx
Result: Confirmed / Ruled out (Reason: xxx)
```

### 4. Fix

- Apply the smallest change that fixes the problem
- Explain what was changed and why
- Run tests to confirm the fix works
- Check whether the fix could introduce new issues

### 5. Verify

- Re-run the reproduction steps to confirm the issue is resolved
- Run the full test suite to confirm nothing else is broken
- Tell the user the fix is complete, summarize the root cause and the fix
