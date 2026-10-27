# dataverse-github-copilot-kit

Reusable GitHub Copilot customizations for Microsoft Power Platform and related Azure development.

## Customizations

| Type | Location | Purpose |
| --- | --- | --- |
| Project instructions | `.github/copilot-instructions.md` | Keep this README aligned with changes to the repository's purpose, customization inventory, structure, and usage. |
| Agent | `.github/agents/power-platform-expert.agent.md` | General Power Platform development and architecture guidance. |
| Agent | `.github/agents/power-platform-story-refinement.agent.md` | Assess Power Platform story criteria against Microsoft Learn and prepare a refinement brief. |
| Instructions | `.github/instructions/` | Guidance for Azure DevOps pipelines, Azure Functions, and Power Apps Code Apps. |
| Standards POC | `.github/instructions/kainos-standards-poc.instructions.md` | Demonstrates file-scoped organizational guidance; its example rules are not official Kainos standards. |
| Skill | `.github/skills/power-platform-architect/` | Turn business requirements into a Power Platform solution architecture. |

## Using the Customizations

- Select a Power Platform agent in Copilot Chat for focused guidance or story refinement.
- Invoke the Power Platform Architect skill for requirements-to-architecture work.
- File-specific instructions are applied when their `applyTo` patterns match the files being edited.
- The Kainos standards POC applies only to `examples/kainos-standards-poc/` Markdown files and must be replaced with approved standards before team adoption.
- The story-refinement agent drafts findings and acceptance criteria for review; it does not create or update Azure DevOps work items.