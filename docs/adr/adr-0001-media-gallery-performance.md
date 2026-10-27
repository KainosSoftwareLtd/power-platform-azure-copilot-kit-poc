---
title: "ADR-0001: Improve Media Gallery Performance"
status: "Proposed"
date: "2026-10-27"
authors: "Demonstration example"
tags: ["architecture", "decision", "dataverse", "media-gallery", "demo"]
supersedes: ""
superseded_by: ""
---

# ADR-0001: Improve Media Gallery Performance

> Demonstration only. This is a synthetic scenario; the stakeholder, performance concerns, and cost comparison are illustrative and are not verified project facts.

## Status

Proposed

## Context

This illustrative scenario assumes that a media gallery relies on Power Automate and that users have raised concerns about latency and throttling. It also assumes that Dataverse image columns may have higher costs. These claims are not based on measured latency, a workload profile, or a cost comparison; those inputs would need to be gathered before treating this as a real decision.

A synthetic project stakeholder is used for this example. No real person or organisation is represented.

## Decision

Replace the performance-critical Power Automate path with a Dataverse Custom API defined as an Action and implemented by a synchronous plug-in. Call the Action through the Dataverse Web API using HTTP POST. This keeps the operation in the Power Platform while reducing reliance on flow orchestration for the gallery's critical path.

The decision is proposed pending a performance test against the current implementation and confirmation that the plug-in can complete within Dataverse execution constraints.

## Consequences

### Positive

- **POS-001**: Removes Power Automate orchestration from the gallery's performance-critical operation, with the aim of reducing latency and flow throttling exposure; load testing must verify the improvement.
- **POS-002**: Provides a defined Dataverse API contract that can be called by the gallery and other authorised clients.
- **POS-003**: Places the operation's application logic alongside Dataverse data and security controls.

### Negative

- **NEG-001**: Introduces custom plug-in code that requires developer skills, automated testing, and managed-solution deployment.
- **NEG-002**: Synchronous plug-in execution holds the caller until processing completes, so inefficient queries or excessive work can worsen perceived performance.
- **NEG-003**: The Custom API and plug-in are less directly configurable by makers than a Power Automate flow and require an explicit support and ownership model.

## Alternatives Considered

### Retain the Power Automate flow

- **ALT-001**: **Description**: Continue using the existing flow, potentially optimising its actions and data retrieval.
- **ALT-002**: **Rejection Reason**: In this illustrative scenario, the current approach is assumed to be slow and throttled. It may be reconsidered if profiling identifies a flow-level change that meets an agreed performance target.

### Store gallery images in Dataverse image columns

- **ALT-003**: **Description**: Use Dataverse image columns as the gallery's image storage and retrieval mechanism.
- **ALT-004**: **Rejection Reason**: In this illustrative scenario, this option is assumed to cost too much. No cost comparison was supplied, so this alternative must be reassessed using project-specific estimates.

### Make no change

- **ALT-005**: **Description**: Keep the current implementation without making a performance change.
- **ALT-006**: **Rejection Reason**: This leaves the reported latency and throttling concerns unresolved.

## Implementation Notes

- **IMP-001**: Measure the current gallery's response time, request volume, and throttling behaviour; agree measurable response-time and load targets with the stakeholder before implementation.
- **IMP-002**: Define a stable Custom API Action contract and implement only the work required for the gallery operation in the synchronous plug-in. Keep queries and returned data scoped to what the gallery needs.
- **IMP-003**: Deploy the Custom API and plug-in through a managed solution, with automated tests and an operational owner for future changes.
- **IMP-004**: Compare the new implementation with the baseline under representative load. Verify response time, failure rate, and throttling; do not retire the existing path until the agreed targets are met.
- **IMP-005**: Monitor plug-in execution duration and failures after release, and review the outcome with the project stakeholder.

## References

- **REF-001**: No related ADRs existed when this record was created.
- **REF-002**: [Create and use custom APIs (Microsoft Dataverse)](https://learn.microsoft.com/power-apps/developer/data-platform/custom-api)
- **REF-003**: [Use plug-ins to extend business processes](https://learn.microsoft.com/power-apps/developer/data-platform/plug-ins)