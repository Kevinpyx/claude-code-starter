---
name: review
description: Code review — check current code changes across three dimensions: security, readability, and potential bugs
---

# Code Review

Review the current uncommitted code changes to help the user catch issues before committing.

## Steps

### 1. Get the changes

Run `git diff` and `git diff --staged` to get all uncommitted changes.

If there are no changes, tell the user "No code changes to review" and stop.

### 2. Review file by file

For each changed file, check across these three dimensions:

**Security**
- Any hardcoded secrets, passwords, or tokens
- SQL injection, XSS, or other security vulnerabilities
- Unsafe file operations or command execution
- User input not being validated

**Readability**
- Are variable and function names clear
- Is the logic easy to follow
- Any overly complex nesting or excessively long functions
- Is it consistent with the existing project style

**Potential Bugs**
- Edge cases handled (null values, empty lists, out-of-range inputs)
- Error handling complete (try/catch used correctly)
- Logic errors (conditions, loop termination)
- Could this break existing functionality

### 3. Output the review report

Output a concise review report in English:

```
## Review Results

### Must Fix
- [filename:line] Description of the issue + suggested fix

### Suggestions
- [filename:line] Description of the improvement

### Looks Good
- List files that passed review
```

Rules:
- Only report issues that are genuinely worth fixing — don't nitpick
- Give a specific fix suggestion for each issue, not just "there's a problem here"
- If the code looks fine, just say "Code looks good, ready to commit"
- Do not suggest adding comments, docs, or refactors unrelated to the changes
