# Onboarding Process — Paper Walkthrough

Status: AI-assisted draft pending portfolio-owner review

This document examines three scenarios against the proposed
onboarding requirements. No software tests, account changes,
or production activities were performed.

## UAT-01: Missing manager information

### Why should the request stop?
Manager information is mandatory under BR-01. Without it,
support cannot reliably identify who should clarify the
employee's business needs. The request should remain
Pending clarification, with provisioning blocked.

### Who should provide the missing information?
The requester should provide it. The assigned support
contact should coordinate the follow-up.

### What allows the request to move forward?
Support confirms that all mandatory fields are complete.
The request can then proceed to access approval.
Complete information alone does not authorize provisioning.

## UAT-06: Reader approved, Admin granted

### Why is this a problem?
Admin access exceeds the approved Reader role. This violates
BR-04 and introduces unnecessary access risk.
The request should not pass the readiness check.

### Who should coordinate the correction?
The support owner should coordinate with an authorized
access administrator and the application owner.
Unexpected privileged access should also be assessed
through the organization's security escalation process.

### What evidence confirms the correction?
An access check must show that the granted role matches
the approved Reader role and that unintended Admin access
has been removed. Record the correction and verification
in the approved internal system without exposing credentials.

## UAT-09: Employee acknowledgement missing

### Why should the request remain open?
BR-07 requires employee acknowledgement and support guidance
before closure. Passing technical checks does not establish
that the handover is complete.

### Who should follow up?
The support owner should contact the employee and arrange
the handover. If the employee is unavailable, record a
follow-up action and retain Awaiting handover status.

### What evidence allows closure?
Record the employee's acknowledgement, confirmation that
support guidance was provided, completed readiness checks,
and the absence of unresolved blockers.

## Questions and improvements identified

- Distinguish complete request information from access approval.
- Define how approval authority will be verified.
- Confirm how urgent requests and absent approvers are handled.
- Confirm whether partial handover is allowed when some
  requested applications remain pending.
- Define an escalation and follow-up schedule for employees
  who are unavailable to acknowledge handover.

These decisions require stakeholder validation before
implementation.

## Validation limits

This is a documentation exercise using fictional scenarios.
It does not demonstrate that a software system enforces
these controls. All software UAT cases remain Not run.
