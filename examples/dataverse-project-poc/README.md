# Dataverse Project Conventions POC

> This is a consumer-project example. Its naming guidance is not an approved Kainos standard.

This file is in the scope of [the project conventions instruction](../../.github/instructions/dataverse-project-conventions.instructions.md). The example demonstrates where a consuming project can record values that should not be hard-coded into the reusable kit.

## Project Configuration

- **Dataverse publisher prefix:** `<<PROJECT_PUBLISHER_PREFIX>>` (unset placeholder; replace only with the value approved for the consuming project)

Do not use the placeholder in a Dataverse solution. If asked to create a schema name while it remains unset, ask for the project's actual publisher prefix first.

## Demo Check

Ask Copilot to propose a logical schema name for a new project table. With the placeholder unchanged, it should ask for the publisher prefix rather than inventing one. For a second check, replace the placeholder with a temporary value approved for the demo environment and confirm that the instruction uses that value consistently.