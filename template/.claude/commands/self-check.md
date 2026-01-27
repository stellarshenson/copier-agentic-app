# Self-Check

Run consistency validation across project configuration: GOAL.md, INSTRUCTIONS.md, workflow phases, and agent definitions.

## Purpose

Validates that all project components are:
- Defined and complete
- Mutually consistent
- Properly cross-referenced

## Execution

Perform the following checks in order:

### 1. Goal Completeness

Read `/GOAL.md` and verify:

- [ ] **Objectives** defined - What the project aims to achieve
- [ ] **Deliverables** listed - Specific outputs to produce
- [ ] **Target audience** specified - Who consumes the outputs
- [ ] **Success criteria** defined - How to measure completion
- [ ] **Constraints** documented - Boundaries and limitations

**Report**: List any missing sections.

### 2. Instructions Alignment

Read `/INSTRUCTIONS.md` and verify:

- [ ] References `/GOAL.md` for objectives
- [ ] Lists prerequisites matching Phase 0
- [ ] Workflow overview matches `/workflow/workflow.md`
- [ ] Phase execution instructions are present
- [ ] Entry point is clear

**Cross-check**:
- Deliverables in INSTRUCTIONS.md match GOAL.md
- Prerequisites in INSTRUCTIONS.md match Phase 0 outputs

**Report**: List inconsistencies between GOAL.md and INSTRUCTIONS.md.

### 3. Workflow Consistency

Read `/workflow/workflow.md` and all phase files. Verify:

- [ ] All phases have definition files (phase-0 through phase-N)
- [ ] Phase sequence is logical (dependencies flow forward)
- [ ] Each phase declares executing agent
- [ ] Phase outputs feed into subsequent phase inputs
- [ ] Completion criteria are defined for each phase

**Cross-check**:
- Phases referenced in INSTRUCTIONS.md exist in workflow/
- Workflow outputs align with GOAL.md deliverables

**Report**: List missing phases, broken dependencies, or orphan phases.

### 4. Agent Definitions

Read `/agents/README.md` and all agent files. Verify:

- [ ] All agents in registry have definition files
- [ ] Each agent definition includes required sections:
  - PERSONA
  - CONTEXT
  - STAKES
  - TOOLS
  - METHODOLOGY
  - CONSTRAINTS
  - SUCCESS CRITERIA
  - INTERACTION
- [ ] TOOLS section lists available tools and scripts
- [ ] INTERACTION section declares workflow mapping

**Cross-check**:
- Agents referenced in workflow phases exist in /agents/
- No orphan agents (defined but never mapped to workflow)

**Report**: List incomplete agents, missing sections, or mapping issues.

### 5. Reference Materials

Check `/4-references/`:

- [ ] `verification-framework.md` exists and defines criteria
- [ ] Verification criteria align with GOAL.md success criteria
- [ ] Rules in `rules/` are referenced by relevant agents
- [ ] Examples in `examples/` match expected output format

**Report**: List missing references or inconsistencies.

### 6. Cross-Reference Matrix

Build and validate cross-reference matrix:

| Element | Referenced By | References | Status |
|---------|---------------|------------|--------|
| GOAL.md | INSTRUCTIONS, workflow | - | ✓/✗ |
| Phase N | INSTRUCTIONS | agents, references | ✓/✗ |
| Agent X | workflow phase N | tools, references | ✓/✗ |

**Report**: List broken references or circular dependencies.

## Output Format

Generate self-check report:

```markdown
# Self-Check Report

**Date**: [timestamp]
**Status**: PASS / FAIL

## Summary

| Category | Status | Issues |
|----------|--------|--------|
| Goal Completeness | ✓/✗ | [count] |
| Instructions Alignment | ✓/✗ | [count] |
| Workflow Consistency | ✓/✗ | [count] |
| Agent Definitions | ✓/✗ | [count] |
| Reference Materials | ✓/✗ | [count] |
| Cross-References | ✓/✗ | [count] |

## Issues Found

### Critical (Must Fix)
1. [issue description]

### Warnings (Should Fix)
1. [issue description]

### Suggestions (Nice to Have)
1. [suggestion]

## Recommendation

[ ] PASS - Project configuration is consistent
[ ] FAIL - Issues must be resolved before processing
```

## Resolution

For each issue found, provide:
- What is wrong
- Where to fix it (file path)
- How to fix it (specific action)

## Automation

For automated self-check, create `/src/self_check.py`:

```python
#!/usr/bin/env python3
"""
Self-check validation for project consistency.
"""
import argparse
from pathlib import Path
import re
import sys

def check_goal(root: Path) -> list[str]:
    """Check GOAL.md completeness."""
    issues = []
    goal_file = root / 'GOAL.md'
    if not goal_file.exists():
        return ["GOAL.md does not exist"]

    content = goal_file.read_text()
    required = ['Objective', 'Deliverable', 'Audience', 'Success', 'Constraint']
    for section in required:
        if section.lower() not in content.lower():
            issues.append(f"GOAL.md: missing {section} section")
    return issues

def check_agents(root: Path) -> list[str]:
    """Check agent definitions."""
    issues = []
    agents_dir = root / 'agents'
    required_sections = ['PERSONA', 'CONTEXT', 'STAKES', 'TOOLS',
                        'METHODOLOGY', 'CONSTRAINTS', 'SUCCESS CRITERIA', 'INTERACTION']

    for agent_file in agents_dir.glob('*-agent.md*'):
        content = agent_file.read_text()
        for section in required_sections:
            if f'## {section}' not in content:
                issues.append(f"{agent_file.name}: missing ## {section}")
    return issues

def main():
    parser = argparse.ArgumentParser(description='Project self-check')
    parser.add_argument('--root', default='.', help='Project root')
    args = parser.parse_args()

    root = Path(args.root)
    all_issues = []

    all_issues.extend(check_goal(root))
    all_issues.extend(check_agents(root))

    if all_issues:
        print("SELF-CHECK FAILED")
        for issue in all_issues:
            print(f"  - {issue}")
        sys.exit(1)
    else:
        print("SELF-CHECK PASSED")
        sys.exit(0)

if __name__ == '__main__':
    main()
```

Run with: `python src/self_check.py --root .`
