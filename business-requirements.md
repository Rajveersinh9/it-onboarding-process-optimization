# Business requirements

Version 0.1 | Independent simulation | Unvalidated draft

## Objective and scope
Propose a repeatable intake-to-handover process that makes missing information, approval status, device readiness, and support ownership visible. No production system or real organization is represented.

In scope: request intake, clarification, access approval, provisioning task coordination, readiness validation, handover, and exception tracking.
Out of scope: building identity integrations, production configuration, procurement, offboarding, clinical systems, and legal compliance certification.

## Assumed stakeholders and questions to validate
| Role | Proposed responsibility | Question requiring validation |
| --- | --- | --- |
| Hiring manager | Submit request and confirm business need | Who can delegate approval? |
| Application owner | Approve application access | Which roles and entitlements are permitted? |
| IT support | Coordinate provisioning, readiness, and handover | Which tools and queues are actually used? |
| Security contact | Resolve access or readiness exceptions | Who may approve an exception and for how long? |
| New employee | Confirm access and receive guidance | What accessible training format is needed? |
| Service owner | Own process and outstanding risks | What lead time and service targets are realistic? |

These roles have not been interviewed. Requirements below are analyst-proposed for the simulation.

## Requirements and acceptance criteria
| ID | Priority | Requirement | Acceptance criterion |
| --- | --- | --- | --- |
| BR-01 | Must | Capture request ID, employee identifier, manager, start date, requested applications, and approval status. | A request missing any required field is Pending clarification; missing fields are listed; provisioning cannot begin. |
| BR-02 | Must | Record an authorized application approval before access is granted. | Each requested application has approver role/identifier, decision, and timestamp. Rejected or pending items cannot move to provisioning. Approval authority must be checked against the assumed approver register. |
| BR-03 | Must | Assign an accountable support owner and maintain status history. | Every accepted request has one owner; each transition records previous status, new status, time, and actor. |
| BR-04 | Must | Provision only the approved application roles. | The granted-access list matches the approved list; extra or mismatched access blocks readiness and is referred for correction. |
| BR-05 | Must | Check device and access readiness before handover. | Asset assignment, approved-access check, encryption confirmation, update check, and MFA enrollment check each have a result and evidence reference. Any failed or missing check blocks Ready for handover. |
| BR-06 | Must | Handle unresolved blockers explicitly. | A blocker has an owner, next action, next-update time, and impact note; manager and support owner receive a status update; the request is not closed. |
| BR-07 | Must | Close only after a documented handover. | Closure requires readiness checks complete, no unresolved blockers, employee acknowledgement, and support guidance provided. Unavailable employee acknowledgement leaves the request Awaiting handover. |
| BR-08 | Should | Measure process performance without exposing sensitive data. | A report shows request counts by status and missing-information counts, identifies its reporting period and denominator, and excludes passwords and personal identifiers. |

Must items gate pilot readiness. BR-08 can be delivered after a controlled pilot begins; it must not delay basic access controls.

## Constraints and design rules
- Store evidence references, never passwords, recovery codes, or tokens, in tickets.
- Apply role-based visibility to request records in any future implementation.
- Use fictional identifiers for public examples; keep production evidence in approved internal systems.
- A requested urgent start does not override approval or readiness checks.
- Retention periods and exception authorities require organizational decisions; none are invented here.

## Open decisions
D-01: Confirm approval register and delegates. D-02: Confirm lead time and escalation deadlines. D-03: Confirm approved evidence storage and retention. D-04: Confirm readiness policy and support tool. D-05: Confirm accessibility and user training needs.

## Change handling
Record proposed changes with reason, affected requirement IDs, impact, decision owner, and decision. Revise linked tests and handover guidance when an acceptance criterion changes. No change has organizational approval in this simulation.
