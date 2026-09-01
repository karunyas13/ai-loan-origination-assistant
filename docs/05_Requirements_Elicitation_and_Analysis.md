# Requirements Elicitation and Analysis

## 1. Purpose

This document defines the requirements elicitation and analysis approach for the **AI-Powered Loan Origination Requirements & Risk Assistant** project.

The purpose of this activity is to identify, clarify, analyze, prioritize, validate, and organize stakeholder needs before converting them into formal business, functional, system, data, integration, reporting, and AI requirements.

The elicitation process covers the complete loan origination lifecycle:

1. Application Initiation
2. Application Submission
3. KYC / Identity Verification
4. Document Collection & Verification
5. Application Data Validation
6. Eligibility & Business Rule Validation
7. Credit / Risk Assessment
8. AI-Assisted Review
9. Exception Management
10. Underwriting
11. Lending Decision
12. Approval Conditions
13. Loan Documentation
14. Disbursement
15. Application Closure / Downstream Handoff
16. Operational Reporting

---

# 2. Elicitation Objectives

The Business Analyst will use requirements elicitation to:

- Understand stakeholder business needs
- Validate problems identified during AS-IS analysis
- Understand desired TO-BE capabilities
- Identify business requirements
- Identify functional requirements
- Identify business rules
- Identify data requirements
- Identify integration requirements
- Identify reporting requirements
- Identify security and audit requirements
- Identify operational requirements
- Identify AI-assisted use cases and controls
- Identify assumptions, constraints and dependencies
- Identify exceptions and alternative flows
- Resolve requirement ambiguity
- Identify conflicting stakeholder expectations
- Prioritize requirements
- Establish requirements traceability

---

# 3. Inputs to Requirements Elicitation

The following completed project artifacts serve as inputs:

- Project Charter and Business Problem
- Stakeholder Analysis
- AS-IS Loan Origination Process
- TO-BE Loan Origination Process
- Gap Analysis
- Impact Analysis

Existing traceability established:

**Pain Point → Gap → Impact**

Example:

`PP-01 → GAP-001 → IMP-001`

Requirements elicitation will extend this traceability into formal requirements.

---

# 4. Stakeholders Participating in Elicitation

| Stakeholder ID | Stakeholder | Primary Elicitation Focus |
|---|---|---|
| STK-01 | Loan Applicant | Application usability, information requirements, document submission, status visibility |
| STK-02 | Loan Officer | Application initiation, applicant support, follow-up, status visibility |
| STK-03 | KYC / Verification Team | Identity verification, KYC outcomes, exceptions |
| STK-04 | Loan Operations Team | Validation, documents, workflow, queues, exceptions |
| STK-05 | Credit / Risk Team | Eligibility, risk indicators, exceptions, business rules |
| STK-06 | Underwriter | Underwriting information, exceptions, decision support |
| STK-07 | Lending Approver | Approval authority, decision reasons, controls |
| STK-08 | Documentation Team | Approval conditions and loan documentation |
| STK-09 | Disbursement / Operations Team | Disbursement readiness and downstream handoff |
| STK-10 | Product Owner | Business priorities, scope and acceptance |
| STK-11 | Business Analyst | Requirements analysis, documentation and traceability |
| STK-12 | Project Manager | Scope, dependencies, risks and delivery priorities |
| STK-13 | Development / Integration Team | Feasibility, workflow, APIs and technical dependencies |
| STK-14 | QA / Testing Team | Testability, scenarios, acceptance criteria |
| STK-15 | Data / Reporting Team | Data requirements, KPIs and reporting |
| STK-16 | Risk / Compliance Team | Controls, auditability, lending governance and AI oversight |

---

# 5. Requirements Elicitation Techniques

A combination of elicitation techniques will be used rather than relying on a single method.

## 5.1 Stakeholder Interviews

Individual or small-group interviews will be used to understand role-specific requirements.

Suitable stakeholders include:

- Loan Officers
- Operations Users
- KYC Reviewers
- Credit / Risk Analysts
- Underwriters
- Lending Approvers
- Documentation Teams
- Disbursement Teams

Interviews are particularly useful for identifying:

- Current pain points
- Manual workarounds
- Exceptions
- Decision criteria
- Information needs
- Role responsibilities

---

## 5.2 Requirements Workshops

Cross-functional workshops will be used when requirements affect multiple teams.

Potential workshop topics include:

- End-to-end loan lifecycle
- Business rules
- Application statuses
- Exception management
- Underwriting workflow
- Approval conditions
- Reporting requirements

Workshops help identify conflicting expectations and cross-functional dependencies.

---

## 5.3 Process Analysis

The AS-IS and TO-BE processes will be reviewed to identify requirements associated with each lifecycle stage.

Process analysis helps ensure that requirements are not captured independently of the business workflow.

---

## 5.4 Document Analysis

In a real implementation, the BA may review relevant artifacts such as:

- Existing procedures
- Product documentation
- Application forms
- Business-rule documents
- Existing reports
- Interface specifications
- Operational guides
- Test cases

For this portfolio project, these are represented through simulated requirements and business artifacts rather than actual institutional documents.

---

## 5.5 Observation / Job Shadowing

In a real project, observation may be used to understand how operations users, underwriters, or other stakeholders perform existing activities.

This can reveal:

- Manual workarounds
- Repetitive activities
- Undocumented steps
- System limitations
- Operational dependencies

For this simulated portfolio project, these findings are represented through the documented AS-IS analysis.

---

## 5.6 Data Analysis

Sample and synthetic data will be analyzed to identify:

- Mandatory fields
- Missing values
- Validation needs
- Data relationships
- Reporting fields
- Status history
- KPI requirements

MySQL and Microsoft Excel will later be used for data validation and analysis.

---

## 5.7 Interface Analysis

Potential system interfaces will be analyzed to identify:

- Required data exchanges
- Request and response information
- Error scenarios
- Dependencies
- Failure handling
- Status synchronization

Detailed API requirements will be documented later.

---

## 5.8 Prototyping / Mockups

Simple conceptual screens or workflow views may be used where visual clarification improves requirement understanding.

Potential examples include:

- Application screen
- Document checklist
- Exception queue
- Underwriting review screen
- Approval-condition tracker
- Operational dashboard

---

# 6. Elicitation Plan

| Session | Stakeholders | Focus |
|---|---|---|
| ELC-01 | Product Owner, BA, PM | Business objectives, scope and priorities |
| ELC-02 | Loan Officer, Operations | Application capture and submission |
| ELC-03 | KYC Team, Operations | KYC workflow and exceptions |
| ELC-04 | Operations, Documentation | Document requirements and validation |
| ELC-05 | Operations, BA, Product Owner | Application-data validation |
| ELC-06 | Credit / Risk, Product Owner, Compliance | Eligibility and business rules |
| ELC-07 | Credit / Risk, Underwriter | Risk assessment and exception handling |
| ELC-08 | Underwriter, Lending Approver | Underwriting and lending decision |
| ELC-09 | Documentation, Operations | Approval conditions and loan documents |
| ELC-10 | Disbursement / Operations | Disbursement readiness and handoff |
| ELC-11 | Data / Reporting, Product Owner | KPIs and reporting |
| ELC-12 | Development / Integration, BA | APIs and system dependencies |
| ELC-13 | QA, BA, Product Owner | Testability and acceptance expectations |
| ELC-14 | Underwriter, Risk / Compliance, Product Owner | AI use cases, controls and human oversight |

---

# 7. Sample Elicitation Questions

## 7.1 Business and Project Questions

- What business problem are we trying to solve?
- Which process stages cause the greatest delays?
- Which activities require the most manual effort?
- Which outcomes define project success?
- Which capabilities are mandatory for the initial release?
- What should explicitly remain out of scope?

---

## 7.2 Application Questions

- What information is required to create an application?
- Which fields are mandatory before submission?
- Can an applicant save a draft?
- What validations should occur during data entry?
- What should happen when required information is missing?
- When should an Application ID be generated?
- Can submitted information be modified?
- If yes, by whom and under what conditions?

---

## 7.3 KYC Questions

- What information is required for KYC?
- What possible KYC outcomes must be supported?
- What happens when verification cannot be completed?
- Which cases require manual review?
- Can processing continue while KYC is pending?
- What KYC history must be retained?

---

## 7.4 Document Questions

- Which documents are required for each loan scenario?
- Can requirements vary by product or applicant characteristics?
- What document statuses are required?
- What makes a document unacceptable?
- How should replacement documents be handled?
- Who can waive a document requirement?
- How should missing documents affect application processing?

---

## 7.5 Data Validation Questions

- Which fields require format validation?
- Which fields require range validation?
- Which fields must be compared with other fields?
- Which data should be compared with supporting documents?
- What should happen when validation fails?
- What reason codes are required?

---

## 7.6 Eligibility and Business Rule Questions

- What determines whether an application is eligible to proceed?
- Which rules result in a hard failure?
- Which rules create an exception?
- Which rules require human judgment?
- What are the boundary conditions?
- Who owns each rule?
- How are rule changes approved?
- Should previous rule versions be retained?

---

## 7.7 Credit / Risk Questions

- What information is required for risk assessment?
- What risk indicators should be displayed?
- What conditions require escalation?
- How should risk exceptions be categorized?
- Which users can resolve or waive an exception?

---

## 7.8 Underwriting Questions

- What information does an underwriter need in one view?
- Which information currently requires manual gathering?
- Which exceptions must be resolved before a decision?
- What supporting evidence should be visible?
- What underwriting outcomes must be supported?
- When should additional information be requested?

---

## 7.9 Lending Decision Questions

- Who is authorized to approve or decline?
- Are approval levels dependent on loan characteristics?
- What decision reasons must be captured?
- Can a decision be reversed?
- If so, what authorization and audit history are required?
- What approval conditions can be attached?

---

## 7.10 Approval Condition Questions

- What types of approval conditions exist?
- Which conditions block documentation?
- Which conditions block disbursement?
- Who owns each condition?
- Who can mark a condition satisfied?
- Who can waive a condition?
- What evidence is required?

---

## 7.11 Disbursement Questions

- What conditions must be satisfied before disbursement?
- What should prevent disbursement?
- What downstream information is required?
- What happens when disbursement fails?
- How should failed disbursement be retried or escalated?

---

## 7.12 Status Questions

- What statuses are required?
- Which transitions are valid?
- Which transitions should be prohibited?
- Which role can trigger each transition?
- Which transitions happen automatically?
- What reason codes are required?
- Should status history be retained?

These answers will later feed the **Status Transition Matrix**.

---

# 8. Reporting and KPI Elicitation

Questions for Product Owner, Operations and Reporting stakeholders include:

- Which KPIs are required?
- Who consumes each KPI?
- How frequently should metrics refresh?
- Which filters are required?
- What defines application completion?
- How should turnaround time be calculated?
- How is rework defined?
- What defines an exception?
- How should approval and decline rates be calculated?
- How should stage aging be measured?
- What AI-related metrics are useful?

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

# 9. API / Integration Elicitation

For each integration, the BA will identify:

- Business purpose
- Source system
- Target system
- Trigger
- Request fields
- Response fields
- Mandatory fields
- Validation rules
- Error codes
- Timeout behavior
- Retry behavior
- Failure handling
- Manual fallback
- Audit requirements

Potential simulated integrations include:

- KYC API
- Document Service
- Credit / Risk Service
- Business Rule Service
- AI Review Service
- Notification Service
- Downstream Loan System

---

# 10. AI Requirements Elicitation

AI requirements require additional questions beyond traditional functional requirements.

## Business Questions

- What problem should AI assist with?
- Which activities should remain deterministic?
- Which activities require human judgment?
- Where could AI reduce reviewer effort?
- What information may AI use?

## Output Questions

- What should the AI return?
- Should output be structured?
- What evidence should accompany observations?
- What should happen when AI is uncertain?
- What information must never be inferred without supporting evidence?

## Human Review Questions

- Who reviews AI output?
- Can the reviewer reject the AI suggestion?
- Should reviewer action be captured?
- When must a case be escalated?

## Governance Questions

- How will AI activity be logged?
- What happens if the AI service is unavailable?
- What controls prevent AI from making the lending decision?
- How will incorrect or low-confidence outputs be handled?

---

# 11. AI Decision Boundary

A mandatory project requirement is established during elicitation:

> AI may assist with summarization, information organization, rule retrieval, exception identification and reviewer support, but it must not autonomously approve or decline a loan.

The final lending decision remains the responsibility of authorized human lending personnel.

This boundary will later be reflected in:

- Business Requirements
- Functional Requirements
- AI Requirements
- Business Rules
- User Stories
- Acceptance Criteria
- UAT
- RTM

---

# 12. Requirements Classification

Requirements discovered during elicitation will be classified as:

## Business Requirements

High-level business outcomes or capabilities.

Example:

`The organization shall reduce incomplete loan applications through earlier completeness validation.`

## Functional Requirements

Specific solution behaviors.

Example:

`The system shall prevent submission when mandatory application fields are missing.`

## Non-Functional Requirements

Quality or operational expectations including:

- Security
- Performance
- Availability
- Auditability
- Usability
- Maintainability

## Business Rules

Conditions controlling business behavior.

## Data Requirements

Data elements, formats, validation and relationships.

## Integration Requirements

System-to-system interaction requirements.

## Reporting Requirements

KPIs, calculations, filters and dashboards.

## AI Requirements

AI behavior, outputs, restrictions, human-review requirements and governance.

---

# 13. Requirement Quality Criteria

Each formal requirement should be:

- Clear
- Complete
- Concise
- Necessary
- Feasible
- Unambiguous
- Testable
- Traceable
- Consistent
- Assigned a unique identifier

Avoid requirements such as:

`The system should be user-friendly.`

Instead define measurable behavior where possible.

---

# 14. Requirement Clarification Log

During elicitation, unclear items will be captured and resolved.

| Clarification ID | Topic | Question | Owner | Status |
|---|---|---|---|---|
| CL-001 | Application | Can submitted application information be edited? | Product Owner | Open |
| CL-002 | Documents | Which document requirements vary by loan product? | Operations / Product Owner | Open |
| CL-003 | KYC | Can processing continue when KYC is pending? | KYC / Compliance | Open |
| CL-004 | Eligibility | Which rule failures are hard stops versus exceptions? | Credit / Risk | Open |
| CL-005 | Exceptions | Who may waive each exception category? | Risk / Compliance | Open |
| CL-006 | Decision | What approval-authority levels are required? | Lending Approver | Open |
| CL-007 | Conditions | Which approval conditions block disbursement? | Operations | Open |
| CL-008 | Reporting | What is the agreed calculation for processing turnaround time? | Product Owner / Reporting | Open |
| CL-009 | AI | What confidence/uncertainty threshold requires human escalation? | Product Owner / Risk | Open |
| CL-010 | Integration | What is the required fallback when an external service is unavailable? | Architecture / Operations | Open |

These are simulated clarification items and will be resolved through documented project assumptions and requirements.

---

# 15. Requirement Conflict Analysis

A BA must identify situations where stakeholders have competing needs.

## Conflict Example 1 — Speed vs Control

### Operations Need

Process applications faster.

### Risk / Compliance Need

Ensure required verification and controls are completed.

### BA Analysis

Automation may reduce repetitive work, but mandatory controls cannot be bypassed solely to reduce turnaround time.

### Proposed Resolution

Automate repeatable validation while retaining required review and blocking controls.

---

## Conflict Example 2 — Flexibility vs Standardization

### Operations Need

Allow users to move applications when exceptional situations occur.

### Product / Control Need

Maintain predictable workflow and auditability.

### Proposed Resolution

Use controlled exception paths rather than unrestricted status changes.

---

## Conflict Example 3 — AI Efficiency vs Human Decision Authority

### Business Need

Use AI to reduce underwriting review effort.

### Risk / Governance Need

Prevent inappropriate automated lending decisions.

### Proposed Resolution

AI provides review assistance while final lending decisions remain with authorized human personnel.

---

# 16. Requirements Prioritization

The project will use the **MoSCoW** prioritization method.

## Must Have

Required for the proposed solution to operate safely and support the core business process.

Examples:

- Application validation
- KYC tracking
- Document tracking
- Business rules
- Exception handling
- Underwriting workflow
- Human lending decision
- Approval-condition control
- Status management
- Audit history

## Should Have

Important capabilities that significantly improve the solution.

Examples:

- Operational dashboards
- Automated notifications
- Enhanced queue management
- AI-assisted application summaries

## Could Have

Useful enhancements that are not required for the initial implementation.

Examples:

- Additional advanced analytics
- Additional AI-assisted insights
- Expanded notification preferences

## Won't Have — Current Scope

Capabilities intentionally excluded from the current project scope.

Examples may include:

- Autonomous AI lending decisions
- Real credit-bureau connectivity
- Real financial transactions
- Production deployment to a financial institution

---

# 17. Requirements Validation

Requirements will be validated by checking:

1. Does the requirement address an identified business need?
2. Is the requirement understood by relevant stakeholders?
3. Is the requirement within scope?
4. Is it technically feasible at the conceptual project level?
5. Does it conflict with another requirement?
6. Is the requirement testable?
7. Is the requirement traceable?
8. Are required exceptions identified?
9. Are data implications understood?
10. Are control implications understood?

---

# 18. Requirements Traceability

The project traceability model will evolve into:

**Pain Point → Gap → Impact → Business Requirement → Functional Requirement → Business Rule → User Story → Acceptance Criteria → Data/API Requirement → Test Scenario → UAT Test Case → KPI**

Example:

`PP-01 → GAP-001 → IMP-001 → BR-001`

Subsequent artifacts will extend this relationship.

The final mapping will be maintained in the **Requirements Traceability Matrix (RTM)**.

---

# 19. Requirements Change Management

Requirements may change after initial approval.

When a change is proposed, the BA will assess:

- Reason for change
- Business value
- Scope impact
- Process impact
- Requirement impact
- Business-rule impact
- Data impact
- API impact
- Reporting impact
- User-story impact
- Testing impact
- Timeline/dependency impact
- Risk impact

The RTM will help identify downstream artifacts affected by the change.

A separate change-request example will be created later in the project to demonstrate this BA activity.

---

# 20. Elicitation Outputs

Requirements elicitation and analysis will produce inputs for:

1. BRS / BRD
2. FRS / FRD
3. SRS
4. Business Rules Catalogue
5. Decision Tables
6. Status Catalogue and Transition Matrix
7. User Stories
8. Acceptance Criteria
9. Data Dictionary
10. Data Mapping
11. API Requirements
12. Reporting Requirements
13. AI Requirements
14. RTM
15. UAT Test Cases

---

# 21. BA Elicitation Outcome

The elicitation approach ensures that requirements are not created in isolation.

Requirements will be derived from:

- Identified business problems
- Stakeholder needs
- AS-IS pain points
- TO-BE capabilities
- Gap Analysis
- Impact Analysis
- Business rules
- Operational scenarios
- Exceptions
- Data needs
- Integration needs
- Reporting needs
- Governance requirements

This provides the foundation for developing the formal Business Requirements Specification.

---

## Disclaimer

This Requirements Elicitation and Analysis document represents a simulated Business Analyst activity created for educational and professional portfolio purposes.

Stakeholder discussions, questions, requirements and scenarios are illustrative and do not represent the processes or policies of any specific financial institution.
