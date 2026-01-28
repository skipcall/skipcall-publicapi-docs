# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

Skipcall Public API documentation site built with Mintlify. MDX files with YAML frontmatter, configured via `docs.json`.

## Commands

```bash
# Install CLI (requires Node.js v19+)
npm i -g mint

# Local development
mint dev                    # Preview at http://localhost:3000
mint dev --port 3333        # Custom port

# Validation and updates
mint broken-links           # Check for broken links
npm mint update             # Update CLI to latest version
```

## Structure

- `docs.json` - Navigation, theme, and site settings (OpenAPI source: `https://api-staging.skipcall.dev/docs-json`)
- `*.mdx` - Documentation pages with YAML frontmatter
- `snippets/` - Reusable content fragments
- `api-reference/` - API documentation and endpoint examples
- `images/`, `logo/` - Static assets

## Frontmatter requirements

Every MDX file must have:
```yaml
---
title: "Clear page title"
description: "Concise SEO summary"
---
```

## Writing standards

- Second-person voice ("you")
- Prerequisites at start of procedural content
- Language tags on all code blocks
- Alt text on all images
- Relative paths for internal links (not absolute URLs)
- Test all code examples before publishing

## Content strategy

- Document just enough for user success
- Search for existing content before adding new - avoid duplication
- Check existing patterns for consistency
- Start with smallest reasonable changes

## Working relationship

- Push back on ideas when warranted - cite sources and explain reasoning
- ALWAYS ask for clarification rather than making assumptions
- NEVER lie, guess, or make up information

## Git workflow

- NEVER use `--no-verify` when committing
- NEVER skip or disable pre-commit hooks
- Ask how to handle uncommitted changes before starting
- Create a new branch when no clear branch exists for changes
- Commit frequently throughout development
- Use conventional commits format: `type(scope): description`
- PRs target `main` branch by default and are created as drafts
