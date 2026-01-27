# Initialize Project

Capture project goals, context, and workflow configuration to populate template files.

## Instructions

Ask the user the following questions to gather project information, then update the project files accordingly.

### Questions to Ask

**1. Project Goals**
- What is the primary objective of this project?
- What specific deliverables should be produced?
- What does success look like?

**2. Source Materials**
- What type of input materials will be processed?
- Where will sources come from?
- How many sources are expected?

**3. Target Audience**
- Who will consume the outputs?
- What is their technical level?
- What decisions will they make based on the outputs?

**4. Processing Approach**
- Are there specific phases or steps required?
- What agents are needed beyond verification?
- Are there domain-specific rules or constraints?

**5. Quality Requirements**
- What verification standards apply?
- Are there specific accuracy requirements?
- What would cause the project to fail?

### Files to Update

Based on answers, update:

1. **`/GOAL.md`** - Populate with:
   - Project objectives
   - Expected deliverables (list each)
   - Target audience description
   - Success criteria
   - Constraints and boundaries

2. **`/workflow/workflow.md`** - Update:
   - Phase descriptions if custom phases needed
   - Agent assignments for each phase
   - Processing plan specifics

3. **`/agents/README.md`** - Update:
   - Agent registry with any new agents
   - Phase-agent mapping table

4. **`/4-references/verification-framework.md`** - Update:
   - Source materials profile
   - Domain-specific verification criteria
   - Prohibited content definitions

5. **`/2-work-in-progress/CHECKLIST.md`** - Update:
   - Phase-specific items based on workflow
   - Custom checkpoints for this project

### Agent Definition Template

If new agents are needed, create them using this structure:

```markdown
# [Agent Name] Agent

## PERSONA
[Character, expertise, approach]

## CONTEXT
[Operating environment, inputs, outputs]

## STAKES
[Consequences of success and failure]

## TOOLS
| Tool | Purpose | When to Use |
|------|---------|-------------|
| `tool` | purpose | conditions |

**Python Scripts**:
| Script | Purpose | Usage |
|--------|---------|-------|
| `script.py` | purpose | `python src/script.py --args` |

## METHODOLOGY
[Step-by-step execution approach]

## CONSTRAINTS
[Boundaries and limitations]

## SUCCESS CRITERIA
[Measurable completion requirements]

## INTERACTION
**Workflow Mapping**: Phase N
[How agent coordinates with others]
```

### Completion

After gathering information and updating files:

1. Run preflight check to validate configuration
2. Report any issues that need resolution
3. Confirm project is ready for workflow execution

```
Execute Preflight Check
```
