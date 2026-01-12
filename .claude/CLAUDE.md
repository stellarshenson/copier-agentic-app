<!-- @import /home/lab/workspace/.claude/CLAUDE.md -->

# Project-Specific Configuration

This file imports workspace-level configuration from `/home/lab/workspace/.claude/CLAUDE.md`.
All workspace rules apply. Project-specific rules below strengthen or extend them.

The workspace `/home/lab/workspace/.claude/` directory contains additional instruction files
(MERMAID.md, NOTEBOOK.md, DATASCIENCE.md, GIT.md, and others) referenced by CLAUDE.md.
Consult workspace CLAUDE.md and the .claude directory to discover all applicable standards.

## Mandatory Bans (Reinforced)

The following workspace rules are STRICTLY ENFORCED for this project:

- **No automatic git tags** - only create tags when user explicitly requests
- **No automatic version changes** - only modify version in package.json/pyproject.toml/etc. when user explicitly requests
- **No automatic publishing** - never run `make publish`, `npm publish`, `twine upload`, or similar without explicit user request
- **No manual package installs if Makefile exists** - use `make install` or equivalent Makefile targets, not direct `pip install`/`uv install`/`npm install`
- **No automatic git commits or pushes** - only when user explicitly requests

## Project Context

**Project Type**: Copier template for agentic workflow applications

**Purpose**: Provides a standardized project structure for creating document transformation pipelines that use agent-based workflows. Users copy this template to create new projects where input documents are processed through defined workflow phases with agent orchestration.

**Template Structure**:
- `example-agentic-project/` - Reference implementation demonstrating the template structure
- Numbered directories (`1-input/`, `2-work-in-progress/`, `3-output/`) for workflow stages
- `agents/` - Agent definitions and configurations
- `workflow/` - Workflow phase definitions
- `4-references/` - Reference materials and standards

**Technology Stack**:
- Copier for template management
- Claude Code agents for document processing
- Markdown for documentation and content

## Strengthened Rules

**Template Integrity**: Changes to `example-agentic-project/` should preserve the reference implementation's integrity as a working example

**Documentation Standards**: All template documentation must follow modus primaris principles - flowing narrative suitable for users learning the template structure

**Agent Definitions**: Agent configuration files in `agents/` directory must include clear entry points, responsibilities, and workflow integration points
