# power-platform-azure-copilot-kit-poc

Reusable GitHub Copilot customisations for Microsoft Power Platform and related Azure development. This POC is a starting point; review and adapt its guidance for each consuming project.

## Customisations

| Type | Location | Purpose |
| --- | --- | --- |
| Project instructions | `.github/copilot-instructions.md` | Keep this README aligned with changes to the repository's purpose, customisation inventory, structure, and usage. |
| Agent | `.github/agents/adr-generator.agent.md` | Gather decision inputs and create structured architectural decision records. |
| Agent | `.github/agents/azure-logic-apps-expert.agent.md` | Provide focused Logic Apps and workflow design guidance. |
| Agent | `.github/agents/azure-principal-architect.agent.md` | Assess Azure architecture against Well-Architected Framework principles. |
| Agent | `.github/agents/power-platform-expert.agent.md` | General Power Platform development and architecture guidance. |
| Agent | `.github/agents/power-platform-story-refinement.agent.md` | Assess Power Platform story criteria against Microsoft Learn and prepare a refinement brief. |
| Instructions | `.github/instructions/` | File-scoped guidance for Azure, Power Platform, and Dataverse projects. |
| Skill | `.github/skills/power-platform-architect/` | Turn business requirements into a Power Platform solution architecture. |
| Architecture decision records | `docs/adr/` | Record architectural decisions, context, alternatives, and consequences. |

## Using This Repository

- The Markdown instructions are stored with the repository and can be copied with it to Azure DevOps or another Git host. No organisation-level policy is required.
- `.github/copilot-instructions.md` provides repository-wide guidance for compatible GitHub Copilot clients. Files in `.github/instructions/` add guidance when their `applyTo` patterns match.
- These files use GitHub Copilot formats; other AI tools may need equivalent instructions in their own supported format. Check client support before relying on agents, skills, or file-scoped instructions.
- Keep project-specific values, such as a Dataverse publisher prefix, in the consuming project's instructions. The existing `examples/dataverse-project-poc/` demonstrates an unset prefix and asks rather than guessing.
- Select a custom agent for focused guidance or invoke the Power Platform Architect skill for requirements-to-architecture work.

## Sources

GitHub's [Awesome Copilot](https://github.com/github/awesome-copilot) collection was used as a resource for agents and skills. Preserve attribution and review source licences before redistribution.

## Demo Walkthrough

1. Select the Power Platform Story Refinement agent and ask it to assess a sample story. Review its evidence and refinement questions; it drafts content but does not create or update Azure DevOps work items.
2. Ask Copilot to propose a Dataverse schema name while editing `examples/dataverse-project-poc/README.md`. The publisher prefix is deliberately unset, so the project instruction should prompt for the real project value rather than invent one.
3. Use VS Code's Agent Customizations diagnostics and response references to inspect which instructions were discovered. If a file is missing, check the selected harness and Agent Debug Logs.