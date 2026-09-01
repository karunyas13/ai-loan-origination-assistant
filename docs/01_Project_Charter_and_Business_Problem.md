# Project Charter & Business Problem

## Document Context

**Typical Real-Project Location:** Confluence / SharePoint / Project Management Repository  
**Typical Ownership:** Project Manager / Project Sponsor, with Business Analyst contribution  
**Primary Users:** Project Sponsor, Product Owner, Business Analyst, Project Manager, Business and Technology Stakeholders  
**Purpose:** Establishes the business problem, objectives, scope, stakeholders, assumptions, constraints, dependencies, risks, success criteria, and high-level project direction.

> **Real-Project Note:** A Project Charter is typically created during project initiation and is commonly owned or coordinated by the Project Manager or Project Sponsor. The Business Analyst contributes to areas such as the business problem, scope, stakeholders, business needs, assumptions, dependencies, and success measures. The exact format and ownership vary by organization.

---

## 1. Project Title

**AI-Powered Loan Origination Requirements & Risk Assistant**

---

## 2. Project Overview

This project is a simulated Banking and Financial Services case study focused on designing and improving the complete Loan Origination Lifecycle through Business Analysis, Project Management, data analytics, system integration, workflow automation, and responsible AI-assisted review.

The project covers the journey of a loan application from initial application through KYC, document verification, eligibility and risk assessment, underwriting, lending decision, loan documentation, disbursement, and final application closure or handoff.

The solution will demonstrate the use of:

- Business Analysis and Requirements Engineering
- Agile Project Management
- MySQL
- Microsoft Excel
- Microsoft Power BI
- REST APIs
- AI / LLM-assisted workflows
- RAG and knowledge retrieval concepts
- Human-in-the-loop review
- Requirements traceability
- UAT and quality validation

The AI component will provide decision-support capabilities such as application summarization, missing-information detection, document-completeness support, business-rule retrieval, and risk/exception identification.

**AI will not autonomously approve or decline a loan. Final lending decisions will remain with authorized human reviewers.**

---

## 3. Business Problem

Loan origination is a complex process involving customers, loan officers, operations teams, KYC verification, document processing, credit and risk assessment, underwriting, approval authorities, technology systems, and reporting teams.

A loan application may pass through multiple systems and manual review stages before it reaches final disbursement.

Potential challenges within the current simulated process include:

- Incomplete loan applications
- Missing or invalid KYC information
- Missing supporting documents
- Inconsistent applicant information across systems
- Repetitive manual data validation
- Manual document-completeness checks
- Delayed eligibility verification
- Delayed identification of risk and exceptions
- Multiple applicant follow-ups
- Manual preparation of underwriting summaries
- Limited visibility into application status
- Applications remaining in processing queues for extended periods
- Delays between underwriting and decision stages
- Manual handoffs between teams
- Limited visibility into stage-level turnaround time
- Limited requirements-to-testing traceability
- Limited operational KPI reporting

These challenges can increase operational effort, processing time, rework, and the risk of inconsistent handling across the loan origination lifecycle.

---

## 4. Business Need

The organization requires a structured digital loan origination process that improves visibility, consistency, traceability, and operational efficiency across the complete application lifecycle.

The proposed solution should support:

- Structured application capture
- Customer and applicant verification
- KYC validation
- Document collection and verification
- Application data validation
- Eligibility assessment
- Business-rule validation
- Credit and risk assessment
- Exception identification
- Underwriting review
- Human lending decisions
- Approval and decline tracking
- Offer and approval-condition management
- Loan documentation
- Disbursement readiness
- Application closure and downstream handoff
- Operational KPI reporting
- Responsible AI-assisted review

---

## 5. Project Objectives

The objectives of this project are to:

1. Design an end-to-end Loan Origination Lifecycle.
2. Improve loan application completeness.
3. Identify missing information and documentation earlier.
4. Improve KYC and document-verification visibility.
5. Establish consistent business rules and validation requirements.
6. Improve eligibility, risk, and exception identification.
7. Reduce repetitive manual review activities.
8. Improve underwriting review support.
9. Provide clear application and workflow status visibility.
10. Improve handoffs between business and operational teams.
11. Establish requirements-to-testing traceability.
12. Define measurable operational KPIs.
13. Demonstrate API-based integration requirements.
14. Provide data-driven operational reporting using Power BI.
15. Demonstrate responsible AI-assisted review with human oversight.

---

## 6. Loan Origination Lifecycle

The project will cover the following high-level lifecycle:

**Application Initiation → Customer & Loan Application → KYC / Identity Verification → Document Collection & Verification → Application Data Validation → Eligibility & Business Rule Validation → Credit / Risk Assessment → AI-Assisted Review & Exception Identification → Underwriting → Human Lending Decision → Approved / Declined → Offer & Approval Conditions → Loan Documentation → Disbursement → Application Closure / Handoff → Operational Reporting**

Individual stages may include additional statuses, exception paths, rework loops, and human-review activities.

Detailed **AS-IS** and **TO-BE** process flows will be documented separately.

---

## 7. In Scope

### Loan Application

- Loan application initiation
- Applicant information capture
- Loan-product selection
- Requested loan amount
- Application submission
- Application status tracking

### KYC & Customer Verification

- Customer identity information
- KYC status tracking
- Required KYC information
- Verification results
- Failed or incomplete KYC handling
- KYC exception management

### Document Management

- Required-document identification
- Document submission
- Document status tracking
- Missing-document identification
- Document verification
- Document-related exceptions

### Application & Data Validation

- Mandatory-field validation
- Applicant-data validation
- Data-quality checks
- Cross-field validation
- Duplicate or inconsistent information identification

### Eligibility & Business Rules

- Eligibility-rule validation
- Loan-product rules
- Applicant criteria
- Business-rule outcomes
- Failed-rule identification
- Exception handling

### Credit, Risk & Exception Management

- Credit/risk information representation
- Risk indicators
- Exception identification
- Exception categorization
- Exception status
- Manual review requirements

### Underwriting

- Underwriting queue
- Application review
- Application summary
- Supporting information
- Risk and exception review
- Underwriter comments
- Review status

### Lending Decision

- Decision-pending status
- Human decision recording
- Approved status
- Declined status
- Decision reason
- Approval conditions where applicable

### Offer & Loan Documentation

- Offer generation concepts
- Approval conditions
- Customer acceptance status
- Loan-document preparation
- Documentation completion status

### Disbursement

- Disbursement-readiness validation
- Required approval checks
- Required documentation checks
- Disbursement status
- Downstream handoff

### Application Closure

- Completed application
- Declined application closure
- Withdrawn application handling
- Cancelled application handling
- Final status tracking

### Data & Reporting

- Synthetic loan data
- MySQL database
- Data dictionary
- Data mapping
- Data validation
- SQL validation queries
- KPI queries
- Microsoft Excel artifacts
- Microsoft Power BI dashboard

### API & Integration

- Application APIs
- Customer/KYC integration concepts
- Document-status APIs
- Validation APIs
- Risk/exception APIs
- Underwriting APIs
- Decision/status APIs
- Disbursement-status integration concepts
- Sample API requests and responses

### AI-Assisted Review

- Application summarization
- Missing-information detection
- Document-completeness support
- Business-rule retrieval
- Exception identification
- Risk-review support
- Structured AI outputs
- Human escalation
- RAG / knowledge retrieval
- Prompt design
- AI evaluation
- Guardrails
- Audit logging

### Project Management

- Stakeholder analysis
- RACI matrix
- RAID / Risk Log
- Product backlog management
- Sprint planning
- Prioritization
- Dependencies
- Project status tracking
- UAT coordination

---

## 8. Out of Scope

The following are outside the scope of this portfolio project:

- Real customer data
- Real financial institution data
- Production deployment
- Actual credit bureau connectivity
- Actual government KYC-system connectivity
- Real fund transfer
- Real payment processing
- Production credit scoring
- Production fraud detection
- Legal or regulatory certification
- Real banking core-system integration
- Autonomous AI lending decisions

External systems may be represented through simulated APIs, requirements, sample payloads, and integration designs.

---

## 9. Key Stakeholders

| Stakeholder | Primary Responsibility |
|---|---|
| Loan Applicant | Provides application, KYC information and supporting documents |
| Loan Officer | Supports application initiation and customer communication |
| KYC / Verification Team | Reviews identity and verification requirements |
| Loan Operations Team | Manages application processing and operational exceptions |
| Credit / Risk Team | Supports credit and risk assessment |
| Underwriter | Reviews the application and provides lending assessment |
| Lending Approver | Provides authorized lending decision where required |
| Documentation Team | Supports loan-document preparation and completion |
| Disbursement / Operations Team | Supports disbursement readiness and downstream handoff |
| Product Owner | Prioritizes requirements and business value |
| Business Analyst | Defines requirements, processes, rules, data needs and traceability |
| Project Manager | Coordinates scope, schedule, dependencies, risks and stakeholders |
| Development Team | Implements application and integration requirements |
| QA / Testing Team | Validates requirements and system behavior |
| Data / Reporting Team | Supports data validation, KPIs and Power BI reporting |
| Risk / Compliance Team | Reviews relevant controls and risk considerations |

A detailed stakeholder analysis will be maintained separately.

---

## 10. Assumptions

- All customer, loan and transaction data will be synthetic.
- The project represents a simulated financial-services environment.
- Business rules will be designed for portfolio demonstration.
- External systems will be represented through simulated integration requirements.
- Required stakeholders are assumed to be available for requirement clarification.
- AI outputs will be treated as recommendations or review assistance.
- Human reviewers will retain final lending-decision authority.
- Power BI reporting will use synthetic project data.

---

## 11. Constraints

- No access to a real bank's production systems.
- No real customer financial information will be used.
- No live credit bureau integration.
- No live KYC-provider integration.
- No real financial disbursement will occur.
- Regulatory requirements will be represented at a portfolio level.
- AI capabilities will be evaluated using synthetic scenarios.
- The project is a portfolio case study rather than a production banking platform.

---

## 12. Key Dependencies

Key project dependencies include:

- Business requirements
- Stakeholder requirements
- Loan-product definition
- Application workflow and status requirements
- KYC requirements
- Document requirements
- Eligibility rules
- Business rules
- Risk and exception rules
- Underwriting requirements
- Decision requirements
- Documentation requirements
- Disbursement-readiness requirements
- Synthetic dataset
- MySQL data model
- API specifications
- Data mapping
- KPI definitions
- UAT scenarios
- AI knowledge sources and review rules

---

## 13. Initial Project Risks

| Risk | Potential Impact | Proposed Mitigation |
|---|---|---|
| Incomplete requirements | Rework during development and testing | Conduct requirement reviews and maintain traceability |
| Unclear business rules | Inconsistent validation | Document rule logic and expected outcomes |
| Poor data quality | Incorrect validation and reporting | Define data-quality rules and SQL checks |
| Missing integration requirements | Process and system gaps | Maintain API specifications and data mappings |
| Scope expansion | Project delays | Maintain scope, priorities and product backlog |
| Incorrect workflow behavior | Processing inconsistencies | Define workflow rules and expected system behavior |
| Incorrect AI output | Misleading reviewer information | Validate outputs and require human review |
| Over-reliance on AI | Increased decision risk | Keep lending decisions under human authority |
| Limited AI explainability | Reduced reviewer confidence | Provide evidence, reason codes and audit information |
| Missing traceability | Requirements may not be adequately tested | Maintain requirements-to-test traceability |

---

## 14. Success Criteria

The project will be considered successful when:

- The complete loan origination lifecycle is documented.
- AS-IS and TO-BE processes are defined.
- Business requirements are documented and traceable.
- Functional and system requirements are defined.
- Business rules and applicable decision logic are documented.
- User stories contain measurable acceptance criteria.
- Requirements are traceable through testing and UAT.
- MySQL supports the required lifecycle data.
- Data mappings and API requirements are documented.
- Power BI provides meaningful operational KPIs.
- Risk and exceptions can be tracked.
- AI-assisted review can support synthetic loan scenarios.
- Human review remains mandatory for lending decisions.

---

## 15. Initial KPI Framework

| KPI | Purpose |
|---|---|
| Total Applications | Monitor loan application volume |
| Application Completion Rate | Measure complete applications |
| KYC Completion Rate | Measure successful KYC completion |
| Missing Document Rate | Monitor document-completeness issues |
| Average Processing Time | Measure application-to-completion time |
| Stage Turnaround Time | Identify processing bottlenecks |
| Eligibility Failure Rate | Measure applications failing eligibility rules |
| Exception Rate | Measure applications requiring exception handling |
| Underwriting Queue Volume | Monitor underwriting workload |
| Approval Rate | Monitor approved applications |
| Decline Rate | Monitor declined applications |
| Approval-to-Disbursement Time | Measure post-approval processing efficiency |
| Human Escalation Rate | Monitor AI-assisted cases escalated for review |
| AI Review Volume | Monitor AI-assisted application reviews |
| UAT Pass Rate | Measure successful UAT execution |
| Requirements Coverage | Measure requirements mapped to testing |

Detailed KPI definitions and calculations will be developed during the reporting phase.

---

## 16. Project Deliverables

The project will progressively include:

### Business Analysis & Requirements

- Project Charter & Business Problem
- Stakeholder Analysis
- Scope / Out of Scope
- AS-IS Process
- TO-BE Process
- Gap Analysis
- Impact Analysis
- Requirements Elicitation & Analysis
- Business Requirements Specification (BRS / BRD)
- Functional Requirements Specification (FRS / FRD)
- System Requirements Specification (SRS)
- Business Rules
- Decision Tables where applicable
- Requirements Traceability Matrix (RTM)

### Agile Delivery

- Product Backlog / Sprint Delivery Artifacts (Jira / Azure DevOps representation)
- User Stories
- Acceptance Criteria
- Prioritization
- Requirement Clarifications
- Change / Impact Analysis

### Data, Integration & Reporting

- Data Dictionary
- Data Mapping
- MySQL Database
- SQL Validation Queries
- KPI Queries
- API Endpoint Specifications
- API Request / Response Samples
- Microsoft Excel validation and reconciliation artifacts
- Microsoft Power BI Dashboard

### Testing & UAT

- Test Scenario Review
- UAT Test Cases
- Defect / Issue Tracking
- Requirements-to-test traceability
- UAT coordination and business validation

### Project Management Support

- RACI Matrix
- RAID / Risk Log
- Dependencies
- Project Status Reporting
- Sprint / Release Coordination

### AI-Assisted Review

- AI Use Cases
- RAG / Knowledge Retrieval Design
- Prompt Design
- Structured AI Outputs
- Human Review Controls
- AI Evaluation
- AI Guardrails
- AI Auditability

> **Real-Project Note:** These artifacts would not necessarily exist as separate documents in every organization. Depending on the delivery model, they may be maintained across Confluence, SharePoint, Jira, Azure DevOps, requirements-management tools, test-management tools, Excel, API documentation platforms, source-control repositories, and reporting platforms.

---

## 17. Project Status

**Status: In Development**

### Completed Analysis & Requirements Activities

- Project Charter & Business Problem
- Stakeholder Analysis
- AS-IS Loan Origination Process
- TO-BE Loan Origination Process
- Gap Analysis
- Impact Analysis
- Requirements Elicitation & Analysis
- Business Requirements Specification (BRS / BRD)
- Functional Requirements Specification (FRS / FRD)
- System Requirements Specification (SRS)
- Business Rules Catalogue
- Decision Tables

### Current Stage

**Requirements Analysis Complete — Preparing for Agile Delivery**

The next stage will translate the established requirements and business rules into delivery-ready backlog items, including user stories and acceptance criteria.

In a real Agile project, backlog items would typically be maintained in a delivery-management tool such as Jira or Azure DevOps rather than as standalone formal requirement documents.

---

## Disclaimer

This is a simulated portfolio case study created for educational and professional demonstration purposes.

It does not represent a production lending platform or work performed for a specific financial institution.

All customer, loan and operational data used in the project will be synthetic.
