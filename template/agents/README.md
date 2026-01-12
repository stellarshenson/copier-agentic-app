# agents

Agent definitions for specialized processing tasks.

Each markdown file in this directory defines an autonomous agent with specific responsibilities, processing instructions, and quality criteria. Agents coordinate to handle parallel processing while maintaining consistency and traceability. Reusable tools supporting agents are stored in `/src/`.

## Agent Structure

Each agent definition should include:
- **Role**: What the agent does
- **Input**: What the agent receives
- **Responsibilities**: Detailed tasks and phases
- **Output**: What the agent produces
- **Success Criteria**: How to measure completion
- **Key Principles**: Guiding rules

## Available Agents

**verification-agent.md** - Executes comprehensive verification protocols across all generated outputs, ensuring source fidelity, data accuracy, cross-output consistency, and audience appropriateness before final delivery

## Adding New Agents

1. Create new markdown file: `[agent-name]-agent.md`
2. Follow the structure in `verification-agent.md`
3. Update this README with agent description
4. Reference agent in relevant workflow phase files
