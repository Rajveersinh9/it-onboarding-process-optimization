# UAT plan and traceability

**Status: planned only. All cases Not run.** No deployed application, participant sign-off, execution evidence, or actual test outcomes exist.

## Purpose
Validate a future prototype against the proposed requirements. A paper walkthrough can review logic but cannot establish that a system enforces controls.

## Setup and entry criteria
Use a sandbox or fictional tracker, synthetic employee EMP-001, application APP-A, manager MGR-001, and assumed authorized approver OWN-001. Prepare a mock approval register. No real accounts, patient records, credentials, or production access are needed.

Before execution: choose and record the prototype/version, implement the intended gates, prepare synthetic fixtures, assign a tester, and agree expected outcomes. Without a prototype, label any exercise a documentation walkthrough only.

## Cases and requirements mapping
| Test | Requirement | Steps / input | Expected outcome | Status |
| --- | --- | --- | --- | --- |
| UAT-01 | BR-01 | Create a request missing manager; attempt to advance. | Pending clarification; missing manager identified; no provisioning. | Not run |
| UAT-02 | BR-01 | Supply all required fields with approval Pending. | Intake accepted; approval gate remains active. | Not run |
| UAT-03 | BR-02 | Attempt provisioning with Pending or Rejected approval; then with an unlisted approver. | Each attempt blocked; missing valid approval explained. | Not run |
| UAT-04 | BR-02 | Record Approved for APP-A by OWN-001 with timestamp. | Approval gate satisfied for APP-A only. | Not run |
| UAT-05 | BR-03 | Accept request; assign support owner; change status. | Owner retained; actor, time, old and new status recorded. | Not run |
| UAT-06 | BR-04 | Compare approved APP-A role Reader with granted role Admin. | Mismatch blocks readiness; correction recorded. | Not run |
| UAT-07 | BR-05 | Omit MFA evidence or mark encryption check Failed; attempt handover. | Ready for handover blocked; missing or failed check visible. | Not run |
| UAT-08 | BR-06 | Mark device unavailable and record blocker. | Owner, action, next-update time, impact, and notification recorded; not closed. | Not run |
| UAT-09 | BR-07 | Complete checks but omit employee acknowledgement; attempt closure. | Awaiting handover; closure blocked. | Not run |
| UAT-10 | BR-01–07 | Use complete approved request, matching access, passing checks, no blockers, acknowledgement and guidance. | Request can close with complete record and history. | Not run |
| UAT-11 | BR-08 | Use five synthetic requests: two Pending clarification, one Awaiting approval, two Closed. Generate aggregate report. | Total 5; counts 2/1/2; clarification rate 2/5 = 40%; period identified; no personal identifiers. | Not run |

## Execution record template
For each executed case record: test ID; date; tester; prototype/version; input fixture; actual result; Pass/Fail/Blocked; evidence reference; defect ID; retest result. Leave unexecuted fields blank. Never turn expected results into actual results.

## Defect record template
Defect ID; requirement/test ID; observed behavior; expected behavior; reproduction steps; impact; owner; status; evidence; fix version; retest outcome.

## Proposed exit criteria
All Must requirements pass positive and negative scenarios; no unresolved access-control or readiness-blocking defects; other defects explicitly assessed by the proposed service owner. Stakeholder acceptance remains a separate decision. This portfolio has no stakeholder acceptance.
