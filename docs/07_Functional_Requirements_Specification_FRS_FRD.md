# Functional Requirements Specification (FRS / FRD)

## AI-Powered Loan Origination Requirements & Risk Assistant

---

# 1. Document Purpose

This Functional Requirements Specification (FRS / FRD) defines the functional behavior required to support the proposed end-to-end loan origination process.

The document decomposes the approved Business Requirements `BR-001` through `BR-023` into detailed functional requirements.

The solution covers:

- Application capture
- KYC / identity verification
- Document management
- Data validation
- Eligibility and business rules
- Credit / risk assessment
- Exception management
- Workflow and queues
- Application statuses
- Underwriting
- Lending decisions
- Approval conditions
- Loan documentation
- Disbursement
- Closure and downstream handoff
- Reporting
- Auditability
- Integrations
- AI-assisted review
- Human review and override
- Requirements traceability

This document focuses on **what the solution must do**.

Detailed business-rule logic, decision tables, data definitions, API contracts, non-functional requirements, and test cases will be maintained in separate artifacts.

---

# 2. Requirement Identification Convention

Functional requirements use the following format:

`FR-001`, `FR-002`, `FR-003`, etc.

Each functional requirement includes:

- Requirement ID
- Related Business Requirement
- Functional Requirement
- Primary Actor
- Priority
- Key Validation / Exception Behavior

These IDs will remain stable throughout subsequent project artifacts.

---

# 3. Priority Definitions

| Priority | Definition |
|---|---|
| Must Have | Required for core processing or an essential control |
| Should Have | Important capability providing significant business value |
| Could Have | Useful enhancement that may follow core implementation |

---

# 4. Application Capture and Submission

## FR-001 — Create Loan Application

**Related Business Requirement:** BR-001  
**Primary Actor:** Loan Applicant / Loan Officer  
**Priority:** Must Have

### Functional Requirement

The system shall allow an authorized user to create a new loan application.

### Expected Behavior

The system shall:

- Create a new application record
- Generate a unique Application ID
- Record the creation date and time
- Record the application creator or source
- Assign the initial application status
- Allow required applicant and loan information to be captured

### Validation / Exception

The Application ID must be unique.

---

## FR-002 — Save Application as Draft

**Related Business Requirement:** BR-001  
**Primary Actor:** Loan Applicant / Loan Officer  
**Priority:** Must Have

### Functional Requirement

The system shall allow an incomplete application to be saved before final submission.

### Expected Behavior

The system shall:

- Preserve entered information
- Assign or retain the `Draft` status
- Allow the application to be reopened
- Display incomplete mandatory information

---

## FR-003 — Validate Mandatory Application Fields

**Related Business Requirement:** BR-001, BR-004  
**Primary Actor:** Loan Applicant / Loan Officer  
**Priority:** Must Have

### Functional Requirement

The system shall validate mandatory application fields before submission.

### Expected Behavior

The system shall identify missing mandatory information and provide validation messages.

### Exception Behavior

The application shall not proceed to successful submission while mandatory submission requirements remain incomplete.

---

## FR-004 — Validate Application Field Formats

**Related Business Requirement:** BR-004  
**Primary Actor:** Loan Applicant / Loan Officer  
**Priority:** Must Have

### Functional Requirement

The system shall validate applicable field formats, data types, ranges, and permitted values.

Examples may include:

- Date format
- Numeric format
- Required value ranges
- Enumerated values
- Cross-field consistency

Detailed validation rules will be defined in the Business Rules Catalogue and Data Dictionary.

---

## FR-005 — Determine Application Completeness

**Related Business Requirement:** BR-001  
**Primary Actor:** Loan Applicant / Loan Officer  
**Priority:** Must Have

### Functional Requirement

The system shall determine whether required application information is complete for submission.

### Expected Behavior

The system shall identify:

- Completed required information
- Missing required information
- Validation failures
- Remaining submission requirements

---

## FR-006 — Submit Loan Application

**Related Business Requirement:** BR-001  
**Primary Actor:** Loan Applicant / Loan Officer  
**Priority:** Must Have

### Functional Requirement

The system shall allow a valid and sufficiently complete loan application to be submitted for processing.

### Expected Behavior

Upon successful submission, the system shall:

- Record submission date and time
- Update the application status
- Preserve submitted information
- Initiate the next applicable workflow stage

### Exception Behavior

Submission shall fail when mandatory submission criteria are not satisfied.

---

# 5. KYC / Identity Verification

## FR-007 — Initiate KYC Verification

**Related Business Requirement:** BR-002, BR-019  
**Primary Actor:** System / KYC Team  
**Priority:** Must Have

### Functional Requirement

The system shall initiate KYC / identity-verification processing when the application reaches the required lifecycle stage.

---

## FR-008 — Record KYC Verification Outcome

**Related Business Requirement:** BR-002  
**Primary Actor:** KYC Team / KYC Service  
**Priority:** Must Have

### Functional Requirement

The system shall record the KYC verification outcome for the application.

Potential outcomes may include:

- Pending
- Verified
- Failed
- Manual Review Required

Final values will be maintained in the Status / Reference Data Catalogue.

---

## FR-009 — Route KYC Exceptions

**Related Business Requirement:** BR-002, BR-007  
**Primary Actor:** KYC Team / Loan Operations  
**Priority:** Must Have

### Functional Requirement

The system shall identify KYC cases requiring manual review and route them to the appropriate work queue.

---

## FR-010 — Maintain KYC History

**Related Business Requirement:** BR-002, BR-018  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall retain relevant KYC processing history, including status changes, outcomes, timestamps, and review activity.

---

# 6. Document Management

## FR-011 — Determine Required Documents

**Related Business Requirement:** BR-003, BR-005  
**Primary Actor:** System / Loan Operations  
**Priority:** Must Have

### Functional Requirement

The system shall determine the required document checklist based on applicable business rules.

---

## FR-012 — Record Document Information

**Related Business Requirement:** BR-003  
**Primary Actor:** Loan Applicant / Loan Officer / Operations  
**Priority:** Must Have

### Functional Requirement

The system shall record document information associated with a loan application.

Document information may include:

- Document ID
- Application ID
- Document Type
- Required Indicator
- Received Date
- Verification Status
- Verification Date
- Rejection Reason
- Replacement Indicator

---

## FR-013 — Track Document Status

**Related Business Requirement:** BR-003, BR-009  
**Primary Actor:** Loan Operations  
**Priority:** Must Have

### Functional Requirement

The system shall maintain the processing status of each required document.

---

## FR-014 — Identify Missing Documents

**Related Business Requirement:** BR-003  
**Primary Actor:** System / Loan Operations  
**Priority:** Must Have

### Functional Requirement

The system shall identify required documents that have not been received or have not satisfied applicable requirements.

---

## FR-015 — Handle Rejected or Replacement Documents

**Related Business Requirement:** BR-003  
**Primary Actor:** Loan Operations  
**Priority:** Must Have

### Functional Requirement

The system shall support rejection and replacement of documents while retaining appropriate history.

---

## FR-016 — Determine Document Completeness

**Related Business Requirement:** BR-003  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall determine whether mandatory document requirements have been satisfied before defined downstream stages.

---

# 7. Application Data Validation

## FR-017 — Execute Data Validation Rules

**Related Business Requirement:** BR-004, BR-005  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall execute applicable data-validation rules against loan application information.

---

## FR-018 — Perform Cross-Field Validation

**Related Business Requirement:** BR-004  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall support validation involving relationships between multiple application fields where required.

---

## FR-019 — Record Validation Results

**Related Business Requirement:** BR-004, BR-018  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall record validation results, including:

- Validation rule
- Result
- Reason
- Date/time
- Relevant field or data element

---

## FR-020 — Route Validation Failures

**Related Business Requirement:** BR-004, BR-007  
**Primary Actor:** System / Loan Operations  
**Priority:** Must Have

### Functional Requirement

The system shall route unresolved validation failures to the appropriate correction or exception workflow.

---

# 8. Eligibility and Business Rules

## FR-021 — Execute Eligibility Rules

**Related Business Requirement:** BR-005  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall evaluate applicable eligibility rules against application information.

---

## FR-022 — Record Business Rule Results

**Related Business Requirement:** BR-005, BR-018  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall record the result of applicable business-rule evaluations.

The record should support traceability to:

- Rule ID
- Rule version where applicable
- Result
- Reason
- Evaluation timestamp

---

## FR-023 — Distinguish Hard Stops and Review Exceptions

**Related Business Requirement:** BR-005, BR-007  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall distinguish between rule outcomes that prevent further processing and outcomes that require authorized human review.

Detailed classification will be maintained in the Business Rules Catalogue.

---

## FR-024 — Route Rule Exceptions

**Related Business Requirement:** BR-005, BR-007  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall route applicable business-rule exceptions to the appropriate reviewer or queue.

---

# 9. Credit and Risk Assessment

## FR-025 — Obtain Credit / Risk Information

**Related Business Requirement:** BR-006, BR-019  
**Primary Actor:** System / Credit-Risk Service  
**Priority:** Must Have

### Functional Requirement

The system shall obtain or simulate the credit and risk information required for assessment.

---

## FR-026 — Record Risk Indicators

**Related Business Requirement:** BR-006  
**Primary Actor:** System / Credit-Risk Team  
**Priority:** Must Have

### Functional Requirement

The system shall record relevant risk indicators associated with the application.

---

## FR-027 — Identify Risk Exceptions

**Related Business Requirement:** BR-006, BR-007  
**Primary Actor:** System / Credit-Risk Team  
**Priority:** Must Have

### Functional Requirement

The system shall identify risk conditions requiring additional review or escalation.

---

## FR-028 — Present Risk Information for Review

**Related Business Requirement:** BR-006, BR-010  
**Primary Actor:** Credit-Risk Team / Underwriter  
**Priority:** Must Have

### Functional Requirement

The system shall present relevant credit and risk information to authorized reviewers.

---

# 10. Exception Management

## FR-029 — Create Exception Record

**Related Business Requirement:** BR-007  
**Primary Actor:** System / Authorized User  
**Priority:** Must Have

### Functional Requirement

The system shall create an exception record when an issue requires tracking or human review.

The record may include:

- Exception ID
- Application ID
- Exception Category
- Reason Code
- Severity / Priority
- Source Stage
- Assigned Team
- Status
- Created Date
- Resolution Date
- Resolution Notes

---

## FR-030 — Assign Exception

**Related Business Requirement:** BR-007, BR-008  
**Primary Actor:** System / Loan Operations  
**Priority:** Must Have

### Functional Requirement

The system shall assign or route exceptions to an appropriate team or authorized user.

---

## FR-031 — Update Exception Status

**Related Business Requirement:** BR-007  
**Primary Actor:** Authorized Reviewer  
**Priority:** Must Have

### Functional Requirement

Authorized users shall be able to update exception status based on permitted workflow transitions.

---

## FR-032 — Record Exception Resolution

**Related Business Requirement:** BR-007, BR-018  
**Primary Actor:** Authorized Reviewer  
**Priority:** Must Have

### Functional Requirement

The system shall record the resolution, reviewer, date/time, and relevant notes for resolved exceptions.

---

## FR-033 — Prevent Progression for Blocking Exceptions

**Related Business Requirement:** BR-007, BR-015  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall prevent progression beyond defined stages while unresolved blocking exceptions exist.

---

# 11. Workflow and Queue Management

## FR-034 — Route Application Between Lifecycle Stages

**Related Business Requirement:** BR-008  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall route applications between applicable loan origination lifecycle stages based on workflow rules.

---

## FR-035 — Assign Work Items

**Related Business Requirement:** BR-008  
**Primary Actor:** System / Authorized User  
**Priority:** Must Have

### Functional Requirement

The system shall support assignment of application-related work items to the appropriate team or user.

---

## FR-036 — Display Work Queues

**Related Business Requirement:** BR-008  
**Primary Actor:** Operations / KYC / Credit-Risk / Underwriter  
**Priority:** Should Have

### Functional Requirement

The system shall provide role-appropriate work queues containing items requiring action.

---

## FR-037 — Track Work Ownership

**Related Business Requirement:** BR-008, BR-018  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall maintain current work ownership and relevant assignment history.

---

# 12. Application Status Management

## FR-038 — Maintain Current Application Status

**Related Business Requirement:** BR-009  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall maintain the current lifecycle status of each loan application.

---

## FR-039 — Enforce Permitted Status Transitions

**Related Business Requirement:** BR-009  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall allow only valid status transitions based on defined transition rules.

Detailed transitions will be documented in the Status Transition Matrix.

---

## FR-040 — Maintain Status History

**Related Business Requirement:** BR-009, BR-018  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall retain application status history.

The history shall include, where applicable:

- Previous Status
- New Status
- Date/time
- Trigger
- User / System Actor
- Reason

---

## FR-041 — Display Application Status

**Related Business Requirement:** BR-009  
**Primary Actor:** Authorized Stakeholders  
**Priority:** Must Have

### Functional Requirement

The system shall display application status appropriate to the user's role and access level.

---

# 13. Underwriting Review

## FR-042 — Create Consolidated Underwriting View

**Related Business Requirement:** BR-010  
**Primary Actor:** Underwriter  
**Priority:** Must Have

### Functional Requirement

The system shall provide a consolidated underwriting view containing relevant application information.

The view may include:

- Applicant information
- Loan information
- KYC outcome
- Document status
- Validation results
- Eligibility results
- Business-rule results
- Credit / risk indicators
- Open exceptions
- AI-assisted review
- Review history

---

## FR-043 — Record Underwriting Assessment

**Related Business Requirement:** BR-010, BR-018  
**Primary Actor:** Underwriter  
**Priority:** Must Have

### Functional Requirement

The system shall allow an authorized underwriter to record an underwriting assessment.

---

## FR-044 — Request Additional Information

**Related Business Requirement:** BR-010  
**Primary Actor:** Underwriter  
**Priority:** Must Have

### Functional Requirement

The system shall allow an underwriter to request additional information when required to complete review.

---

## FR-045 — Route Completed Underwriting Review

**Related Business Requirement:** BR-008, BR-010  
**Primary Actor:** System / Underwriter  
**Priority:** Must Have

### Functional Requirement

The system shall route a completed underwriting assessment to the appropriate lending-decision stage.

---

# 14. Human Lending Decision

## FR-046 — Restrict Lending Decision to Authorized Users

**Related Business Requirement:** BR-011  
**Primary Actor:** Lending Approver  
**Priority:** Must Have

### Functional Requirement

The system shall permit final loan approval or decline only by users with appropriate lending-decision authority.

---

## FR-047 — Record Lending Decision

**Related Business Requirement:** BR-012  
**Primary Actor:** Lending Approver  
**Priority:** Must Have

### Functional Requirement

The system shall record the final lending decision.

The record shall include:

- Application ID
- Decision
- Decision Reason
- Decision Authority
- Decision Date/time
- Relevant comments
- Applicable approval conditions

---

## FR-048 — Prevent AI from Executing Lending Decision

**Related Business Requirement:** BR-011, BR-020, BR-021  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall prevent the AI-assisted review capability from independently executing or recording a final loan approval or decline.

---

## FR-049 — Maintain Decision History

**Related Business Requirement:** BR-012, BR-018  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall maintain appropriate history of lending-decision activity.

---

# 15. Approval Condition Management

## FR-050 — Create Approval Condition

**Related Business Requirement:** BR-013  
**Primary Actor:** Lending Approver / Authorized User  
**Priority:** Must Have

### Functional Requirement

The system shall allow authorized users to create approval conditions for approved applications.

---

## FR-051 — Track Approval Condition Status

**Related Business Requirement:** BR-013  
**Primary Actor:** Loan Operations / Documentation Team  
**Priority:** Must Have

### Functional Requirement

The system shall track each approval condition through its lifecycle.

Potential information includes:

- Condition ID
- Application ID
- Condition Type
- Description
- Owner
- Status
- Required Date
- Completion Date
- Waiver Indicator
- Waiver Authority
- Resolution Notes

---

## FR-052 — Restrict Condition Waivers

**Related Business Requirement:** BR-013, BR-018  
**Primary Actor:** Authorized User  
**Priority:** Must Have

### Functional Requirement

The system shall restrict controlled approval-condition waivers to authorized users.

---

## FR-053 — Prevent Progression for Blocking Conditions

**Related Business Requirement:** BR-013, BR-015  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall prevent disbursement readiness while mandatory blocking approval conditions remain unresolved.

---

# 16. Loan Documentation

## FR-054 — Initiate Loan Documentation

**Related Business Requirement:** BR-014  
**Primary Actor:** Documentation Team  
**Priority:** Must Have

### Functional Requirement

The system shall allow loan documentation processing to begin when applicable prerequisite requirements are satisfied.

---

## FR-055 — Track Documentation Status

**Related Business Requirement:** BR-014, BR-009  
**Primary Actor:** Documentation Team  
**Priority:** Must Have

### Functional Requirement

The system shall track loan documentation status through defined lifecycle values.

---

## FR-056 — Validate Documentation Completion

**Related Business Requirement:** BR-014, BR-015  
**Primary Actor:** System / Documentation Team  
**Priority:** Must Have

### Functional Requirement

The system shall verify that mandatory documentation requirements have been completed before disbursement readiness.

---

# 17. Disbursement

## FR-057 — Evaluate Disbursement Readiness

**Related Business Requirement:** BR-015  
**Primary Actor:** System / Disbursement Operations  
**Priority:** Must Have

### Functional Requirement

The system shall evaluate whether an approved application satisfies defined disbursement-readiness criteria.

---

## FR-058 — Block Ineligible Disbursement

**Related Business Requirement:** BR-015  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall prevent progression to disbursement when mandatory readiness requirements are not satisfied.

---

## FR-059 — Initiate Disbursement Processing

**Related Business Requirement:** BR-015, BR-019  
**Primary Actor:** Disbursement Operations  
**Priority:** Must Have

### Functional Requirement

The system shall support initiation of simulated disbursement processing for eligible applications.

---

## FR-060 — Record Disbursement Outcome

**Related Business Requirement:** BR-015, BR-018  
**Primary Actor:** System / Disbursement Operations  
**Priority:** Must Have

### Functional Requirement

The system shall record the outcome and relevant details of the simulated disbursement process.

---

# 18. Application Closure and Handoff

## FR-061 — Close Completed Application

**Related Business Requirement:** BR-016  
**Primary Actor:** System / Loan Operations  
**Priority:** Must Have

### Functional Requirement

The system shall support controlled closure of applications that have reached a valid terminal state.

---

## FR-062 — Support Non-Disbursed Terminal Outcomes

**Related Business Requirement:** BR-016  
**Primary Actor:** System / Loan Operations  
**Priority:** Must Have

### Functional Requirement

The system shall support appropriate closure of applications with terminal outcomes such as:

- Declined
- Withdrawn
- Cancelled

where applicable to the modeled process.

---

## FR-063 — Handoff Disbursed Loan

**Related Business Requirement:** BR-016, BR-019  
**Primary Actor:** System / Loan Operations  
**Priority:** Must Have

### Functional Requirement

The system shall support simulated handoff of successfully disbursed loan information to a downstream loan-servicing process.

---

# 19. Operational Reporting

## FR-064 — Capture KPI Source Data

**Related Business Requirement:** BR-017  
**Primary Actor:** System  
**Priority:** Should Have

### Functional Requirement

The system shall capture sufficient structured data to calculate defined operational KPIs.

---

## FR-065 — Calculate Operational KPIs

**Related Business Requirement:** BR-017  
**Primary Actor:** Reporting Solution  
**Priority:** Should Have

### Functional Requirement

The reporting solution shall support calculation of defined loan origination KPIs.

Potential KPIs include:

- Total Applications
- Application Completion Rate
- KYC Completion Rate
- Missing Document Rate
- Average Processing Time
- Stage Turnaround Time
- Eligibility Failure Rate
- Exception Rate
- Rework Rate
- Underwriting Queue Volume
- Approval Rate
- Decline Rate
- Approval-to-Disbursement Time
- AI-Assisted Review Volume
- Human Escalation Rate

---

## FR-066 — Provide Operational Dashboard

**Related Business Requirement:** BR-017  
**Primary Actor:** Product Owner / Project Manager / Operations  
**Priority:** Should Have

### Functional Requirement

The solution shall provide a Power BI dashboard displaying agreed operational KPIs.

---

## FR-067 — Support Reporting Filters

**Related Business Requirement:** BR-017  
**Primary Actor:** Reporting User  
**Priority:** Should Have

### Functional Requirement

The reporting solution shall support appropriate filters for analyzing loan origination performance.

Detailed dimensions will be finalized during data and reporting design.

---

# 20. Auditability

## FR-068 — Record Significant User Activities

**Related Business Requirement:** BR-018  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall retain appropriate audit information for significant controlled user activities.

---

## FR-069 — Record Significant Automated Activities

**Related Business Requirement:** BR-018  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall retain appropriate audit information for significant automated processing activities.

---

## FR-070 — Provide Audit Traceability

**Related Business Requirement:** BR-018  
**Primary Actor:** Authorized User  
**Priority:** Must Have

### Functional Requirement

Authorized users shall be able to trace relevant application activities using retained history.

---

# 21. Integration Requirements

## FR-071 — Support KYC Service Integration

**Related Business Requirement:** BR-002, BR-019  
**Primary Actor:** System  
**Priority:** Should Have

### Functional Requirement

The solution shall support a simulated API-based interaction with a KYC verification service.

---

## FR-072 — Support Document Service Integration

**Related Business Requirement:** BR-003, BR-019  
**Primary Actor:** System  
**Priority:** Should Have

### Functional Requirement

The solution shall support simulated exchange of document-related information with a document service.

---

## FR-073 — Support Credit / Risk Service Integration

**Related Business Requirement:** BR-006, BR-019  
**Primary Actor:** System  
**Priority:** Should Have

### Functional Requirement

The solution shall support simulated API-based retrieval of credit / risk information.

---

## FR-074 — Support Business Rule Service Interaction

**Related Business Requirement:** BR-005, BR-019  
**Primary Actor:** System  
**Priority:** Should Have

### Functional Requirement

The solution shall support structured interaction with the business-rule evaluation capability.

---

## FR-075 — Support AI Review Service Interaction

**Related Business Requirement:** BR-020, BR-019  
**Primary Actor:** System  
**Priority:** Should Have

### Functional Requirement

The solution shall support structured interaction with the AI-assisted review capability.

---

## FR-076 — Support Notification Service Interaction

**Related Business Requirement:** BR-008, BR-019  
**Primary Actor:** System  
**Priority:** Could Have

### Functional Requirement

The solution shall support simulated notification requests for applicable lifecycle events.

---

## FR-077 — Handle Integration Failure

**Related Business Requirement:** BR-019  
**Primary Actor:** System / Operations  
**Priority:** Must Have

### Functional Requirement

The system shall detect applicable integration failures and provide controlled error, retry, exception, or manual-fallback handling.

Detailed behavior will be defined in the API Requirements document.

---

# 22. AI-Assisted Review

## FR-078 — Initiate AI-Assisted Review

**Related Business Requirement:** BR-020  
**Primary Actor:** Authorized Reviewer / System  
**Priority:** Should Have

### Functional Requirement

The system shall allow AI-assisted review to be initiated for eligible applications.

---

## FR-079 — Generate Application Summary

**Related Business Requirement:** BR-020  
**Primary Actor:** AI Review Service  
**Priority:** Should Have

### Functional Requirement

The AI-assisted review capability shall generate a structured summary based on permitted application information.

---

## FR-080 — Highlight Potential Missing Information

**Related Business Requirement:** BR-020  
**Primary Actor:** AI Review Service  
**Priority:** Should Have

### Functional Requirement

The AI-assisted review capability shall be able to highlight potentially missing or incomplete information for human review.

---

## FR-081 — Summarize Recorded Exceptions and Risk Indicators

**Related Business Requirement:** BR-020  
**Primary Actor:** AI Review Service  
**Priority:** Should Have

### Functional Requirement

The AI-assisted review capability shall summarize relevant recorded exceptions and risk indicators without independently determining the lending outcome.

---

## FR-082 — Retrieve Relevant Business Rule Information

**Related Business Requirement:** BR-005, BR-020  
**Primary Actor:** AI Review Service  
**Priority:** Should Have

### Functional Requirement

The AI-assisted review capability shall support retrieval of relevant approved business-rule information for reviewer reference.

---

## FR-083 — Identify Potential Information Conflicts

**Related Business Requirement:** BR-020  
**Primary Actor:** AI Review Service  
**Priority:** Should Have

### Functional Requirement

The AI-assisted review capability may identify potential conflicts between available information and present them for human review.

---

## FR-084 — Produce Structured AI Output

**Related Business Requirement:** BR-020, BR-022  
**Primary Actor:** AI Review Service  
**Priority:** Must Have

### Functional Requirement

AI-assisted review output shall be represented in a structured format suitable for review and traceability.

Potential output elements include:

- Application Summary
- Missing Information Observations
- Rule References
- Risk / Exception Summary
- Potential Conflicts
- Supporting References
- Uncertainty / Review Indicator

---

# 23. Human Review and AI Governance

## FR-085 — Require Human Review of AI Output

**Related Business Requirement:** BR-021  
**Primary Actor:** Underwriter / Authorized Reviewer  
**Priority:** Must Have

### Functional Requirement

AI-generated observations shall remain subject to review by an authorized human user.

---

## FR-086 — Allow AI Output Acceptance or Rejection

**Related Business Requirement:** BR-021  
**Primary Actor:** Authorized Reviewer  
**Priority:** Must Have

### Functional Requirement

The system shall allow an authorized reviewer to accept, reject, correct, or disregard applicable AI-generated observations.

---

## FR-087 — Escalate Uncertain AI Output

**Related Business Requirement:** BR-021, BR-022  
**Primary Actor:** System / AI Review Service  
**Priority:** Must Have

### Functional Requirement

AI output identified as uncertain or requiring additional judgment shall be flagged for human review.

---

## FR-088 — Preserve Human Decision Authority

**Related Business Requirement:** BR-011, BR-021  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall preserve human authority for final lending decisions regardless of AI-generated observations.

---

## FR-089 — Continue Human Processing During AI Unavailability

**Related Business Requirement:** BR-021  
**Primary Actor:** System / Operations  
**Priority:** Must Have

### Functional Requirement

Failure or unavailability of the AI-assisted review capability shall not remove authorized human ability to continue the loan review process through an approved fallback path.

---

# 24. AI Traceability

## FR-090 — Record AI Review Activity

**Related Business Requirement:** BR-022  
**Primary Actor:** System  
**Priority:** Must Have

### Functional Requirement

The system shall record relevant AI-assisted review activity.

The record may include:

- Application ID
- Review ID
- Review timestamp
- AI use case
- Output
- Supporting references
- Review status
- Human reviewer
- Human action

---

## FR-091 — Retain Supporting References

**Related Business Requirement:** BR-022  
**Primary Actor:** System / AI Review Service  
**Priority:** Must Have

### Functional Requirement

Where applicable, the system shall retain or reference the supporting information used for reviewable AI observations.

---

## FR-092 — Record Human Response to AI Output

**Related Business Requirement:** BR-021, BR-022  
**Primary Actor:** Authorized Reviewer  
**Priority:** Must Have

### Functional Requirement

The system shall record applicable human action taken in response to AI-assisted observations.

---

# 25. Requirements Traceability

## FR-093 — Maintain Requirement Identifiers

**Related Business Requirement:** BR-023  
**Primary Actor:** Business Analyst / Project Team  
**Priority:** Must Have

### Functional Requirement

Project requirements and related artifacts shall use stable unique identifiers.

---

## FR-094 — Maintain Requirement Relationships

**Related Business Requirement:** BR-023  
**Primary Actor:** Business Analyst  
**Priority:** Must Have

### Functional Requirement

The project shall maintain traceable relationships between applicable analysis, requirements, design, and testing artifacts.

---

## FR-095 — Support Change Impact Analysis

**Related Business Requirement:** BR-023  
**Primary Actor:** Business Analyst  
**Priority:** Must Have

### Functional Requirement

Traceability information shall support identification of downstream artifacts affected by requirement changes.

---

# 26. Functional Requirements Summary

| Functional Area | FR Range |
|---|---|
| Application Capture & Submission | FR-001 – FR-006 |
| KYC / Identity Verification | FR-007 – FR-010 |
| Document Management | FR-011 – FR-016 |
| Data Validation | FR-017 – FR-020 |
| Eligibility & Business Rules | FR-021 – FR-024 |
| Credit / Risk Assessment | FR-025 – FR-028 |
| Exception Management | FR-029 – FR-033 |
| Workflow & Queue Management | FR-034 – FR-037 |
| Application Status Management | FR-038 – FR-041 |
| Underwriting | FR-042 – FR-045 |
| Human Lending Decision | FR-046 – FR-049 |
| Approval Conditions | FR-050 – FR-053 |
| Loan Documentation | FR-054 – FR-056 |
| Disbursement | FR-057 – FR-060 |
| Closure & Handoff | FR-061 – FR-063 |
| Operational Reporting | FR-064 – FR-067 |
| Auditability | FR-068 – FR-070 |
| Integrations | FR-071 – FR-077 |
| AI-Assisted Review | FR-078 – FR-084 |
| Human Review & AI Governance | FR-085 – FR-089 |
| AI Traceability | FR-090 – FR-092 |
| Requirements Traceability | FR-093 – FR-095 |

**Total Functional Requirements: 95**

---

# 27. Key Error and Exception Scenarios

Detailed test scenarios will be created later; however, the functional design must account for scenarios including:

| Scenario | Expected Functional Response |
|---|---|
| Mandatory application field missing | Prevent applicable submission and identify missing information |
| Invalid field format | Display validation failure |
| KYC cannot be completed | Route for appropriate review |
| Required document missing | Identify document as outstanding |
| Document rejected | Record reason and allow controlled replacement |
| Data validation failure | Record failure and route for correction/review |
| Eligibility hard-stop rule fails | Prevent prohibited progression |
| Review exception triggered | Create and route exception |
| Blocking exception unresolved | Prevent defined downstream progression |
| Invalid status transition attempted | Reject transition |
| Unauthorized lending decision attempted | Prevent action |
| Approval condition unresolved | Prevent applicable disbursement progression |
| Unauthorized condition waiver attempted | Prevent waiver |
| Integration unavailable | Apply defined failure/fallback handling |
| AI service unavailable | Preserve approved human processing path |
| AI output uncertain | Flag for human review |
| AI attempts decision action | Prevent final decision execution |

---

# 28. Role-Based Functional Access

Detailed access-control requirements will be finalized later.

At a high level:

- Applicants may access appropriate application-related functions.
- Loan Officers may support application processing.
- KYC users may perform KYC-related review activities.
- Operations users may perform assigned operational activities.
- Credit / Risk users may review risk-related information.
- Underwriters may perform underwriting activities.
- Lending Approvers may perform authorized lending-decision activities.
- Documentation users may perform loan-documentation activities.
- Disbursement users may perform disbursement-related activities.
- Reporting users may access authorized reporting information.
- Risk / Compliance users may review applicable controlled and audit information.

Final lending-decision capability shall remain restricted to appropriately authorized human users.

---

# 29. Functional Traceability Model

The traceability model is now extended to:

**Pain Point → Gap → Impact → Business Requirement → Functional Requirement**

Examples:

`PP-01 → GAP-001 → IMP-001 → BR-001 → FR-001 / FR-002 / FR-003 / FR-005 / FR-006`

`PP-02 → GAP-002 → IMP-002 → BR-003 → FR-011 – FR-016`

`PP-04 → GAP-004 → IMP-004 → BR-005 → FR-021 – FR-024`

`PP-08 → GAP-008 → IMP-008 → BR-010 → FR-042 – FR-045`

`PP-11 → GAP-011 → IMP-011 → BR-013 / BR-015 → FR-050 – FR-053 / FR-057 – FR-060`

Future artifacts will extend traceability into:

**Business Rule → User Story → Acceptance Criteria → Data/API Requirement → Test Scenario → UAT Test Case → KPI / Outcome**

The complete relationship will be maintained in the Requirements Traceability Matrix.

---

# 30. Functional Requirements Validation

Functional requirements should be reviewed to confirm that they are:

- Traceable to a business requirement
- Clear
- Unambiguous
- Feasible
- Testable
- Consistent
- Within scope
- Assigned a priority
- Compatible with required business controls
- Suitable for decomposition into user stories and test scenarios

---

# 31. Downstream BA Artifacts

The functional requirements defined in this document will provide input into:

- System Requirements Specification
- Business Rules Catalogue
- Decision Tables / Decision Trees
- Status Catalogue
- Status Transition Matrix
- User Stories
- Acceptance Criteria
- Data Dictionary
- Data Mapping
- API Requirements
- Non-Functional Requirements
- Test Scenarios
- UAT Test Cases
- Requirements Traceability Matrix
- Power BI KPI Design
- AI Use Cases and Governance Controls

---

# 32. Functional Requirements Baseline

Requirements `FR-001` through `FR-095` represent the initial functional requirements baseline for this portfolio project.

Future requirement changes should be evaluated through impact analysis and reflected in applicable downstream artifacts and the Requirements Traceability Matrix.

---

# 33. Conclusion

This Functional Requirements Specification translates the approved business requirements into detailed functional capabilities covering the complete loan origination lifecycle.

The specification establishes the functional baseline required for subsequent business-rule definition, system requirements, data analysis, API design, Agile user stories, acceptance criteria, testing, reporting, and AI-assisted workflow design.

The final lending decision remains under authorized human control.

---

## Disclaimer

This Functional Requirements Specification represents a simulated Business Analyst deliverable created for educational and professional portfolio purposes.

The requirements, rules, integrations, workflows, lending scenarios, and AI capabilities are illustrative and do not represent the systems, policies, lending criteria, or regulatory interpretation of any specific financial institution.
