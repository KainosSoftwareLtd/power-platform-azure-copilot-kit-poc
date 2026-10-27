---
description: "Use when creating or documenting Dataverse schema names for the consumer-project POC. Ask for the project's publisher prefix if it is not configured."
applyTo: "examples/dataverse-project-poc/**"
---

# Dataverse Project Conventions POC

These are project-specific example conventions, not Kainos-wide standards. Use only a publisher prefix explicitly configured by the consuming project.

- The example project currently sets its publisher prefix to `<<PROJECT_PUBLISHER_PREFIX>>`. This is an unset placeholder, not a valid prefix.
- If the placeholder remains, or no explicit project prefix is available, ask the user for the value before proposing or generating publisher-owned Dataverse schema names.
- Never replace the placeholder with a guessed, generic, or purported Kainos prefix.
- Once configured, use the supplied prefix consistently for new publisher-owned schema names and follow the project's other naming decisions.