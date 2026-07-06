# Agent team

The Project Pulse dashboard is built using four specialized AI agents orchestrated through GitHub Copilot CLI in a Codespace. Each agent has a distinct responsibility and operates within a defined scope.

## Agents

### Orchestrator
- **Model:** Claude Opus 4.7 (copilot)
- **Definition:** `.github/agents/orchestrator.agent.md`
- **Responsibility:** Breaks down complex requests into tasks and delegates to specialist agents (Planner, Coder, Designer). Coordinates work sequentially and in parallel based on file scope and dependencies. Verifies that the integrated result is complete and coherent.

### Planner
- **Model:** Claude Opus 4.7 (copilot)
- **Definition:** `.github/agents/planner.agent.md`
- **Responsibility:** Creates implementation strategies and technical plans by researching the codebase, documentation, and requirements. Produces ordered implementation steps with file assignments, identifies dependencies, highlights edge cases, and specifies validation expectations. Does not write code.

### Designer
- **Model:** Gemini 3.1 Pro (copilot)
- **Definition:** `.github/agents/designer.agent.md`
- **Responsibility:** Handles UI/UX, accessibility, information hierarchy, interaction flow, visual design, and consistency. For Project Pulse, creates a polished dashboard with visible project cards, status badges, clear priority treatment, responsive layout, and visual affordances like rounded corners and shadows.

### Coder
- **Model:** GPT-5.5 (copilot)
- **Definition:** `.github/agents/coder.agent.md`
- **Responsibility:** Writes code, implements logic, and creates configuration files within the scope assigned by the Orchestrator. Follows explicit patterns, prefers clear code over clever abstractions, and validates changes before completion. Creates support files like `.vscode/launch.json` for runnable applications.

## Workflow

This team uses GitHub Copilot CLI in a Codespace to orchestrate the Project Pulse dashboard build. The Orchestrator coordinates phases of work:

1. **Planning phase** — Planner researches requirements and creates a detailed implementation plan
2. **Design phase** — Designer defines the visual direction and UI/UX patterns
3. **Implementation phase** — Coder builds the dashboard files and support configuration
4. **Validation phase** — Verify that all outputs meet specifications and work together

The Orchestrator ensures file scopes don't conflict, manages sequential vs. parallel work, and integrates results from all agents into a cohesive product.
