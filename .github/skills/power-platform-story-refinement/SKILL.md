---
name: power-platform-story-refinement
description: Use this skill when the user wants to check a Power Platform user story or acceptance criteria before refinement - feasibility, out-of-the-box capability, configuration versus customisation, open questions and a T-shirt size estimate - assessed against official Microsoft Learn documentation. Produces a draft brief only; never writes to Azure DevOps.
---

# Power Platform Story Refinement

Help product owners, analysts and delivery teams prepare Power Platform user stories for refinement. Assess the supplied story and acceptance criteria against current official Microsoft Learn documentation and produce a concise, evidence-based refinement brief. Do not create or update Azure DevOps work items.

## Assessment Workflow

1. Read the user story, acceptance criteria and any supplied context. Identify the Power Platform products and features involved.
2. Find relevant, current Microsoft Learn documentation using available documentation or web-search tools. Prefer product documentation and API references over community sources.
3. Assess each acceptance criterion separately. Distinguish documented product capability from tenant-specific availability and project assumptions.
4. Classify each criterion as one of:
   - **Out of the box**: a documented standard capability, subject to licensing and service availability.
   - **Configuration**: achievable through supported configuration, administration or solution setup without custom code.
   - **Customisation or integration**: requires custom logic, Power Fx, Power Automate, PCF, a custom connector, code or an external service.
   - **Not supported / not feasible**: official documentation explicitly rules out the behaviour or establishes a conflicting limitation.
   - **Unable to verify**: available evidence is insufficient for a reliable determination.
5. Identify assumptions and dependencies: licensing, product/version or preview status, environment and region, security roles, connectors, data access, governance policies and ALM constraints where relevant.
6. Identify ambiguities, risks and focused questions to answer before the team estimates or commits to the story.
7. Suggest clarified, testable acceptance criteria when the originals are ambiguous or not verifiable.
8. Recommend a T-shirt size estimate based on the assessment and identified risks.

## T-shirt Size Estimates

| Size | Effort | Points |
| --- | --- | --- |
| XS | Up to 1 day | 6 |
| S | 1-3 days | 18 |
| M | 3-5 days | 30 |
| L | 1-2 weeks | 60 |
| XL | Sprint-sized or significant unknowns | 90 (challenge whether it can be broken down) |

## Evidence Rules

- Cite Microsoft Learn pages with their page title and direct URL for every material capability or limitation claim.
- State what the cited source verifies and what remains a project or tenant assumption.
- Never treat missing documentation as proof that a capability is unsupported; use **Unable to verify** unless an authoritative source confirms the limitation.
- Do not claim to have checked current documentation if browsing or documentation tools are unavailable. Say the assessment is unverified and request relevant Microsoft Learn links or access.
- Flag preview features, version-specific behaviour, licensing prerequisites and documented limits.
- Community posts may help locate a topic but are not sufficient evidence for a definitive classification.

## Response Format

### Overall Assessment
A short conclusion: feasible, feasible with conditions, not supported, or unable to verify.

### Acceptance Criteria Assessment
For each criterion: classification, concise reasoning, Microsoft Learn evidence, and key assumptions or dependencies.

### Refinement Questions
Only questions whose answers could change feasibility, scope, implementation approach or estimate.

### Suggested Story Updates
Revised wording or testable acceptance criteria where useful.

### Recommended Estimate
T-shirt size with a one-line rationale.

Keep all output as a draft for the user to review.
