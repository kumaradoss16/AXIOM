# AXIOM - Engineering Standards Specification

**Project:** AXIOM  
**Document ID:** AX-SPEC-003  
**Document Type:** Engineering Standards and Quality Governance Specification  
**Version:** 0.1.0  
**Status:** Proposed - Pending Approval  
**Applies To:** All AXIOM skills, reviewers, engineering artifacts, and evaluation workflows  
**Classification:** Foundational Engineering Standard  
**Implementation Status:** Not Started

---

# 1. Executive Definition

## 1.1 Purpose

The AXIOM Engineering Standards Specification defines the engineering quality requirements, evaluation criteria, evidence expectations, and compliance rules that govern engineering activities performed through AXIOM.

Its primary purpose is to establish a consistent engineering quality baseline across:

- Requirements engineering.
- Software architecture.
- Technical specifications.
- Security design.
- Database design.
- API design.
- Software reliability.
- Testing and verification.
- Code quality.
- Technical documentation.

These standards provide the authoritative evaluation criteria used by AXIOM skills and independent reviewers.

## 1.2 Core Objective

Ensure that engineering outputs produced through AXIOM are:

1. Technically defensible.
2. Consistent with approved requirements.
3. Supported by evidence.
4. Explicit about assumptions.
5. Verifiable through defined criteria.
6. Maintainable.
7. Secure by design.
8. Traceable across the engineering lifecycle.

## 1.3 Fundamental Principle

> Engineering quality must be evaluated against explicit, measurable criteria rather than subjective judgments or the apparent sophistication of an AI-generated artifact.

A document is not high quality simply because it is lengthy, detailed, or professionally formatted.

Its quality depends on correctness, completeness, consistency, feasibility, evidence, and verifiability.

---

# 2. Standards Architecture

## 2.1 Standards Organizational Model

AXIOM Engineering Standards are organized into four levels.

| Level | Classification | Responsibility |
|---|---|---|
| Level 1 | Foundational Standards | Define universal engineering requirements |
| Level 2 | Domain Standards | Define quality requirements for specific engineering disciplines |
| Level 3 | Technical Standards | Define detailed technology or implementation-specific criteria |
| Level 4 | Evaluation Standards | Define how compliance and quality are measured |

### Level 1 - Foundational Standards

Apply across the AXIOM framework.

Examples:

- Evidence and Traceability.
- Engineering Decision Quality.
- Scope and Requirement Consistency.
- Security and Safety.
- Documentation Integrity.

### Level 2 - Domain Standards

Apply to specific engineering activities.

Examples:

- Requirements Quality.
- Architecture Quality.
- Specification Quality.
- Security Design.
- Database Design.
- API Design.
- Reliability Engineering.
- Testing Strategy.

### Level 3 - Technical Standards

Provide technology-specific guidance.

Examples:

- Python Engineering Standard.
- JavaScript Engineering Standard.
- FastAPI Engineering Standard.
- PostgreSQL Design Standard.
- REST API Implementation Standard.
- Linux Deployment Standard.

These standards should be optional and activated only when relevant.

### Level 4 - Evaluation Standards

Define:

- Compliance checks.
- Quality dimensions.
- Evidence requirements.
- Severity calibration.
- Acceptance thresholds.
- Evaluation datasets.
- Regression requirements.

---

# 3. Standards Governance and Classification

## 3.1 Mandatory and Recommended Requirements

Every standard requirement must have an explicit classification.

| Classification | Meaning |
|---|---|
| MUST | Mandatory compliance requirement |
| MUST NOT | Prohibited engineering behavior |
| SHOULD | Recommended engineering practice |
| SHOULD NOT | Discouraged practice |
| MAY | Optional capability |

A mandatory requirement cannot be silently ignored because a reviewer prefers an alternative approach.

If a mandatory requirement cannot be satisfied, the responsible party must document the conflict and seek an authorized exception where permitted.

## 3.2 Applicability Classification

Each requirement must also declare its applicability.

- `UNIVERSAL`: Applies to all relevant engineering artifacts.
- `CONDITIONAL`: Applies when a defined condition is met.
- `CONTEXTUAL`: Depends on project-specific constraints.
- `NOT_APPLICABLE`: Does not apply to the evaluated artifact.

Reviewers must not penalize a project for failing to implement a requirement that is demonstrably not applicable.

## 3.3 Requirement Priority

Apply the following precedence when engineering requirements conflict:

1. Applicable laws, regulations, and contractual obligations.
2. Explicitly authorized project constraints.
3. Approved architecture and engineering decisions.
4. AXIOM mandatory standards.
5. AXIOM recommended practices.
6. General engineering guidance.

Conflicts must be documented and escalated when they affect correctness, security, or material project outcomes.

## 3.4 Standard Identification

Use the following identifier format:

`AX-STD-{DOMAIN}-{NUMBER}`

Examples:

- `AX-STD-CORE-001`
- `AX-STD-REQ-001`
- `AX-STD-ARCH-001`
- `AX-STD-SPEC-001`
- `AX-STD-SEC-001`
- `AX-STD-DB-001`
- `AX-STD-API-001`
- `AX-STD-REL-001`
- `AX-STD-TEST-001`
- `AX-STD-DOC-001`

Identifiers must remain stable after publication.

---

# 4. Foundational Engineering Standards

## 4.1 AX-STD-CORE-001 - Evidence and Traceability Standard

**Objective:** Ensure that engineering claims, recommendations, and decisions can be traced to supporting evidence.

### Requirements

| ID | Requirement | Classification |
|---|---|---|
| CORE-001 | Material technical claims MUST have identifiable supporting evidence or an explicit uncertainty classification. | MUST |
| CORE-002 | Observed facts MUST be distinguished from assumptions and recommendations. | MUST |
| CORE-003 | Engineering decisions SHOULD reference their originating requirements and constraints. | SHOULD |
| CORE-004 | Validation claims MUST identify the actual verification method and result. | MUST |
| CORE-005 | Unavailable evidence MUST NOT be represented as verified. | MUST |
| CORE-006 | Material assumptions MUST be documented with their potential impact. | MUST |
| CORE-007 | Review findings MUST identify affected artifacts and relevant locations where available. | MUST |

### Evidence Classification

| Classification | Definition |
|---|---|
| Observed | Directly inspected information |
| Derived | Conclusion based on observed evidence |
| Assumed | Temporary or unverified premise |
| Recommended | Proposed engineering action |
| Verified | Confirmed through an appropriate verification method |
| Unverified | Not yet validated |
| Unknown | Insufficient information |

### Evaluation Criteria

A compliant artifact must:

- Identify material assumptions.
- Provide traceable evidence for important claims.
- Avoid unsupported verification claims.
- Identify missing information.
- Preserve the distinction between existing behavior and proposed behavior.

**Acceptance condition:** No material claim presented as verified may lack an appropriate verification basis.

---

## 4.2 AX-STD-CORE-002 - Engineering Decision Quality Standard

**Objective:** Ensure that important technical decisions are reasoned, documented, and consistent with project constraints.

### Requirements

| ID | Requirement | Classification |
|---|---|---|
| DEC-001 | Material architecture and technology decisions MUST include a rationale. | MUST |
| DEC-002 | Significant alternatives SHOULD be evaluated before selecting a solution. | SHOULD |
| DEC-003 | Decisions MUST identify relevant constraints. | MUST |
| DEC-004 | Material trade-offs MUST be documented. | MUST |
| DEC-005 | Decisions MUST identify their consequences and relevant risks. | MUST |
| DEC-006 | Superseded decisions SHOULD remain traceable. | SHOULD |

### Decision Record Structure

Every material engineering decision SHOULD use an Architecture Decision Record.

Required fields:

1. Decision identifier.
2. Decision title.
3. Context.
4. Problem statement.
5. Constraints.
6. Considered alternatives.
7. Decision.
8. Rationale.
9. Consequences.
10. Risks.
11. Status.
12. Related requirements.

### Evaluation Criteria

A decision is acceptable when:

- It addresses the identified problem.
- It respects project constraints.
- Its rationale is technically defensible.
- Important alternatives and trade-offs are considered.
- Its consequences are documented.

A decision need not compare numerous alternatives when the constraints leave only one viable solution. That limitation should be recorded.

---

## 4.3 AX-STD-CORE-003 - Scope and Change Integrity Standard

**Objective:** Prevent unauthorized scope expansion and inconsistent engineering changes.

### Requirements

| ID | Requirement | Classification |
|---|---|---|
| SCOPE-001 | Engineering activities MUST operate within an explicitly defined scope. | MUST |
| SCOPE-002 | New requirements MUST be identifiable and traceable. | MUST |
| SCOPE-003 | Approved decisions MUST NOT be silently replaced. | MUST |
| SCOPE-004 | Material scope changes MUST be authorized. | MUST |
| SCOPE-005 | Deferred functionality SHOULD be documented. | SHOULD |
| SCOPE-006 | Changes affecting approved requirements SHOULD undergo impact analysis. | SHOULD |

### Evaluation Criteria

Check whether:

- Requested and delivered scope match.
- Out-of-scope functionality is clearly identified.
- Material changes have authorization.
- Existing approved decisions remain consistent.
- Dependencies and affected artifacts are identified.

---

## 4.4 AX-STD-CORE-004 - Security and Safety Baseline

**Objective:** Establish minimum security and execution safety requirements across AXIOM engineering outputs.

### Requirements

| ID | Requirement | Classification |
|---|---|---|
| SAFE-001 | Sensitive information MUST be protected. | MUST |
| SAFE-002 | External and imported content MUST be treated as untrusted. | MUST |
| SAFE-003 | Execution permissions MUST follow least privilege. | MUST |
| SAFE-004 | Destructive operations MUST require appropriate authorization. | MUST |
| SAFE-005 | Security assumptions SHOULD be documented. | SHOULD |
| SAFE-006 | Security-related limitations MUST be disclosed. | MUST |
| SAFE-007 | Credentials MUST NOT be included in generated engineering reports. | MUST |

### Evaluation Criteria

Assess:

- Access control.
- Data exposure.
- Secret handling.
- Trust boundaries.
- Authorization requirements.
- Unsafe execution behavior.
- Security assumptions.

This standard provides a baseline. Detailed application security requirements are defined by the Security Design Standard.

---

# 5. Requirements Engineering Standard

## AX-STD-REQ-001 - Requirements Quality Standard

**Objective:** Ensure that requirements are understandable, necessary, feasible, traceable, and verifiable.

## 5.1 Requirement Classification

Requirements should be divided into:

- Functional Requirements (FR).
- Non-Functional Requirements (NFR).
- Business Requirements (BR).
- Technical Constraints (CON).
- Interface Requirements (IR).
- Security Requirements (SR).
- Operational Requirements (OR).

## 5.2 Mandatory Requirements

| ID | Requirement | Classification |
|---|---|---|
| REQ-001 | Each material requirement MUST have a unique identifier. | MUST |
| REQ-002 | Each requirement MUST describe one identifiable obligation or outcome. | MUST |
| REQ-003 | Requirements MUST be understandable without relying on hidden context. | MUST |
| REQ-004 | Requirements MUST be testable or have an explicitly documented verification limitation. | MUST |
| REQ-005 | Requirements MUST NOT contradict other approved requirements. | MUST |
| REQ-006 | Functional and non-functional requirements SHOULD be distinguished. | SHOULD |
| REQ-007 | Material requirements MUST have acceptance criteria. | MUST |
| REQ-008 | Requirements SHOULD reference their origin. | SHOULD |
| REQ-009 | Requirements MUST identify relevant dependencies and constraints. | MUST |
| REQ-010 | Out-of-scope requirements SHOULD be explicitly documented. | SHOULD |

## 5.3 Requirement Quality Attributes

Evaluate every important requirement against the following attributes.

| Attribute | Evaluation question |
|---|---|
| Correctness | Does it represent a genuine stakeholder need? |
| Clarity | Can it be interpreted consistently? |
| Completeness | Is sufficient information provided? |
| Consistency | Does it conflict with another requirement? |
| Feasibility | Can it realistically be implemented? |
| Verifiability | Can compliance be demonstrated? |
| Traceability | Can its origin and downstream impact be identified? |
| Necessity | Does it contribute to an intended outcome? |

## 5.4 Acceptance Criteria

Acceptance criteria must describe observable outcomes.

Weak example:

"The application should be fast."

Improved example:

"The application should return the requested dashboard data within the approved response-time target under the defined workload and test environment."

The actual target must be agreed upon by the project owner and validated under specified conditions.

Do not invent performance targets when the project has not established them.

## 5.5 Requirements Quality Gate

An artifact passes the requirements quality gate when:

- No unresolved critical requirement contradiction exists.
- Every material requirement has an identifier.
- Material requirements have acceptance criteria.
- Ambiguities affecting implementation are resolved or explicitly recorded.
- Scope and constraints are documented.
- Requirements are sufficiently traceable.

---

# 6. Software Architecture Standard

## AX-STD-ARCH-001 - Architecture Quality Standard

**Objective:** Ensure that software architecture is technically coherent, aligned with requirements, secure, maintainable, and feasible.

## 6.1 Architecture Requirements

| ID | Requirement | Classification |
|---|---|---|
| ARCH-001 | Architecture MUST identify major system components. | MUST |
| ARCH-002 | Component responsibilities MUST be defined. | MUST |
| ARCH-003 | Material dependencies and interactions MUST be documented. | MUST |
| ARCH-004 | Architecture MUST address relevant functional and non-functional requirements. | MUST |
| ARCH-005 | Material technology decisions MUST have documented justification. | MUST |
| ARCH-006 | Important data flows MUST be identified. | MUST |
| ARCH-007 | Security and trust boundaries MUST be considered. | MUST |
| ARCH-008 | Important failure scenarios SHOULD be evaluated. | SHOULD |
| ARCH-009 | Architecture MUST identify relevant external dependencies. | MUST |
| ARCH-010 | Architecture MUST identify known scalability and performance constraints. | MUST |
| ARCH-011 | Major architectural decisions SHOULD be documented through ADRs. | SHOULD |
| ARCH-012 | Architecture MUST distinguish current implementation from proposed design. | MUST |

## 6.2 Architecture Quality Attributes

### A. Modularity

Evaluate:

- Component cohesion.
- Coupling.
- Responsibility separation.
- Dependency boundaries.
- Change isolation.

### B. Maintainability

Evaluate:

- Understandability.
- Modification complexity.
- Component ownership.
- Dependency management.
- Documentation quality.

### C. Scalability

Evaluate:

- Expected workload.
- Resource constraints.
- Growth assumptions.
- Bottlenecks.
- Scaling strategy.

Scalability claims must be supported by an explicit workload model or technical rationale.

### D. Reliability

Evaluate:

- Failure isolation.
- Error handling.
- Recovery.
- Data consistency.
- Dependency availability.

### E. Security

Evaluate:

- Trust boundaries.
- Authentication.
- Authorization.
- Data handling.
- External interfaces.
- Privilege boundaries.

### F. Performance

Evaluate:

- Expected latency.
- Throughput.
- Resource consumption.
- Computational complexity.
- I/O bottlenecks.

Performance must not be claimed without defined workload assumptions and an appropriate measurement method.

## 6.3 Architecture Documentation Requirements

A complete architecture artifact SHOULD contain:

1. System overview.
2. Architecture goals.
3. Requirements and constraints.
4. System context.
5. Component architecture.
6. Component responsibilities.
7. Data architecture.
8. Interface architecture.
9. Security architecture.
10. Deployment architecture, where applicable.
11. Failure and recovery considerations.
12. Technology decisions.
13. Risks and limitations.
14. Architecture decision records.

## 6.4 Architecture Quality Gate

An architecture passes when:

- Required components and boundaries are identifiable.
- Responsibilities are clear.
- Important interactions are documented.
- Major requirements have architectural coverage.
- Important technology choices are justified.
- Security considerations are addressed.
- Material risks are documented.
- No unresolved critical architectural contradiction remains.

---

# 7. Technical Specification Standard

## AX-STD-SPEC-001 - Implementation Specification Quality Standard

**Objective:** Ensure that technical specifications are sufficiently detailed for implementation without requiring developers to invent material behavior.

## 7.1 Requirements

| ID | Requirement | Classification |
|---|---|---|
| SPEC-001 | Specifications MUST reference approved requirements. | MUST |
| SPEC-002 | Module responsibilities MUST be documented. | MUST |
| SPEC-003 | Important interfaces MUST have defined contracts. | MUST |
| SPEC-004 | Data structures MUST be documented where relevant. | MUST |
| SPEC-005 | Input validation requirements MUST be defined. | MUST |
| SPEC-006 | Error handling MUST be addressed. | MUST |
| SPEC-007 | Security controls MUST be documented where applicable. | MUST |
| SPEC-008 | Test requirements MUST be identifiable. | MUST |
| SPEC-009 | External dependencies MUST be identified. | MUST |
| SPEC-010 | Material unresolved decisions MUST be disclosed. | MUST |

## 7.2 Interface Contract Requirements

For each important interface, document:

- Interface identifier.
- Purpose.
- Inputs.
- Outputs.
- Data types.
- Validation rules.
- Error behavior.
- Authorization requirements.
- Side effects.
- Relevant dependencies.

## 7.3 API Specification Requirements

Where APIs are involved, document:

- Endpoint or operation.
- HTTP method or protocol operation.
- Request structure.
- Response structure.
- Status codes.
- Authentication.
- Authorization.
- Validation.
- Error responses.
- Rate limits where relevant.
- Idempotency requirements where relevant.

## 7.4 Implementation Readiness Gate

A specification passes when:

- Requirements are traceable.
- Major components have defined responsibilities.
- Critical interfaces are unambiguous.
- Data contracts are sufficient.
- Error and validation behavior are defined.
- Security requirements are addressed.
- Test expectations are identifiable.
- Material implementation decisions are not hidden.

---

# 8. Security Engineering Standard

## AX-STD-SEC-001 - Security Design Standard

**Objective:** Ensure that security considerations are integrated into software architecture and technical specifications.

## 8.1 Security Design Requirements

| ID | Requirement | Classification |
|---|---|---|
| SEC-001 | Relevant assets and trust boundaries MUST be identified. | MUST |
| SEC-002 | Authentication requirements MUST be defined where applicable. | MUST |
| SEC-003 | Authorization rules MUST be defined for protected resources. | MUST |
| SEC-004 | Sensitive data MUST have documented handling requirements. | MUST |
| SEC-005 | Secrets MUST be separated from ordinary application configuration. | MUST |
| SEC-006 | Input validation MUST be addressed at appropriate trust boundaries. | MUST |
| SEC-007 | Security-relevant errors MUST avoid exposing sensitive information. | MUST |
| SEC-008 | External dependencies MUST be considered in the threat assessment. | MUST |
| SEC-009 | Relevant threats SHOULD be prioritized by risk. | SHOULD |
| SEC-010 | Security controls SHOULD have corresponding verification methods. | SHOULD |

## 8.2 Threat Modeling

AXIOM SHOULD support structured threat modeling using an appropriate methodology.

The threat assessment should identify:

1. System assets.
2. Entry points.
3. Trust boundaries.
4. Actors.
5. Attack surfaces.
6. Threat scenarios.
7. Potential impact.
8. Existing controls.
9. Residual risk.
10. Verification requirements.

STRIDE may be used as one threat-classification method, but it should not be mandatory for every small application.

## 8.3 Security Review Criteria

Reviewers should evaluate:

- Broken access control.
- Authentication weaknesses.
- Sensitive data exposure.
- Injection risks.
- Insecure configuration.
- Insufficient logging.
- Dependency vulnerabilities.
- Insecure external communication.
- Inadequate privilege separation.
- Unsafe execution or file handling.

These categories are guidance, not proof that a complete security assessment has occurred.

## 8.4 Security Acceptance Gate

A security design passes when:

- Relevant trust boundaries are documented.
- Authentication and authorization requirements are addressed.
- Sensitive data handling is defined.
- Major threats are evaluated.
- Required controls are identifiable.
- Residual risks are documented.
- Critical unresolved security findings are absent or explicitly handled through authorized risk governance.

---

# 9. Database Engineering Standard

## AX-STD-DB-001 - Database Design Quality Standard

**Objective:** Ensure that data models and persistence architectures preserve integrity, consistency, security, and maintainability.

## 9.1 Database Requirements

| ID | Requirement | Classification |
|---|---|---|
| DB-001 | Important entities and relationships MUST be defined. | MUST |
| DB-002 | Data types MUST be appropriate for stored values. | MUST |
| DB-003 | Primary key and identity strategies MUST be documented. | MUST |
| DB-004 | Referential integrity MUST be addressed where applicable. | MUST |
| DB-005 | Data constraints MUST be defined for important invariants. | MUST |
| DB-006 | Sensitive data handling MUST be addressed. | MUST |
| DB-007 | Transaction boundaries MUST be evaluated where relevant. | MUST |
| DB-008 | Indexes SHOULD be justified by query and workload requirements. | SHOULD |
| DB-009 | Data lifecycle and retention SHOULD be documented. | SHOULD |
| DB-010 | Migration and rollback strategies SHOULD be documented. | SHOULD |

## 9.2 Data Model Quality

Evaluate:

- Entity completeness.
- Relationship correctness.
- Normalization.
- Intentional denormalization.
- Constraint coverage.
- Data ownership.
- Referential integrity.
- Data lifecycle.
- Query access patterns.

Do not enforce normalization mechanically. Denormalization can be justified when workload and consistency requirements support it.

## 9.3 Database Quality Gate

An acceptable database design must:

- Define core entities.
- Identify relationships.
- Address integrity constraints.
- Define important transaction requirements.
- Address sensitive data.
- Consider migration safety.
- Document performance assumptions.

---

# 10. API Engineering Standard

## AX-STD-API-001 - API Design Quality Standard

**Objective:** Ensure that application interfaces are consistent, secure, understandable, and predictable.

## 10.1 API Requirements

| ID | Requirement | Classification |
|---|---|---|
| API-001 | API operations MUST have documented purposes. | MUST |
| API-002 | Request and response contracts MUST be defined. | MUST |
| API-003 | Input validation MUST be specified. | MUST |
| API-004 | Error responses MUST have consistent behavior. | MUST |
| API-005 | Authorization requirements MUST be documented. | MUST |
| API-006 | API versioning strategy SHOULD be defined where evolution requires it. | SHOULD |
| API-007 | Pagination SHOULD be addressed for potentially large collections. | SHOULD |
| API-008 | Idempotency MUST be addressed for operations where duplicate execution creates material risk. | MUST |
| API-009 | Rate limiting SHOULD be considered for exposed services. | SHOULD |
| API-010 | API documentation SHOULD include usable examples. | SHOULD |

## 10.2 API Quality Criteria

Evaluate:

- Contract clarity.
- Naming consistency.
- HTTP semantics where applicable.
- Validation.
- Error handling.
- Authentication.
- Authorization.
- Versioning.
- Compatibility.
- Observability.
- Idempotency.

## 10.3 API Quality Gate

An API design passes when:

- Important operations have defined contracts.
- Input and output structures are clear.
- Error behavior is documented.
- Security requirements are defined.
- Relevant compatibility concerns are addressed.

---

# 11. Reliability Engineering Standard

## AX-STD-REL-001 - Software Reliability Standard

**Objective:** Ensure that software systems handle failures predictably and maintain acceptable service behavior.

## 11.1 Requirements

| ID | Requirement | Classification |
|---|---|---|
| REL-001 | Important external dependencies MUST have failure considerations. | MUST |
| REL-002 | Timeout behavior MUST be defined for relevant external operations. | MUST |
| REL-003 | Retry behavior MUST avoid uncontrolled retry amplification. | MUST |
| REL-004 | Critical failure paths MUST have defined handling. | MUST |
| REL-005 | Data integrity requirements MUST be addressed. | MUST |
| REL-006 | Recovery behavior SHOULD be documented for important services. | SHOULD |
| REL-007 | Observability SHOULD support diagnosis of material failures. | SHOULD |
| REL-008 | Resource exhaustion risks SHOULD be evaluated. | SHOULD |

## 11.2 Reliability Evaluation

Evaluate:

- Dependency failure.
- Network interruption.
- Timeout behavior.
- Retry policy.
- Circuit breaking where appropriate.
- Partial failure.
- Data corruption.
- Recovery.
- Resource exhaustion.
- Operational visibility.

## 11.3 Reliability Quality Gate

A reliability design passes when:

- Important failure modes are identified.
- External dependency failures are addressed.
- Recovery behavior is documented where necessary.
- Data integrity is protected.
- Critical failure paths have predictable behavior.

---

# 12. Testing and Verification Standard

## AX-STD-TEST-001 - Software Testing Standard

**Objective:** Ensure that engineering requirements can be verified through appropriate testing and inspection methods.

## 12.1 Testing Categories

- Unit Testing.
- Integration Testing.
- System Testing.
- End-to-End Testing.
- API Testing.
- Security Testing.
- Performance Testing.
- Regression Testing.
- Acceptance Testing.

The required categories depend on project scope and risk.

## 12.2 Testing Requirements

| ID | Requirement | Classification |
|---|---|---|
| TEST-001 | Material requirements MUST have identifiable verification methods. | MUST |
| TEST-002 | Critical business behavior SHOULD have appropriate automated tests. | SHOULD |
| TEST-003 | Important integration boundaries MUST be considered for testing. | MUST |
| TEST-004 | Error and failure scenarios MUST be evaluated where material. | MUST |
| TEST-005 | Regression testing SHOULD cover previously corrected defects. | SHOULD |
| TEST-006 | Test results MUST identify the execution environment. | MUST |
| TEST-007 | Failed tests MUST NOT be represented as successful. | MUST |
| TEST-008 | Test coverage percentages MUST NOT be treated as proof of correctness. | MUST |

## 12.3 Verification Method Classification

Each requirement should identify an appropriate verification method:

| Method | Description |
|---|---|
| Inspection | Examine source, documents, or configuration |
| Analysis | Evaluate technical properties or logic |
| Demonstration | Observe system behavior |
| Test | Execute a defined test procedure |

## 12.4 Test Quality Gate

A testing strategy passes when:

- Material requirements have verification methods.
- Important integration boundaries are addressed.
- Critical failure behavior is covered.
- Test environments are identifiable.
- Results are traceable.
- Known limitations are disclosed.

---

# 13. Code Quality Standard

## AX-STD-CODE-001 - Implementation Quality Standard

**Objective:** Define baseline quality requirements for source code when AXIOM evaluates existing or proposed implementation.

## 13.1 Code Quality Requirements

| ID | Requirement | Classification |
|---|---|---|
| CODE-001 | Code MUST follow the relevant language's valid syntax and semantics. | MUST |
| CODE-002 | Functions and modules SHOULD have clear responsibilities. | SHOULD |
| CODE-003 | Important business logic SHOULD be testable. | SHOULD |
| CODE-004 | Error handling MUST be appropriate to the operation. | MUST |
| CODE-005 | Secrets MUST NOT be hardcoded into source code. | MUST |
| CODE-006 | Input validation MUST be implemented at relevant trust boundaries. | MUST |
| CODE-007 | Dependencies MUST be identifiable. | MUST |
| CODE-008 | Critical logic SHOULD have appropriate automated tests. | SHOULD |
| CODE-009 | Dead or unreachable code SHOULD be identified. | SHOULD |
| CODE-010 | Material technical debt SHOULD be documented. | SHOULD |

## 13.2 Code Quality Evaluation

Evaluate:

- Correctness.
- Readability.
- Modularity.
- Maintainability.
- Testability.
- Security.
- Dependency management.
- Error handling.
- Resource management.
- Consistency with project conventions.

## 13.3 Static Analysis

Where available, use:

- Language-specific linters.
- Type checkers.
- Static analyzers.
- Dependency scanners.
- Security scanners.
- Test frameworks.

Tool output must be interpreted in context. A clean static analysis report does not prove that an application is correct or secure.

---

# 14. Technical Documentation Standard

## AX-STD-DOC-001 - Engineering Documentation Standard

**Objective:** Ensure that technical documentation remains understandable, accurate, consistent, and maintainable.

## 14.1 Documentation Requirements

| ID | Requirement | Classification |
|---|---|---|
| DOC-001 | Documents MUST have a clear purpose. | MUST |
| DOC-002 | Material technical claims MUST be accurate or explicitly qualified. | MUST |
| DOC-003 | Important documents MUST identify their scope. | MUST |
| DOC-004 | Material decisions MUST be traceable. | MUST |
| DOC-005 | Documentation SHOULD identify relevant version or status. | SHOULD |
| DOC-006 | Examples SHOULD be consistent with the described behavior. | SHOULD |
| DOC-007 | Superseded documentation SHOULD be identified. | SHOULD |
| DOC-008 | Instructions MUST NOT expose credentials or secrets. | MUST |

## 14.2 Documentation Quality Attributes

- Accuracy.
- Clarity.
- Completeness.
- Consistency.
- Discoverability.
- Maintainability.
- Traceability.
- Version awareness.

## 14.3 Documentation Quality Gate

Documentation passes when:

- Purpose and scope are clear.
- Material technical statements are supported.
- Examples do not contradict the described behavior.
- Important decisions are traceable.
- Known limitations are disclosed.

---

# 15. Engineering Quality Evaluation Framework

## 15.1 Purpose

AXIOM must use a consistent evaluation model across its standards.

The model should support:

- Requirement-level compliance.
- Artifact-level quality.
- Reviewer calibration.
- Regression testing.
- Project-level quality reporting.

## 15.2 Evaluation Dimensions

Every relevant artifact should be assessed against these dimensions.

| Dimension | Meaning |
|---|---|
| Correctness | Technical claims and design decisions are accurate |
| Completeness | Required engineering areas are covered |
| Consistency | No unresolved material contradictions |
| Feasibility | Proposed solution is realistic |
| Verifiability | Claims and requirements can be checked |
| Maintainability | Future changes are manageable |
| Security | Relevant security risks are addressed |
| Reliability | Failure behavior is adequately considered |
| Traceability | Inputs, decisions, and outputs are connected |
| Evidence | Findings and claims are adequately supported |

Not every dimension applies to every artifact. Applicability must be recorded.

## 15.3 Compliance States

Every evaluated requirement must receive one of the following states:

| State | Definition |
|---|---|
| PASS | Requirement is satisfied with sufficient evidence |
| FAIL | Requirement is demonstrably not satisfied |
| PARTIAL | Some aspects are satisfied, but required coverage remains incomplete |
| NOT_VERIFIED | Insufficient evidence to determine compliance |
| NOT_APPLICABLE | Requirement does not apply |
| WAIVED | Authorized exception has been granted |

`NOT_VERIFIED` is not equivalent to `PASS`.

`WAIVED` is not equivalent to technical compliance.

## 15.4 Weighted Quality Scores

AXIOM MAY calculate a weighted quality score for comparative analysis.

However:

- Scores MUST NOT replace individual findings.
- Mandatory failures MUST remain visible.
- Unverified requirements MUST NOT be treated as passed.
- Weights MUST be documented.
- Scores MUST be interpreted within artifact type and project context.
- A high score MUST NOT automatically authorize approval.

### Proposed Evaluation Formula

For a defined set of applicable evaluation criteria:

\[
Q = \frac{\sum_{i=1}^{n} w_i s_i}{\sum_{i=1}^{n} w_i}
\]

Where:

- \(Q\) = weighted quality score.
- \(w_i\) = assigned criterion weight.
- \(s_i\) = normalized evaluation result.
- \(n\) = number of applicable criteria.

A possible normalized scale is:

- 0 = Not satisfied.
- 0.5 = Partially satisfied.
- 1 = Satisfied.

Unverified and not-applicable criteria must be handled separately, not automatically scored as passing.

### Score Interpretation

| Score | Interpretation |
|---|---|
| 90–100 | Strong quality |
| 75–89 | Acceptable with improvements |
| 60–74 | Significant weaknesses |
| Below 60 | Inadequate |

These are provisional interpretation bands, not validated universal thresholds.

The score is supplementary. Critical or high-severity findings can block approval regardless of the score.

---

# 16. Risk and Severity Governance

## 16.1 Risk Classification

Engineering risks should be classified using:

- Impact.
- Likelihood.
- Exposure.
- Detectability.
- Recoverability.
- Existing controls.

## 16.2 Finding Severity

AXIOM uses the following severity levels:

| Severity | Description |
|---|---|
| Critical | Severe correctness, security, integrity, or operational issue |
| High | Material engineering defect requiring correction |
| Medium | Significant weakness requiring resolution or justified deferral |
| Low | Limited impact issue |
| Informational | Observation or optional improvement |

## 16.3 Risk Acceptance

A risk may be accepted only when:

- It is explicitly documented.
- Its impact is understood.
- A responsible human authority approves it.
- Any required compensating controls are recorded.
- The decision has a review or expiry condition where appropriate.

AI-generated risk acceptance is not authorized.

---

# 17. Standards Compliance and Exceptions

## 17.1 Compliance Assessment

Each standard MUST identify:

- Applicable requirements.
- Requirement classification.
- Evaluation method.
- Evidence expectations.
- Compliance state.
- Exception handling.

## 17.2 Exception Request

A mandatory standard exception must document:

```yaml
exception_id: AX-EX-001

standard_id: AX-STD-ARCH-001

requirement_id: ARCH-008

reason: >
  The project scope does not justify the
  proposed additional architecture complexity.

impact: >
  Some failure scenarios will remain
  documented at a higher-level abstraction.

risk_level: medium

compensating_controls:
  - Document operational assumptions.

requested_by: project_owner

approval_status: pending

review_condition: before_production_release
```

The example is illustrative.

## 17.3 Exception Rules

- Exceptions MUST have explicit scope.
- Exceptions MUST include rationale.
- Exceptions MUST identify residual risk.
- Exceptions MUST have an authorized approver.
- Exceptions SHOULD have an expiry or review condition.
- Exceptions MUST NOT silently change the underlying standard.

---

# 18. Standards Validation and Evaluation

## 18.1 Evaluation Methods

AXIOM should validate standards through:

1. Golden test cases.
2. Seeded-defect evaluation.
3. Human expert assessment.
4. Cross-model testing.
5. Regression testing.
6. Real repository case studies.
7. Adversarial and incomplete-input testing.

## 18.2 Evaluation Dataset Requirements

Evaluation datasets should contain:

- Valid engineering artifacts.
- Incomplete artifacts.
- Contradictory artifacts.
- Artifacts with known defects.
- Artifacts containing misleading assumptions.
- False-positive traps.
- Security-sensitive cases.
- Context-dependent cases.

Expected findings must be validated by qualified human reviewers.

## 18.3 Standard Effectiveness

A standard should be evaluated on:

- Clarity.
- Applicability.
- Measurability.
- Consistency.
- Reviewer agreement.
- Defect detection effectiveness.
- False-positive reduction.
- Practical engineering usefulness.

A standard that generates excessive irrelevant findings should be revised rather than treated as successful simply because it is strict.

---

# 19. Standards Versioning and Maintenance

## 19.1 Versioning

Use semantic versioning:

`MAJOR.MINOR.PATCH`

- Major: Breaking changes to requirement meaning or compliance behavior.
- Minor: New backward-compatible requirements or evaluation capabilities.
- Patch: Editorial clarification or correction without changing requirement intent.

## 19.2 Change Management

Every material standards change must document:

- Standard identifier.
- Previous version.
- New version.
- Changed requirement IDs.
- Reason for change.
- Affected skills.
- Affected reviewers.
- Required regression tests.
- Approval authority.

## 19.3 Standards Lifecycle

```text
PROPOSED
   |
   v
DRAFT
   |
   v
UNDER_REVIEW
   |
   v
APPROVED
   |
   v
ACTIVE
   |
   v
DEPRECATED
   |
   v
RETIRED
```

Standards must not be treated as authoritative before approval.

---

# 20. Initial AXIOM Standards Catalog

The initial catalog is divided into release priorities.

| Standard ID | Standard | Priority |
|---|---|---|
| AX-STD-CORE-001 | Evidence and Traceability | P0 |
| AX-STD-CORE-002 | Engineering Decision Quality | P0 |
| AX-STD-CORE-003 | Scope and Change Integrity | P0 |
| AX-STD-CORE-004 | Security and Safety Baseline | P0 |
| AX-STD-REQ-001 | Requirements Quality | P0 |
| AX-STD-ARCH-001 | Architecture Quality | P0 |
| AX-STD-SPEC-001 | Specification Quality | P0 |
| AX-STD-SEC-001 | Security Design | P1 |
| AX-STD-DB-001 | Database Design | P1 |
| AX-STD-API-001 | API Design | P1 |
| AX-STD-REL-001 | Reliability Engineering | P1 |
| AX-STD-TEST-001 | Testing and Verification | P1 |
| AX-STD-CODE-001 | Code Quality | P2 |
| AX-STD-DOC-001 | Documentation Quality | P2 |

### Release Priority Definitions

- P0: Required for the initial engineering foundation.
- P1: Required for broader engineering assurance.
- P2: Required for implementation and engineering maturity expansion.

The foundational security and safety baseline applies from the beginning even though the detailed Security Design Standard is a later expansion.

---

# 21. Integration with AXIOM Skills

Each skill must reference its applicable standards.

| Skill | Required standards |
|---|---|
| axiom-discover | CORE-001, CORE-003, DOC-001 |
| axiom-requirements | CORE-001, CORE-002, CORE-003, REQ-001 |
| axiom-brainstorm | CORE-001, CORE-002, CORE-003 |
| axiom-architecture | CORE-001, CORE-002, CORE-004, ARCH-001 |
| axiom-specification | CORE-001, CORE-003, SPEC-001 |
| axiom-review | All applicable standards |
| axiom-resolve | CORE-001, CORE-003, applicable domain standards |

The exact standard versions must be resolved during skill execution and recorded in the output.

A skill should not silently use an outdated standard version when a newer compatible approved version is available.

---

# 22. Integration with AXIOM Reviewers

Reviewers must evaluate artifacts against relevant standards.

| Reviewer | Primary standards |
|---|---|
| Requirements Reviewer | CORE-001, CORE-002, REQ-001 |
| Architecture Reviewer | CORE-001, CORE-002, ARCH-001 |
| Security Reviewer | CORE-004, SEC-001 |
| Reliability Reviewer | REL-001, CORE-001 |
| Specification Reviewer | SPEC-001, REQ-001, API-001 where relevant |

Reviewers may reference additional standards where relevant to the artifact.

Every finding should reference its applicable standard and requirement identifier when a specific requirement has been violated.

---

# 23. Initial Quality Gates

AXIOM should define separate quality gates rather than relying on one universal engineering score.

## Gate 1 - Requirements Readiness

Required conditions:

- Material requirements are identifiable.
- Acceptance criteria are present.
- Important contradictions are resolved.
- Constraints are documented.
- Traceability is established.

## Gate 2 - Architecture Readiness

Required conditions:

- Component responsibilities are clear.
- Interfaces and data flows are defined.
- Material decisions are justified.
- Relevant security concerns are addressed.
- Major risks are documented.

## Gate 3 - Specification Readiness

Required conditions:

- Requirements are traceable.
- Interfaces are sufficiently detailed.
- Data contracts are defined.
- Error handling is addressed.
- Verification expectations are documented.

## Gate 4 - Review Readiness

Required conditions:

- The artifact is accessible.
- Review scope is defined.
- Applicable standards are identified.
- Relevant context is available.
- Known limitations are disclosed.

## Gate 5 - Approval Readiness

Required conditions:

- No unresolved blocking findings.
- Mandatory compliance is established or authorized exceptions exist.
- Required corrections are verified.
- Residual risks are documented.
- Human approval is obtained.

---

# 24. AXIOM Engineering Standards Acceptance Criteria

This specification is ready for implementation planning when:

1. Standards architecture and hierarchy are approved.
2. Requirement classifications are accepted.
3. Evidence and traceability rules are established.
4. P0 standards have been reviewed.
5. Evaluation states are consistent with the Reviewer Protocol.
6. Quality gates are defined.
7. Exception and risk acceptance procedures are established.
8. Standard versioning and governance are approved.
9. Skill-to-standard mappings are validated.
10. Initial evaluation cases are identified.

A standards document is not itself proof of compliance. Compliance must be demonstrated by evaluating actual engineering artifacts.

---

# 25. Architectural Decisions

| ID | Decision | Status |
|---|---|---|
| AX-ADR-021 | Engineering standards remain independent of skills | Proposed |
| AX-ADR-022 | Standards are classified into four levels | Proposed |
| AX-ADR-023 | Mandatory and recommended requirements are distinguished | Proposed |
| AX-ADR-024 | Every evaluated requirement has an explicit compliance state | Proposed |
| AX-ADR-025 | Unverified requirements cannot be treated as passed | Proposed |
| AX-ADR-026 | Weighted quality scores cannot override blocking findings | Proposed |
| AX-ADR-027 | Mandatory requirement exceptions require human authorization | Proposed |
| AX-ADR-028 | Standards have independent versioning | Proposed |
| AX-ADR-029 | Standard effectiveness must be evaluated against real cases | Proposed |
| AX-ADR-030 | Skills and reviewers must reference applicable standard versions | Proposed |

---

# 26. Final Specification Statement

The AXIOM Engineering Standards Specification establishes a consistent and measurable quality baseline for AI-assisted software engineering.

The standards define what constitutes acceptable engineering work, how compliance is evaluated, what evidence is required, and how exceptions are governed.

The framework must not confuse documentation completeness with engineering correctness, automated scores with verified quality, or AI recommendations with human authorization.

**AXIOM Engineering Quality Principle:**

"Every engineering requirement must be assessable. Every material decision must be defensible. Every reported finding must be supported. Every accepted exception must be accountable."

---

**Document ID:** AX-SPEC-003  
**Version:** 0.1.0  
**Status:** Proposed - Pending Human Approval

**End of Specification**
