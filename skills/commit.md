---
name: commit
description: Safe commit — automatically checks code style, scans for sensitive info, and generates a proper commit message
---

# Safe Commit Process

Follow these steps in order. Each step must be completed before moving to the next.

## Steps

### 1. Check for changes to commit

Run `git status` to see the current state. If there are no changes, tell the user "Nothing to commit" and stop.

### 2. Run lint check

Read the lint command from CLAUDE.md. If a lint command is configured (not "none"), run it.

- If lint passes: continue to the next step
- If lint fails: show the errors and ask the user "Should I fix these for you?"
  - Fix them and re-run lint until it passes
- If no lint command is configured: skip this step

### 3. Scan for sensitive information

Check all staged files for:
- `.env` files or lines containing `API_KEY`, `SECRET`, `PASSWORD`, `TOKEN` assignments
- Hardcoded secrets (long strings that look like keys or tokens)
- Private key files (.pem, .key)

If sensitive content is found:
- List the problematic files and lines
- Suggest the user remove those files or use environment variables instead
- Do not proceed with the commit until the user confirms the issue is resolved

If nothing is found: continue to the next step.

### 4. Show a change summary

Show a summary of `git diff --staged` (which files changed and roughly what). No need to show the full diff — a concise summary is enough.

### 5. Generate a commit message

Based on the changes, generate a commit message following the convention:
- Format: `type: short description`
- Type: feat / fix / docs / refactor / test / chore
- Description: short and clear, in English

Show the generated message and ask the user:
> Commit message: `xxx`
> Confirm commit? You can say "yes" or tell me what to change.

### 6. Execute the commit

Once the user confirms, run `git commit`. Show the result.
