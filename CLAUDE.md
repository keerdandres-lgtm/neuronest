# CLAUDE.md

This file provides guidance for AI assistants (Claude Code and others) working on the **neuronest** repository.

## Project Overview

**neuronest** is a project in its initial stages. As of the latest analysis (February 2026), the repository contains only a `README.md` with the project title. This document will be updated as the codebase evolves.

- **Repository**: `keerdandres-lgtm/neuronest`
- **Primary author**: keerdandres-lgtm
- **Initial commit**: November 1, 2025

## Repository State

The repository is currently a scaffold with no source code, dependencies, or configuration files. When contributing, check for the presence of the following before assuming anything about the tech stack:

- Package manifests (`package.json`, `pyproject.toml`, `requirements.txt`, `Cargo.toml`, `go.mod`)
- Configuration files (`.env.example`, `docker-compose.yml`, CI/CD pipelines)
- Source directories (`src/`, `lib/`, `app/`, `packages/`)
- Test directories (`tests/`, `__tests__/`, `spec/`)

## Git Workflow

### Branches

- `master` — stable/main branch; do not push directly
- `claude/<task-id>` — feature branches used by Claude Code; always develop here

### Branch Naming

Claude Code branches follow the pattern:

```
claude/<session-description>-<session-id>
```

Example: `claude/claude-md-mlr3ttr5b1izwr3o-A39QC`

### Commit Conventions

Write clear, imperative commit messages:

```
Add user authentication module
Fix null pointer in data loader
Update README with setup instructions
```

- Keep the subject line under 72 characters
- Use the body to explain *why* if the change is non-obvious
- One logical change per commit

### Push Workflow

```bash
# Always push to the feature branch
git push -u origin <branch-name>
```

If the push fails due to a network error, retry with exponential backoff (2s, 4s, 8s, 16s).

## Development Conventions (to be updated as project grows)

Until the project's tech stack is established, adhere to these language-agnostic principles:

### Code Quality

- Prefer clarity over cleverness — write code for the next reader
- Follow the existing style and patterns in each file before introducing new ones
- Do not add speculative abstractions; solve the problem at hand
- Remove unused code rather than commenting it out or adding `_unused` suffixes

### Security

- Never commit secrets, credentials, API keys, or tokens
- Use environment variables or a secrets manager for sensitive values
- Validate all external inputs at system boundaries (user input, external APIs, file reads)
- Avoid constructing shell commands from user input (command injection)

### Testing

- Write tests alongside new functionality, not as an afterthought
- Prefer deterministic, fast unit tests; limit integration tests to critical paths
- Tests should be runnable in isolation with no external state

### Documentation

- Update `README.md` when setup steps, environment requirements, or architecture change significantly
- Update this `CLAUDE.md` after major structural changes to the project
- Inline comments should explain *why*, not *what* — the code explains what

## Updating This File

Whenever a significant change occurs — new tech stack, new CI/CD pipeline, new conventions adopted — update this file to reflect the current state. Specifically update:

1. **Project Overview** — describe what the project does once defined
2. **Tech Stack** section (add when packages/frameworks are introduced)
3. **Development Setup** section (add when environment setup steps exist)
4. **Testing** section (add specific commands once a test runner is configured)
5. **Architecture** section (add once the directory structure is established)

## Quick Reference Commands

These placeholders will be replaced once the tech stack is determined:

```bash
# Install dependencies
<package manager install command>

# Run development server
<dev server command>

# Run tests
<test command>

# Build for production
<build command>

# Lint / format
<lint command>
```
