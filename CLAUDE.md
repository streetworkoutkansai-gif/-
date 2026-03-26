# CLAUDE.md

This file provides guidance to Claude Code and other AI assistants working in this repository.

## Repository Status

This is a newly initialized repository. This document will be updated as the codebase grows.

## General Conventions

### Git Workflow

- **Default branch:** `main`
- **Feature branches:** Use descriptive names in the format `<type>/<short-description>` (e.g., `feat/add-login`, `fix/null-pointer`, `docs/update-readme`)
- **Commit messages:** Use the [Conventional Commits](https://www.conventionalcommits.org/) format:
  - `feat:` — new feature
  - `fix:` — bug fix
  - `docs:` — documentation only
  - `refactor:` — code restructure without behavior change
  - `test:` — adding or updating tests
  - `chore:` — tooling, dependency updates, config changes
- **Never force-push to `main`**
- **Always create a new commit** rather than amending an existing one, unless explicitly asked

### Code Style

- Prefer clarity over cleverness
- Keep functions small and single-purpose
- Avoid premature abstraction — three similar lines of code is better than a premature helper
- Do not add error handling for scenarios that cannot happen
- Do not add comments unless the logic is non-obvious

### File Conventions

- Do not create files unless absolutely necessary
- Prefer editing existing files over creating new ones
- Do not create documentation files (e.g., `*.md`) unless explicitly requested

## Development Workflow

### Before Making Changes

1. Read the relevant files before editing them
2. Understand existing patterns before introducing new ones
3. Run existing tests (if any) to confirm a clean baseline

### When Adding Features

1. Implement only what was asked — do not add extra configurability or future-proofing
2. Do not add feature flags, backwards-compatibility shims, or dead code
3. Match the existing code style exactly

### When Fixing Bugs

1. Identify the root cause before touching code
2. Fix the root cause — do not work around it
3. Do not clean up surrounding code as part of a bug fix

### Testing

- All new behavior should be covered by tests
- Tests should be deterministic and not rely on external state
- Do not use `sleep` in tests

## Security

- Never commit secrets, credentials, API keys, or `.env` files
- Validate all external inputs at system boundaries
- Avoid SQL injection, XSS, command injection, and other OWASP Top 10 vulnerabilities
- When in doubt, flag a potential security issue rather than silently proceeding

## Working with AI Assistants (Claude Code)

### What Claude Should Do

- Read files before editing them
- Prefer dedicated tools (`Read`, `Edit`, `Grep`, `Glob`) over shell commands
- Ask for confirmation before destructive or irreversible actions
- Keep changes minimal and scoped to the task at hand
- Commit with clear, descriptive messages
- Push to the branch specified in the session context

### What Claude Should NOT Do

- Push to `main` without explicit permission
- Create pull requests unless explicitly asked
- Add unsolicited improvements, refactors, or docstrings
- Retry failing commands in a loop — diagnose and fix the root cause instead
- Skip pre-commit hooks (`--no-verify`)

## Updating This File

Update `CLAUDE.md` whenever:
- A new technology, framework, or tool is added to the project
- A new architectural decision is made
- Development workflows change
- New conventions are established by the team

Keep this file concise and accurate. Remove outdated information promptly.
