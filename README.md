# Copier Agentic App Template

A Copier template for creating agentic workflow projects. Generates a project structure for transforming input materials into structured outputs using agent-based parallel processing with comprehensive verification.

## Quick Start

1. Copy the template:
   ```bash
   copier copy /path/to/copier-agentic-app /path/to/new-project
   ```

2. Navigate to project and initialize:
   ```bash
   cd /path/to/new-project
   ```

3. Run `/init-project` to capture goals, context, and workflow configuration

4. Run `/self-check` to validate project consistency

5. Run `/process` to execute the workflow:
   - Preflight validation (aborts if configuration invalid)
   - Project Manager agent assessment
   - Phase 0-5 execution
   - Verified outputs delivered to `/3-output/`

## Usage

```bash
copier copy /path/to/copier-agentic-app /path/to/new-project
```

Or from git:
```bash
copier copy git+https://github.com/user/copier-agentic-app /path/to/new-project
```

## Template Variables

- `project_name` - Project name for documentation (default: my-agentic-project)
- `project_description` - Short project description (default: An agentic workflow project)
- `goal_summary` - Main goal of the project (default: Transform input documents...)
- `input_type` - Type of input materials (default: documents)
- `output_type` - Type of output generated (default: structured reports)
- `target_audience` - Target audience for outputs (default: stakeholders)
- `max_parallel_agents` - Max concurrent agents (default: 3)

## Generated Structure

```
project/
├── .claude/
│   ├── CLAUDE.md              # Claude Code configuration
│   ├── JOURNAL.md             # Session tracking
│   └── commands/              # Project commands
│       ├── init-project.md    # Initialize project configuration
│       ├── process.md         # Execute workflow
│       └── self-check.md      # Validate consistency
├── 1-input/                   # Source materials (read-only)
├── 2-work-in-progress/        # Active workspace
├── 3-output/                  # Verified deliverables
├── 4-references/              # Reference materials
│   ├── verification-framework.md
│   ├── examples/              # Sample outputs
│   ├── rules/                 # Processing constraints
│   └── knowledge/             # Methodology articles
├── agents/                    # Agent definitions
│   ├── project-manager-agent.md
│   └── verification-agent.md
├── workflow/                  # Workflow phases
│   ├── preflight.md           # Pre-execution validation
│   ├── workflow.md            # Main workflow
│   └── phase-*.md             # Phase definitions
├── src/                       # Scripts and tools
├── doc/                       # Documentation
├── GOAL.md                    # Project objectives
├── INSTRUCTIONS.md            # Execution entry point
└── README.md                  # Project overview
```

## Commands

- `/init-project` - Capture goals, context, and workflow configuration
- `/process` - Execute full workflow (preflight -> assessment -> phases)
- `/self-check` - Validate consistency across goals, workflow, and agents

## Workflow Overview

Generated projects follow a multi-phase workflow:

1. **Preflight** - Validate project configuration (abort if invalid)
2. **Project Assessment** - Project Manager agent scans and understands project
3. **Phase 0** - Preprocessing: prepare source materials
4. **Phase 1** - Analysis: understand sources, design outputs (requires user approval)
5. **Phase 2** - Framework: establish processing standards
6. **Phase 3** - Content Generation: parallel agent processing
7. **Phase 4** - Verification: quality and source fidelity checks
8. **Phase 5** - Finalization: deliver verified outputs

## Key Features

- **Preflight validation** - Abort before execution if configuration invalid
- **Agent-driven execution** - All actions through defined agents with TOOLS
- **Parallel processing** - Configurable concurrent agent limit
- **Source fidelity** - All content traceable to input materials
- **Verification** - Comprehensive quality checks before delivery
- **User approval** - Processing plans require approval before execution
