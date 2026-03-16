# Claude Code Starter Template

A ready-to-use CLAUDE.md template and practical Skills to make Claude Code work better for your project.

## How to Use

### Step 1: Download the template

Open Claude Code in your project and type:

```
Help me download CLAUDE.md from https://github.com/lighthouse-strategy/claude-code-starter to the project root, and the skills folder to .claude/skills/
```

### Step 2: Configure project info

```
/setup
```

Claude will ask you about your project step by step and automatically fill in the placeholders.

## What's Included

### CLAUDE.md — Project Rules File

| Section | Purpose |
|---------|---------|
| Response Language & Style | Keep Claude's responses in English and concise |
| Project Info | Tell Claude what your project is |
| Code Standards | Unified naming, commit format, branch strategy |
| Security Rules | Prevent leaking secrets or destructive mistakes |
| Workflow | Ensure Claude reads before editing, tests before committing |
| Don'ts | Explicitly prohibit certain Claude behaviors |
| Known Pitfalls | Record project-specific gotchas so Claude won't repeat them |

### Skills — Useful Commands

| Command | Purpose |
|---------|---------|
| `/setup` | Interactive project configuration |
| `/commit` | Safe commit: lint check + sensitive info scan + proper commit message |
| `/review` | Code review: security, readability, and potential bug checks |
| `/debug` | Systematic debugging: no guessing, step-by-step root cause analysis |

## Advanced Usage

### Global CLAUDE.md

In addition to the project-level CLAUDE.md, you can create a global config that applies to all your projects (e.g. "always respond in English"):

```
Help me save the contents of global-CLAUDE.md from this repo to ~/.claude/CLAUDE.md
```

### Already have a project?

If your project already has code, you can also let Claude auto-generate a baseline first:

```
/init
```

Then use this template as a reference to add the rules you need.
