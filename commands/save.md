---
allowed-tools: Bash(git add:*), Bash(git status:*), Bash(git commit:*), Bash(git push:*), Bash(git pull:*)
description: Review changes and create a conventional commit
---

## Context

- Current git status: !`git status`
- Staged changes: !`git diff --cached`
- Unstaged changes: !`git diff`
- Current branch: !`git branch --show-current`
- Recent commits: !`git log --oneline -10`

## Staging Rules

- If there ARE staged changes (staged changes output is not empty): ONLY commit the staged files. Do NOT stage any additional files.
- If there are NO staged changes: Stage and commit all changed files (new, modified, deleted).

## Commit Message Rules

You MUST follow these rules for the commit message:

### Format
- First line: `<type>: <message>` or `<type>!: <message>` for breaking changes
- Valid types: build, ci, docs, feat, fix, perf, refactor, style, test
- First line MUST be 80 characters or less
- There must be a non-empty message after ": "
- After the first line, add a blank line, then a bullet list of specific changes

### Commit Body
After the subject line, ALWAYS include a body with:
- A blank line after the subject
- A bulleted list (using `-`) of specific changes made
- Each bullet should describe a concrete change, not just repeat the subject

Example:
```
feat: add user authentication system

- Add login and logout endpoints in auth controller
- Create JWT token generation and validation
- Add password hashing with bcrypt
- Create user session middleware
```

### Content Rules
- Do NOT include `Co-Authored-By` lines
- If you were explicitly asked to fix or work on a specific GitHub issue during this session, add `Closes #<issue-number>` at the bottom after the bullet list
- Keep bullets concise but specific

### Type Selection Guide
- **feat**: New feature
- **fix**: Bug fix
- **docs**: Documentation only
- **style**: Formatting, missing semi-colons, etc (no code change)
- **refactor**: Code change that neither fixes a bug nor adds a feature
- **perf**: Performance improvement
- **test**: Adding or updating tests
- **build**: Changes to build system or dependencies
- **ci**: Changes to CI configuration

## Your Task

1. Check if there are staged changes
2. If staged changes exist: Review ONLY the staged changes and commit them (do not stage anything else)
3. If no staged changes: Stage all changes and commit them
4. Determine the appropriate commit type based on the changes being committed
5. Craft a commit message following the rules above

You have the capability to call multiple tools in a single response. Stage (if needed) and create the commit using a single message. Do not use any other tools or do anything else. Do not send any other text or messages besides these tool calls.
