# Gap Analysis

## 1. Purpose

This document identifies the gaps between the current **AS-IS Loan Origination Process** and the proposed **TO-BE Loan Origination Process**.

The analysis translates the pain points identified in the current-state process into clearly defined gaps and required business or system changes.

The Gap Analysis will provide input to subsequent deliverables including:

- Impact Analysis
- Business Requirements Specification (BRS / BRD)
- Functional Requirements Specification (FRS / FRD)
- System Requirements Specification (SRS)
- Business Rules
- Decision Tables
- User Stories
- Acceptance Criteria
- Requirements Traceability Matrix (RTM)
- UAT Test Cases

---

# 2. Analysis Approach

The following structure is used for each identified gap:

**AS-IS Condition → Pain Point → TO-BE Expectation → Gap → Required Change**

Each gap is assigned a unique identifier:

`GAP-001` through `GAP-012`

These identifiers will be reused in subsequent requirements and traceability artifacts.

---

# 3. Gap Analysis Summary

| Gap ID | Pain Point | Gap Area | Priority |
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

---

# 4. Detailed Gap Analysis

## GAP-001 — Application Completeness

### Related Pain Point

**PP-01 — Incomplete Applications**

### AS-IS

Applications may be submitted with missing or incomplete information.

Operations or loan officers may identify missing information only after the application has entered downstream processing.

This results in follow-up communication and processing delays.

### TO-BE

The application process should provide:

- Mandatory-field validation
- Guided application capture
- Application completeness checks
- Clear missing-information indicators
- Validation before submission
- Draft functionality for incomplete applications

### Identified Gap

The current process lacks standardized controls to prevent or reduce incomplete application submissions.

### Required Change

Introduce application-level validation and completeness controls before submission.

### Expected Benefit

- Reduced incomplete applications
- Reduced applicant follow-up
- Reduced downstream rework
- Improved application completion rate

### Priority

**High**

---

## GAP-002 — Document Management

### Related Pain Point

**PP-02 — Missing Documents**

### AS-IS

Document requirements may be identified or tracked manually.

Missing, outdated, rejected, or replacement documents can require repeated follow-up.

### TO-BE

The solution should provide:

- Product-based document checklist
- Required-document identification
- Document status tracking
- Missing-document detection
- Replacement-document tracking
- Document verification status
- Outstanding-document visibility

### Identified Gap

There is no centralized and standardized mechanism for managing document completeness throughout the application lifecycle.

### Required Change

Introduce structured document requirements, statuses, validation, and tracking.

### Expected Benefit

- Earlier missing-document identification
- Reduced manual follow-up
- Improved document completeness
- Improved status visibility

### Priority

**High**

---

## GAP-003 — Application Data Validation

### Related Pain Point

**PP-03 — Manual Data Validation**

### AS-IS

Business and operations users perform repetitive manual checks to identify missing, invalid, or inconsistent application information.

### TO-BE

The solution should support:

- Mandatory-field validation
- Data-type validation
- Cross-field validation
- Range validation
- Application/document consistency checks
- Standard validation reason codes
- Validation result storage

### Identified Gap

The current process lacks standardized automated validation for repeatable data-quality checks.

### Required Change

Introduce configurable application-data validation rules and structured validation outcomes.

### Expected Benefit

- Reduced manual validation
- Earlier error detection
- Improved data quality
- Reduced processing time
- Reduced rework

### Priority

**High**

---

## GAP-004 — Business Rule Management

### Related Pain Point

**PP-04 — Fragmented Business Rules**

### AS-IS

Eligibility and processing rules may be distributed across procedures, documents, systems, and operational knowledge.

This can lead to inconsistent interpretation.

### TO-BE

The future process should provide:

- Centralized business-rule catalogue
- Unique rule identifiers
- Rule descriptions
- Input conditions
- Rule outcomes
- Reason codes
- Effective dates
- Rule ownership
- Version tracking
- Exception handling

### Identified Gap

Business rules are not managed through a centralized, traceable structure.

### Required Change

Establish a formal Business Rules Catalogue and structured rule-execution approach.

### Expected Benefit

- Consistent rule interpretation
- Improved requirements clarity
- Easier testing
- Improved auditability
- Better change-impact assessment

### Priority

**High**

---

## GAP-005 — Exception Management

### Related Pain Point

**PP-05 — Late Exception Identification**

### AS-IS

Exceptions may be identified at different stages and sometimes only during underwriting.

There may be limited standardization in how exceptions are categorized, assigned, resolved, or tracked.

### TO-BE

The solution should support:

- Early exception detection
- Exception categories
- Exception reason codes
- Severity or priority
- Exception ownership
- Review queues
- Resolution status
- Resolution comments
- Exception history
- Human escalation

### Identified Gap

The current process lacks centralized and structured exception management.

### Required Change

Introduce an exception-management workflow covering identification, routing, review, resolution, and audit history.

### Expected Benefit

- Earlier exception identification
- Reduced underwriting delays
- Clear ownership
- Improved auditability
- Reduced rework

### Priority

**High**

---

## GAP-006 — Workflow and Manual Handoffs

### Related Pain Point

**PP-06 — Multiple Manual Handoffs**

### AS-IS

Applications move between applicants, loan officers, operations, KYC, credit/risk, underwriting, documentation, and disbursement teams.

Manual handoffs can cause delays and unclear ownership.

### TO-BE

The solution should provide:

- Workflow-based routing
- Defined processing queues
- Stage ownership
- Automated status updates
- API-based integration where appropriate
- Assignment history
- Queue visibility

### Identified Gap

The current process depends heavily on manual coordination between lifecycle participants.

### Required Change

Introduce structured workflow routing and integration between process stages.

### Expected Benefit

- Reduced manual coordination
- Clear ownership
- Improved turnaround time
- Improved operational visibility

### Priority

**Medium**

---

## GAP-007 — Application Status Visibility

### Related Pain Point

**PP-07 — Limited Status Visibility**

### AS-IS

Application progress may be tracked differently by different teams.

Users may not have a consistent view of the current lifecycle stage.

### TO-BE

The solution should maintain:

- Central application status
- Sub-status where required
- Status history
- Status date/time
- Status reason
- Responsible team
- Allowed status transitions

### Identified Gap

The current process lacks standardized end-to-end application status management.

### Required Change

Define and implement a formal application status model and Status Transition Matrix.

### Expected Benefit

- Improved application visibility
- Better customer communication
- Improved queue management
- Improved reporting
- Better audit history

### Priority

**High**

---

## GAP-008 — Underwriting Review Efficiency

### Related Pain Point

**PP-08 — Underwriting Review Effort**

### AS-IS

Underwriters may need to gather and review information from multiple sources before reaching an assessment.

Missing information or exceptions may be discovered late.

### TO-BE

Underwriters should receive a consolidated review view containing:

- Application information
- KYC status
- Document status
- Eligibility results
- Business-rule results
- Risk information
- Exceptions
- Supporting evidence
- AI-assisted application summary

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

### Control Requirement

AI may assist the underwriter but must not autonomously approve or decline a loan.

Final lending decisions remain with authorized human personnel.

---

## GAP-009 — Rework Management

### Related Pain Point

**PP-09 — Rework**

### AS-IS

Applications may move backward because missing information, validation failures, document issues, or exceptions are identified late.

### TO-BE

The process should identify issues earlier through:

- Application completeness validation
- Document completeness checks
- Data validation
- Business-rule validation
- Exception detection
- Structured reason codes

### Identified Gap

Current controls do not consistently prevent avoidable downstream rework.

### Required Change

Move repeatable validations and completeness checks earlier in the lifecycle.

### Expected Benefit

- Reduced backward process movement
- Reduced processing delays
- Reduced operational effort
- Improved first-time-right processing

### Priority

**Medium**

---

## GAP-010 — KPI and Operational Reporting

### Related Pain Point

**PP-10 — Limited KPI Visibility**

### AS-IS

Operational reporting may require manual consolidation and may not provide sufficient visibility into lifecycle bottlenecks.

### TO-BE

The solution should support reporting for:

- Application volumes
- Application completion rate
- KYC completion
- Missing-document rate
- Stage turnaround time
- Total processing time
- Eligibility failures
- Exception rates
- Rework
- Underwriting queue
- Approval rate
- Decline rate
- Approval-to-disbursement time
- AI-assisted review volume
- Human escalation rate

### Identified Gap

The current process lacks structured lifecycle data suitable for consistent operational KPI reporting.

### Required Change

Define KPI requirements, capture required data, develop SQL-based metrics, and visualize results using Microsoft Power BI.

Microsoft Excel will be used where appropriate for validation and reconciliation.

### Expected Benefit

- Better management visibility
- Easier bottleneck identification
- Data-driven process improvement
- Improved operational monitoring

### Priority

**Medium**

---

## GAP-011 — Approval Condition Management

### Related Pain Point

**PP-11 — Manual Condition Tracking**

### AS-IS

Conditions associated with approved applications may require manual tracking and repeated follow-up.

### TO-BE

The solution should maintain:

- Condition ID
- Condition description
- Condition owner
- Condition status
- Required-by date where applicable
- Supporting information
- Resolution
- Waiver information where authorized
- Condition history

### Identified Gap

Approval conditions are not managed through a standardized lifecycle.

### Required Change

Introduce centralized approval-condition tracking.

### Expected Benefit

- Improved condition visibility
- Reduced manual follow-up
- Improved disbursement readiness
- Better auditability

### Priority

**High**

---

## GAP-012 — End-to-End Traceability

### Related Pain Point

**PP-12 — Limited End-to-End Traceability**

### AS-IS

Requirements, business rules, process steps, system behavior, data, testing, and operational outcomes may not be consistently linked.

### TO-BE

The project should maintain traceability between:

- Business problems
- Pain points
- Gaps
- Business requirements
- Functional requirements
- Business rules
- User stories
- Acceptance criteria
- Data requirements
- API requirements
- Test scenarios
- UAT test cases
- Defects
- Implementation outcomes

### Identified Gap

There is no standardized end-to-end traceability framework.

### Required Change

Implement a Requirements Traceability Matrix and consistent requirement identifiers across project artifacts.

### Expected Benefit

- Improved requirement coverage
- Easier impact analysis
- Improved testing coverage
- Reduced missed requirements
- Improved auditability

### Priority

**High**

---

# 5. Gap-to-Solution Summary

| Gap ID | Required Solution Capability |
|---|---|
| GAP-001 | Application completeness validation |
| GAP-002 | Document checklist and tracking |
| GAP-003 | Automated data-validation framework |
| GAP-004 | Centralized Business Rules Catalogue |
| GAP-005 | Exception-management workflow |
| GAP-006 | Workflow routing and integration |
| GAP-007 | Application status-management framework |
| GAP-008 | Consolidated underwriting and AI-assisted review |
| GAP-009 | Earlier validation and rework prevention |
| GAP-010 | KPI data model and Power BI reporting |
| GAP-011 | Approval-condition management |
| GAP-012 | Requirements and testing traceability |

---

# 6. Gap Prioritization

## High Priority

The following gaps have a direct impact on application quality, processing control, underwriting, decision support, or traceability:

- GAP-001 — Application Completeness
- GAP-002 — Document Management
- GAP-003 — Data Validation
- GAP-004 — Business Rule Management
- GAP-005 — Exception Management
- GAP-007 — Application Status Visibility
- GAP-008 — Underwriting Review Efficiency
- GAP-011 — Approval Condition Management
- GAP-012 — End-to-End Traceability

## Medium Priority

The following gaps primarily improve operational efficiency, reporting, and workflow optimization:

- GAP-006 — Workflow and Manual Handoffs
- GAP-009 — Rework Management
- GAP-010 — KPI and Operational Reporting

Priorities may be revised following stakeholder review and detailed impact analysis.

---

# 7. Preliminary Change Areas

Based on the Gap Analysis, the proposed solution will introduce changes across the following areas:

### Process

- Earlier validation
- Standardized lifecycle stages
- Structured exception handling
- Controlled underwriting and decision process
- Defined disbursement-readiness checks

### People

- Clearer process ownership
- Defined review responsibilities
- Human oversight of AI-generated observations
- Reduced repetitive manual review

### Technology

- Workflow automation
- Centralized status tracking
- Business-rule processing
- API integrations
- AI-assisted review

### Data

- Standardized application data
- Validation results
- Rule outcomes
- Exception data
- Status history
- KPI data

### Reporting

- Operational KPI tracking
- Lifecycle bottleneck analysis
- Power BI dashboards

### Controls

- Audit history
- Decision ownership
- Human lending authority
- Traceable exceptions
- AI governance

These change areas will be assessed in greater detail during **Impact Analysis**.

---

# 8. Traceability Approach

The project will progressively establish traceability using the following structure:

Pain Point  
↓  
Gap  
↓  
Business Requirement  
↓  
Functional Requirement  
↓  
Business Rule / Decision Logic  
↓  
User Story  
↓  
Acceptance Criteria  
↓  
Data / API Requirement  
↓  
Test Scenario  
↓  
UAT Test Case  
↓  
Business Outcome / KPI

Example:

`PP-01 → GAP-001 → BR-001 → FR-xxx → US-xxx → AC-xxx → UAT-xxx`

Requirement identifiers will be assigned during the requirements-analysis phase.

---

# 9. BA Observations

The Gap Analysis indicates that the primary issue is not simply the absence of AI.

Several improvements require foundational process and system capabilities such as:

- Better application capture
- Standardized validation
- Centralized business rules
- Document tracking
- Exception management
- Workflow routing
- Status management
- Data quality
- Reporting
- Traceability

AI should therefore be introduced as an **assistive capability within a well-defined loan origination process**, rather than being treated as a replacement for core business controls.

---

# 10. Conclusion

The Gap Analysis identifies twelve major gaps between the AS-IS and TO-BE loan origination processes.

These gaps establish the business justification for the solution capabilities that will be defined through detailed requirements.

The next analysis activity will assess the impact of the proposed changes across:

- Business Process
- Stakeholders and Roles
- Technology
- Data
- Integration
- Reporting
- Testing
- Operations
- Controls
- AI Governance

---

## Disclaimer

This Gap Analysis is based on a simulated loan origination environment created for educational and professional portfolio purposes.

It does not represent the processes, policies, eligibility rules, or lending practices of any specific financial institution.
