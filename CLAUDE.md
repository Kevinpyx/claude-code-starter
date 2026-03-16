# Project Rules

<!-- This file tells Claude Code how to work in your project.
     Replace all {{}} placeholders with your project information.
     You can run /setup to let Claude fill them in automatically. -->

## Response Language & Style

<!-- Controls how Claude responds -->

- Always respond in English
- Be concise and direct, no filler words
- Do not use emoji in responses
- Act first, explain later (if needed)

## Project Info

<!-- Tell Claude what your project is so it can better understand the context -->

- Project name: {{project_name}}
- Tech stack: {{tech_stack}}
- Project description: {{project_description}}
- Source directory: {{source_dir}}
- Test directory: {{test_dir}}
- Lint command: {{lint_command}}

## Thinking Approach

<!-- Encourage Claude to think with higher quality, not just blindly execute -->

### First Principles
- When facing a problem, reason from fundamental facts — don't just copy "how everyone else does it"
- For every technical decision, ask: why do it this way? Is there a simpler approach?
- If the only reason for a solution is "everyone does it this way", reconsider

### KISS Principle
- Keep It Simple, Stupid — always choose the simplest solution
- If 10 lines can solve it, don't write 50
- If one function can solve it, don't split it into three classes

### 80/20 Rule
- Complete the most important 20% of features first to solve 80% of the problem
- Don't chase perfection from the start — get it running, then optimize
- MVP first: a working prototype > a perfect design

### Feynman Technique
- When asked about a concept or technology, explain it in the simplest language possible, as if teaching someone who knows nothing
- Avoid jargon — use analogies and examples instead
- If you can't explain it simply, you don't truly understand it

## Code Standards

<!-- Enforce consistent code style so Claude doesn't write differently each time -->

### Naming Conventions
- Variables and functions: follow the existing naming style in the project (e.g. camelCase or snake_case)
- File naming: stay consistent with existing project files
- If no style is established, default to the language community's common conventions

### Commit Message Format
- Format: `type: short description`
- Allowed types: feat (new feature), fix (bug fix), docs (documentation), refactor, test, chore
- Examples: `feat: add user login`, `fix: fix list sort order`

### Branch Strategy
- Main branch: main
- New features or fixes: create feature/xxx or fix/xxx branches from main
- Merge back into main when done

## Security Rules

<!-- These rules must never be broken — they prevent leaking secrets or destructive mistakes -->

### Never Commit Sensitive Files
- Never commit .env files, API keys, passwords, or tokens to git
- If sensitive content is found in staged files, warn immediately and remove it
- Make sure .gitignore covers all sensitive file types

### Pre-Push Security Check
- Before every push, scan code for hardcoded secrets, passwords, or tokens
- Check for debug logs or temp files accidentally staged
- Fix any issues before pushing

### No Destructive Operations Without Confirmation
- Without my explicit approval, never run:
  - `rm -rf` (recursive delete)
  - `git push --force` (force push)
  - `git reset --hard` (discard all changes)
  - `git checkout .` (discard uncommitted changes)
  - Deleting branches or database tables

## Workflow

<!-- Ensure Claude does things in the right order to reduce mistakes -->

### Read Before Editing
- Before modifying any file, read and understand the existing code
- Do not suggest changes to code you haven't read
- Understand the context before making any changes

### Check Before Committing
- After every code change, run {{lint_command}} to check code style
- Run tests to ensure nothing is broken
- For multi-file changes, do a self-review before committing

### Keep It Simple
- Only do what is asked — no over-engineering
- Do not add unrequested features, comments, or refactors
- If a simple solution solves the problem, don't use a complex one

## Don'ts

<!-- Explicitly tell Claude what not to do — clearer than just prohibiting it.
     Keep adding to this based on your experience. -->

- Do not suggest changes to code you haven't read
- Do not change too many files at once — commit in batches
- Do not add new dependencies without asking me first
- Do not write comments in languages other than English (unless I ask)
- Do not re-explain what you just did — I can see the diff
- (Add your own don'ts here)

## Known Pitfalls

<!-- Record project-specific gotchas here so Claude doesn't repeat the same mistakes.
     Format: brief description of the problem + correct approach. -->

- Example: After modifying .env.example, always update the env variable docs as well
- Example: Never manually edit database migration files — use the framework CLI to generate them
- (Add your own project-specific pitfalls here)
