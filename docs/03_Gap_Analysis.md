# Gap Analysis

## Document Context

**Typical Real-Project Location:** Confluence / SharePoint / Excel Analysis Workbook / Business Requirements Repository  
**Typical Ownership:** Business Analyst, with input from Business SMEs, Product Owner and Technology stakeholders  
**Primary Users:** Business Analyst, Product Owner, Business SMEs, Project Manager, Solution / Technology Team and QA  
**Artifact Type:** Business analysis working artifact; may be incorporated into a BRD, business case or process-improvement analysis rather than maintained as a standalone document

**Purpose:** Compares the current AS-IS process with the desired TO-BE state, identifies what is missing or ineffective, and establishes the business and solution changes required to close those gaps.

> **Real-Project Note:** Gap Analysis is a common Business Analysis activity, but organizations do not always create a document specifically called "Gap Analysis." The analysis may appear within a BRD, process-improvement assessment, business case, workshop output, Excel workbook or Confluence page. In this portfolio, it is maintained separately to demonstrate the analysis and its traceability to requirements.

---

## 1. Purpose

This analysis identifies the gaps between the current **AS-IS Loan Origination Process** and the proposed **TO-BE Loan Origination Process**.

It translates the pain points identified during current-state analysis into defined gaps and required changes.

The analysis supports:

- Impact Analysis
- Business Requirements
- Functional Requirements
- System Requirements
- Business Rules
- Decision Logic
- Backlog refinement
- Data and integration analysis
- Testing and UAT
- Change-impact assessment
- Requirements traceability

The objective is not simply to identify what technology is missing, but to understand the differences across **process, people, technology, data, integration, controls and reporting**.

---

## 2. Analysis Approach

The following structure is used:

**AS-IS Condition → Pain Point → TO-BE Expectation → Identified Gap → Required Change → Expected Benefit**

Each gap has a unique identifier:

`GAP-001` through `GAP-012`

These identifiers are retained throughout the project to support traceability.

### Source of the Gaps

The gaps were derived from:

- AS-IS process analysis
- Identified operational pain points
- TO-BE process expectations
- Stakeholder needs
- Process-control requirements
- Data and reporting needs
- Integration requirements
- Underwriting and operational review needs

> **BA Principle:** A gap should be supported by an observed or agreed current-state problem and a desired future-state outcome. The BA should not create solution features without understanding the underlying business need.

---

## 3. Gap Analysis Summary

| Gap ID | Related Pain Point | Gap Area | Priority |
|---|---|---|---|
| GAP-001 | PP-01 | Application Completeness | High |
| GAP-002 | PP-02 | Document Management | High |
| GAP-003 | PP-03 | Data Validation | High |
| GAP-004 | PP-04 | Business Rules | High |
| GAP-005 | PP-05 | Exception Management | High |
| GAP-006 | PP-06 | Workflow & Handoffs | Medium |
| GAP-007 | PP-07 | Status Visibility | High |
| GAP-008 | PP-08 | Underwriting Review | High |
| GAP-009 | PP-09 | Rework Management | Medium |
| GAP-010 | PP-10 | KPI & Reporting | Medium |
| GAP-011 | PP-11 | Approval Conditions | High |
| GAP-012 | PP-12 | End-to-End Traceability | High |

Priority represents the current simulated project assessment and may change following stakeholder review, dependency analysis and delivery planning.

---

# 4. Detailed Gap Analysis

## GAP-001 — Application Completeness

### Related Pain Point

**PP-01 — Incomplete Applications**

### AS-IS Condition

Applications may be submitted with missing or incomplete information.

Operations or Loan Officers may identify missing information only after the application has entered downstream processing.

This results in additional customer follow-up, processing delays and rework.

### TO-BE Expectation

The application process should support:

- Mandatory-field validation
- Guided application capture
- Application completeness checks
- Clear missing-information indicators
- Validation before submission
- Draft functionality for incomplete applications

### Identified Gap

The current process lacks standardized controls to prevent or reduce incomplete application submissions.

### Required Change

Introduce application-level validation and completeness controls before submission while allowing incomplete applications to remain in draft where appropriate.

### Expected Benefit

- Reduced incomplete submissions
- Reduced applicant follow-up
- Reduced downstream rework
- Improved application completion rate
- Improved processing efficiency

### Priority

**High**

### Requirement Traceability

Primary downstream business requirement:

**BR-001 — Application Capture and Completeness**

---

## GAP-002 — Document Management

### Related Pain Point

**PP-02 — Missing Documents**

### AS-IS Condition

Document requirements may be identified or tracked manually.

Missing, outdated, rejected or replacement documents can require repeated follow-up.

Operations may not always have a consolidated view of document completeness.

### TO-BE Expectation

The solution should support:

- Product-based document requirements
- Required-document identification
- Document status tracking
- Missing-document detection
- Replacement-document tracking
- Document verification status
- Outstanding-document visibility

### Identified Gap

There is no centralized and standardized mechanism for managing document completeness throughout the application lifecycle.

### Required Change

Introduce structured document requirements, statuses, validation and tracking.

### Expected Benefit

- Earlier missing-document identification
- Reduced manual follow-up
- Improved document completeness
- Improved operational visibility
- Reduced downstream delays

### Priority

**High**

### Requirement Traceability

Primary downstream business requirement:

**BR-003 — Document Requirement and Tracking**

---

## GAP-003 — Application Data Validation

### Related Pain Point

**PP-03 — Manual Data Validation**

### AS-IS Condition

Business and operations users perform repetitive manual checks to identify missing, invalid or inconsistent application information.

### TO-BE Expectation

The solution should support:

- Mandatory-field validation
- Data-type validation
- Cross-field validation
- Range validation
- Application/document consistency checks
- Standard validation reason codes
- Validation-result storage

### Identified Gap

The current process lacks standardized automated validation for repeatable data-quality checks.

### Required Change

Introduce structured application-data validation rules and consistent validation outcomes.

### Expected Benefit

- Reduced repetitive manual validation
- Earlier error detection
- Improved data quality
- Reduced processing time
- Reduced rework

### Priority

**High**

### Requirement Traceability

Primary downstream business requirement:

**BR-004 — Application Data Quality and Validation**

---

## GAP-004 — Business Rule Management

### Related Pain Point

**PP-04 — Fragmented Business Rules**

### AS-IS Condition

Eligibility and processing rules may be distributed across procedures, documents, systems and operational knowledge.

This can result in inconsistent interpretation and make change-impact analysis difficult.

### TO-BE Expectation

The future process should support:

- Defined business rules
- Unique rule identifiers
- Rule descriptions
- Input conditions
- Expected outcomes
- Reason codes
- Rule ownership
- Effective/version information where applicable
- Exception handling
- Traceability to requirements and testing

### Identified Gap

Business rules are not represented through a consistent and traceable structure.

### Required Change

Establish a structured Business Rules Catalogue and defined rule outcomes.

### Expected Benefit

- More consistent rule interpretation
- Improved requirements clarity
- Easier development clarification
- Improved testing
- Improved auditability
- Better change-impact assessment

### Priority

**High**

### Requirement Traceability

Primary downstream business requirement:

**BR-005 — Eligibility and Business Rule Management**

---

## GAP-005 — Exception Management

### Related Pain Point

**PP-05 — Late Exception Identification**

### AS-IS Condition

Exceptions may be identified at different stages and sometimes only during underwriting.

There may be limited standardization in how exceptions are categorized, assigned, resolved or tracked.

### TO-BE Expectation

The solution should support:

- Earlier exception detection
- Exception categories
- Exception reason codes
- Severity or priority where applicable
- Exception ownership
- Review queues
- Resolution status
- Resolution comments
- Exception history
- Human escalation

### Identified Gap

The current process lacks centralized and structured exception management.

### Required Change

Introduce an exception-management workflow covering identification, routing, review, resolution and audit history.

### Expected Benefit

- Earlier exception identification
- Reduced underwriting delays
- Clear ownership
- Improved auditability
- Reduced rework

### Priority

**High**

### Requirement Traceability

Primary downstream business requirement:

**BR-007 — Exception Management**

---

## GAP-006 — Workflow and Manual Handoffs

### Related Pain Point

**PP-06 — Multiple Manual Handoffs**

### AS-IS Condition

Applications move between applicants, Loan Officers, Operations, KYC, Credit/Risk, Underwriting, Documentation and Disbursement teams.

Manual coordination can cause delays, unclear ownership and inconsistent handoffs.

### TO-BE Expectation

The solution should support:

- Workflow-based routing
- Defined processing queues
- Stage ownership
- Consistent workflow updates
- API-based integration where appropriate
- Assignment history
- Queue visibility
- Exception routing

### Identified Gap

The current process depends heavily on manual coordination between lifecycle participants.

### Required Change

Introduce structured workflow routing, assignment and integration between relevant process stages.

### Expected Benefit

- Reduced manual coordination
- Clear ownership
- Improved turnaround time
- Improved operational visibility
- Better handoff consistency

### Priority

**Medium**

### Requirement Traceability

Primary downstream business requirement:

**BR-008 — Workflow and Work Queue Management**

---

## GAP-007 — Application Status Visibility

### Related Pain Point

**PP-07 — Limited Status Visibility**

### AS-IS Condition

Application progress may be tracked differently by different teams.

Users may not have a consistent view of the application's current lifecycle stage or previous processing history.

### TO-BE Expectation

The solution should maintain:

- Central application status
- Relevant sub-status where required
- Status history
- Status date/time
- Status reason where applicable
- Responsible team or queue
- Controlled workflow progression

### Identified Gap

The current process lacks standardized end-to-end application status management and consistent lifecycle visibility.

### Required Change

Define the required application statuses, workflow behavior and permitted progression as part of the functional requirements and business rules.

### Expected Benefit

- Improved application visibility
- Better customer communication
- Improved queue management
- Improved reporting
- Better audit history

### Priority

**High**

### Requirement Traceability

Primary downstream business requirement:

**BR-009 — Application Status Management**

Supporting business rules include:

- **RULE-026 — Permitted Status Transition**
- **RULE-027 — Status History**

> **Real-Project Note:** Status values and transition logic may be maintained within functional requirements, workflow specifications, business rules, state diagrams or backlog acceptance criteria. A standalone Status Transition Matrix is not required unless the project or organization finds one useful.

---

## GAP-008 — Underwriting Review Efficiency

### Related Pain Point

**PP-08 — Underwriting Review Effort**

### AS-IS Condition

Underwriters may need to gather and review information from multiple sources before completing their assessment.

Missing information, conflicting information or exceptions may be discovered late.

### TO-BE Expectation

Underwriters should receive a consolidated review view containing:

- Application information
- KYC status
- Document status
- Eligibility results
- Business-rule results
- Credit/risk information
- Exceptions
- Supporting evidence
- AI-assisted application summary and observations where applicable

### Identified Gap

The current process does not provide a consolidated and structured underwriting review experience.

### Required Change

Provide consolidated underwriting information and controlled AI-assisted review capabilities.

### Expected Benefit

- Reduced information-gathering effort
- Earlier exception visibility
- Improved reviewer efficiency
- More structured underwriting review

### Priority

**High**

### Requirement Traceability

Primary downstream requirements include:

- **BR-010 — Underwriting Review**
- **BR-020 — AI-Assisted Application Review**
- **BR-021 — AI Human Review and Override**
- **BR-022 — AI Transparency and Traceability**

### AI Control

AI may assist with:

- Application summarization
- Missing-information observations
- Existing risk/exception summarization
- Retrieval of approved rules or knowledge
- Structured reviewer observations

AI must **not autonomously approve or decline a loan**.

Final lending decisions remain with authorized human lending personnel.

---

## GAP-009 — Rework Management

### Related Pain Point

**PP-09 — Rework**

### AS-IS Condition

Applications may require backward movement or repeated processing because missing information, validation failures, document issues or exceptions are identified late.

### TO-BE Expectation

The process should identify issues earlier through:

- Application completeness validation
- Document completeness checks
- Data validation
- Business-rule validation
- Exception detection
- Structured reason codes
- Clear rework ownership

### Identified Gap

Current controls do not consistently prevent avoidable downstream rework.

### Required Change

Move repeatable validations and completeness checks earlier in the lifecycle and provide structured handling when rework is required.

### Expected Benefit

- Reduced unnecessary backward process movement
- Reduced processing delays
- Reduced operational effort
- Improved first-time-right processing

### Priority

**Medium**

### Requirement Traceability

This gap is cross-functional and is primarily addressed through:

- **BR-001 — Application Capture and Completeness**
- **BR-003 — Document Requirement and Tracking**
- **BR-004 — Application Data Quality and Validation**
- **BR-005 — Eligibility and Business Rule Management**
- **BR-007 — Exception Management**

---

## GAP-010 — KPI and Operational Reporting

### Related Pain Point

**PP-10 — Limited KPI Visibility**

### AS-IS Condition

Operational reporting may require manual consolidation and may not provide sufficient visibility into lifecycle volumes, delays or bottlenecks.

### TO-BE Expectation

The solution should support reporting for measures such as:

- Application volumes
- Application completion rate
- KYC completion
- Missing-document rate
- Stage turnaround time
- Total processing time
- Eligibility failures
- Exception rates
- Rework
- Underwriting queue volume
- Approval rate
- Decline rate
- Approval-to-disbursement time
- AI-assisted review volume
- Human escalation rate

### Identified Gap

The current process lacks structured lifecycle data suitable for consistent operational KPI reporting.

### Required Change

Define KPI requirements, required data elements and calculation logic.

Use:

- **MySQL** for structured project data and KPI queries
- **Microsoft Excel** for validation and reconciliation where appropriate
- **Microsoft Power BI** for operational visualization and analysis

### Expected Benefit

- Better management visibility
- Easier bottleneck identification
- Data-driven process improvement
- Improved operational monitoring

### Priority

**Medium**

### Requirement Traceability

Primary downstream business requirement:

**BR-017 — Operational KPI Reporting**

---

## GAP-011 — Approval Condition Management

### Related Pain Point

**PP-11 — Manual Condition Tracking**

### AS-IS Condition

Conditions associated with approved applications may require manual tracking and repeated follow-up.

Incomplete or unresolved conditions may delay documentation or disbursement.

### TO-BE Expectation

The solution should maintain:

- Condition ID
- Condition description
- Condition owner
- Condition status
- Required-by date where applicable
- Supporting information
- Resolution details
- Waiver information where appropriately authorized
- Condition history

### Identified Gap

Approval conditions are not managed through a standardized and traceable lifecycle.

### Required Change

Introduce centralized approval-condition tracking and readiness controls.

### Expected Benefit

- Improved condition visibility
- Reduced manual follow-up
- Improved disbursement readiness
- Better auditability

### Priority

**High**

### Requirement Traceability

Primary downstream business requirement:

**BR-013 — Approval Condition Management**

Related downstream requirements include documentation and disbursement readiness.

---

## GAP-012 — End-to-End Traceability

### Related Pain Point

**PP-12 — Limited End-to-End Traceability**

### AS-IS Condition

Business needs, requirements, rules, development items and testing evidence may not always be consistently linked.

This makes it more difficult to determine:

- Whether every requirement has been addressed
- Whether every requirement has been tested
- What is affected by a requirement change
- Why a specific system behavior exists

### TO-BE Expectation

The project should support traceability between relevant items such as:

- Pain points
- Gaps
- Impacts
- Business requirements
- Functional requirements
- System requirements where applicable
- Business rules
- Decision logic
- User stories
- Acceptance criteria
- Data requirements
- API requirements
- Test scenarios
- UAT test cases
- Defects
- Business outcomes / KPIs

### Identified Gap

There is no standardized end-to-end requirements traceability approach.

### Required Change

Use consistent requirement identifiers and maintain traceability through an RTM or an appropriate requirements/delivery-management tool.

### Expected Benefit

- Improved requirement coverage
- Easier impact analysis
- Improved testing coverage
- Reduced missed requirements
- Improved auditability

### Priority

**High**

### Requirement Traceability

Primary downstream business requirement:

**BR-023 — Requirements Traceability**

> **Real-Project Note:** A standalone RTM is common in projects requiring formal traceability, but it is not mandatory in every Agile organization. Traceability may instead be maintained through Jira, Azure DevOps, a requirements-management platform or test-management tooling.

---

# 5. Gap-to-Requirement Summary

| Gap ID | Pain Point | Primary Business Requirement / Solution Direction |
|---|---|---|
| GAP-001 | PP-01 | BR-001 — Application Capture and Completeness |
| GAP-002 | PP-02 | BR-003 — Document Requirement and Tracking |
| GAP-003 | PP-03 | BR-004 — Application Data Quality and Validation |
| GAP-004 | PP-04 | BR-005 — Eligibility and Business Rule Management |
| GAP-005 | PP-05 | BR-007 — Exception Management |
| GAP-006 | PP-06 | BR-008 — Workflow and Work Queue Management |
| GAP-007 | PP-07 | BR-009 — Application Status Management |
| GAP-008 | PP-08 | BR-010 / BR-020–BR-022 — Underwriting & AI-Assisted Review |
| GAP-009 | PP-09 | Cross-functional — BR-001 / BR-003–BR-005 / BR-007 |
| GAP-010 | PP-10 | BR-017 — Operational KPI Reporting |
| GAP-011 | PP-11 | BR-013 — Approval Condition Management |
| GAP-012 | PP-12 | BR-023 — Requirements Traceability |

This table provides high-level traceability. Detailed mappings to Functional Requirements, System Requirements, Business Rules, stories and testing will be maintained through project traceability mechanisms.

---

# 6. Gap Prioritization

## High Priority

- GAP-001 — Application Completeness
- GAP-002 — Document Management
- GAP-003 — Data Validation
- GAP-004 — Business Rule Management
- GAP-005 — Exception Management
- GAP-007 — Application Status Visibility
- GAP-008 — Underwriting Review Efficiency
- GAP-011 — Approval Condition Management
- GAP-012 — End-to-End Traceability

These gaps have significant impact on application quality, processing controls, underwriting, decision support or traceability.

## Medium Priority

- GAP-006 — Workflow and Manual Handoffs
- GAP-009 — Rework Management
- GAP-010 — KPI and Operational Reporting

These gaps primarily improve operational efficiency, workflow management and management visibility.

> **BA Note:** Priority is not determined by the BA alone. Final prioritization should be agreed with appropriate stakeholders such as the Product Owner, business owners and delivery team while considering business value, risk, dependencies, effort and delivery constraints.

---

# 7. Preliminary Change Areas

The identified gaps indicate changes across several areas.

## Process

- Earlier validation
- Improved application completeness
- Standardized lifecycle processing
- Structured exception handling
- Controlled underwriting and lending-decision process
- Defined approval-condition handling
- Defined disbursement-readiness checks

## People / Roles

- Clearer process ownership
- Defined review responsibilities
- Improved handoff responsibilities
- Human oversight of AI-generated observations
- Reduced repetitive manual review

## Technology

- Workflow support
- Centralized application visibility
- Business-rule processing
- API integrations
- Exception-management capability
- AI-assisted review

## Data

- Standardized application data
- Validation results
- Rule outcomes
- Exception data
- Status history
- Approval-condition information
- KPI data

## Integration

- KYC / identity verification integration
- Document-related integration
- Credit / risk integration
- Business-rule services
- Notification services
- Downstream loan/disbursement integration
- Reporting data flow

## Reporting

- Operational KPI tracking
- Lifecycle bottleneck analysis
- Queue analysis
- Power BI dashboards
- Excel-based validation/reconciliation where appropriate

## Controls

- Audit history
- Human decision ownership
- Lending authority controls
- Traceable exceptions
- Disbursement-readiness controls
- AI governance
- Human/manual fallback

These change areas are analyzed further in the **Impact Analysis**.

---

# 8. Traceability Approach

Traceability is progressively established using the following relationship:

```text
Pain Point
    ↓
Gap
    ↓
Impact
    ↓
Business Requirement
    ↓
Functional Requirement
    ↓
System Requirement (where applicable)
    ↓
Business Rule / Decision Logic
    ↓
User Story & Acceptance Criteria
    ↓
Data / API Requirement (where applicable)
    ↓
Test Scenario / UAT
    ↓
Business Outcome / KPI
```

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
Application Completion KPI
```

Detailed many-to-many traceability will be maintained later through the project's traceability mechanism rather than forcing every relationship into this Gap Analysis.

---

# 9. BA Observations

The Gap Analysis shows that the primary business problem is **not simply the absence of AI**.

The major improvements require foundational capabilities such as:

- Better application capture
- Standardized validation
- Structured business rules
- Document tracking
- Exception management
- Workflow routing
- Application visibility
- Data quality
- Integration
- Reporting
- Traceability

AI should therefore be introduced as an **assistive capability within a controlled loan-origination process**.

It should not replace:

- Deterministic business rules
- Required validation
- KYC controls
- Underwriting judgment
- Lending authority
- Disbursement controls

The AI component is primarily intended to support human review through summarization, information retrieval, exception/risk observations and structured review assistance.

---

# 10. BA Activities Demonstrated

This Gap Analysis demonstrates practical BA activities including:

- Reviewing the AS-IS process
- Identifying operational pain points
- Comparing AS-IS and TO-BE states
- Identifying process and system gaps
- Distinguishing business problems from proposed solutions
- Assessing expected business benefits
- Supporting prioritization
- Identifying impacted change areas
- Establishing requirement traceability
- Preparing input for impact analysis and detailed requirements

In a real project, these activities would normally involve workshops, SME discussions, process walkthroughs, data review and stakeholder validation rather than being completed by the BA in isolation.

---

# 11. Outcome

The Gap Analysis identified twelve major gaps:

- GAP-001 — Application Completeness
- GAP-002 — Document Management
- GAP-003 — Application Data Validation
- GAP-004 — Business Rule Management
- GAP-005 — Exception Management
- GAP-006 — Workflow and Manual Handoffs
- GAP-007 — Application Status Visibility
- GAP-008 — Underwriting Review Efficiency
- GAP-009 — Rework Management
- GAP-010 — KPI and Operational Reporting
- GAP-011 — Approval Condition Management
- GAP-012 — End-to-End Traceability

These gaps establish the rationale for the business, functional, system, data, integration, reporting and AI requirements defined elsewhere in the project.

> **Portfolio Representation:** This GitHub file represents analysis that, in a real enterprise project, could be maintained as a standalone Gap Analysis, an Excel analysis workbook, a Confluence page, or as part of broader business/process requirements documentation.

---

## Disclaimer

This Gap Analysis is based on a simulated loan origination environment created for educational and professional portfolio purposes.

It does not represent the processes, policies, eligibility rules, risk rules or lending practices of any specific financial institution.
