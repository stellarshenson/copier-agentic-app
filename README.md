# Copier Agentic App Template

A Copier template for creating agentic workflow projects. Generates a project structure for transforming input materials into structured outputs using agent-based parallel processing with comprehensive verification.

## Usage

```bash
copier copy /path/to/copier-agentic-app /path/to/new-project
```

Or from git:
```bash
copier copy git+https://github.com/user/copier-agentic-app /path/to/new-project
```

## Template Variables

The template prompts for:

| Variable | Description | Default |
|----------|-------------|---------|
| `project_name` | Project name for documentation | my-agentic-project |
| `project_description` | Short project description | An agentic workflow project |
| `goal_summary` | Main goal of the project | Transform input documents... |
| `input_type` | Type of input materials | documents |
| `output_type` | Type of output generated | structured reports |
| `target_audience` | Target audience for outputs | stakeholders |
| `max_parallel_agents` | Max concurrent agents | 3 |

## Generated Structure

```
project/
├── .claude/
│   ├── CLAUDE.md          # Claude Code configuration
│   └── JOURNAL.md         # Session tracking
├── 1-input/               # Source materials (read-only)
├── 2-work-in-progress/    # Active workspace
├── 3-output/              # Verified deliverables
├── 4-references/          # Reference materials
│   └── verification-framework.md
├── agents/                # Agent definitions
│   └── verification-agent.md
├── workflow/              # Workflow phases
│   ├── workflow.md
│   └── phase-*.md
├── src/                   # Scripts and tools
├── doc/                   # Documentation
├── GOAL.md                # Project objectives
├── INSTRUCTIONS.md        # Execution entry point
└── README.md              # Project overview
```

## Workflow Overview

Generated projects follow a multi-phase workflow:

1. **Phase 0**: Preprocessing - Prepare source materials
2. **Phase 1**: Analysis - Understand sources, design output structure
3. **Phase 2**: Framework - Establish processing framework
4. **Phase 3**: Content Generation - Parallel agent processing
5. **Phase 4**: Verification - Quality and source fidelity checks
6. **Phase 5**: Finalization - Deliver verified outputs

## Key Features

- **Parallel processing**: Configurable concurrent agent limit
- **Source fidelity**: All content traceable to input materials
- **Verification**: Comprehensive quality checks before delivery
- **Transparency**: Reasoning documentation for all decisions
- **User approval**: Processing plans require approval before execution
