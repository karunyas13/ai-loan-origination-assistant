# Business Rules Catalogue

## AI-Powered Loan Origination Requirements & Risk Assistant

---

# 1. Document Purpose

This Business Rules Catalogue defines the business rules used within the simulated end-to-end loan origination process.

The catalogue translates approved business, functional, and system requirements into explicit decision and processing rules.

The rules cover:

- Application capture
- KYC / identity verification
- Document management
- Data validation
- Eligibility
- Credit / risk review
- Exception management
- Workflow
- Underwriting
- Lending decisions
- Approval conditions
- Documentation
- Disbursement
- Closure
- AI-assisted review
- Audit and traceability

These rules are illustrative portfolio examples and do not represent the lending policy of any real financial institution.

---

# 2. Business Rule Identification

Business rules use the identifier:

`RULE-001`, `RULE-002`, `RULE-003`, etc.

These IDs shall remain stable across downstream project artifacts.

Each rule contains:

- Rule ID
- Rule Name
- Rule Statement
- Rule Type
- Related Requirement
- Outcome / Action
- Priority

---

# 3. Rule Types

| Rule Type | Description |
|---|---|
| Validation | Validates data or required information |
| Eligibility | Determines whether defined eligibility criteria are satisfied |
| Document | Controls document requirements |
| Workflow | Controls routing or lifecycle progression |
| Exception | Determines when human review is required |
| Authorization | Restricts controlled actions |
| Decision Control | Controls lending-decision behavior |
| Disbursement Control | Controls readiness for disbursement |
| AI Control | Defines permitted AI behavior |
| Audit Control | Defines traceability requirements |

---

# 4. Application Rules

## RULE-001 — Mandatory Application Information

**Type:** Validation  
**Related Requirements:** BR-001, BR-004; FR-003, FR-005; SR-004, SR-005  
**Priority:** Must Have

### Rule

An application shall not be submitted unless all information classified as mandatory for submission has been provided.

### Outcome

If mandatory information is missing:

- Submission is prevented.
- Missing information is identified to the user.
- Application remains in an editable pre-submission state.

---

## RULE-002 — Unique Application Identifier

**Type:** Validation  
**Related Requirements:** BR-001; FR-001; SR-001  
**Priority:** Must Have

### Rule

Every loan application shall have one unique Application ID.

### Outcome

Duplicate Application IDs shall not be permitted.

---

## RULE-003 — Draft Application

**Type:** Workflow  
**Related Requirements:** BR-001; FR-002; SR-003  
**Priority:** Must Have

### Rule

An application that has been created but has not been successfully submitted may remain in `Draft` status.

---

## RULE-004 — Application Submission

**Type:** Workflow  
**Related Requirements:** BR-001; FR-006; SR-005  
**Priority:** Must Have

### Rule

Only an application satisfying mandatory submission validations may transition from `Draft` to `Submitted`.

---

# 5. KYC Rules

## RULE-005 — KYC Requirement

**Type:** Validation / Workflow  
**Related Requirements:** BR-002; FR-007, FR-008; SR-007, SR-008  
**Priority:** Must Have

### Rule

An application shall undergo the required KYC / identity-verification process before proceeding to lifecycle stages that require verified identity.

---

## RULE-006 — KYC Manual Review

**Type:** Exception  
**Related Requirements:** BR-002, BR-007; FR-009; SR-009  
**Priority:** Must Have

### Rule

A KYC outcome classified as requiring manual review shall create or trigger an appropriate review workflow.

### Outcome

The application shall be routed to an authorized reviewer.

---

## RULE-007 — Failed KYC Control

**Type:** Workflow / Exception  
**Related Requirements:** BR-002, BR-007; FR-008, FR-009; SR-008, SR-009  
**Priority:** Must Have

### Rule

A failed KYC result shall not be treated as successfully verified.

Any further processing shall follow the defined exception or resolution path.

---

# 6. Document Rules

## RULE-008 — Required Document Checklist

**Type:** Document  
**Related Requirements:** BR-003, BR-005; FR-011; SR-011  
**Priority:** Must Have

### Rule

Required documents shall be determined using applicable application characteristics and approved business rules.

---

## RULE-009 — Missing Mandatory Document

**Type:** Document / Validation  
**Related Requirements:** BR-003; FR-014, FR-016; SR-014  
**Priority:** Must Have

### Rule

A mandatory document that has not been received shall be classified as outstanding.

### Outcome

The application shall not be considered document-complete.

---

## RULE-010 — Rejected Document

**Type:** Document  
**Related Requirements:** BR-003; FR-015; SR-013, SR-015  
**Priority:** Must Have

### Rule

A rejected document shall not satisfy the applicable document requirement.

### Outcome

A valid replacement or approved resolution shall be required.

---

## RULE-011 — Document Completeness

**Type:** Document / Workflow  
**Related Requirements:** BR-003; FR-016; SR-014  
**Priority:** Must Have

### Rule

An application may be classified as `Documents Complete` only when all mandatory document requirements applicable at that stage are satisfied.

---

# 7. Data Validation Rules

## RULE-012 — Required Data Format

**Type:** Validation  
**Related Requirements:** BR-004; FR-004, FR-017; SR-004  
**Priority:** Must Have

### Rule

Application data shall satisfy the defined data type, format, permitted-value, and range requirements.

---

## RULE-013 — Cross-Field Consistency

**Type:** Validation  
**Related Requirements:** BR-004; FR-018; SR-004  
**Priority:** Must Have

### Rule

Related application data elements shall satisfy defined cross-field consistency rules.

### Example

Where two related values conflict, the application shall be flagged for correction or review.

Detailed field-level logic will be defined in the Data Dictionary and validation specifications.

---

## RULE-014 — Validation Failure Handling

**Type:** Validation / Exception  
**Related Requirements:** BR-004, BR-007; FR-019, FR-020; SR-017, SR-020  
**Priority:** Must Have

### Rule

A failed validation shall be recorded with sufficient information to identify the failed validation and required resolution.

---

# 8. Eligibility Rules

> The following eligibility rules are intentionally illustrative and do not represent real lending policy.

## RULE-015 — Applicant Age Validation

**Type:** Eligibility  
**Related Requirements:** BR-005; FR-021, FR-022; SR-016, SR-017  
**Priority:** Must Have

### Rule

The applicant shall satisfy the minimum age requirement configured for the simulated loan product.

### Outcome

Failure shall result in the outcome defined by the associated decision table.

---

## RULE-016 — Loan Amount Range

**Type:** Eligibility  
**Related Requirements:** BR-005; FR-021, FR-022; SR-016, SR-017  
**Priority:** Must Have

### Rule

The requested loan amount shall fall within the configured minimum and maximum values for the selected simulated loan product.

---

## RULE-017 — Product Eligibility

**Type:** Eligibility  
**Related Requirements:** BR-005; FR-021; SR-016  
**Priority:** Must Have

### Rule

The applicant and application shall satisfy the configured eligibility requirements for the selected product.

---

## RULE-018 — Eligibility Hard Stop

**Type:** Eligibility / Workflow  
**Related Requirements:** BR-005; FR-023; SR-018  
**Priority:** Must Have

### Rule

An eligibility rule classified as a `Hard Stop` shall prevent progression through the normal approval workflow until the application reaches an appropriate terminal or resolution path.

---

## RULE-019 — Eligibility Review Exception

**Type:** Eligibility / Exception  
**Related Requirements:** BR-005, BR-007; FR-023, FR-024; SR-018, SR-020  
**Priority:** Must Have

### Rule

An eligibility result classified as `Review Exception` shall be routed to an authorized human reviewer rather than being automatically treated as an approval or decline.

---

# 9. Credit / Risk Rules

## RULE-020 — Credit / Risk Review Requirement

**Type:** Workflow  
**Related Requirements:** BR-006; FR-025, FR-028; SR-021, SR-024  
**Priority:** Must Have

### Rule

Applications requiring credit / risk assessment shall complete the defined credit / risk review before final lending decision.

---

## RULE-021 — Risk Indicator Recording

**Type:** Validation / Audit  
**Related Requirements:** BR-006; FR-026; SR-022  
**Priority:** Must Have

### Rule

Applicable risk indicators shall be recorded against the relevant application.

---

## RULE-022 — Risk Exception

**Type:** Exception  
**Related Requirements:** BR-006, BR-007; FR-027; SR-023  
**Priority:** Must Have

### Rule

A risk condition classified as requiring human review shall create or trigger a review exception.

---

# 10. Exception Management Rules

## RULE-023 — Unique Exception Identifier

**Type:** Exception / Audit  
**Related Requirements:** BR-007; FR-029; SR-025  
**Priority:** Must Have

### Rule

Every tracked exception shall have a unique Exception ID.

---

## RULE-024 — Blocking Exception

**Type:** Exception / Workflow  
**Related Requirements:** BR-007, BR-015; FR-033; SR-030  
**Priority:** Must Have

### Rule

An unresolved exception classified as `Blocking` shall prevent progression through the lifecycle stage controlled by that exception.

---

## RULE-025 — Exception Resolution

**Type:** Exception / Audit  
**Related Requirements:** BR-007, BR-018; FR-032; SR-029  
**Priority:** Must Have

### Rule

A tracked exception may be considered resolved only after an authorized resolution has been recorded.

The resolution shall include appropriate reviewer and timestamp information.

---

# 11. Workflow and Status Rules

## RULE-026 — Permitted Status Transition

**Type:** Workflow  
**Related Requirements:** BR-009; FR-039; SR-036  
**Priority:** Must Have

### Rule

An application may transition only between status values permitted by the approved Status Transition Matrix.

---

## RULE-027 — Status History

**Type:** Workflow / Audit  
**Related Requirements:** BR-009, BR-018; FR-040; SR-037  
**Priority:** Must Have

### Rule

Every controlled application-status change shall retain sufficient history to identify:

- Previous status
- New status
- Timestamp
- Actor / trigger
- Reason where applicable

---

# 12. Underwriting Rules

## RULE-028 — Underwriting Information Availability

**Type:** Workflow  
**Related Requirements:** BR-010; FR-042; SR-039  
**Priority:** Must Have

### Rule

The underwriter shall be provided with the applicable information required to perform the underwriting review.

This may include:

- Application information
- KYC outcome
- Document status
- Validation results
- Eligibility results
- Business-rule results
- Credit / risk information
- Exceptions
- AI-assisted observations

---

## RULE-029 — Underwriting Completion

**Type:** Workflow  
**Related Requirements:** BR-010; FR-043, FR-045; SR-040, SR-042  
**Priority:** Must Have

### Rule

An underwriting review shall be considered complete only after the required underwriting assessment has been recorded by an authorized user.

---

# 13. Lending Decision Rules

## RULE-030 — Human Lending Decision

**Type:** Authorization / Decision Control  
**Related Requirements:** BR-011, BR-012; FR-046, FR-047; SR-043, SR-044  
**Priority:** Must Have

### Rule

Final loan approval or decline shall be performed only by an appropriately authorized human lending decision-maker.

---

## RULE-031 — Decision Reason

**Type:** Decision Control / Audit  
**Related Requirements:** BR-012, BR-018; FR-047, FR-049; SR-044, SR-046  
**Priority:** Must Have

### Rule

A final lending decision shall retain an applicable decision reason and decision-authority information.

---

# 14. Approval Condition Rules

## RULE-032 — Approval Condition Tracking

**Type:** Workflow  
**Related Requirements:** BR-013; FR-050, FR-051; SR-047, SR-048, SR-049  
**Priority:** Must Have

### Rule

Conditions attached to an approved application shall be individually tracked until satisfied, waived by authorized personnel, or otherwise resolved.

---

## RULE-033 — Approval Condition Waiver

**Type:** Authorization  
**Related Requirements:** BR-013; FR-052; SR-050, SR-085  
**Priority:** Must Have

### Rule

A controlled approval condition may be waived only by an appropriately authorized human user.

---

## RULE-034 — Blocking Approval Condition

**Type:** Disbursement Control  
**Related Requirements:** BR-013, BR-015; FR-053; SR-051  
**Priority:** Must Have

### Rule

An unresolved mandatory blocking approval condition shall prevent the application from becoming ready for disbursement.

---

# 15. Documentation and Disbursement Rules

## RULE-035 — Documentation Completion

**Type:** Disbursement Control  
**Related Requirements:** BR-014, BR-015; FR-056; SR-053  
**Priority:** Must Have

### Rule

Mandatory loan-documentation requirements shall be complete before the application can satisfy documentation-related disbursement-readiness criteria.

---

## RULE-036 — Disbursement Readiness

**Type:** Disbursement Control  
**Related Requirements:** BR-015; FR-057, FR-058; SR-054, SR-055  
**Priority:** Must Have

### Rule

An application may become `Ready for Disbursement` only when all mandatory disbursement-readiness controls are satisfied.

These controls may include:

- Final decision is Approved
- Required approval conditions are satisfied or validly waived
- Mandatory documentation is complete
- No applicable blocking exception remains unresolved
- Required readiness validations have passed

---

## RULE-037 — Disbursement Restriction

**Type:** Disbursement Control  
**Related Requirements:** BR-015; FR-058, FR-059; SR-055, SR-056  
**Priority:** Must Have

### Rule

The system shall not initiate simulated disbursement for an application that has not satisfied the defined disbursement-readiness requirements.

---

# 16. AI Business Rules

## RULE-038 — AI Decision Restriction

**Type:** AI Control / Authorization  
**Related Requirements:** BR-011, BR-020, BR-021; FR-048, FR-088; SR-045, SR-087, SR-093  
**Priority:** Must Have

### Rule

The AI-assisted review capability shall not autonomously approve or decline a loan application.

AI shall operate only as a decision-support capability.

---

## RULE-039 — Human Review of AI Output

**Type:** AI Control  
**Related Requirements:** BR-021; FR-085, FR-086, FR-087; SR-091, SR-092  
**Priority:** Must Have

### Rule

AI-generated observations used in the review process shall remain subject to authorized human review.

The reviewer may:

- Accept
- Reject
- Correct
- Disregard

the applicable AI observation.

Uncertain output shall be routed or flagged for human review.

---

## RULE-040 — AI Traceability and Fallback

**Type:** AI Control / Audit  
**Related Requirements:** BR-021, BR-022; FR-089, FR-090, FR-091, FR-092; SR-094, SR-095  
**Priority:** Must Have

### Rule

Relevant AI review activity and applicable human responses shall be traceable.

AI-service unavailability shall not remove the approved human-processing path.

---

# 17. Rule Outcome Classification

Business-rule execution may produce outcomes such as:

| Outcome | Meaning |
|---|---|
| PASS | Rule requirements satisfied |
| FAIL | Rule requirements not satisfied |
| HARD_STOP | Normal workflow progression prohibited |
| REVIEW_REQUIRED | Authorized human review required |
| NOT_APPLICABLE | Rule does not apply to the application |
| ERROR | Rule could not be successfully evaluated |

The exact permitted outcome for each rule will be refined in the Decision Tables.

---

# 18. Rule Priority

| Priority | Meaning |
|---|---|
| Must Have | Required for the core process or control framework |
| Should Have | Important but not required for the minimum core flow |
| Could Have | Enhancement opportunity |

---

# 19. Rule Ownership

In a real implementation, business-rule ownership would be assigned to appropriate business and control stakeholders.

Illustrative ownership may include:

| Rule Area | Potential Owner |
|---|---|
| Application | Product / Loan Operations |
| KYC | KYC / Compliance |
| Documents | Loan Operations |
| Eligibility | Product / Credit Policy |
| Credit / Risk | Credit / Risk |
| Exceptions | Operations / Risk |
| Underwriting | Underwriting |
| Lending Decision | Lending Authority |
| Approval Conditions | Underwriting / Lending Operations |
| Disbursement | Disbursement Operations |
| AI Controls | Business, Risk, Compliance and Technology |

The Business Analyst facilitates rule discovery, clarification, documentation, traceability, and validation but does not independently invent or approve real lending policy.

---

# 20. Rule Traceability Examples

Example 1:

`PP-01 → GAP-001 → IMP-001 → BR-001 → FR-003 → SR-004 / SR-005 → RULE-001`

Example 2:

`PP-02 → GAP-002 → IMP-002 → BR-003 → FR-014 / FR-016 → SR-014 → RULE-009 / RULE-011`

Example 3:

`PP-04 → GAP-004 → IMP-004 → BR-005 → FR-021 / FR-023 → SR-016 / SR-018 → RULE-015 – RULE-019`

Example 4:

`PP-11 → GAP-011 → IMP-011 → BR-013 / BR-015 → FR-053 / FR-057 / FR-058 → SR-051 / SR-054 / SR-055 → RULE-034 / RULE-036 / RULE-037`

Example 5:

`BR-011 → FR-048 / FR-088 → SR-045 / SR-093 → RULE-038`

---

# 21. Rules Requiring Decision Tables

The following rules are good candidates for detailed decision tables:

- RULE-008 — Required Document Checklist
- RULE-015 — Applicant Age Validation
- RULE-016 — Loan Amount Range
- RULE-017 — Product Eligibility
- RULE-018 — Eligibility Hard Stop
- RULE-019 — Eligibility Review Exception
- RULE-022 — Risk Exception
- RULE-024 — Blocking Exception
- RULE-034 — Blocking Approval Condition
- RULE-036 — Disbursement Readiness

Decision tables will define combinations of conditions and expected actions without changing the permanent Rule IDs.

---

# 22. Rules Relevant to AI / RAG

Not every rule should be delegated to AI.

Deterministic rules such as mandatory validations, status-transition controls, authorization controls, and disbursement blocking should remain system-enforced controls.

The AI assistant may retrieve approved rule information to help a human reviewer understand why a rule or exception is relevant.

Example:

`Application → Rule Engine → RULE-009 failed → Missing Document Exception`

The AI assistant may then retrieve `RULE-009` and provide a reviewer-oriented explanation such as:

> A mandatory document is currently outstanding. The application cannot be considered document-complete until the requirement is resolved.

The AI explanation does not replace the deterministic rule-engine result.

---

# 23. Business Rule Change Management

A proposed rule change should be evaluated for impact on applicable:

- Business Requirements
- Functional Requirements
- System Requirements
- Process flows
- Decision tables
- User stories
- Acceptance criteria
- Data requirements
- APIs
- SQL logic
- Test scenarios
- UAT cases
- Reporting
- AI retrieval knowledge
- Training / operating procedures

The RTM will be used to identify affected downstream artifacts.

---

# 24. Business Rule Validation

Business rules should be reviewed for:

- Clear ownership
- Clear trigger
- Defined inputs
- Unambiguous conditions
- Defined outcome
- Exception handling
- Testability
- Traceability
- Consistency with other rules
- Appropriate authorization controls

---

# 25. Business Rules Baseline

`RULE-001` through `RULE-040` represent the initial Business Rules Catalogue baseline for this simulated portfolio project.

Future changes shall preserve traceability and use controlled change management.

---

# 26. Downstream Artifacts

This Business Rules Catalogue will provide input into:

- Decision Tables
- Decision Trees
- Status Catalogue
- Status Transition Matrix
- User Stories
- Acceptance Criteria
- Data Dictionary
- SQL Validation Rules
- API Requirements
- Test Scenarios
- UAT Test Cases
- Requirements Traceability Matrix
- AI / RAG Knowledge Design

---

# 27. Conclusion

The Business Rules Catalogue converts the project's requirements into explicit and traceable processing, validation, eligibility, workflow, authorization, disbursement, and AI-control rules.

It establishes a controlled business-logic baseline that can be used consistently across system design, development, testing, reporting, and AI-assisted review.

Final loan approval or decline remains under the authority of appropriately authorized human lending personnel.

---

## Disclaimer

This Business Rules Catalogue is a simulated Business Analyst portfolio artifact.

All eligibility rules, document rules, workflow controls, lending scenarios, risk examples, and AI controls are illustrative and do not represent the actual lending policies, credit criteria, underwriting standards, or regulatory interpretation of any financial institution.
