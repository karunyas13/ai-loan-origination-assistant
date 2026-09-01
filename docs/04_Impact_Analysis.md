# Impact Analysis

## 1. Purpose

This document assesses the impact of the proposed TO-BE Loan Origination Process across business processes, stakeholders, technology, data, integrations, reporting, controls, testing, operations, and AI governance.

The Impact Analysis builds on:

- Project Charter and Business Problem
- Stakeholder Analysis
- AS-IS Loan Origination Process
- TO-BE Loan Origination Process
- Gap Analysis

The objective is to understand what must change to move from the current state to the proposed future state and identify the areas requiring detailed business and functional requirements.

---

# 2. Impact Analysis Objectives

The objectives of this analysis are to:

1. Identify business areas affected by the proposed solution.
2. Assess changes to existing processes and responsibilities.
3. Identify new system capabilities.
4. Identify data and integration impacts.
5. Identify reporting and KPI impacts.
6. Identify operational and control impacts.
7. Identify testing requirements.
8. Identify AI-related governance and human-review impacts.
9. Support requirement prioritization.
10. Provide traceability between gaps and future requirements.

---

# 3. Impact Categories

The proposed changes are assessed across the following categories:

| Impact Category | Description |
|---|---|
| Process | Changes to loan origination activities, workflows and handoffs |
| People / Roles | Changes to responsibilities, ownership and user activities |
| Technology | New or modified system functionality |
| Data | Changes to data capture, validation, storage and history |
| Integration / API | Changes involving external or internal system interfaces |
| Reporting | New KPIs, dashboards and operational reporting |
| Controls | Changes to authorization, auditability and business controls |
| Testing | Testing required to validate the proposed changes |
| Operations | Changes to queues, exception handling and daily processing |
| AI Governance | Controls required for AI-assisted capabilities |

---

# 4. Impact Rating

The following rating scale is used:

| Rating | Definition |
|---|---|
| High | Significant process, system, data or control change |
| Medium | Moderate change requiring configuration, training or testing |
| Low | Limited change with minimal operational impact |

---

# 5. Overall Gap Impact Summary

| Gap ID | Change Area | Primary Impact Categories | Impact Level |
|---|---|---|---|
| GAP-001 | Application Completeness | Process, Technology, Data, Testing | High |
| GAP-002 | Document Management | Process, Technology, Data, Operations | High |
| GAP-003 | Data Validation | Technology, Data, Testing | High |
| GAP-004 | Business Rules | Process, Technology, Controls, Testing | High |
| GAP-005 | Exception Management | Process, People, Technology, Operations | High |
| GAP-006 | Workflow & Handoffs | Process, People, Integration | Medium |
| GAP-007 | Status Visibility | Process, Technology, Data, Reporting | High |
| GAP-008 | Underwriting Review | Process, People, Technology, AI Governance | High |
| GAP-009 | Rework Management | Process, Operations, Reporting | Medium |
| GAP-010 | KPI & Reporting | Data, Reporting, Technology | Medium |
| GAP-011 | Approval Conditions | Process, Technology, Data, Controls | High |
| GAP-012 | End-to-End Traceability | Process, Controls, Testing, Governance | High |

---

# 6. Detailed Impact Analysis

## IMP-001 — Application Completeness

### Related Gap

**GAP-001 — Application Completeness**

### Proposed Change

Introduce guided application capture, mandatory-field validation and application completeness checks before submission.

### Process Impact

**High**

The application-submission process changes because validation occurs earlier.

Incomplete applications should remain in Draft or require correction before successful submission where applicable.

### People / Role Impact

**Medium**

Loan applicants and loan officers receive earlier validation feedback.

Operations teams should receive fewer incomplete applications.

### Technology Impact

**High**

The solution requires:

- Mandatory-field configuration
- Validation messages
- Completeness calculation
- Draft functionality
- Submission controls

### Data Impact

**Medium**

Application fields require defined:

- Mandatory/optional indicators
- Data types
- Validation rules
- Allowed values

### Testing Impact

**High**

Testing must cover:

- Complete applications
- Missing mandatory information
- Invalid values
- Draft applications
- Successful submissions

### Expected Outcome

Reduced incomplete applications and downstream rework.

---

## IMP-002 — Document Management

### Related Gap

**GAP-002 — Document Management**

### Proposed Change

Introduce centralized document requirements and document-status tracking.

### Process Impact

**High**

Document requirements are identified earlier and tracked throughout the lifecycle.

### People / Role Impact

**Medium**

Applicants receive clearer document requirements.

Loan officers and operations users gain visibility into outstanding documents.

### Technology Impact

**High**

The solution requires:

- Document checklist generation
- Document statuses
- Missing-document identification
- Replacement tracking
- Document history

### Data Impact

**High**

New data elements may include:

- Document ID
- Application ID
- Document Type
- Required Indicator
- Document Status
- Received Date
- Verification Date
- Rejection Reason
- Replacement Indicator

### Operations Impact

**High**

Operations teams move from manual follow-up tracking toward structured document queues and statuses.

### Testing Impact

**High**

Testing should cover document requirements, missing documents, replacements, rejection and verification.

### Expected Outcome

Improved document completeness and reduced processing delays.

---

## IMP-003 — Data Validation

### Related Gap

**GAP-003 — Application Data Validation**

### Proposed Change

Introduce standardized automated validation for repeatable application-data checks.

### Technology Impact

**High**

Validation logic must support:

- Mandatory-field validation
- Data-type validation
- Range validation
- Cross-field validation
- Consistency checks
- Reason codes

### Data Impact

**High**

Data definitions and validation rules must be standardized.

A Data Dictionary will be required.

### Process Impact

**Medium**

Errors are identified earlier rather than during downstream manual review.

### People / Role Impact

**Medium**

Operations teams spend less time performing repetitive validation.

### Testing Impact

**High**

Positive, negative and boundary-value scenarios will be required.

### Expected Outcome

Improved data quality and reduced manual validation.

---

## IMP-004 — Business Rule Management

### Related Gap

**GAP-004 — Business Rule Management**

### Proposed Change

Introduce a centralized Business Rules Catalogue and standardized decision logic.

### Process Impact

**High**

Eligibility and processing decisions become more consistent and traceable.

### Technology Impact

**High**

The solution requires structured execution or evaluation of defined business rules.

### Data Impact

**Medium**

Rule inputs and outputs must be clearly defined.

### Control Impact

**High**

Business-rule ownership, versioning, effective dates and exceptions must be controlled.

### Testing Impact

**High**

Each business rule requires test scenarios covering:

- Pass
- Fail
- Boundary conditions
- Exceptions
- Missing information

### BA Deliverables Triggered

This impact creates the need for:

- Business Rules Catalogue
- Decision Tables
- Decision Trees where appropriate
- Rule-to-requirement traceability

### Expected Outcome

Consistent and testable business-rule execution.

---

## IMP-005 — Exception Management

### Related Gap

**GAP-005 — Exception Management**

### Proposed Change

Introduce structured identification, classification, routing and resolution of exceptions.

### Process Impact

**High**

Exception handling becomes a defined workflow rather than an informal activity.

### People / Role Impact

**High**

Exception ownership must be defined across:

- Loan Operations
- KYC Team
- Credit / Risk Team
- Underwriters
- Lending Approvers

### Technology Impact

**High**

The solution requires:

- Exception categories
- Reason codes
- Priority/severity
- Assignment
- Resolution status
- Comments
- History

### Operations Impact

**High**

Dedicated exception queues may be required.

### Reporting Impact

**Medium**

Exception volumes, aging and resolution times should be measurable.

### Testing Impact

**High**

Testing must verify routing, ownership, resolution and status behavior.

### Expected Outcome

Earlier exception resolution and clearer ownership.

---

## IMP-006 — Workflow and Handoffs

### Related Gap

**GAP-006 — Workflow and Manual Handoffs**

### Proposed Change

Introduce structured workflow routing and system integrations.

### Process Impact

**High**

Applications move through defined stages and queues.

### People / Role Impact

**Medium**

Users work from assigned queues rather than relying primarily on manual coordination.

### Technology Impact

**Medium**

Workflow configuration and assignment logic are required.

### Integration Impact

**High**

APIs may support communication between:

- KYC service
- Document service
- Credit / Risk service
- AI review service
- Notification service
- Downstream loan system

### Operations Impact

**Medium**

Queue ownership and escalation processes must be defined.

### Expected Outcome

Reduced manual handoffs and improved turnaround time.

---

## IMP-007 — Application Status Management

### Related Gap

**GAP-007 — Application Status Visibility**

### Proposed Change

Introduce a standardized application status model and controlled status transitions.

### Process Impact

**High**

Each lifecycle stage receives defined statuses and transition rules.

### Technology Impact

**High**

The solution must manage:

- Current status
- Previous status
- Status date/time
- Status reason
- Status history
- Allowed transitions

### Data Impact

**High**

Status-history data must be stored for audit and reporting.

### Reporting Impact

**High**

Status data enables:

- Pipeline reporting
- Stage aging
- Bottleneck analysis
- Turnaround-time calculations

### Testing Impact

**High**

Every allowed and prohibited status transition should be tested.

### BA Deliverables Triggered

- Status Catalogue
- Status Transition Matrix
- Workflow Rules

### Expected Outcome

Improved lifecycle visibility and traceability.

---

## IMP-008 — Underwriting and AI-Assisted Review

### Related Gap

**GAP-008 — Underwriting Review Efficiency**

### Proposed Change

Provide a consolidated underwriting review view supported by controlled AI-assisted analysis.

### Process Impact

**High**

Underwriters receive structured application information before completing their assessment.

### People / Role Impact

**High**

Underwriters remain responsible for professional judgment.

Authorized lending personnel remain responsible for final lending decisions.

### Technology Impact

**High**

The solution requires a consolidated view of:

- Application information
- KYC results
- Documents
- Validation results
- Eligibility results
- Business-rule outcomes
- Risk indicators
- Exceptions
- AI-assisted summary

### AI Impact

**High**

The AI capability may:

- Summarize application information
- Highlight missing information
- Highlight recorded exceptions
- Retrieve relevant rule information
- Organize risk indicators
- Identify conflicting information
- Generate structured review assistance

### AI Governance Impact

**High**

Controls must ensure:

- No autonomous loan approval
- No autonomous loan decline
- Human review
- Traceable AI output
- Uncertainty handling
- Supporting evidence where applicable
- Audit history
- Defined escalation

### Testing Impact

**High**

Testing must cover both functional AI integration and human-control requirements.

### Expected Outcome

Reduced information-gathering effort while maintaining human lending authority.

---

## IMP-009 — Rework Reduction

### Related Gap

**GAP-009 — Rework Management**

### Proposed Change

Move validation, completeness and exception identification earlier in the lifecycle.

### Process Impact

**Medium**

Issues should be resolved closer to the point where they originate.

### Operations Impact

**Medium**

Reduced backward movement between teams is expected.

### Reporting Impact

**Medium**

Rework should be measured using defined reason codes and stage movements.

### Data Impact

**Medium**

Rework events may require:

- Rework reason
- Source stage
- Destination stage
- Date/time
- Responsible team

### Expected Outcome

Improved first-time-right processing.

---

## IMP-010 — KPI and Reporting

### Related Gap

**GAP-010 — KPI and Operational Reporting**

### Proposed Change

Introduce structured KPI calculation and Power BI reporting.

### Data Impact

**High**

Required reporting fields must be captured consistently.

### Technology Impact

**Medium**

MySQL will support structured project data and KPI queries.

Microsoft Excel will support validation and reconciliation.

Microsoft Power BI will provide dashboards and visual reporting.

### Reporting Impact

**High**

Planned KPIs include:

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
- AI Review Volume
- Human Escalation Rate

### Testing Impact

**Medium**

KPI calculations must be reconciled against source data and SQL results.

### Expected Outcome

Improved operational visibility and data-driven decision-making.

---

## IMP-011 — Approval Condition Management

### Related Gap

**GAP-011 — Approval Condition Management**

### Proposed Change

Introduce centralized tracking of approval conditions.

### Process Impact

**High**

Conditions become formal workflow items before documentation and disbursement.

### Technology Impact

**High**

The solution requires condition creation, assignment, status and history.

### Data Impact

**High**

Condition data may include:

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

### Control Impact

**High**

Only appropriately authorized users should waive controlled conditions.

### Testing Impact

**High**

Testing must ensure applications cannot proceed to disbursement while blocking conditions remain unresolved.

### Expected Outcome

Improved control over approval-to-disbursement readiness.

---

## IMP-012 — End-to-End Traceability

### Related Gap

**GAP-012 — End-to-End Traceability**

### Proposed Change

Establish structured traceability across requirements, solution components and testing.

### Process Impact

**Medium**

BA, development and testing activities must use consistent requirement identifiers.

### Control Impact

**High**

Changes to requirements must be traceable to impacted functionality and tests.

### Testing Impact

**High**

Each test should trace back to applicable requirements and acceptance criteria.

### BA Impact

**High**

The BA will maintain relationships between:

- Pain Points
- Gaps
- Business Requirements
- Functional Requirements
- Business Rules
- User Stories
- Acceptance Criteria
- Data Requirements
- API Requirements
- Test Scenarios
- UAT Test Cases

### Expected Outcome

Improved requirement coverage and change-impact visibility.

---

# 7. Stakeholder Impact Analysis

| Stakeholder | Key Impact |
|---|---|
| Loan Applicant | Guided application, earlier validation, clearer document requirements and improved status visibility |
| Loan Officer | Improved application tracking and reduced manual follow-up |
| KYC / Verification Team | Structured KYC workflow and exception handling |
| Loan Operations Team | Automated validation, structured queues and improved visibility |
| Credit / Risk Team | Standardized risk and exception information |
| Underwriter | Consolidated review information and AI-assisted review |
| Lending Approver | Structured decision information and clearer audit trail |
| Documentation Team | Improved condition and documentation readiness visibility |
| Disbursement Team | Standardized disbursement-readiness checks |
| Product Owner | Requirement prioritization and business-rule ownership |
| Business Analyst | Requirements, rules, traceability, impact analysis and UAT support |
| Project Manager | Dependencies, risks, delivery planning and stakeholder coordination |
| Development / Integration Team | Workflow, API, validation and system implementation |
| QA / Testing Team | Increased requirement-based functional and integration testing |
| Data / Reporting Team | Structured data and KPI reporting |
| Risk / Compliance Team | Rule governance, auditability, decision controls and AI oversight |

---

# 8. Data Impact Summary

The proposed solution introduces or strengthens data requirements for:

- Applicant information
- Loan application information
- KYC results
- Document information
- Validation results
- Eligibility results
- Business-rule results
- Credit / risk information
- Exceptions
- Underwriting assessments
- Lending decisions
- Approval conditions
- Status history
- Disbursement information
- Audit information
- AI review information
- KPI reporting

Detailed field definitions will be maintained through the **Data Dictionary**.

Source-to-target movement will be documented through **Data Mapping**.

---

# 9. Integration Impact Summary

The future-state design may require simulated APIs for:

1. KYC verification
2. Document information
3. Credit / risk information
4. Business-rule processing
5. AI-assisted review
6. Notifications
7. Downstream loan processing

For each integration, later BA documentation will define:

- Endpoint
- Method
- Request
- Response
- Mandatory fields
- Validation
- Error responses
- Authentication assumption
- Timeout / failure handling
- Business impact of failure

---

# 10. Reporting Impact Summary

Reporting requirements will require structured lifecycle timestamps and outcome data.

The reporting solution will use:

- **MySQL** for structured data and SQL analysis
- **Microsoft Excel** for validation and reconciliation
- **Microsoft Power BI** for dashboards and visualization

Reporting requirements will be traced to defined business KPIs.

---

# 11. Control and Compliance Impact

The proposed process requires controls around:

- User access
- Role-based activities
- Lending authority
- Business-rule changes
- Exception resolution
- Condition waivers
- Decision recording
- Audit history
- Sensitive data handling
- AI-assisted outputs
- Human review

The portfolio will demonstrate these controls conceptually without representing the policies of any specific financial institution.

---

# 12. Testing Impact

The proposed changes require multiple levels of testing.

## Functional Testing

Validate system functionality against requirements.

## Business Rule Testing

Validate rule conditions, outcomes and boundary scenarios.

## Integration Testing

Validate API requests, responses, errors and failure handling.

## Data Testing

Validate mappings, mandatory fields, transformations and data quality.

## Workflow Testing

Validate routing, queues and status transitions.

## Negative Testing

Validate invalid inputs and prohibited actions.

## Regression Testing

Validate that changes do not negatively affect existing functionality.

## UAT

Business users validate that the solution meets agreed business requirements and supports expected business processes.

---

# 13. Training and Operational Readiness Impact

The proposed solution may require training or guidance for:

- Loan Officers
- Loan Operations
- KYC Reviewers
- Credit / Risk Teams
- Underwriters
- Lending Approvers
- Documentation Teams
- Disbursement Teams

Training topics may include:

- New workflow
- Application statuses
- Exception handling
- Business-rule outcomes
- Approval-condition tracking
- Reporting
- AI-assisted review
- Human-review responsibilities

Operational readiness will be assessed before implementation.

---

# 14. AI Governance Impact

AI introduces additional governance requirements beyond traditional workflow automation.

The proposed AI capability must follow these principles:

1. AI provides decision support only.
2. AI does not independently approve loans.
3. AI does not independently decline loans.
4. Authorized humans retain lending decision authority.
5. AI output should be reviewable.
6. Important observations should be supported by available information.
7. Uncertain output should be identified or escalated.
8. AI interactions should be auditable where appropriate.
9. AI failures should not prevent authorized human processing.
10. Human reviewers should be able to override or disregard AI-generated observations.

Detailed AI requirements, risks and controls will be documented later in the project.

---

# 15. Change Risk Summary

| Risk | Potential Impact | Initial Mitigation |
|---|---|---|
| Incorrect business-rule configuration | Incorrect eligibility or workflow outcome | Rule review, versioning and testing |
| Integration failure | Processing delays | Error handling and manual fallback |
| Poor data quality | Incorrect validation/reporting | Data-quality rules and validation |
| Incorrect status transitions | Workflow inconsistency | Status Transition Matrix and testing |
| Unresolved conditions | Incorrect disbursement readiness | Blocking-condition controls |
| User adoption issues | Operational inefficiency | Training and clear process documentation |
| Incorrect AI output | Reviewer confusion or inappropriate reliance | Human review, evidence and AI controls |
| Requirement changes | Scope, schedule and testing impact | Change control and RTM |

These risks will later be expanded in the project **RAID Log / Risk Register**.

---

# 16. Requirements Impact

The Impact Analysis identifies the need for detailed requirements covering:

### Business Requirements

What business outcomes and capabilities are required.

### Functional Requirements

How the proposed solution should behave.

### System Requirements

Technical and non-functional expectations.

### Business Rules

Conditions governing eligibility, validation, routing and processing.

### Data Requirements

Required fields, definitions, mappings and quality controls.

### Integration Requirements

System-to-system interaction requirements.

### Reporting Requirements

KPIs, calculations and dashboard requirements.

### AI Requirements

AI behavior, human review, limitations and governance.

These requirements will be formally documented in subsequent artifacts.

---

# 17. Traceability

The current analysis establishes the following traceability:

**Pain Point → Gap → Impact**

Example:

`PP-01 → GAP-001 → IMP-001`

Future artifacts will extend this chain:

`PP-01 → GAP-001 → IMP-001 → BR-001 → FR-xxx → US-xxx → AC-xxx → UAT-xxx`

This structure will later be consolidated within the **Requirements Traceability Matrix (RTM)**.

---

# 18. BA Conclusion

The Impact Analysis shows that the proposed loan origination transformation affects more than system functionality.

The changes influence:

- Business processes
- Stakeholder responsibilities
- Data
- Workflow
- Integrations
- Reporting
- Testing
- Operational controls
- AI governance

The results of this analysis will be used during requirements elicitation and requirements documentation to ensure that proposed changes are fully understood before solution implementation.

---

## Disclaimer

This Impact Analysis represents a simulated loan origination transformation created for educational and professional portfolio purposes.

It does not represent the internal processes, technology architecture, lending rules, regulatory interpretation, or policies of any specific financial institution.
