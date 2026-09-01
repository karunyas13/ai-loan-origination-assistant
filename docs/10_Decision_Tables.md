# Decision Tables

## AI-Powered Loan Origination Requirements & Risk Assistant

---

# 1. Document Purpose

This document defines decision tables for selected business rules within the simulated end-to-end loan origination process.

Decision tables convert business rules into structured combinations of:

**Conditions → Outcomes → Actions**

They help the Business Analyst:

- Remove ambiguity from requirements
- Validate business logic with stakeholders
- Identify missing scenarios
- Clarify exception behavior
- Support developers
- Support QA and UAT
- Improve requirements traceability

The tables in this document reference the approved Business Rules Catalogue `RULE-001` through `RULE-040`.

---

# 2. Decision Table Identification

Decision tables use the identifier:

`DT-001`, `DT-002`, `DT-003`, etc.

These IDs should remain stable throughout downstream project artifacts.

---

# 3. Decision Table Conventions

| Symbol | Meaning |
|---|---|
| Y | Yes / Condition satisfied |
| N | No / Condition not satisfied |
| - | Condition not relevant for that scenario |
| PASS | Rule evaluation passed |
| FAIL | Rule evaluation failed |
| HARD_STOP | Normal workflow progression prohibited |
| REVIEW_REQUIRED | Human review required |

---

# 4. DT-001 — Application Submission Decision

**Related Rules:** RULE-001, RULE-003, RULE-004  
**Related Requirements:** BR-001, BR-004; FR-003, FR-005, FR-006; SR-004, SR-005

## Business Question

Can the loan application be successfully submitted?

| Condition / Action | R1 | R2 | R3 | R4 |
|---|---:|---:|---:|---:|
| Mandatory fields complete? | Y | N | Y | Y |
| Field validations passed? | Y | - | N | Y |
| Application currently editable? | Y | Y | Y | N |
| **Allow submission** | Y | N | N | N |
| **Remain / return to correction path** | N | Y | Y | Y |

### Interpretation

- **R1:** Application satisfies submission requirements and may be submitted.
- **R2:** Missing mandatory information prevents submission.
- **R3:** Validation errors must be corrected.
- **R4:** Submission is not permitted from a state that does not allow the action.

---

# 5. DT-002 — KYC Processing Decision

**Related Rules:** RULE-005, RULE-006, RULE-007  
**Related Requirements:** BR-002, BR-007; FR-007 – FR-010; SR-007 – SR-010

## Business Question

How should the application proceed based on the KYC result?

| KYC Result | Continue Normal Processing | Manual Review | Treat as Verified |
|---|---:|---:|---:|
| Verified | Y | N | Y |
| Pending | N | N | N |
| Manual Review Required | N | Y | N |
| Failed | N | Y | N |
| Service Error / Unable to Verify | N | Y | N |

### Interpretation

Only a successful verification may be treated as `KYC Verified`.

Failed, uncertain, or unavailable verification shall not silently become a successful KYC outcome.

---

# 6. DT-003 — Required Document Determination

**Related Rules:** RULE-008, RULE-009, RULE-010, RULE-011  
**Related Requirements:** BR-003, BR-005; FR-011 – FR-016; SR-011 – SR-015

## Business Question

What document requirements apply to the simulated application?

For portfolio purposes, assume the following illustrative document types:

- Identity Proof
- Income Proof
- Bank Statement
- Employment Proof

| Condition / Document | R1 | R2 | R3 | R4 |
|---|---:|---:|---:|---:|
| Salaried applicant? | Y | Y | N | N |
| Self-employed applicant? | N | N | Y | Y |
| Enhanced financial review required? | N | Y | N | Y |
| **Identity Proof required** | Y | Y | Y | Y |
| **Income Proof required** | Y | Y | Y | Y |
| **Bank Statement required** | N | Y | Y | Y |
| **Employment Proof required** | Y | Y | N | N |

### BA Note

These document requirements are intentionally simulated. A real financial institution would determine required documents through approved product and credit policy.

---

# 7. DT-004 — Document Completeness Decision

**Related Rules:** RULE-009, RULE-010, RULE-011  
**Related Requirements:** BR-003; FR-013 – FR-016; SR-013 – SR-015

## Business Question

Can the application be classified as `Documents Complete`?

| Condition / Action | R1 | R2 | R3 | R4 |
|---|---:|---:|---:|---:|
| All mandatory documents received? | Y | N | Y | Y |
| All received mandatory documents acceptable? | Y | - | N | Y |
| Replacement required? | N | - | Y | N |
| Outstanding mandatory requirement? | N | Y | Y | N |
| **Documents Complete** | Y | N | N | Y |
| **Documents Pending** | N | Y | Y | N |

### Interpretation

A rejected mandatory document does not satisfy the requirement until an acceptable replacement or approved resolution exists.

---

# 8. DT-005 — Illustrative Product Eligibility

**Related Rules:** RULE-015, RULE-016, RULE-017, RULE-018, RULE-019  
**Related Requirements:** BR-005; FR-021 – FR-024; SR-016 – SR-020

## Business Question

How should the application be classified after the simulated eligibility evaluation?

For this portfolio case study, assume:

- Configured minimum applicant age = 18
- Requested amount must fall within the configured product range
- Product-specific eligibility requirements must be satisfied

These values are illustrative only.

| Condition / Outcome | R1 | R2 | R3 | R4 | R5 |
|---|---:|---:|---:|---:|---:|
| Minimum age satisfied? | Y | N | Y | Y | Y |
| Loan amount within product range? | Y | - | N | Y | Y |
| Product eligibility satisfied? | Y | - | - | N | Y |
| Review exception triggered? | N | N | N | N | Y |
| **PASS** | Y | N | N | N | N |
| **HARD_STOP** | N | Y | Y | Y | N |
| **REVIEW_REQUIRED** | N | N | N | N | Y |

### Important

This table demonstrates BA decision modeling. It is not intended to represent real lending eligibility criteria.

---

# 9. DT-006 — Hard Stop vs Review Exception

**Related Rules:** RULE-018, RULE-019, RULE-022, RULE-024  
**Related Requirements:** BR-005, BR-006, BR-007; FR-023, FR-024, FR-027, FR-033; SR-018, SR-020, SR-023, SR-030

## Business Question

What should happen when a rule or risk condition fails?

| Condition / Action | R1 | R2 | R3 | R4 |
|---|---:|---:|---:|---:|
| Rule failed? | N | Y | Y | Y |
| Failure classified as Hard Stop? | - | Y | N | N |
| Failure classified as Review Exception? | - | N | Y | N |
| Technical evaluation error? | N | N | N | Y |
| **Continue normal processing** | Y | N | N | N |
| **Prevent normal progression** | N | Y | N | N |
| **Create human-review exception** | N | N | Y | Y |
| **Record evaluation outcome** | Y | Y | Y | Y |

### BA Principle

A rule failure is not automatically equivalent to a loan decline.

The rule determines processing behavior; the authorized human lending process determines the final lending outcome.

---

# 10. DT-007 — Exception Routing Decision

**Related Rules:** RULE-006, RULE-014, RULE-019, RULE-022, RULE-023, RULE-024, RULE-025  
**Related Requirements:** BR-007, BR-008; FR-029 – FR-037; SR-025 – SR-034

## Business Question

Which team should receive an identified exception?

| Exception Source | Primary Routing |
|---|---|
| KYC / Identity Verification | KYC / Verification Team |
| Missing / Rejected Document | Loan Operations |
| Application Data Validation | Loan Operations |
| Eligibility Review Exception | Loan Operations / Authorized Business Reviewer |
| Credit / Risk Exception | Credit / Risk Team |
| Underwriting Information Request | Underwriting / Loan Operations |
| Approval Condition | Documentation / Loan Operations |
| Disbursement Readiness | Disbursement Operations |
| AI Uncertainty / AI Review Issue | Authorized Human Reviewer |

### Routing Principle

The assigned team may vary based on the final RACI and workflow design.

---

# 11. DT-008 — Blocking Exception Decision

**Related Rules:** RULE-024  
**Related Requirements:** BR-007, BR-015; FR-033; SR-030

## Business Question

Can processing continue when an exception exists?

| Condition / Action | R1 | R2 | R3 | R4 |
|---|---:|---:|---:|---:|
| Open exception exists? | N | Y | Y | Y |
| Exception is Blocking? | - | N | Y | Y |
| Blocking exception resolved? | - | - | N | Y |
| **Allow applicable progression** | Y | Y | N | Y |
| **Prevent applicable progression** | N | N | Y | N |

---

# 12. DT-009 — Underwriting Readiness

**Related Rules:** RULE-020, RULE-022, RULE-028, RULE-029  
**Related Requirements:** BR-006, BR-007, BR-010; FR-025 – FR-028, FR-042 – FR-045; SR-021 – SR-024, SR-039 – SR-042

## Business Question

Is the application ready for completion of underwriting review?

| Condition / Action | R1 | R2 | R3 | R4 | R5 |
|---|---:|---:|---:|---:|---:|
| Required application data available? | Y | N | Y | Y | Y |
| Required KYC outcome available? | Y | Y | N | Y | Y |
| Required documents available? | Y | Y | Y | N | Y |
| Required credit/risk information available? | Y | Y | Y | Y | N |
| **Proceed with complete underwriting review** | Y | N | N | N | N |
| **Request / resolve missing information** | N | Y | Y | Y | Y |

### Note

AI-assisted review may support the underwriter, but it does not replace required source information or human underwriting responsibility.

---

# 13. DT-010 — Human Lending Decision Authorization

**Related Rules:** RULE-030, RULE-031, RULE-038  
**Related Requirements:** BR-011, BR-012, BR-021; FR-046 – FR-049, FR-088; SR-043 – SR-046, SR-084, SR-093

## Business Question

May the final lending decision be recorded?

| Condition / Action | R1 | R2 | R3 | R4 |
|---|---:|---:|---:|---:|
| Actor is an authorized human lending approver? | Y | N | N | Y |
| Actor is AI service? | N | N | Y | N |
| Required decision information complete? | Y | Y | Y | N |
| **Allow final lending decision** | Y | N | N | N |
| **Reject decision action** | N | Y | Y | Y |

### Mandatory Control

AI shall never independently execute final approval or decline.

---

# 14. DT-011 — Approval Condition Resolution

**Related Rules:** RULE-032, RULE-033, RULE-034  
**Related Requirements:** BR-013, BR-015; FR-050 – FR-053; SR-047 – SR-051

## Business Question

Has an approval condition been validly resolved?

| Condition / Action | R1 | R2 | R3 | R4 |
|---|---:|---:|---:|---:|
| Condition satisfied? | Y | N | N | N |
| Waiver requested? | N | Y | Y | N |
| Waiver approved by authorized user? | - | Y | N | - |
| Condition still outstanding? | N | N | Y | Y |
| **Condition resolved** | Y | Y | N | N |
| **Condition remains open** | N | N | Y | Y |

---

# 15. DT-012 — Disbursement Readiness Decision

**Related Rules:** RULE-034, RULE-035, RULE-036, RULE-037  
**Related Requirements:** BR-013, BR-014, BR-015; FR-053 – FR-060; SR-051 – SR-057

## Business Question

Can the approved application proceed to simulated disbursement?

| Condition / Action | R1 | R2 | R3 | R4 | R5 | R6 |
|---|---:|---:|---:|---:|---:|---:|
| Human lending decision = Approved? | Y | N | Y | Y | Y | Y |
| Mandatory approval conditions resolved? | Y | - | N | Y | Y | Y |
| Mandatory loan documentation complete? | Y | - | - | N | Y | Y |
| Blocking exceptions resolved? | Y | - | - | - | N | Y |
| Other readiness validations passed? | Y | - | - | - | - | N |
| **Ready for Disbursement** | Y | N | N | N | N | N |
| **Block Disbursement** | N | Y | Y | Y | Y | Y |

### Mandatory Control

No single AI output can override any failed disbursement-readiness condition.

---

# 16. DT-013 — Application Closure Decision

**Related Requirements:** BR-016; FR-061 – FR-063; SR-058, SR-059

## Business Question

What closure path applies?

| Application Outcome | Disbursement Completed | Closure / Handoff Action |
|---|---:|---|
| Approved | Y | Close origination and perform downstream handoff |
| Approved | N | Remain in applicable pre-disbursement workflow |
| Declined | N | Close as Declined |
| Withdrawn | N | Close as Withdrawn |
| Cancelled | N | Close as Cancelled |

---

# 17. DT-014 — AI Review Routing

**Related Rules:** RULE-038, RULE-039, RULE-040  
**Related Requirements:** BR-020, BR-021, BR-022; FR-078 – FR-092; SR-087 – SR-095

## Business Question

How should AI-assisted review output be handled?

| Condition / Action | R1 | R2 | R3 | R4 |
|---|---:|---:|---:|---:|
| AI review completed successfully? | Y | Y | N | Y |
| Output requires human review? | N | Y | - | Y |
| AI service unavailable/error? | N | N | Y | N |
| AI output contains uncertainty indicator? | N | N | - | Y |
| **Present AI output to reviewer** | Y | Y | N | Y |
| **Flag for explicit human review** | N | Y | N | Y |
| **Use human fallback path** | N | N | Y | N |
| **Allow AI to make final lending decision** | N | N | N | N |

---

# 18. DT-015 — Human Response to AI Observation

**Related Rules:** RULE-039, RULE-040  
**Related Requirements:** BR-021, BR-022; FR-085 – FR-092; SR-091 – SR-095

## Business Question

What actions may an authorized human reviewer take on an AI observation?

| Reviewer Action | Permitted | Audit Response |
|---|---:|---|
| Accept AI observation | Y | Record reviewer action |
| Reject AI observation | Y | Record reviewer action |
| Correct AI observation | Y | Record corrected information / action |
| Disregard AI observation | Y | Record reviewer action where required |
| Request additional human investigation | Y | Create / route review activity |
| Allow AI to execute final approval | N | Reject action |
| Allow AI to execute final decline | N | Reject action |

---

# 19. Decision Table Traceability Summary

| Decision Table | Primary Rules |
|---|---|
| DT-001 | RULE-001, RULE-003, RULE-004 |
| DT-002 | RULE-005 – RULE-007 |
| DT-003 | RULE-008 – RULE-011 |
| DT-004 | RULE-009 – RULE-011 |
| DT-005 | RULE-015 – RULE-019 |
| DT-006 | RULE-018, RULE-019, RULE-022, RULE-024 |
| DT-007 | RULE-006, RULE-014, RULE-019, RULE-022 – RULE-025 |
| DT-008 | RULE-024 |
| DT-009 | RULE-020, RULE-022, RULE-028, RULE-029 |
| DT-010 | RULE-030, RULE-031, RULE-038 |
| DT-011 | RULE-032 – RULE-034 |
| DT-012 | RULE-034 – RULE-037 |
| DT-013 | Application closure requirements |
| DT-014 | RULE-038 – RULE-040 |
| DT-015 | RULE-039, RULE-040 |

---

# 20. Example End-to-End Traceability

A document-completeness requirement can now be traced as:

`PP-02 → GAP-002 → IMP-002 → BR-003 → FR-014 / FR-016 → SR-014 → RULE-009 / RULE-011 → DT-004`

A disbursement-control requirement can be traced as:

`PP-11 → GAP-011 → IMP-011 → BR-013 / BR-015 → FR-053 / FR-057 / FR-058 → SR-051 / SR-054 / SR-055 → RULE-034 / RULE-036 / RULE-037 → DT-012`

AI decision control can be traced as:

`BR-011 / BR-021 → FR-048 / FR-088 → SR-045 / SR-093 → RULE-038 → DT-010 / DT-014`

---

# 21. How Decision Tables Support Development

Decision tables provide developers with explicit expected behavior.

For example:

Instead of implementing a vague requirement such as:

> Validate whether the loan is ready for disbursement.

The development team can use `DT-012` to understand the specific conditions that must be evaluated before the application can become `Ready for Disbursement`.

---

# 22. How Decision Tables Support Testing

Decision-table columns can be converted directly into test scenarios.

For example, `DT-012 R3` can later produce a test scenario:

**Given**

- Human approval exists
- Mandatory approval condition remains unresolved

**When**

The system evaluates disbursement readiness

**Then**

The system shall:

- Not assign `Ready for Disbursement`
- Prevent disbursement initiation
- Identify the unresolved condition

This will later become formal acceptance criteria and UAT coverage.

---

# 23. BA Validation Checklist

The Business Analyst should validate each decision table by confirming:

- Conditions are complete.
- Conditions do not conflict.
- Outcomes are unambiguous.
- Exception paths are represented.
- Authorization requirements are represented.
- Business rules are correctly referenced.
- Requirements are traceable.
- Each important scenario is testable.
- AI does not override deterministic controls.
- Human lending authority remains explicit.

---

# 24. Decision Table Baseline

`DT-001` through `DT-015` represent the initial decision-table baseline for this simulated portfolio project.

Future changes to business rules shall be assessed for their impact on applicable decision tables and downstream artifacts.

---

# 25. Downstream Artifacts

These decision tables will support:

- Status Catalogue
- Status Transition Matrix
- User Stories
- Acceptance Criteria
- Data Validation
- SQL Validation Queries
- API Requirements
- Test Scenarios
- UAT Test Cases
- Requirements Traceability Matrix
- AI Evaluation Scenarios

---

# 26. Conclusion

The Decision Tables convert selected loan origination business rules into structured, testable decision logic.

They provide a common reference for business stakeholders, Business Analysts, developers, QA teams, and UAT participants while maintaining traceability from business problems through system behavior.

The AI-assisted review capability remains advisory. It cannot override deterministic business controls or independently approve or decline a loan application.

---

## Disclaimer

These decision tables are simulated Business Analyst portfolio artifacts.

All lending scenarios, eligibility conditions, document requirements, workflow rules, risk scenarios, and decision logic are illustrative and do not represent the actual lending policies, underwriting criteria, credit policies, or regulatory interpretation of any financial institution.
