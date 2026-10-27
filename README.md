# power-platform-azure-copilot-kit

Reusable GitHub Copilot customisations for Microsoft Power Platform and related Azure development.

## Customisations

| Type | Location | Purpose |
| --- | --- | --- |
| Project instructions | `.github/copilot-instructions.md` | Keep this README aligned with changes to the repository's purpose, customisation inventory, structure, and usage. |
| Agent | `.github/agents/adr-generator.agent.md` | Gather decision inputs and create structured architectural decision records. |
| Agent | `.github/agents/azure-logic-apps-expert.agent.md` | Provide focused Logic Apps and workflow design guidance. |
| Agent | `.github/agents/azure-principal-architect.agent.md` | Assess Azure architecture against Well-Architected Framework principles. |
| Agent | `.github/agents/power-platform-expert.agent.md` | General Power Platform development and architecture guidance. |
| Agent | `.github/agents/power-platform-story-refinement.agent.md` | Assess Power Platform story criteria against Microsoft Learn and prepare a refinement brief. |
| Instructions | `.github/instructions/azure-devops-pipelines.instructions.md` | Guide Azure DevOps pipeline authoring. |
| Instructions | `.github/instructions/azure-functions-csharp.instructions.md` | Guide Azure Functions development in C#. |
| Instructions | `.github/instructions/azure-logic-apps-power-automate.instructions.md` | Guide workflow definition files matching its `applyTo` patterns. |
| Instructions | `.github/instructions/kainos-standards-poc.instructions.md` | Demonstrate a local, file-scoped standards pattern; the sample is not Kainos policy. |
| Instructions | `.github/instructions/power-apps-code-apps.instructions.md` | Guide Power Apps Code Apps and matching TypeScript, JavaScript, and configuration files. |
| Instructions | `.github/instructions/dataverse-project-conventions.instructions.md` | Demonstrate project-specific Dataverse naming guidance using an unset publisher-prefix placeholder. |
| Skill | `.github/skills/power-platform-architect/` | Turn business requirements into a Power Platform solution architecture. |
| Architecture decision records | `docs/adr/` | Record architectural decisions, context, alternatives, and consequences. |

## Guidance Scopes

- **Kainos-wide standards**: Put approved organisation-wide rules in GitHub organisation custom instructions. The checked-in Kainos standards POC is only a local demonstration; it does not publish or define Kainos policy.
- **This repository**: `.github/copilot-instructions.md` describes how to work on this reusable kit. It is not the place for a consuming project's publisher prefix or environment values.
- **Consuming project**: Keep project-specific values, such as a Dataverse publisher prefix, in that project's own instructions. The example under `examples/dataverse-project-poc/` demonstrates a placeholder and asks for a value when it is unset.
- **File-specific guidance**: Files under `.github/instructions/` are attached when their `applyTo` patterns match. Applicable guidance can be additive; do not rely on file order or pattern specificity to resolve conflicting rules.
- **Agents and skills**: Select a custom agent in Copilot Chat for its focused role. Invoke the Power Platform Architect skill for requirements-to-architecture work.

## Demo Walkthrough

1. Select the Power Platform Story Refinement agent and ask it to assess a sample story. Review its evidence and refinement questions; it drafts content but does not create or update Azure DevOps work items.
2. Edit `examples/kainos-standards-poc/README.md` with Copilot. Inspect the response references to confirm the local standards POC was applied, and note that its generic rules are not approved Kainos policy.
3. Ask Copilot to propose a Dataverse schema name while editing `examples/dataverse-project-poc/README.md`. The publisher prefix is deliberately unset, so the project instruction should prompt for the real project value rather than invent one.
4. Use VS Code's Agent Customisations diagnostics and response references to inspect which instructions were discovered. If a file is missing, check the selected harness and Agent Debug Logs.
