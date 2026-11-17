# power-platform-azure-copilot-kit

Reusable GitHub Copilot customisations for Microsoft Power Platform and related Azure development. This POC is a starting point; review and adapt its guidance for each consuming project.

## Customisations

| Type | Location | Purpose |
| --- | --- | --- |
| Project instructions | `.github/copilot-instructions.md` | Keep this README aligned with changes to the repository's purpose, customisation inventory, structure, and usage. |
| Agent | `.github/agents/azure-logic-apps-expert.agent.md` | Provide focused Logic Apps and workflow design guidance. |
| Agent | `.github/agents/azure-principal-architect.agent.md` | Assess Azure architecture against Well-Architected Framework principles. |
| Agent | `.github/agents/power-platform-expert.agent.md` | General Power Platform development and architecture guidance. |
| Instructions | `.github/instructions/` | File-scoped guidance for Azure, Power Platform, and Dataverse projects. |
| Skill | `.github/skills/power-platform-architect/` | Turn business requirements into a Power Platform solution architecture. |
| Skill | `.github/skills/create-architectural-decision-record/` | Gather decision inputs and create structured architectural decision records, with local demo and attribution safeguards. |
| Skill | `.github/skills/power-platform-story-refinement/` | Assess Power Platform story criteria against Microsoft Learn and prepare a refinement brief with a T-shirt size estimate. |
| Architecture decision records | `docs/adr/` | Record architectural decisions, context, alternatives, and consequences. |

## Using This Repository

- The Markdown instructions are stored with the repository and can be copied with it to Azure DevOps or another Git host. No organisation-level policy is required.
- `.github/copilot-instructions.md` provides repository-wide guidance for compatible GitHub Copilot clients. Files in `.github/instructions/` add guidance when their `applyTo` patterns match.
- These files use GitHub Copilot formats; other AI tools may need equivalent instructions in their own supported format. Check client support before relying on agents, skills, or file-scoped instructions.
- Keep project-specific values, such as a Dataverse publisher prefix, in the consuming project's instructions. The existing `examples/dataverse-project-poc/` demonstrates an unset prefix and asks rather than guessing.
- Select a custom agent for focused guidance. Invoke a skill for a repeatable procedure: Power Platform Architect for requirements-to-architecture work, Story Refinement for pre-refinement briefs, or Create Architectural Decision Record for ADRs.

## Sources

GitHub's [Awesome Copilot](https://github.com/github/awesome-copilot) collection was used as a resource for agents and skills. Preserve attribution and review source licences before redistribution.

## Demo Walkthrough

1. Ask Copilot to assess a sample story for refinement; the Power Platform Story Refinement skill should be applied. Review its evidence and refinement questions; it drafts content but does not create or update Azure DevOps work items.
2. Edit `examples/kainos-standards-poc/README.md` with Copilot. Inspect the response references to confirm the local standards POC was applied, and note that its generic rules are not approved Kainos policy.
3. Ask Copilot to propose a Dataverse schema name while editing `examples/dataverse-project-poc/README.md`. The publisher prefix is deliberately unset, so the project instruction should prompt for the real project value rather than invent one.
4. Use VS Code's Agent Customisations diagnostics and response references to inspect which instructions were discovered. If a file is missing, check the selected harness and Agent Debug Logs.
