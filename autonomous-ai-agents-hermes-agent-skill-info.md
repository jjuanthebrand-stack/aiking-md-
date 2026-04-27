# Transcript

**User:** What is autonomous-ai-agents? How does it work with Hermes Agent and Opencode?

**Assistant:**

The `autonomous-ai-agents` skill in Hermes Agent enables creating and managing multiple AI agents or subagents to handle complex tasks through orchestration. Here's how it works with Hermes Agent and Opencode:

1. **Hermes Agent Integration**  
   - The `autonomous-ai-agents` skill is built into Hermes Agent and allows spawning independent agent processes.  
   - Agents can be configured to run in parallel, delegate subtasks, and coordinate workflows (e.g., splitting a project into frontend/backend, testing, and documentation streams).  
   - Hermes Agent’s `run_agent.py` core handles task delegation, ensuring each agent has its own session context and toolset access.

2. **Opencode Integration**  
   - The `opencode` skill (under `autonomous-ai-agents`) delegates coding tasks to the OpenCode CLI.  
   - When a subagent needs to generate code, review PRs, or perform feature‑based coding, it can invoke `opencode` via CLI commands (e.g., `opencode feature --name my‑feature`).  
   - Hermes Agent manages the workflow: it can split tasks between agents using `opencode` for code generation and `hermes-agent` for coordination.

**Example Workflow**:  
- A user asks to build a web app.  
- Hermes Agent spawns two subagents via `autonomous-ai-agents`: one for backend logic (using `hermes-agent` tools) and one for frontend UI (using `opencode` for code generation).  
- The frontend agent uses `opencode` to generate React components, while the backend agent handles API logic via terminal tools.  
- Results are merged and reviewed through Hermes Agent’s interface.
