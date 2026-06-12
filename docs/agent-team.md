# Agent Team

This Project Pulse dashboard will be built using GitHub Copilot CLI in a GitHub Codespace with a team of custom agents defined under `.github/agents/`.

## Orchestrator

- Model: Claude Opus 4.7 (copilot)
- Agent definition: `.github/agents/orchestrator.agent.md`
- Responsibility:
  - Coordinates the overall Project Pulse dashboard effort.
  - Breaks work into phases.
  - Delegates tasks to Planner, Designer, and Coder.
  - Verifies that all completed work integrates correctly.

## Planner

- Model: Claude Opus 4.7 (copilot)
- Agent definition: `.github/agents/planner.agent.md`
- Responsibility:
  - Researches the repository and requirements.
  - Creates implementation plans and ordered phases.
  - Identifies dependencies, risks, edge cases, and validation requirements.
  - Assigns file ownership to avoid conflicts.

## Designer

- Model: Gemini 3.1 Pro (copilot)
- Agent definition: `.github/agents/designer.agent.md`
- Responsibility:
  - Defines the dashboard user experience and visual design.
  - Focuses on usability, accessibility, information hierarchy, and responsive behavior.
  - Creates styling guidance for Project Pulse, including dashboard layouts, project cards, status badges, and visual clarity.

## Coder

- Model: GPT-5.5 (copilot)
- Agent definition: `.github/agents/coder.agent.md`
- Responsibility:
  - Implements code and application logic.
  - Creates and updates files assigned by the Orchestrator.
  - Fixes bugs, validates behavior, and follows repository patterns.
  - Creates support files such as `.vscode/launch.json` when assigned.

## Team Workflow

1. The Orchestrator receives the Project Pulse dashboard request.
2. The Planner researches the repository and creates an implementation plan.
3. The Designer provides UI/UX guidance and dashboard design recommendations.
4. The Coder implements the dashboard files and application behavior.
5. The Orchestrator reviews the combined work and confirms the final result.

All agent definitions are stored under `.github/agents/` and are orchestrated through GitHub Copilot CLI in a Codespace.