# Stakeholder Analysis

## Document Context

**Typical Real-Project Location:** Confluence / SharePoint / Excel Stakeholder Register / Project Management Repository  
**Typical Ownership:** Business Analyst and/or Project Manager  
**Primary Users:** Business Analyst, Project Manager, Product Owner, Project Sponsor and Delivery Team  
**Artifact Type:** Working analysis / stakeholder-management artifact

**Purpose:** Identifies the people and teams affected by the solution, their involvement in the loan origination lifecycle, their influence and interest, and how they should participate in requirements, validation, testing and delivery.

> **Real-Project Note:** Stakeholder analysis is a common project activity, but it does not always exist as a formal standalone document. Depending on the organization, the information may be maintained in a stakeholder register, Excel matrix, Confluence page, project-management plan, RACI matrix, or other project repository. The Business Analyst typically focuses on identifying requirement stakeholders and their involvement in analysis and validation, while the Project Manager may maintain the broader stakeholder engagement and communication strategy.

---

## 1. Purpose

This stakeholder analysis identifies the key business, operational, technology and control stakeholders involved in the **AI-Powered Loan Origination Requirements & Risk Assistant** case study.

The analysis covers the complete Loan Origination Lifecycle:

**Application Initiation → Customer & Loan Application → KYC / Identity Verification → Document Collection & Verification → Application Data Validation → Eligibility & Business Rule Validation → Credit / Risk Assessment → AI-Assisted Review & Exception Identification → Underwriting → Human Lending Decision → Approved / Declined → Offer & Approval Conditions → Loan Documentation → Disbursement → Application Closure / Handoff → Operational Reporting**

The analysis helps determine:

- Who provides requirements
- Who validates business processes
- Who owns or contributes to business rules
- Who makes business decisions
- Who uses the proposed solution
- Who supports development and integration
- Who validates the solution during testing and UAT
- Who needs to be consulted when requirements change
- Who is affected by process or system changes
- Who participates in AI governance and human review

---

## 2. Stakeholder Identification

| ID | Stakeholder | Role in Loan Origination |
|---|---|---|
| STK-01 | Loan Applicant | Provides application, KYC information and supporting documents |
| STK-02 | Loan Officer | Supports application initiation and customer communication |
| STK-03 | KYC / Verification Team | Performs identity and KYC verification |
| STK-04 | Loan Operations Team | Manages application processing and operational exceptions |
| STK-05 | Credit / Risk Team | Performs credit and risk assessment |
| STK-06 | Underwriter | Reviews application information, risks, exceptions and supporting evidence |
| STK-07 | Lending Approver | Provides authorized lending decision where required |
| STK-08 | Documentation Team | Prepares and validates loan documentation |
| STK-09 | Disbursement / Operations Team | Validates disbursement readiness and supports downstream handoff |
| STK-10 | Product Owner | Owns product priorities, business value and product backlog |
| STK-11 | Business Analyst | Elicits, analyzes, documents and clarifies business and solution requirements |
| STK-12 | Project Manager | Coordinates scope, schedule, dependencies, risks, issues and project communication |
| STK-13 | Development / Integration Team | Implements application, database and integration requirements |
| STK-14 | QA / Testing Team | Validates expected system behavior against requirements |
| STK-15 | Data / Reporting Team | Supports data requirements, KPI calculations and Power BI reporting |
| STK-16 | Risk / Compliance Team | Reviews applicable controls, risks, auditability and AI-governance considerations |

---

## 3. Detailed Stakeholder Analysis

| Stakeholder | Interest | Influence | Key Requirements / Concerns |
|---|---|---|---|
| Loan Applicant | High | Medium | Simple application process, clear document requirements, application-status visibility and timely communication |
| Loan Officer | High | High | Complete application information, customer visibility, reduced follow-up and clear application status |
| KYC / Verification Team | High | High | Accurate identity information, required KYC documents, verification status and exception handling |
| Loan Operations Team | High | High | Workflow visibility, queue management, document completeness, status tracking and exception management |
| Credit / Risk Team | High | High | Accurate applicant information, risk indicators, business rules, supporting evidence and exception visibility |
| Underwriter | High | High | Complete application summary, validated information, risk indicators, exceptions, supporting documents and explainable AI assistance |
| Lending Approver | High | High | Reliable underwriting information, risk information, approval conditions and appropriate decision-authority controls |
| Documentation Team | Medium | Medium | Approved terms, approval conditions, customer details and documentation status |
| Disbursement / Operations Team | High | Medium | Completed approvals, required documentation, fulfilled conditions and disbursement readiness |
| Product Owner | High | High | Business value, prioritized backlog, measurable outcomes and controlled scope |
| Business Analyst | High | High | Clear requirements, stakeholder alignment, business rules, traceability and testable acceptance criteria |
| Project Manager | High | High | Scope, schedule, dependencies, risks, issues, resources and delivery status |
| Development / Integration Team | High | High | Clear requirements, data mappings, API contracts, business rules and exception scenarios |
| QA / Testing Team | High | High | Testable requirements, acceptance criteria, business rules, test data and expected outcomes |
| Data / Reporting Team | Medium | Medium | Data definitions, data quality, KPI formulas, source mappings and reporting requirements |
| Risk / Compliance Team | High | High | Appropriate controls, auditability, human oversight, data handling and responsible AI usage |

---

## 4. Influence–Interest Assessment

A Power / Interest assessment is used to determine the appropriate level of stakeholder engagement.

### High Influence / High Interest — Manage Closely

- STK-02 — Loan Officer
- STK-03 — KYC / Verification Team
- STK-04 — Loan Operations Team
- STK-05 — Credit / Risk Team
- STK-06 — Underwriter
- STK-07 — Lending Approver
- STK-10 — Product Owner
- STK-11 — Business Analyst
- STK-12 — Project Manager
- STK-13 — Development / Integration Team
- STK-14 — QA / Testing Team
- STK-16 — Risk / Compliance Team

These stakeholders require active involvement depending on the lifecycle stage and subject being discussed.

### High Interest / Medium Influence — Keep Engaged

- STK-01 — Loan Applicant
- STK-09 — Disbursement / Operations Team

Their requirements and operational impacts must be understood even when they do not participate in every project decision.

### Medium Interest / Medium Influence — Keep Informed / Consult as Required

- STK-08 — Documentation Team
- STK-15 — Data / Reporting Team

These stakeholders should be consulted when requirements affect documentation, downstream processing, data, KPIs or reporting.

> **BA Note:** Influence and interest can change during a project. For example, the Data / Reporting Team may become a high-engagement stakeholder when reporting development begins.

---

## 5. Stakeholder Involvement by Lifecycle Stage

| Lifecycle Stage | Primary Stakeholders |
|---|---|
| Application Initiation | Loan Applicant, Loan Officer, Product Owner |
| Customer & Loan Application | Loan Applicant, Loan Officer, Loan Operations Team |
| KYC / Identity Verification | Loan Applicant, Loan Officer, KYC / Verification Team |
| Document Collection & Verification | Loan Applicant, Loan Officer, Loan Operations Team |
| Application Data Validation | Loan Operations Team, Business Analyst, Development / Integration Team |
| Eligibility & Business Rule Validation | Product Owner, Business Analyst, Credit / Risk Team, Risk / Compliance Team |
| Credit / Risk Assessment | Credit / Risk Team, Underwriter, Risk / Compliance Team |
| AI-Assisted Review | Underwriter, Credit / Risk Team, Business Analyst, Risk / Compliance Team, Development / Integration Team |
| Exception Management | Loan Operations Team, Credit / Risk Team, Underwriter |
| Underwriting | Underwriter, Credit / Risk Team |
| Human Lending Decision | Lending Approver, Underwriter |
| Offer & Approval Conditions | Loan Officer, Documentation Team, Loan Applicant |
| Loan Documentation | Documentation Team, Loan Operations Team |
| Disbursement | Disbursement / Operations Team |
| Application Closure / Handoff | Loan Operations Team, Disbursement / Operations Team |
| Operational Reporting | Product Owner, Project Manager, Data / Reporting Team, Loan Operations Team |

---

## 6. Key Stakeholder Expectations

### STK-01 — Loan Applicant

The Loan Applicant expects:

- Clear application requirements
- Clear KYC requirements
- Clear supporting-document requirements
- Timely requests for additional information
- Application-status visibility
- Efficient processing
- Clear communication

### STK-02 — Loan Officer

The Loan Officer expects:

- Visibility into customer and application information
- Clear application requirements
- Missing-information visibility
- Application-status visibility
- Reduced unnecessary customer follow-up
- Clear operational next steps

### STK-03 — KYC / Verification Team

The KYC / Verification Team expects:

- Complete identity information
- Required KYC documentation
- Clear verification outcomes
- Exception handling
- Traceable verification results
- Ability to identify cases requiring manual review

### STK-04 — Loan Operations Team

The Loan Operations Team expects:

- Clear workflow stages
- Queue visibility
- Application-status visibility
- Missing-document identification
- Exception tracking
- Clear ownership
- Reduced repetitive manual validation
- Traceable processing activities

### STK-05 — Credit / Risk Team

The Credit / Risk Team expects:

- Accurate applicant information
- Consistent business-rule execution
- Credit and risk information
- Supporting evidence
- Clear exception categorization
- Traceable review results
- Appropriate control handling

### STK-06 — Underwriter

The Underwriter expects:

- Complete application information
- Verified supporting information
- Business-rule outcomes
- Credit and risk information
- Exception details
- Structured application summaries
- Supporting evidence for AI-generated observations
- Ability to accept, reject, correct or disregard AI-assisted observations

AI-generated information must support rather than replace underwriting judgment.

### STK-07 — Lending Approver

The Lending Approver expects:

- Complete underwriting information
- Relevant risk and exception information
- Decision reason capture
- Appropriate approval authority controls
- Visibility into outstanding approval conditions
- Complete audit history

Final lending decisions must remain with appropriately authorized human personnel.

### STK-08 — Documentation Team

The Documentation Team expects:

- Approved loan terms
- Approval-condition status
- Accurate customer and loan information
- Documentation-readiness information
- Clear documentation status

### STK-09 — Disbursement / Operations Team

The Disbursement / Operations Team expects:

- Valid lending approval
- Completed documentation
- Fulfilled or appropriately resolved approval conditions
- Disbursement-readiness confirmation
- Clear downstream handoff information

### STK-10 — Product Owner

The Product Owner expects:

- Clearly defined business value
- Prioritized backlog
- Measurable outcomes
- Controlled project scope
- Visibility into dependencies
- Timely clarification of business requirements

### STK-11 — Business Analyst

The Business Analyst requires:

- Access to relevant business and technology stakeholders
- Clear business objectives
- Timely requirement clarification
- Access to existing processes and business rules
- Stakeholder participation in requirement reviews
- Support for resolving conflicting requirements
- Business participation during UAT

### STK-12 — Project Manager

The Project Manager expects:

- Visibility into scope and requirement changes
- Dependencies and delivery risks
- Issues requiring escalation
- Milestone and delivery status
- Stakeholder participation
- Timely identification of blockers

### STK-13 — Development / Integration Team

The Development / Integration Team expects:

- Clear and testable requirements
- Business rules
- Expected workflow behavior
- Data definitions and mappings
- API/interface requirements
- Exception and error scenarios
- Timely BA clarification during development

### STK-14 — QA / Testing Team

The QA / Testing Team expects:

- Testable requirements
- Acceptance criteria
- Business-rule outcomes
- Positive and negative scenarios
- Test data requirements
- Expected exception behavior
- Timely clarification of requirement-related defects

### STK-15 — Data / Reporting Team

The Data / Reporting Team expects:

- Data definitions
- Source-to-target mappings
- KPI definitions
- Calculation rules
- Data-quality requirements
- Reporting dimensions
- Reconciliation expectations

### STK-16 — Risk / Compliance Team

The Risk / Compliance Team expects:

- Human lending-decision ownership
- Appropriate access controls
- Auditability
- Traceable system actions
- Controlled handling of information
- AI review transparency
- Human oversight
- AI fallback and exception controls

---

## 7. Stakeholder Communication & Engagement

> **Real-Project Note:** A detailed communication plan is often owned by the Project Manager. The Business Analyst typically manages requirements-related stakeholder engagement through workshops, walkthroughs, refinement sessions, clarifications and UAT discussions.

| Stakeholder Group | Typical Engagement | Indicative Frequency | Purpose |
|---|---|---|---|
| Product Owner | Backlog / requirement review | Weekly or as required | Confirm priorities, scope and business value |
| Business Stakeholders | Requirement workshop / walkthrough | During analysis and when changes occur | Elicit and validate requirements |
| Project Manager | Project status / dependency discussion | Weekly | Review progress, risks, issues and dependencies |
| Operations / KYC / Credit / Underwriting | Process and requirement workshops | As required | Validate workflow, rules and operational scenarios |
| Development / Integration Team | Backlog refinement / technical clarification | During delivery | Clarify requirements, APIs, data and dependencies |
| QA / Testing Team | Test review / defect triage | During testing | Confirm expected behavior and resolve requirement questions |
| Data / Reporting Team | Data and KPI review | During data/reporting work | Validate mappings, definitions and KPI calculations |
| Risk / Compliance Team | Control / AI governance review | At relevant checkpoints | Validate controls, auditability and human oversight |

Frequency is indicative and would normally be adjusted according to the delivery methodology, project phase and stakeholder availability.

---

## 8. Business Analyst Engagement Approach

The Business Analyst will use different engagement techniques depending on the stakeholder and requirement.

### Workshops

Used when multiple stakeholders need to:

- Agree on a business process
- Define requirements
- Resolve differences
- Review business rules
- Analyze exceptions
- Agree on future-state behavior

### Interviews / Discussions

Used when detailed information is required from:

- Subject Matter Experts
- Underwriters
- Loan Operations
- Credit / Risk
- KYC teams
- Technical stakeholders

### Requirement Walkthroughs

Used to validate:

- Business requirements
- Functional requirements
- Business rules
- Process flows
- User stories
- Acceptance criteria
- Data and integration requirements

### Backlog Refinement

Used with the Product Owner, Development Team and QA Team to:

- Clarify user stories
- Review acceptance criteria
- Identify dependencies
- Identify missing scenarios
- Support estimation
- Prepare items for development

### UAT Support

Used with business stakeholders to:

- Confirm business scenarios
- Clarify expected results
- Review issues
- Determine whether observed behavior is a defect or requirement change
- Support business acceptance

---

## 9. Handling Stakeholder Conflicts

Stakeholders may provide conflicting requirements.

Example:

**Loan Operations requirement:** Allow an application to continue when information is incomplete so processing can begin.

**Risk / Compliance requirement:** Do not allow specific controlled stages to proceed until mandatory information has been validated.

The Business Analyst should not independently choose one stakeholder's requirement.

The BA will:

1. Document both requirements.
2. Identify the affected process and requirements.
3. Analyze business and system impact.
4. Identify applicable rules or controls.
5. Facilitate discussion between relevant stakeholders.
6. Escalate to the Product Owner or authorized decision-maker when necessary.
7. Record the agreed decision.
8. Update affected requirements and traceability.
9. Communicate the approved change to Development and QA.

This provides an auditable requirement-decision process.

---

## 10. Requirement Clarification & Decision Ownership

The Business Analyst facilitates clarification but does not independently define lending policy or approve business decisions.

| Requirement Area | Primary Business Input / Decision Authority |
|---|---|
| Application Process | Product Owner / Loan Operations |
| KYC Requirements | KYC / Verification Team and applicable control stakeholders |
| Document Requirements | Loan Operations / Product Owner |
| Eligibility Rules | Product Owner / Credit / Risk / applicable control stakeholders |
| Credit / Risk Requirements | Credit / Risk Team |
| Underwriting Requirements | Underwriter / Credit / Risk Team |
| Lending Decision Authority | Authorized Lending Approver / applicable lending governance |
| Approval Conditions | Lending / Underwriting stakeholders |
| Documentation | Documentation Team |
| Disbursement Readiness | Disbursement / Operations Team |
| KPI Definitions | Product Owner / Operations / Data & Reporting |
| AI Review Controls | Product Owner / Underwriter / Risk / Compliance / Technology stakeholders |

> **BA Principle:** The BA elicits, analyzes, challenges, clarifies, documents and traces requirements. The appropriate business or control stakeholder owns the underlying business policy or decision.

---

## 11. Business Analyst Responsibilities

The Business Analyst will:

- Identify requirement stakeholders
- Plan and facilitate requirement discussions
- Analyze stakeholder needs
- Document business and functional requirements
- Analyze AS-IS processes
- Define TO-BE process requirements with stakeholders
- Document business rules and decision logic
- Identify data and integration requirements
- Prepare and refine user stories and acceptance criteria
- Facilitate requirement reviews
- Support backlog refinement
- Clarify requirements for Development and QA
- Analyze requirement changes
- Assess downstream impacts
- Maintain appropriate requirements traceability
- Support UAT preparation and execution
- Support defect clarification
- Facilitate stakeholder alignment

The BA collaborates with the Project Manager, Product Owner, SMEs, technical teams and QA rather than independently owning every project activity.

---

## 12. AI Governance Stakeholders

Because the proposed solution includes AI-assisted review, additional stakeholder participation is required.

Primary stakeholders include:

- STK-05 — Credit / Risk Team
- STK-06 — Underwriter
- STK-07 — Lending Approver
- STK-10 — Product Owner
- STK-11 — Business Analyst
- STK-13 — Development / Integration Team
- STK-14 — QA / Testing Team
- STK-16 — Risk / Compliance Team

These stakeholders will help ensure that:

- AI is used as decision support
- AI does not autonomously approve or decline loans
- AI does not override deterministic business rules
- AI observations are traceable
- Approved knowledge sources are used where applicable
- Human reviewers can verify supporting information
- Uncertain outputs are routed for human review
- Human reviewers can accept, reject, correct or disregard AI observations
- AI outputs can be evaluated
- AI failures have an appropriate human/manual fallback
- AI activity is appropriately logged
- Final lending decisions remain under authorized human control

---

## 13. Stakeholder Analysis Outcome

This analysis identifies the stakeholders required throughout:

- Requirements elicitation
- Process analysis
- Requirement validation
- Business-rule definition
- Data and integration analysis
- Backlog refinement
- Development clarification
- Testing
- UAT
- Reporting
- Release preparation
- AI-assisted workflow design and governance

Stakeholder information will be referenced by subsequent project activities and artifacts, including:

- Business Requirements Specification
- Functional Requirements Specification
- System Requirements Specification
- AS-IS and TO-BE Process Flows
- Business Rules
- Decision Tables
- User Stories and Acceptance Criteria
- Data Mapping
- API / Interface Requirements
- Requirements Traceability
- UAT
- RACI Matrix
- RAID / Risk Log
- KPI Definitions
- AI Governance and Human Review Controls

> **Portfolio Representation:** This GitHub file represents stakeholder-analysis work that, in an enterprise project, could be distributed across a stakeholder register, Confluence pages, project-management documentation, RACI artifacts and requirements-workshop records.

---

## Disclaimer

This stakeholder analysis is part of a simulated Banking and Financial Services portfolio case study.

The stakeholder roles, influence assessments, engagement approaches and responsibilities are representative examples created for educational and professional demonstration purposes. They do not represent the stakeholder structure of a specific financial institution.
