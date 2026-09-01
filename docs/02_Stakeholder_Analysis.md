# Stakeholder Analysis

## 1. Purpose

This document identifies and analyzes the key stakeholders involved in the **AI-Powered Loan Origination Requirements & Risk Assistant** project.

The stakeholder analysis covers the complete Loan Origination Lifecycle, including application initiation, KYC, document verification, eligibility validation, credit and risk assessment, underwriting, lending decision, documentation, disbursement, closure, reporting, and AI-assisted review.

The purpose is to understand each stakeholder's:

- Role and responsibilities
- Business interest
- Level of influence
- Key requirements and concerns
- Communication needs
- Engagement approach

---

## 2. Stakeholder Identification

| ID | Stakeholder | Role in Loan Origination |
|---|---|---|
| STK-01 | Loan Applicant | Provides application, KYC information and supporting documents |
| STK-02 | Loan Officer | Supports application initiation and customer communication |
| STK-03 | KYC / Verification Team | Performs identity and KYC verification |
| STK-04 | Loan Operations Team | Manages application processing and operational exceptions |
| STK-05 | Credit / Risk Team | Performs credit and risk assessment |
| STK-06 | Underwriter | Reviews application, financial information, risks and exceptions |
| STK-07 | Lending Approver | Provides authorized lending decision where required |
| STK-08 | Documentation Team | Prepares and validates loan documentation |
| STK-09 | Disbursement / Operations Team | Validates disbursement readiness and supports downstream handoff |
| STK-10 | Product Owner | Owns business priorities and product backlog |
| STK-11 | Business Analyst | Defines requirements, processes, rules, data needs and traceability |
| STK-12 | Project Manager | Manages scope, schedule, dependencies, risks and communication |
| STK-13 | Development / Integration Team | Implements application, database and API requirements |
| STK-14 | QA / Testing Team | Validates functional and system requirements |
| STK-15 | Data / Reporting Team | Supports data validation, KPI calculation and Power BI reporting |
| STK-16 | Risk / Compliance Team | Reviews controls, risks and compliance considerations |

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
| Lending Approver | High | High | Reliable underwriting information, decision recommendations, risk information and approval authority controls |
| Documentation Team | Medium | Medium | Approved terms, approval conditions, customer details and documentation status |
| Disbursement / Operations Team | High | Medium | Completed approvals, required documents, fulfilled conditions and disbursement readiness |
| Product Owner | High | High | Business value, prioritized requirements, measurable outcomes and controlled scope |
| Business Analyst | High | High | Clear requirements, stakeholder alignment, business rules, traceability and acceptance criteria |
| Project Manager | High | High | Scope, schedule, dependencies, RAID items, resources and delivery status |
| Development / Integration Team | High | High | Clear functional requirements, data mappings, API contracts, business rules and exception scenarios |
| QA / Testing Team | High | High | Testable requirements, acceptance criteria, business rules, test data and expected outcomes |
| Data / Reporting Team | Medium | Medium | Data definitions, data quality, KPI formulas, source mappings and reporting requirements |
| Risk / Compliance Team | High | High | Appropriate controls, auditability, human oversight, data handling and AI risk management |

---

## 4. Influence–Interest Matrix

Stakeholders are categorized using a Power / Interest approach.

### High Influence / High Interest — Manage Closely

- Product Owner
- Business Analyst
- Project Manager
- Loan Operations Team
- Credit / Risk Team
- Underwriter
- Lending Approver
- KYC / Verification Team
- Risk / Compliance Team
- Development / Integration Team
- QA / Testing Team

These stakeholders require frequent communication, active participation in requirement reviews, and involvement in key project decisions.

### High Interest / Medium Influence — Keep Informed and Engaged

- Loan Applicant
- Loan Officer
- Disbursement / Operations Team

These stakeholders require clear communication about process requirements, workflow changes, application status, and operational impacts.

### Medium Interest / Medium Influence — Keep Informed

- Documentation Team
- Data / Reporting Team

These stakeholders should participate when requirements affect documentation, data, reporting, or downstream processing.

---

## 5. Stakeholder Requirements by Lifecycle Stage

| Lifecycle Stage | Primary Stakeholders |
|---|---|
| Application Initiation | Loan Applicant, Loan Officer, Product Owner |
| KYC / Identity Verification | Loan Applicant, Loan Officer, KYC / Verification Team |
| Document Collection & Verification | Loan Applicant, Loan Officer, Loan Operations Team |
| Application Data Validation | Loan Operations Team, Business Analyst, Development Team |
| Eligibility & Business Rules | Product Owner, Business Analyst, Credit / Risk Team |
| Credit / Risk Assessment | Credit / Risk Team, Underwriter, Risk / Compliance Team |
| AI-Assisted Review | Underwriter, Business Analyst, Risk / Compliance Team, Development Team |
| Exception Management | Loan Operations Team, Credit / Risk Team, Underwriter |
| Underwriting | Underwriter, Credit / Risk Team |
| Lending Decision | Underwriter, Lending Approver |
| Offer & Approval Conditions | Loan Officer, Documentation Team, Loan Applicant |
| Loan Documentation | Documentation Team, Loan Operations Team |
| Disbursement | Disbursement / Operations Team |
| Application Closure / Handoff | Loan Operations Team, Disbursement Team |
| KPI Reporting | Product Owner, Project Manager, Data / Reporting Team |

---

## 6. Key Stakeholder Expectations

### Loan Applicant

The applicant expects:

- Clear application requirements
- Clear KYC requirements
- Clear document requirements
- Timely status updates
- Transparent requests for additional information
- Efficient processing

### Loan Operations Team

The operations team expects:

- Clear workflow stages
- Application-status visibility
- Queue visibility
- Missing-document alerts
- Exception tracking
- Reduced repetitive manual checks

### Credit / Risk Team

The Credit / Risk Team expects:

- Accurate applicant information
- Consistent business-rule execution
- Risk indicators
- Supporting evidence
- Clear exception categorization
- Auditability

### Underwriter

The underwriter expects:

- Complete application information
- Verified documents
- Risk information
- Business-rule results
- Exception details
- Structured application summaries
- Supporting evidence for AI-generated observations

AI-generated information must support rather than replace underwriting judgment.

### Product Owner

The Product Owner expects:

- Clearly defined business value
- Prioritized requirements
- Measurable KPIs
- Controlled project scope
- Transparent backlog status

### Risk / Compliance Team

The Risk / Compliance Team expects:

- Human decision ownership
- Appropriate access controls
- Traceable system actions
- AI auditability
- Explainable AI-assisted observations
- Exception handling
- Controlled use of customer information

---

## 7. Stakeholder Communication Plan

| Stakeholder Group | Communication | Frequency | Purpose |
|---|---|---|---|
| Product Owner | Project / backlog review | Weekly | Review priorities, scope and business value |
| Business Analyst | Requirements workshops | Throughout requirement phase | Elicit, analyze and validate requirements |
| Project Manager | Project status meeting | Weekly | Review progress, dependencies, risks and issues |
| Operations / KYC / Credit / Underwriting | Requirement workshops | As required | Validate business processes and requirements |
| Development Team | Refinement / technical discussion | During each sprint | Clarify requirements, APIs, data and dependencies |
| QA Team | Test planning / defect review | During testing | Validate coverage and resolve requirement questions |
| Data / Reporting Team | KPI and data review | During reporting phase | Validate data sources, mappings and KPI definitions |
| Risk / Compliance | Control / AI review | At key design checkpoints | Review risks, controls, auditability and human oversight |

---

## 8. Stakeholder Engagement Strategy

### Manage Closely

High-influence and high-interest stakeholders will:

- Participate in requirement workshops
- Review major requirements
- Validate business rules
- Review process changes
- Participate in solution reviews
- Support UAT and acceptance decisions where applicable

### Keep Engaged

Operational stakeholders will:

- Validate workflow requirements
- Review status transitions
- Review exception scenarios
- Participate in relevant UAT scenarios
- Provide feedback on usability and operational impact

### Keep Informed

Supporting stakeholders will receive:

- Relevant requirement updates
- Project-status information
- Changes affecting their process
- Testing and implementation information where applicable

---

## 9. Business Analyst Stakeholder Responsibilities

The Business Analyst will:

- Identify stakeholders
- Facilitate requirement workshops
- Document business requirements
- Document functional requirements
- Analyze AS-IS processes
- Design TO-BE processes
- Document business rules
- Define user stories and acceptance criteria
- Coordinate requirement reviews
- Maintain the Requirements Traceability Matrix
- Support UAT
- Clarify requirements for development and QA
- Track requirement changes
- Support stakeholder alignment

---

## 10. AI Governance Stakeholders

Because the solution includes AI-assisted review, additional stakeholder attention is required.

The primary AI-governance stakeholders are:

- Underwriter
- Credit / Risk Team
- Risk / Compliance Team
- Business Analyst
- Product Owner
- Development / Integration Team
- QA / Testing Team

These stakeholders will help ensure:

- AI is used for decision support only
- AI observations are traceable
- Human reviewers can verify supporting information
- Uncertain cases are escalated
- AI outputs are evaluated
- Appropriate guardrails are maintained
- Final lending decisions remain under authorized human control

---

## 11. Stakeholder Analysis Outcome

The stakeholder analysis establishes the stakeholder groups that will participate throughout requirements elicitation, process design, development, testing, reporting, and AI-assisted workflow design.

These stakeholders will be referenced throughout subsequent project artifacts including:

- BRS
- FRS
- SRS
- AS-IS Process
- TO-BE Process
- Business Rules
- User Stories
- Acceptance Criteria
- RACI Matrix
- RTM
- UAT Test Cases
- API Requirements
- KPI Definitions
- AI Governance and Human Review Controls

---

## Disclaimer

This stakeholder analysis is part of a simulated Banking and Financial Services portfolio case study.

The stakeholder roles and responsibilities are representative project roles created for educational and professional demonstration purposes.
