# Impact Analysis

## Document Context

**Typical Real-Project Location:** Confluence / SharePoint / Excel Impact Assessment / Change Request / Requirements Repository  
**Typical Ownership:** Business Analyst, with input from Business SMEs, Product Owner, Solution / Technical Teams, QA and Project Manager  
**Primary Users:** Business Analyst, Product Owner, Project Manager, Business SMEs, Development, QA, Data / Reporting and Control Stakeholders  
**Artifact Type:** Business analysis working artifact / change-impact assessment

**Purpose:** Assesses how the proposed TO-BE solution affects business processes, people, technology, data, integrations, reporting, controls, testing and operations before implementation.

> **Real-Project Note:** Impact Analysis is a common Business Analysis activity, particularly for transformation projects and requirement changes. It does not always exist as a standalone document. Depending on the organization, impact analysis may be maintained within a Change Request, BRD, Jira / Azure DevOps item, Confluence page, Excel workbook or solution-impact assessment. This portfolio maintains it separately to demonstrate the analysis clearly.

---

## 1. Purpose

This analysis assesses the impact of moving from the **AS-IS Loan Origination Process** to the proposed **TO-BE Loan Origination Process**.

It builds on:

- Project Charter and Business Problem
- Stakeholder Analysis
- AS-IS Loan Origination Process
- TO-BE Loan Origination Process
- Gap Analysis

The objective is to understand what will be affected by the proposed changes before those changes are implemented.

The analysis considers impacts across:

- Business processes
- Stakeholders and roles
- Technology
- Data
- Integrations
- Reporting
- Controls
- Testing
- Operations
- AI governance

---

## 2. Impact Analysis Objectives

The objectives are to:

1. Identify business areas affected by the proposed solution.
2. Assess changes to existing processes and responsibilities.
3. Identify new or modified system capabilities.
4. Identify data impacts.
5. Identify integration impacts.
6. Identify reporting and KPI impacts.
7. Identify operational and control impacts.
8. Identify testing implications.
9. Identify training and readiness considerations.
10. Identify AI-related governance and human-review impacts.
11. Support prioritization and delivery planning.
12. Support requirement-change analysis.
13. Establish traceability between identified gaps and requirements.

> **BA Principle:** Impact Analysis helps the project understand the consequences of a proposed change. The BA facilitates the analysis, but technical, operational, control and delivery impacts should be validated with the appropriate SMEs rather than determined by the BA alone.

---

## 3. Impact Categories

| Impact Category | Description |
|---|---|
| Process | Changes to loan-origination activities, workflows and handoffs |
| People / Roles | Changes to responsibilities, ownership and user activities |
| Technology | New or modified application/system functionality |
| Data | Changes to data capture, validation, storage, history or usage |
| Integration / API | Changes involving internal or external interfaces |
| Reporting | Changes to KPIs, dashboards and operational reporting |
| Controls | Changes to authorization, auditability and business controls |
| Testing | Testing required to validate proposed changes |
| Operations | Changes to queues, exception handling and daily processing |
| Training / Readiness | User guidance, training and implementation-readiness considerations |
| AI Governance | Controls and oversight required for AI-assisted capabilities |

---

## 4. Impact Rating

The following qualitative scale is used for the portfolio assessment:

| Rating | Definition |
|---|---|
| High | Significant change affecting major process, system, data, operational or control areas |
| Medium | Moderate change requiring configuration, coordination, testing or user adjustment |
| Low | Limited change with relatively small operational or implementation impact |

> **Real-Project Note:** Organizations may use different impact-scoring methods, including High / Medium / Low, numerical scoring, risk matrices or formal change-assessment criteria.

---

## 5. Overall Gap Impact Summary

| Impact ID | Gap ID | Change Area | Primary Impact Categories | Impact Level |
|---|---|---|---|---|
| IMP-001 | GAP-001 | Application Completeness | Process, Technology, Data, Testing | High |
| IMP-002 | GAP-002 | Document Management | Process, Technology, Data, Operations | High |
| IMP-003 | GAP-003 | Data Validation | Technology, Data, Testing | High |
| IMP-004 | GAP-004 | Business Rules | Process, Technology, Controls, Testing | High |
| IMP-005 | GAP-005 | Exception Management | Process, People, Technology, Operations | High |
| IMP-006 | GAP-006 | Workflow & Handoffs | Process, People, Integration | Medium |
| IMP-007 | GAP-007 | Status Visibility | Process, Technology, Data, Reporting | High |
| IMP-008 | GAP-008 | Underwriting Review | Process, People, Technology, AI Governance | High |
| IMP-009 | GAP-009 | Rework Management | Process, Operations, Reporting | Medium |
| IMP-010 | GAP-010 | KPI & Reporting | Data, Reporting, Technology | Medium |
| IMP-011 | GAP-011 | Approval Conditions | Process, Technology, Data, Controls | High |
| IMP-012 | GAP-012 | End-to-End Traceability | Process, Controls, Testing, Governance | High |

---

# 6. Detailed Impact Analysis

## IMP-001 — Application Completeness

### Related Gap

**GAP-001 — Application Completeness**

### Proposed Change

Introduce guided application capture, mandatory-field validation and application-completeness checks before submission.

### Process Impact — High

The application-submission process changes because repeatable completeness validation occurs earlier.

Incomplete applications should remain in Draft or require correction before successful submission where applicable.

### People / Role Impact — Medium

Loan Applicants and Loan Officers receive earlier validation feedback.

Loan Operations should receive fewer incomplete applications requiring downstream follow-up.

### Technology Impact — High

The solution requires capabilities for:

- Mandatory-field configuration
- Validation messages
- Completeness checks
- Draft functionality
- Submission controls

### Data Impact — Medium

Application data requires defined:

- Mandatory / optional indicators
- Data types
- Allowed values
- Validation requirements

### Testing Impact — High

Testing should cover:

- Complete applications
- Missing mandatory information
- Invalid values
- Draft applications
- Submission validation
- Successful submissions

### Expected Outcome

Reduced incomplete applications and downstream rework.

### Primary Requirement Traceability

**BR-001 — Application Capture and Completeness**

---

## IMP-002 — Document Management

### Related Gap

**GAP-002 — Document Management**

### Proposed Change

Introduce structured document requirements and document-status tracking.

### Process Impact — High

Required documents are identified earlier and tracked throughout the relevant stages of the lifecycle.

### People / Role Impact — Medium

Applicants receive clearer document requirements.

Loan Officers and Loan Operations gain improved visibility into outstanding and rejected documents.

### Technology Impact — High

The solution requires:

- Document checklist generation
- Document statuses
- Missing-document identification
- Replacement tracking
- Document history
- Verification results

### Data Impact — High

Relevant data may include:

- Document ID
- Application ID
- Document type
- Required indicator
- Document status
- Received date
- Verification date
- Rejection reason
- Replacement indicator

Final field definitions will be validated during data analysis.

### Operations Impact — High

Loan Operations moves from primarily manual follow-up toward structured document tracking and work queues.

### Testing Impact — High

Testing should cover:

- Required-document determination
- Missing documents
- Document receipt
- Rejected documents
- Replacement documents
- Document verification
- Document completeness

### Expected Outcome

Improved document completeness and reduced processing delays.

### Primary Requirement Traceability

**BR-003 — Document Requirement and Tracking**

---

## IMP-003 — Data Validation

### Related Gap

**GAP-003 — Application Data Validation**

### Proposed Change

Introduce standardized validation for repeatable application-data checks.

### Technology Impact — High

Validation capabilities should support applicable:

- Mandatory-field validation
- Data-type validation
- Range validation
- Cross-field validation
- Consistency checks
- Validation reason codes

### Data Impact — High

Data definitions and validation rules must be clearly defined.

Data-analysis activities will establish:

- Field definitions
- Data types
- Allowed values
- Mandatory indicators
- Validation rules
- Source information where applicable

### Process Impact — Medium

Errors are identified earlier rather than relying primarily on downstream manual review.

### People / Role Impact — Medium

Loan Operations should spend less time performing repetitive validation while retaining responsibility for cases requiring business judgment.

### Testing Impact — High

Testing should include:

- Positive scenarios
- Negative scenarios
- Boundary conditions
- Missing values
- Invalid formats
- Cross-field inconsistencies

### Expected Outcome

Improved data quality and reduced repetitive manual validation.

### Primary Requirement Traceability

**BR-004 — Application Data Quality and Validation**

---

## IMP-004 — Business Rule Management

### Related Gap

**GAP-004 — Business Rule Management**

### Proposed Change

Introduce structured and traceable business-rule definitions and decision logic.

### Process Impact — High

Eligibility and processing behavior becomes more consistently defined.

### Technology Impact — High

Relevant deterministic rules must be implemented or evaluated consistently by the solution.

### Data Impact — Medium

Inputs, outputs and reason codes associated with rules must be clearly defined.

### Control Impact — High

Relevant rules require appropriate:

- Ownership
- Review
- Change control
- Effective/version information where applicable
- Exception handling
- Auditability

### Testing Impact — High

Applicable rules require scenarios covering:

- PASS
- FAIL
- HARD_STOP
- REVIEW_REQUIRED
- Boundary conditions
- Missing information
- Exceptions
- Error conditions where relevant

### Supporting Analysis

Business-rule analysis may use:

- Business Rules Catalogue
- Decision Tables
- Decision Trees where useful
- Process flows
- Functional requirements
- Acceptance criteria

> **Real-Project Note:** These are analysis techniques and artifacts, not mandatory separate documents. Decision logic may be embedded within functional specifications, Confluence, rules-engine specifications or backlog items.

### Expected Outcome

More consistent, traceable and testable business-rule behavior.

### Primary Requirement Traceability

**BR-005 — Eligibility and Business Rule Management**

---

## IMP-005 — Exception Management

### Related Gap

**GAP-005 — Exception Management**

### Proposed Change

Introduce structured identification, classification, routing and resolution of exceptions.

### Process Impact — High

Exception handling becomes a defined workflow rather than relying primarily on informal coordination.

### People / Role Impact — High

Exception responsibilities may involve:

- Loan Operations
- KYC / Verification Team
- Credit / Risk Team
- Underwriters
- Lending Approvers
- Other authorized SMEs where applicable

Ownership depends on the exception type.

### Technology Impact — High

The solution requires support for:

- Exception categories
- Reason codes
- Priority / severity where applicable
- Assignment
- Resolution status
- Comments
- History
- Escalation

### Operations Impact — High

Structured work queues and exception-aging visibility may be required.

### Reporting Impact — Medium

Operational reporting may include:

- Exception volume
- Exception category
- Exception aging
- Resolution time
- Outstanding exceptions

### Testing Impact — High

Testing should verify:

- Exception creation
- Categorization
- Assignment
- Routing
- Blocking behavior
- Resolution
- History

### Expected Outcome

Earlier exception identification, clearer ownership and improved resolution tracking.

### Primary Requirement Traceability

**BR-007 — Exception Management**

---

## IMP-006 — Workflow and Handoffs

### Related Gap

**GAP-006 — Workflow and Manual Handoffs**

### Proposed Change

Introduce structured workflow routing, work queues and relevant system integrations.

### Process Impact — High

Applications move through defined stages with clearer ownership and routing.

### People / Role Impact — Medium

Users increasingly work from assigned queues and defined workflow activities rather than relying primarily on manual coordination.

### Technology Impact — Medium

Workflow and assignment capabilities are required.

### Integration Impact — High

Relevant integrations may include:

- KYC / identity verification service
- Document service
- Credit / risk service
- Business-rule service
- AI-assisted review service
- Notification service
- Reporting flow
- Downstream loan system

### Operations Impact — Medium

Queue ownership, escalation and fallback processes must be defined.

### Testing Impact — High

Testing should validate:

- Workflow routing
- Assignment
- Queue behavior
- Integration success
- Integration failure
- Retry/fallback behavior where applicable

### Expected Outcome

Reduced manual coordination and improved processing visibility.

### Primary Requirement Traceability

**BR-008 — Workflow and Work Queue Management**

Supporting requirement:

**BR-019 — Integration Capability**

---

## IMP-007 — Application Status Management

### Related Gap

**GAP-007 — Application Status Visibility**

### Proposed Change

Introduce consistent application statuses and controlled workflow progression.

### Process Impact — High

Lifecycle stages have defined status behavior that reflects application progression.

### Technology Impact — High

The solution must support:

- Current status
- Previous status where required
- Status date/time
- Status reason where applicable
- Status history
- Permitted workflow progression

### Data Impact — High

Status-history information must be stored for operational visibility, reporting and audit purposes.

### Reporting Impact — High

Status data supports:

- Application pipeline reporting
- Stage aging
- Bottleneck analysis
- Turnaround-time calculations
- Queue reporting

### Testing Impact — High

Testing should verify:

- Permitted progression
- Prohibited progression
- Status history
- Status timestamps
- Role restrictions where applicable
- Exception/rework behavior

### Supporting Analysis

Status behavior may be represented through:

- Functional requirements
- Business rules
- Process flows
- Workflow diagrams
- User stories and acceptance criteria
- A status-transition table/matrix where complexity makes one useful

> **Real-Project Note:** A standalone Status Catalogue or Status Transition Matrix is not inherently required. The information is often maintained within workflow requirements, functional specifications, state diagrams or delivery-tool acceptance criteria.

### Expected Outcome

Improved lifecycle visibility and traceability.

### Primary Requirement Traceability

**BR-009 — Application Status Management**

Relevant rules:

- **RULE-026 — Permitted Status Transition**
- **RULE-027 — Status History**

---

## IMP-008 — Underwriting and AI-Assisted Review

### Related Gap

**GAP-008 — Underwriting Review Efficiency**

### Proposed Change

Provide a consolidated underwriting review experience supported by controlled AI-assisted analysis.

### Process Impact — High

Underwriters receive relevant application information in a structured review experience before completing their assessment.

### People / Role Impact — High

Underwriters retain responsibility for professional review and judgment.

Authorized lending personnel retain responsibility for final lending decisions.

### Technology Impact — High

The solution requires access to relevant:

- Application information
- KYC results
- Documents
- Validation results
- Eligibility results
- Business-rule outcomes
- Credit / risk indicators
- Exceptions
- Supporting evidence
- AI-assisted review output

### AI Impact — High

The AI capability may support:

- Application summarization
- Missing/incomplete-information observations
- Summarization of recorded risk indicators
- Summarization of existing exceptions
- Retrieval of relevant approved rules/knowledge
- Identification of possible conflicting information
- Structured review output

### AI Governance Impact — High

Controls must ensure:

- No autonomous loan approval
- No autonomous loan decline
- No AI override of authorized human decisions
- No AI replacement of deterministic business-rule results
- Human review
- Traceable AI output
- Uncertainty handling
- Supporting evidence where applicable
- Audit history
- Human/manual fallback
- Reviewer ability to accept, reject, correct or disregard AI observations

### Testing Impact — High

Testing should cover:

- AI integration behavior
- Structured output
- Missing information
- Uncertainty handling
- Human review
- AI failure
- Manual fallback
- Audit logging
- Prohibited autonomous actions

### Expected Outcome

Reduced information-gathering effort while maintaining human lending authority and appropriate controls.

### Primary Requirement Traceability

- **BR-010 — Underwriting Review**
- **BR-020 — AI-Assisted Application Review**
- **BR-021 — AI Human Review and Override**
- **BR-022 — AI Transparency and Traceability**

---

## IMP-009 — Rework Reduction

### Related Gap

**GAP-009 — Rework Management**

### Proposed Change

Move applicable completeness, validation and exception identification earlier in the lifecycle.

### Process Impact — Medium

Issues should be identified and resolved closer to the stage where they originate.

### Operations Impact — Medium

Reduced unnecessary backward movement between teams is expected.

Some rework will remain legitimate and must be supported rather than eliminated.

### Reporting Impact — Medium

Rework may be measured using:

- Rework reason
- Source stage
- Destination stage
- Date/time
- Responsible team
- Resolution time

### Data Impact — Medium

The solution may require structured rework information to support operational analysis.

### Expected Outcome

Improved first-time-right processing and better visibility into avoidable rework.

### Primary Requirement Traceability

This impact is cross-functional and relates primarily to:

- **BR-001 — Application Capture and Completeness**
- **BR-003 — Document Requirement and Tracking**
- **BR-004 — Application Data Quality and Validation**
- **BR-005 — Eligibility and Business Rule Management**
- **BR-007 — Exception Management**

---

## IMP-010 — KPI and Reporting

### Related Gap

**GAP-010 — KPI and Operational Reporting**

### Proposed Change

Introduce structured KPI calculation, validation and Power BI reporting.

### Data Impact — High

Required reporting fields and lifecycle timestamps must be captured consistently.

### Technology Impact — Medium

The portfolio solution will use:

- **MySQL** for structured project data and KPI queries
- **Microsoft Excel** for validation and reconciliation
- **Microsoft Power BI** for dashboards and visual reporting

### Reporting Impact — High

Planned KPI areas include:

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

Detailed definitions, filters, business logic and calculation rules will be agreed during reporting analysis.

### Testing Impact — Medium

KPI calculations should be reconciled against source data and SQL results.

Testing should include:

- Calculation accuracy
- Filters
- Date ranges
- Null handling
- Duplicate handling
- Reconciliation

### Expected Outcome

Improved operational visibility and data-driven process management.

### Primary Requirement Traceability

**BR-017 — Operational KPI Reporting**

---

## IMP-011 — Approval Condition Management

### Related Gap

**GAP-011 — Approval Condition Management**

### Proposed Change

Introduce structured tracking and control of approval conditions.

### Process Impact — High

Conditions become formal workflow items between approval and downstream documentation/disbursement activities.

### Technology Impact — High

The solution requires:

- Condition creation
- Assignment
- Status tracking
- Supporting information
- Resolution
- History
- Waiver handling where permitted

### Data Impact — High

Condition information may include:

- Condition ID
- Application ID
- Condition type
- Description
- Owner
- Status
- Required date
- Completion date
- Waiver indicator
- Waiver authority
- Resolution notes

Detailed fields will be finalized during data analysis.

### Control Impact — High

Only appropriately authorized personnel should waive controlled conditions.

Blocking conditions must prevent progression where the approved business rule requires it.

### Testing Impact — High

Testing should cover:

- Condition creation
- Assignment
- Satisfaction
- Blocking conditions
- Authorized waiver
- Unauthorized waiver attempts
- Documentation/disbursement readiness

### Expected Outcome

Improved control over approval-to-disbursement readiness.

### Primary Requirement Traceability

**BR-013 — Approval Condition Management**

Supporting requirements include:

- **BR-014 — Loan Documentation Readiness**
- **BR-015 — Disbursement Readiness**

---

## IMP-012 — End-to-End Traceability

### Related Gap

**GAP-012 — End-to-End Traceability**

### Proposed Change

Establish appropriate traceability across business needs, requirements, implementation items and testing.

### Process Impact — Medium

Business Analysis, Development and Testing activities use consistent identifiers and relationships where appropriate.

### Control Impact — High

Requirement changes should be assessed against impacted:

- Functional requirements
- Business rules
- Data requirements
- Interfaces
- Backlog items
- Tests
- UAT scenarios
- Reporting

### Testing Impact — High

Testing should be traceable to applicable requirements or acceptance criteria where formal coverage is required.

### BA Impact — High

The BA supports traceability between relevant items such as:

- Pain Points
- Gaps
- Impacts
- Business Requirements
- Functional Requirements
- System Requirements
- Business Rules
- Decision Logic
- User Stories
- Acceptance Criteria
- Data Requirements
- API Requirements
- Test Scenarios
- UAT Test Cases

### Traceability Mechanism

Depending on the project, traceability may be maintained through:

- Requirements Traceability Matrix
- Jira
- Azure DevOps
- Requirements-management platform
- Test-management tool
- Combination of linked delivery artifacts

> **Real-Project Note:** A standalone RTM is not required on every Agile project. The required level of traceability depends on organizational governance, regulatory requirements, delivery methodology and tooling.

### Expected Outcome

Improved requirement coverage and change-impact visibility.

### Primary Requirement Traceability

**BR-023 — Requirements Traceability**

---

# 7. Stakeholder Impact Analysis

| Stakeholder | Key Impact |
|---|---|
| Loan Applicant | Guided application, earlier validation, clearer document requirements and improved status visibility |
| Loan Officer | Improved application tracking and reduced unnecessary manual follow-up |
| KYC / Verification Team | Structured KYC workflow and exception handling |
| Loan Operations Team | Earlier validation, structured queues, exception management and improved lifecycle visibility |
| Credit / Risk Team | More structured risk, rule and exception information |
| Underwriter | Consolidated review information and controlled AI-assisted support |
| Lending Approver | Structured decision information, approval controls and improved audit history |
| Documentation Team | Improved condition and documentation-readiness visibility |
| Disbursement / Operations Team | Standardized disbursement-readiness information and controls |
| Product Owner | Prioritization, scope and business-value decisions |
| Business Analyst | Requirements analysis, clarification, impact analysis, traceability and UAT support |
| Project Manager | Dependencies, risks, schedule and stakeholder coordination |
| Development / Integration Team | Workflow, API, validation, data and system implementation impacts |
| QA / Testing Team | Requirement-based functional, integration, negative and regression testing |
| Data / Reporting Team | Structured data, KPI calculation and reporting requirements |
| Risk / Compliance Team | Control, auditability, lending-decision and AI-governance impacts |

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
- AI-review information
- KPI reporting

Detailed data analysis will define:

- Business definitions
- Field names
- Data types
- Allowed values
- Mandatory/optional indicators
- Validation rules
- Source information
- Target information where applicable
- Transformation logic where applicable

A **Data Dictionary** and **Data Mapping** may be used to represent these requirements.

> **Real-Project Note:** Data dictionaries and mapping specifications are commonly maintained in Excel, Confluence, data-modeling tools or integration documentation depending on the organization.

---

# 9. Integration Impact Summary

The future-state solution may require simulated interfaces for:

1. KYC / identity verification
2. Document information
3. Credit / risk information
4. Business-rule processing
5. AI-assisted review
6. Notifications
7. Reporting
8. Downstream loan processing

For each relevant interface, analysis should consider:

- Business purpose
- Source and target
- Trigger
- Endpoint / operation where applicable
- Request
- Response
- Mandatory fields
- Validation
- Error responses
- Authentication assumptions
- Timeout / failure handling
- Retry/fallback behavior
- Business impact of failure

> **Real-Project Note:** The BA commonly defines and validates business/interface requirements with architects, developers and integration SMEs. Detailed technical API design is normally a collaborative technical responsibility rather than solely a BA deliverable.

---

# 10. Reporting Impact Summary

Reporting requires structured lifecycle timestamps, statuses and outcome data.

The portfolio implementation will use:

- **MySQL** for structured data and SQL analysis
- **Microsoft Excel** for validation and reconciliation
- **Microsoft Power BI** for dashboards and visualization

Reporting analysis will define:

- KPI name
- Business definition
- Calculation
- Source fields
- Filters
- Reporting frequency
- Dimensions
- Expected reconciliation
- Business owner

---

# 11. Control and Compliance Impact

The proposed process requires consideration of controls around:

- User access
- Role-based activities
- Lending authority
- Business-rule changes
- Exception resolution
- Condition waivers
- Lending-decision recording
- Disbursement readiness
- Audit history
- Sensitive data handling
- AI-assisted outputs
- Human review

The Business Analyst documents relevant requirements and facilitates clarification.

Applicable business, risk, compliance, security and technology stakeholders validate and approve controls according to organizational governance.

---

# 12. Testing Impact

The proposed changes require multiple forms of validation.

## Functional Testing

Validate expected functionality against functional requirements and acceptance criteria.

## Business Rule Testing

Validate applicable:

- Conditions
- Outcomes
- Boundaries
- Hard stops
- Review-required scenarios
- Exceptions

## Integration Testing

Validate:

- Requests
- Responses
- Errors
- Timeouts
- Failure handling
- Data exchange

## Data Testing

Validate:

- Mappings
- Mandatory fields
- Data types
- Transformations
- Data quality
- Reconciliation

## Workflow Testing

Validate:

- Routing
- Queues
- Assignment
- Workflow progression
- Prohibited progression
- Rework paths

## Negative Testing

Validate invalid inputs, unauthorized activities and prohibited system behavior.

## Regression Testing

Confirm that implemented changes do not adversely affect previously working functionality.

## User Acceptance Testing

Business users validate that the solution supports agreed business processes and requirements.

The BA commonly supports UAT by:

- Helping identify business scenarios
- Clarifying expected outcomes
- Supporting test-data preparation
- Answering requirement questions
- Supporting defect triage
- Helping distinguish defects from requirement changes
- Tracking business acceptance issues

---

# 13. Training and Operational Readiness Impact

Potentially affected users include:

- Loan Officers
- Loan Operations
- KYC Reviewers
- Credit / Risk Teams
- Underwriters
- Lending Approvers
- Documentation Teams
- Disbursement Teams

Potential training/readiness areas include:

- New workflow
- Application processing
- Exception handling
- Business-rule outcomes
- Approval-condition tracking
- Reporting
- AI-assisted review
- Human-review responsibilities
- Fallback procedures

> **Real-Project Note:** Training ownership varies by organization. The BA may provide process knowledge and support training-content preparation, while formal training may be owned by Change Management, Operations, Product or Learning teams.

---

# 14. AI Governance Impact

AI introduces additional considerations beyond traditional workflow automation.

The proposed AI capability follows these principles:

1. AI provides decision support only.
2. AI does not independently approve loans.
3. AI does not independently decline loans.
4. AI does not override deterministic business-rule outcomes.
5. Authorized humans retain final lending-decision authority.
6. AI output must be reviewable.
7. Relevant observations should be supported by available information.
8. Uncertainty should result in appropriate human review.
9. AI activity should be traceable where required.
10. AI failure must not prevent authorized human processing.
11. Human reviewers must be able to accept, reject, correct or disregard AI observations.
12. Approved/controlled knowledge sources should be used for rule or policy retrieval where applicable.

Detailed AI requirements and controls are addressed through the project's AI-related business, functional and system requirements.

---

# 15. Change Risk Summary

| Risk | Potential Impact | Initial Mitigation |
|---|---|---|
| Incorrect business-rule configuration | Incorrect eligibility or workflow outcome | Rule review, controlled changes and testing |
| Integration failure | Processing delays | Error handling, retry/fallback and operational procedures |
| Poor data quality | Incorrect validation or reporting | Data-quality rules, validation and reconciliation |
| Incorrect workflow progression | Processing inconsistency | Workflow requirements, business rules and testing |
| Unresolved approval conditions | Incorrect readiness for downstream processing | Blocking-condition controls |
| User-adoption issues | Operational inefficiency | Training, communication and process guidance |
| Incorrect AI output | Reviewer confusion or inappropriate reliance | Human review, evidence, uncertainty handling and AI controls |
| Requirement changes | Scope, schedule and testing impact | Impact analysis, prioritization and traceability |

These risks can later be incorporated into the project **RAID Log / Risk Register** where appropriate.

---

# 16. Requirements Impact

The Impact Analysis identifies the need for requirements across several areas.

## Business Requirements

Define the business outcomes and capabilities required.

## Functional Requirements

Define expected solution behavior.

## System Requirements

Define applicable system, technical and non-functional expectations.

## Business Rules

Define conditions governing validation, eligibility, routing, exceptions and processing.

## Data Requirements

Define required data, definitions, validation, mappings and quality expectations.

## Integration Requirements

Define required system-to-system interactions and business behavior.

## Reporting Requirements

Define KPIs, calculations, dimensions and dashboard expectations.

## AI Requirements

Define AI-assisted behavior, limitations, human review, fallback and governance.

The detailed requirements are maintained in the project's requirements artifacts and delivery backlog.

---

# 17. Traceability

The initial analysis establishes:

```text
Pain Point → Gap → Impact
```

For example:

```text
PP-01 → GAP-001 → IMP-001
```

The project has subsequently extended this relationship into detailed requirements.

Example:

```text
PP-01
  ↓
GAP-001
  ↓
IMP-001
  ↓
BR-001
  ↓
FR-001–FR-006
  ↓
Relevant System Requirements
  ↓
Relevant Business Rules
  ↓
User Story / Acceptance Criteria
  ↓
Test / UAT
  ↓
Business Outcome / KPI
```

Traceability is many-to-many. A single gap may result in multiple requirements, and a single requirement may address more than one business problem.

Detailed traceability will be maintained through the appropriate project traceability mechanism.

---

# 18. Requirement Change Impact Analysis

Impact Analysis is also used during delivery when an existing requirement changes.

For example, assume a stakeholder requests:

> "Allow an application with an unresolved approval condition to proceed to disbursement."

The BA should not simply update the user story.

The BA should analyze potential impact on:

- Business rules
- Approval-condition requirements
- Disbursement-readiness requirements
- Workflow behavior
- User permissions
- Data
- API behavior
- Existing test scenarios
- UAT scenarios
- Reporting
- Controls
- Documentation
- Delivery estimate

The BA then facilitates review with the appropriate business and control stakeholders before the change is accepted.

This is one of the practical uses of Impact Analysis during an active project.

---

# 19. BA Activities Demonstrated

This Impact Analysis demonstrates practical BA activities including:

- Reviewing proposed process changes
- Identifying impacted stakeholders
- Assessing process impact
- Assessing data impact
- Identifying integration impact
- Identifying reporting impact
- Identifying operational impact
- Identifying control impact
- Identifying testing implications
- Supporting prioritization
- Supporting requirement-change analysis
- Identifying downstream dependencies
- Supporting traceability

The BA facilitates the analysis and coordinates with SMEs rather than independently determining every technical, operational or compliance impact.

---

# 20. Outcome

The Impact Analysis confirms that the proposed loan-origination transformation affects more than application functionality.

The changes influence:

- Business processes
- Stakeholder responsibilities
- Data
- Workflow
- Integrations
- Reporting
- Testing
- Operations
- Controls
- Training/readiness
- AI governance

The analysis provides context for the detailed requirements already established and will continue to support requirement-change assessment during delivery.

> **Portfolio Representation:** This GitHub file represents impact-analysis work that, in an enterprise project, may be maintained within Confluence, Excel, a Change Request, a BRD, a requirements repository or a delivery-management tool.

---

## Disclaimer

This Impact Analysis represents a simulated loan origination transformation created for educational and professional portfolio purposes.

It does not represent the internal processes, technology architecture, lending rules, regulatory interpretation or policies of any specific financial institution.
