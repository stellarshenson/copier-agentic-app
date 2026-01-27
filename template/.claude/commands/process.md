# Process Workflow

Execute the project workflow as defined in INSTRUCTIONS.md.

## Execution Sequence

### Step 1: Preflight Check (MANDATORY - FIRST)

Before anything else, execute preflight validation:

```
Execute Preflight Check
```

**Preflight validates**:
- All required directories exist
- Agent definitions are complete (all required sections)
- Workflow-agent mappings are consistent
- Reference materials exist
- Goals are defined
- Tools and scripts are available

**ABORT if any preflight check fails.** Do not proceed until all issues are resolved.

### Step 2: Project Assessment

After preflight passes, invoke the Project Manager Agent to scan and understand the project:

```
Invoke Project Manager Agent
```

The project manager agent will:
- Scan project structure and key artefacts
- Review GOAL.md for objectives
- Inventory source materials in `/1-input/`
- Review workflow phases and agent mappings
- Check 4-references for rules and standards
- Produce PROJECT-ASSESSMENT.md

Review project assessment. Note any risks or blockers identified.

### Step 3: Read Instructions

Read and understand `/INSTRUCTIONS.md`:
- Entry point for workflow execution
- Prerequisites and dependencies
- Phase-by-phase guidance

### Step 4: Execute Workflow

Follow INSTRUCTIONS.md to execute each phase in sequence:

1. **Phase 0**: Preprocessing - prepare source materials
2. **Phase 1**: Analysis - understand sources, design outputs (requires user approval)
3. **Phase 2**: Framework - establish processing standards
4. **Phase 3**: Content Generation - parallel agent processing
5. **Phase 4**: Verification - quality and source fidelity checks
6. **Phase 5**: Finalization - deliver verified outputs

### Step 5: Deliver Outputs

After verification passes:
- Move verified outputs to `/3-output/`
- Generate completion summary
- Archive work-in-progress materials

## Key Principles

**Preflight first**: Always validate project configuration before any processing.

**Reconnaissance before execution**: Understand full project context before starting work.

**User approval**: Processing plan (Phase 1, Step 5) requires explicit user approval.

**Agent-driven**: All actions execute through defined agents.

**Transparency**: Update CHECKLIST.md throughout execution.

## Abort Conditions

**Preflight aborts if**:
- Required directories missing
- Agent definitions incomplete (missing PERSONA, TOOLS, etc.)
- Workflow-agent mapping inconsistent
- Verification framework missing
- Goals undefined

**Execution aborts if**:
- Reconnaissance reveals critical blockers
- User rejects processing plan
- Verification fails (return to content generation)
- Sources insufficient for goals

## Recovery

If execution is interrupted:
1. Read CHECKLIST.md for current status
2. Run preflight to validate configuration
3. Run project assessment to re-establish context
4. Resume from last incomplete phase
