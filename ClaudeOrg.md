# CLAUDE.md — AI Assistant Guide for Claude-Cli

This file provides context, conventions, and workflow guidance for AI assistants
(including Claude Code) working on the **Claude-Cli** repository.

---

## Project Overview

**Claude-Cli** is a repository for client communication tooling. Based on the current
README, the project is described as "Communication with my Client."

The project is in its initial stage — the repository contains only a `README.md` as of
the last audit. This document will grow alongside the codebase.

---

## Repository Structure

```
Claude-Cli/
├── README.md      # Project description
└── CLAUDE.md      # This file — AI assistant guide
```

As source files are added, this section should be updated to reflect the actual layout.

---

## Git Workflow

### Branches

| Branch | Purpose |
|--------|---------|
| `main` / `master` | Stable, production-ready code |
| `claude/<description>-<id>` | AI-generated feature branches |

### Branch Naming Convention

All AI-generated branches must follow this pattern:

```
claude/<short-description>-<session-id>
```

Example: `claude/add-claude-documentation-837nl`

### Commit Style

- Write commit messages in the imperative mood ("Add feature", not "Added feature")
- Keep the subject line under 72 characters
- Reference the relevant issue or context in the body when applicable

### Push Rules

- Always push with: `git push -u origin <branch-name>`
- Never force-push to `main` or `master`
- AI assistants must only push to their designated `claude/` branch

---

## Development Conventions

### General

- Prefer editing existing files over creating new ones
- Delete unused code rather than commenting it out
- Do not add error handling for scenarios that cannot occur
- Avoid premature abstractions — solve the current problem simply

### File Operations

- Use dedicated tools (Read, Edit, Write) for file operations rather than shell commands
- Never write files unless strictly necessary for the task

### Security

- Never commit secrets, credentials, or `.env` files
- Validate all input at system boundaries (user input, external APIs)
- Do not introduce OWASP Top 10 vulnerabilities (XSS, SQL injection, command injection, etc.)

---

## AI Assistant Instructions

When working in this repository, AI assistants should:

1. **Read before writing** — always read a file before modifying it
2. **Stay focused** — only make changes directly requested or clearly necessary
3. **Track tasks** — use the TodoWrite tool to plan and track multi-step work
4. **Commit clearly** — write descriptive commit messages that explain the *why*
5. **Push to the right branch** — only push to the `claude/` branch assigned for the session
6. **Update this file** — when the codebase grows substantially, update the structure and
   conventions sections of this document to reflect reality

---

## Updating This Document

This file should be kept current. Update it when:

- New directories or major files are added to the project
- Build, test, or lint tooling is introduced
- New development conventions are adopted
- Dependencies or language/runtime choices are made

---

*Last audited: 2026-02-22*
