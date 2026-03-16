---
name: setup
description: Interactive CLAUDE.md configuration — fill in project info through Q&A, replacing all placeholders
---

# Project Setup

Help the user configure the project info in CLAUDE.md. Ask the questions below one at a time.

## Steps

1. First, read the CLAUDE.md file in the project root.

2. Ask the following questions one at a time (with a suggested default value each time):

   **Question 1: Project name**
   > What is your project called?
   (Use the current directory name as the suggested default)

   **Question 2: Tech stack**
   > What tech stack does this project use? e.g. Python, React, Node.js
   (Check package.json / pyproject.toml / go.mod etc. to suggest a value)

   **Question 3: Project description**
   > In one sentence, what does this project do?

   **Question 4: Source directory**
   > Where is your source code located?
   (Check the project structure and suggest common ones like src, app, lib)

   **Question 5: Test directory**
   > Where are your test files located?
   (Suggest common ones like tests, test, __tests__)

   **Question 6: Lint command**
   > What command do you use to check code style? e.g. `ruff check .`, `eslint .`, `npx prettier --check .`
   > If you don't have one yet, you can skip this — just type "none"
   (Suggest the appropriate lint tool based on the tech stack)

3. After collecting all info, replace all `{{placeholder}}` values in CLAUDE.md:
   - `{{project_name}}` → user's project name
   - `{{tech_stack}}` → user's tech stack
   - `{{project_description}}` → user's project description
   - `{{source_dir}}` → user's source directory
   - `{{test_dir}}` → user's test directory
   - `{{lint_command}}` → user's lint command (if the user said "none" or "skip", replace with "none")

4. Show the updated "Project Info" section and ask for confirmation:
   > Setup complete. Here's your project info — does everything look right?

5. Once confirmed, save the file. If the user wants to change something, go back to that question.
