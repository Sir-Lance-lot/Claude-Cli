# CLAUDE.md

This file provides guidance for AI assistants (Claude Code and similar tools) working in this repository.

## Project Overview

**Repository:** Claude-Cli
**Owner:** Sir-Lance-lot
**Purpose:** Communication with my Client

This is currently an early-stage project. The repository was initialized with a single README and is under active development. This document will grow as the project structure evolves.

## Repository Structure

```
Claude-Cli/
├── README.md       # Project overview
└── CLAUDE.md       # This file — AI assistant guidance
```

> As the project grows, update this section to reflect new directories, modules, and files.

## Git Workflow

### Branch Naming

- Feature branches must follow: `claude/<description>-<session-id>`
- Never push directly to `main` or `master` without explicit permission
- Always develop on the designated feature branch

### Standard Git Operations

```bash
# Push to the current feature branch
git push -u origin <branch-name>

# Fetch a specific branch
git fetch origin <branch-name>

# Pull latest changes
git pull origin <branch-name>
```

### Retry Policy for Network Failures

If `git push` or `git fetch` fails due to network errors, retry up to 4 times with exponential backoff:
- Attempt 1: wait 2s
- Attempt 2: wait 4s
- Attempt 3: wait 8s
- Attempt 4: wait 16s

### Commit Message Conventions

- Use the imperative mood: "Add feature" not "Added feature"
- Be concise and descriptive: one line summary, optionally followed by a blank line and longer description
- Reference issue numbers where applicable

```
Add client communication handler

Implements the core message routing logic for client interactions.
Closes #12
```

## Development Conventions

### General Principles

- **Read before modifying:** Always read a file fully before making changes to it.
- **Minimal changes:** Only change what is necessary for the task at hand. Avoid refactoring unrelated code.
- **No speculative features:** Do not add functionality that has not been requested.
- **No unnecessary files:** Do not create markdown files, READMEs, or documentation unless explicitly asked.
- **Delete unused code:** Do not leave commented-out code or `_unused` variables. Remove dead code entirely.

### Security

- Never introduce command injection, XSS, SQL injection, or other OWASP Top 10 vulnerabilities.
- Do not commit secrets, credentials, API keys, or `.env` files.
- Validate all input at system boundaries (user input, external APIs). Do not over-validate internal data.

### Code Style

> This section should be updated once a language/framework is chosen for the project.

- Follow the conventions of whatever language and framework the project adopts.
- Prefer clear, readable code over clever optimizations unless performance is a documented requirement.
- Add comments only where logic is non-obvious — not for self-explanatory code.

## AI Assistant Guidelines

### Task Management

- Use todo lists for tasks with 3 or more steps.
- Mark tasks `in_progress` before starting and `completed` immediately upon finishing.
- Only one task should be `in_progress` at any time.

### Searching the Codebase

- Use `Glob` for file pattern matching.
- Use `Grep` for content searches — never shell `grep` or `find`.
- Use `Read` to inspect files — never `cat`, `head`, or `tail` via Bash.
- Use `Edit` for targeted changes — never `sed` or `awk` via Bash.
- For open-ended codebase exploration, delegate to the `Explore` agent via the `Task` tool.

### Communication

- Output explanations as text, not via `echo` or code comments.
- Do not use emojis unless the user explicitly requests them.
- Keep responses concise and accurate — do not validate assumptions without verifying in code.

## Current State and Next Steps

This project is at its very beginning. As features are added:

1. Update the **Repository Structure** section with new directories.
2. Add a **Build & Test** section once a build system or test runner is established.
3. Add a **Language & Framework** section once a technology stack is chosen.
4. Document any environment variables or configuration requirements.
5. Add linting and formatting tool instructions when they are configured.

## Changelog

| Date       | Change                                  |
|------------|-----------------------------------------|
| 2026-02-23 | Initial CLAUDE.md created for new repo  |
