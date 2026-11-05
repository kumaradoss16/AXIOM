# AXIOM - Skill Architecture Specification

**Document Type:** Product / Technical Architecture Specification  
**Project Name:** AXIOM   
**Document Status:** Proposed - Pending Approval  
**Version:** 0.1.0  
**Classification:** Foundational Architecture  
**Primary Domain:** AI-Assisted Software Engineering  
**Implementation Status:** Not Started  
**Decision Authority:** Human Project Owner

---

## 1. Executive Definition

### 1.1 What is AXIOM?

AXIOM is a modular, model-agnostic software engineering intelligence framework built around specialized AI skills, independent reviewers, engineering standards, and evidence-based validation.

Its purpose is to improve the quality, consistency, traceability, and reliability of software engineering activities performed by humans and AI coding agents.

AXIOM provides reusable engineering methodologies for:

- Understanding existing software projects.
- Discovering and analyzing requirements.
- Exploring and evaluating technical alternatives.
- Designing software architectures.
- Producing implementation-ready specifications.
- Reviewing engineering artifacts independently.
- Resolving review findings systematically.
- Validating engineering decisions against documented standards.

AXIOM is not intended to replace software engineers, automatically approve engineering decisions, or act as an unrestricted autonomous coding agent.

Its central principle is:

> Every important engineering decision should have an explicit rationale, a documented standard, an identifiable owner, and sufficient evidence to support its acceptance.

### 1.2 Product Vision

Establish a reusable engineering intelligence framework that makes AI-assisted software engineering more systematic, inspectable, reproducible, and accountable.

AXIOM should enable different AI models and coding environments to follow consistent engineering practices without making those practices dependent on one model provider, agent framework, IDE, or orchestration platform.

### 1.3 Core Design Principles

1. **Engineering before implementation:** Understand the problem and establish requirements before proposing implementation.
2. **Evidence over assumptions:** Findings must be supported by available evidence or explicitly identified uncertainty.
3. **Independent review:** Authors and reviewers must have distinct responsibilities and evaluation criteria.
4. **Human authority:** AI recommendations never constitute automatic approval of material engineering decisions.
5. **Explicit scope:** Every skill must define what it does and does not do.
6. **Reproducibility:** Equivalent inputs and framework versions should produce comparable, auditable workflows.
7. **Model independence:** Engineering standards must not depend on a specific LLM.
8. **Progressive complexity:** Introduce advanced capabilities only when the core workflow demonstrates measurable value.
9. **Security by design:** Protect source code, credentials, user data, and execution boundaries.
10. **Traceability:** Maintain relationships between requirements, decisions, specifications, reviews, and validation evidence.

---

## 2. Product Positioning and Boundaries

### 2.1 What AXIOM Is

AXIOM is an engineering methodology and reusable skill framework.

Its primary deliverables are:

- Engineering skills.
- Reviewer definitions and review protocols.
- Engineering standards.
- Document and report templates.
- Evaluation datasets and quality rubrics.
- Workflow definitions.
- Engineering evidence and traceability conventions.

### 2.2 What AXIOM Is Not

| Category | AXIOM's position |
|---|---|
| AI coding agent | Not a replacement for Codex, Claude Code, or other coding agents |
| LLM provider | Does not train or host foundation models |
| Workflow orchestrator | Does not own model routing or multi-agent execution infrastructure |
| IDE | Does not replace VS Code or other development environments |
| CI/CD platform | Does not replace build, test, or deployment systems |
| Autonomous development system | Does not independently authorize consequential engineering changes |
| Project management system | Does not replace issue tracking or project management platforms |

### 2.3 Relationship with AI Workflow Orchestrator

AXIOM and the AI Workflow Orchestrator should remain separate products with clearly defined integration boundaries.

| Dimension | AXIOM | AI Workflow Orchestrator |
|---|---|---|
| Primary responsibility | Engineering intelligence | AI workflow coordination |
| Core abstraction | Skill and engineering standard | Workflow and execution |
| Main functionality | Analyze, design, review, validate | Route, execute, coordinate, aggregate |
| Model selection | External responsibility | Internal capability |
| Agent execution | Uses compatible host agents | Coordinates agents |
| Engineering authority | Defines approval requirements | Enforces configured execution permissions |
| Quality methodology | Owns standards and evaluation | Consumes workflow quality requirements |
| Output | Engineering artifacts and findings | Execution records and aggregated results |

**Integration principle:** AXIOM must work independently through compatible AI coding environments. The orchestrator may execute AXIOM skills, but AXIOM must not require the orchestrator to function.

---

## 3. Architectural Overview

AXIOM is organized into six logical layers.

### 3.1 Layer 1 - Skill Layer

Contains specialized, reusable engineering capabilities.

Examples:

- Project discovery.
- Requirement analysis.
- Technical brainstorming.
- Architecture design.
- Specification authoring.
- Architecture review.
- Review resolution.

Each skill is independently understandable and has a documented execution contract.

### 3.2 Layer 2 - Reviewer Layer

Defines specialized reviewer roles responsible for evaluating engineering artifacts.

Potential reviewers:

- Requirements Reviewer.
- Architecture Reviewer.
- Security Reviewer.
- Database Reviewer.
- Reliability Reviewer.
- Implementation Reviewer.

Reviewers should use explicit evaluation criteria rather than relying on general-purpose instructions such as "review this carefully."

### 3.3 Layer 3 - Standards Layer

Contains the engineering rules against which skills and reviewers evaluate work.

Examples:

- Requirements Quality Standard.
- Architecture Quality Standard.
- Security Design Standard.
- API Design Standard.
- Database Design Standard.
- Documentation Quality Standard.
- Reliability and Failure Handling Standard.

Standards should distinguish mandatory requirements, recommended practices, and context-dependent guidance.

### 3.4 Layer 4 - Evidence and Validation Layer

Ensures that engineering claims are supported by appropriate evidence.

Examples:

- Repository inspection results.
- Source file references.
- Requirement traceability.
- Architecture decision records.
- Test results.
- Static analysis results.
- Review findings.
- Human approval records.

An AI-generated assertion must not be presented as an executed test result.

### 3.5 Layer 5 - Governance Layer

Defines how AXIOM manages:

- Skill versions.
- Standard versions.
- Reviewer responsibilities.
- Approval requirements.
- Scope changes.
- Exceptions.
- Risk classification.
- Quality gates.
- Auditability.

### 3.6 Layer 6 - Compatibility Layer

Defines how AXIOM skills are packaged and consumed by supported AI environments.

Initial compatibility should prioritize portable Markdown-based skill packages, with optional host-specific adapters where necessary.

The engineering methodology remains independent of the host.

---

## 4. Core Engineering Lifecycle

AXIOM should organize its initial capabilities around a controlled engineering lifecycle.

```text
Project Context
      |
      v
Project Discovery
      |
      v
Requirements Analysis
      |
      v
Technical Brainstorming
      |
      v
Architecture Design
      |
      v
Specification Authoring
      |
      v
Independent Review
      |
      v
Review Resolution
      |
      v
Human Approval
      |
      v
Implementation (External)
```

This is a logical lifecycle, not a requirement that every project execute every stage in a rigid sequence.

For example, an existing project may enter directly at architecture review if its requirements and implementation already exist.

### 4.1 Lifecycle Stage Definitions

| Stage | Purpose | Primary output |
|---|---|---|
| Discovery | Understand the project and its existing state | Project Context Report |
| Requirements | Establish functional and non-functional expectations | Requirements Specification |
| Brainstorming | Evaluate possible solutions | Options and Trade-off Report |
| Architecture | Establish system structure and technical decisions | Architecture Design |
| Specification | Convert approved decisions into actionable contracts | Technical Specification |
| Review | Independently evaluate artifacts | Review Report |
| Resolution | Address findings and verify corrections | Resolution Report |
| Approval | Obtain human authorization | Approval Record |
| Implementation | Execute approved specifications | External implementation artifacts |

### 4.2 Workflow State Model

AXIOM should distinguish between the following states:

- `NOT_STARTED`
- `IN_PROGRESS`
- `DRAFT`
- `UNDER_REVIEW`
- `CHANGES_REQUIRED`
- `READY_FOR_APPROVAL`
- `APPROVED`
- `REJECTED`
- `BLOCKED`
- `SUPERSEDED`

A skill must never silently convert a draft or reviewed artifact into an approved artifact.

---

## 5. Standard Skill Architecture

### 5.1 Skill Definition

An AXIOM skill is a self-contained engineering capability that provides a repeatable process for performing a clearly defined software engineering task.

A skill is not simply a prompt that tells an AI to perform an activity.

It must define:

1. Its engineering responsibility.
2. When it should be activated.
3. Required inputs.
4. Context acquisition requirements.
5. Execution methodology.
6. Applicable engineering standards.
7. Expected outputs.
8. Validation requirements.
9. Safety boundaries.
10. Completion criteria.

### 5.2 Standard Skill Package

Proposed package structure:

```text
skill-name/
├── SKILL.md
├── references/
│   ├── methodology.md
│   └── applicable-standards.md
├── templates/
│   └── output-template.md
└── examples/
    └── example-output.md
```

Not every skill requires every directory. Avoid unnecessary files and duplicated instructions.

### 5.3 Mandatory SKILL.md Contract

Every AXIOM skill must follow a common metadata and instruction contract.

```yaml
---
name: axiom-example-skill
description: A concise description of the engineering capability.
version: 0.1.0
category: engineering
stage: architecture
risk_level: medium
status: experimental
---

# Skill Name

## 1. Purpose

## 2. Activation Conditions

## 3. Scope

## 4. Non-Goals

## 5. Required Inputs

## 6. Context Acquisition

## 7. Execution Procedure

## 8. Engineering Standards

## 9. Output Contract

## 10. Validation Criteria

## 11. Safety Boundaries

## 12. Failure Handling

## 13. Completion Criteria

## 14. References
```

This is the AXIOM logical contract. The final metadata syntax must be adapted to the supported host skill format without losing required information.

### 5.4 Skill Contract Requirements

| Contract field | Requirement |
|---|---|
| Purpose | Define exactly one primary engineering responsibility |
| Activation | Define relevant requests and workflow conditions |
| Scope | Define included activities |
| Non-goals | Prevent unintended responsibilities |
| Inputs | Identify required and optional inputs |
| Context acquisition | Specify which files, documents, or evidence must be inspected |
| Execution procedure | Provide ordered, actionable steps |
| Standards | Identify applicable standards and their priority |
| Output contract | Define required deliverables and structure |
| Validation | Define how output correctness is checked |
| Safety | Define prohibited actions and authority limitations |
| Failure handling | Explain incomplete, missing, or contradictory information |
| Completion | Establish objective exit conditions |

### 5.5 Skill Execution Rules

Every skill must:

- Inspect available project context before making project-specific claims.
- Distinguish observed facts from assumptions and recommendations.
- Identify missing information explicitly.
- Preserve existing approved decisions unless a change is authorized.
- Avoid inventing repository files, source code behavior, test results, or implementation status.
- Produce outputs appropriate to the requested scope.
- Identify unresolved issues before claiming completion.
- Request human input when a material decision cannot be safely inferred.

---

## 6. Initial Core Skill Catalog

The first release should contain seven core skills.

### 6.1 `axiom-discover`

**Purpose:** Understand an existing software project before making engineering recommendations.

Responsibilities:

- Inspect repository structure.
- Identify application entry points.
- Identify languages, frameworks, and dependencies.
- Examine relevant configuration and documentation.
- Identify architectural boundaries.
- Identify existing tests and validation mechanisms.
- Identify missing or contradictory project information.

Output:

`PROJECT_CONTEXT_REPORT.md`

Must not modify application source code.

### 6.2 `axiom-requirements`

**Purpose:** Convert a problem statement into a structured, verifiable requirements specification.

Responsibilities:

- Identify stakeholders and user problems.
- Define functional requirements.
- Define non-functional requirements.
- Identify constraints and assumptions.
- Define measurable acceptance criteria.
- Identify dependencies and unresolved questions.
- Identify scope exclusions.

Output:

`REQUIREMENTS.md`

Requirements should have stable identifiers, such as `FR-001`, `NFR-001`, and `CON-001`.

### 6.3 `axiom-brainstorm`

**Purpose:** Explore and compare alternative technical solutions before committing to a design.

Responsibilities:

- Understand the problem and constraints.
- Generate technically plausible alternatives.
- Evaluate trade-offs.
- Consider complexity, security, reliability, performance, and maintainability.
- Identify implementation risks.
- Recommend an option with explicit justification.

Output:

`TECHNICAL_OPTIONS.md`

The skill must not present a single preferred solution as objectively optimal without comparing relevant alternatives.

### 6.4 `axiom-architecture`

**Purpose:** Develop a coherent architecture aligned with approved requirements and project constraints.

Responsibilities:

- Define system boundaries.
- Identify components and responsibilities.
- Define component interactions.
- Establish data flows.
- Define technology choices.
- Identify external dependencies.
- Evaluate security and reliability considerations.
- Record material architectural decisions.

Output:

`ARCHITECTURE.md`

Related artifacts may include architecture diagrams and ADRs.

### 6.5 `axiom-specification`

**Purpose:** Convert approved requirements and architecture into implementation-ready technical specifications.

Responsibilities:

- Define module-level responsibilities.
- Define interfaces and contracts.
- Define data structures.
- Define API behavior.
- Define validation and error handling.
- Define security requirements.
- Define testing expectations.
- Establish traceability to requirements and architecture decisions.

Output:

`TECHNICAL_SPECIFICATION.md`

The specification must not silently introduce new product requirements or reverse approved architecture decisions.

### 6.6 `axiom-review`

**Purpose:** Independently evaluate engineering artifacts against explicit standards.

Responsibilities:

- Inspect the artifact under review.
- Verify its referenced evidence.
- Apply relevant engineering standards.
- Identify gaps, contradictions, risks, and unsupported assumptions.
- Classify findings by severity.
- Provide actionable correction recommendations.
- Identify areas that cannot be verified.

Output:

`REVIEW_REPORT.md`

Review must be evidence-driven and must not assume that an artifact is correct merely because another AXIOM skill generated it.

### 6.7 `axiom-resolve`

**Purpose:** Manage review findings and verify proposed corrections.

Responsibilities:

- Read the original review report.
- Map findings to the relevant artifacts.
- Determine whether each finding is accepted, rejected with justification, deferred, or unresolved.
- Apply only authorized changes.
- Recheck corrected content.
- Identify newly introduced issues.
- Maintain finding traceability.

Output:

`REVIEW_RESOLUTION_REPORT.md`

A finding cannot be marked resolved merely because a suggested correction was written. Its resolution must be verified against the original finding.

---

## 7. Reviewer Architecture

### 7.1 Reviewer Independence

AXIOM must distinguish the artifact author from its reviewer.

Where supported, reviews should run in fresh context without relying on the author's hidden reasoning or conclusions.

A fresh context alone does not guarantee independent judgment. Reviewers must also have distinct evaluation responsibilities, evidence requirements, and assessment criteria.

### 7.2 Initial Reviewer Roles

| Reviewer | Primary responsibility |
|---|---|
| Requirements Reviewer | Completeness, consistency, feasibility, testability |
| Architecture Reviewer | Boundaries, coupling, scalability, trade-offs |
| Security Reviewer | Threats, trust boundaries, access control, sensitive data |
| Reliability Reviewer | Failure modes, recovery, fault isolation, resilience |
| Specification Reviewer | Technical completeness, interface consistency, implementation clarity |

Not all reviewers need to run for every artifact. Reviewer selection should be risk- and artifact-dependent.

### 7.3 Review Finding Contract

Every review finding must contain:

```yaml
finding_id: AXIOM-REV-001
category: architecture
severity: high
title: Missing component boundary definition

affected_artifact: ARCHITECTURE.md
affected_section: Component Responsibilities

description: >
  The architecture does not define ownership
  of the shared persistence interface.

evidence:
  - artifact: ARCHITECTURE.md
    location: Component Responsibilities

impact: >
  Multiple components may implement conflicting
  persistence behavior.

recommendation: >
  Define the persistence boundary and ownership.

confidence: high

status: open
```

The example is illustrative, not a finding about an actual repository.

### 7.4 Severity Classification

| Severity | Meaning |
|---|---|
| Critical | Fundamental security, correctness, or architectural failure |
| High | Material engineering risk requiring correction before approval |
| Medium | Significant quality or maintainability concern |
| Low | Limited issue with manageable impact |
| Informational | Observation or improvement opportunity |

Severity must be justified by impact, likelihood, and context. It must not be assigned merely to make a review appear rigorous.

### 7.5 Finding Resolution States

- `OPEN`
- `ACCEPTED`
- `REJECTED_WITH_JUSTIFICATION`
- `DEFERRED`
- `RESOLVED`
- `REOPENED`

Only verified corrections may receive `RESOLVED`.

---

## 8. Engineering Standards Architecture

### 8.1 Purpose

Standards establish a shared quality baseline across AXIOM skills and reviewers.

They must be reusable, independently versioned, and understandable without requiring a particular LLM.

### 8.2 Proposed Standards Catalog

| Standard | Initial priority | Purpose |
|---|---|---|
| Requirements Quality | P0 | Requirement completeness and testability |
| Architecture Quality | P0 | Architecture coherence and decision quality |
| Specification Quality | P0 | Implementation readiness |
| Review Quality | P0 | Evidence-based findings and severity |
| Documentation Quality | P1 | Structure, traceability, maintainability |
| Security Design | P1 | Trust boundaries and security controls |
| Database Design | P2 | Data integrity and persistence quality |
| API Design | P2 | Interface consistency and contract quality |
| Reliability Engineering | P2 | Failure handling and recovery |
| Testing Strategy | P2 | Testability and verification coverage |

P0 standards are required for the first release. P1 and P2 are expansion priorities.

### 8.3 Standard Definition Contract

Each standard should include:

```text
Standard ID
Standard Name
Version
Status
Purpose
Applicability
Mandatory Requirements
Recommended Practices
Evaluation Criteria
Evidence Expectations
Exceptions
Related Standards
Change History
```

### 8.4 Standards Priority

When standards conflict, use the following precedence:

1. Applicable laws, regulations, and contractual requirements.
2. Explicit project constraints and approved decisions.
3. AXIOM mandatory standards.
4. AXIOM recommended practices.
5. General engineering recommendations.

A conflict must be reported rather than silently resolved by the AI.

---

## 9. Evidence and Traceability Model

### 9.1 Evidence Principles

AXIOM must distinguish:

- **Observed:** Directly inspected in available source material.
- **Derived:** Reasonably concluded from observed evidence.
- **Assumed:** Accepted temporarily without sufficient verification.
- **Recommended:** Proposed engineering action.
- **Verified:** Supported by an appropriate validation result.
- **Unverified:** Not yet checked.
- **Unknown:** Insufficient information to determine.

### 9.2 Traceability Relationships

The framework should support these relationships:

```text
Requirement
    |
    v
Architecture Decision
    |
    v
Technical Specification
    |
    v
Review Finding
    |
    v
Correction
    |
    v
Validation Evidence
    |
    v
Human Approval
```

Each relationship should be explicit where relevant.

### 9.3 Evidence Quality

Evidence should include:

- Source artifact or repository location.
- Relevant section, file, or symbol.
- Observation or test result.
- Date or execution context where applicable.
- Limitations.
- Verification status.

An AI-generated explanation is not independent evidence that its own claim is correct.

---

## 10. Skill Quality and Evaluation Framework

AXIOM skills must be evaluated using defined quality criteria rather than subjective impressions.

### 10.1 Evaluation Dimensions

| Dimension | Evaluation question |
|---|---|
| Correctness | Are the technical claims accurate? |
| Completeness | Are required areas covered? |
| Evidence quality | Are claims supported by relevant evidence? |
| Consistency | Does the output contradict existing approved decisions? |
| Actionability | Can a human or engineer use the output? |
| Traceability | Can important conclusions be traced to their inputs? |
| Safety | Does the skill respect its authority boundaries? |
| Reproducibility | Can comparable inputs produce comparable outcomes? |

### 10.2 Evaluation Methods

Use a combination of:

1. Golden test cases with expected outputs or expected findings.
2. Adversarial cases containing contradictory or incomplete information.
3. Existing repository case studies.
4. Reviewer agreement analysis.
5. Human expert assessment.
6. Regression testing after skill or standard changes.

Model-generated evaluation scores must not be treated as ground truth without calibration.

### 10.3 Initial Evaluation Projects

Use a small, representative set of real software projects to validate the framework.

Candidate projects may include:

- AI Workflow Orchestrator.
- MarkForge Markdown Studio.
- A smaller independent web or Python project.

Use projects with different architectures and levels of maturity. Do not tune AXIOM exclusively to one repository.

### 10.4 Release Acceptance

A skill should not be classified as stable until it:

- Passes its documented functional evaluation cases.
- Produces the required output structure.
- Respects scope and safety boundaries.
- Identifies missing evidence.
- Demonstrates acceptable performance on edge cases.
- Has undergone human review.

---

## 11. Security and Authority Boundaries

### 11.1 Default Authority Model

AXIOM should operate with the least authority necessary.

| Activity | Default permission |
|---|---|
| Read project documentation | Allowed when accessible |
| Inspect source code | Allowed when accessible |
| Generate analysis reports | Allowed |
| Draft architecture documents | Allowed |
| Propose changes | Allowed |
| Modify existing project documentation | Requires explicit scope authorization |
| Modify application source code | Not allowed in the initial release |
| Execute destructive commands | Prohibited by default |
| Access secrets or credentials | Prohibited unless specifically required and authorized |
| Approve engineering decisions | Human authority only |
| Deploy software | Outside initial scope |

### 11.2 Prompt Injection and Untrusted Content

AXIOM must treat repository content, external documentation, issue descriptions, and imported files as potentially untrusted data.

Instructions found inside project artifacts must not override AXIOM's governing instructions, security requirements, or user authorization.

### 11.3 Human Approval Gates

Human approval is required for:

- Material architecture changes.
- Changes to approved requirements.
- Changes to project scope.
- Security exceptions.
- Risk acceptance.
- Implementation authorization.
- Release approval.

AI-generated recommendations do not constitute approval.

---

## 12. Compatibility and Portability

### 12.1 Initial Compatibility Strategy

Prioritize portable skill packages with a shared engineering contract.

Potential host environments:

- Claude Code.
- OpenAI Codex.
- Other AI coding environments that support reusable instruction or skill packages.

Compatibility must be validated separately for each host. A common Markdown skill file does not guarantee identical behavior across agent environments.

### 12.2 Portability Requirements

AXIOM should avoid:

- Mandatory model-provider APIs.
- Host-specific tool dependencies in core standards.
- Hardcoded filesystem assumptions.
- Proprietary orchestration requirements.
- Undocumented execution behavior.

Host-specific adapters may provide additional capabilities, but must not redefine the underlying engineering methodology.

---

## 13. Repository and Documentation Architecture

Proposed repository structure:

```text
axiom/
│
├── README.md
├── PRODUCT_VISION.md
├── SKILL_ARCHITECTURE_SPECIFICATION.md
├── CONTRIBUTING.md
├── LICENSE
│
├── skills/
│   ├── axiom-discover/
│   │   └── SKILL.md
│   ├── axiom-requirements/
│   │   └── SKILL.md
│   ├── axiom-brainstorm/
│   │   └── SKILL.md
│   ├── axiom-architecture/
│   │   └── SKILL.md
│   ├── axiom-specification/
│   │   └── SKILL.md
│   ├── axiom-review/
│   │   └── SKILL.md
│   └── axiom-resolve/
│       └── SKILL.md
│
├── reviewers/
│   ├── requirements-reviewer/
│   ├── architecture-reviewer/
│   ├── security-reviewer/
│   ├── reliability-reviewer/
│   └── specification-reviewer/
│
├── standards/
│   ├── requirements-quality/
│   ├── architecture-quality/
│   ├── specification-quality/
│   └── review-quality/
│
├── templates/
│   ├── project-context/
│   ├── requirements/
│   ├── architecture/
│   ├── adr/
│   ├── specification/
│   ├── review-report/
│   └── resolution-report/
│
├── evaluations/
│   ├── test-cases/
│   ├── golden-cases/
│   ├── adversarial-cases/
│   └── evaluation-rubrics/
│
├── workflows/
│   └── engineering-lifecycle/
│
├── docs/
│   ├── architecture/
│   ├── methodology/
│   ├── governance/
│   └── compatibility/
│
└── CHANGELOG.md
```

This is a proposed logical structure. Directory names and packaging conventions should be finalized after the repository and target host environments are confirmed.

---

## 14. Versioning and Governance

### 14.1 Versioning

AXIOM should use semantic versioning for stable skill and standard contracts.

- Major: Breaking changes to skill behavior or output contracts.
- Minor: Backward-compatible capabilities or new optional fields.
- Patch: Corrections and clarifications without breaking existing contracts.

Experimental skills may use a pre-release version.

### 14.2 Change Management

Every material change to a skill or standard should record:

- What changed.
- Why it changed.
- Which artifacts are affected.
- Whether compatibility is preserved.
- Which evaluations must be rerun.
- Who approved the change.

### 14.3 Governance Rules

- No silent changes to approved standards.
- No automatic acceptance of review findings.
- No unrecorded changes to approved requirements.
- No unsupported claims of validation.
- No promotion of experimental skills to stable without evaluation.
- No expansion of implementation permissions without explicit authorization.

---

## 15. Initial Release Scope

### 15.1 AXIOM v0.1 - Engineering Foundation

The initial release should focus on engineering analysis and design, not implementation automation.

**Included:**

- Common skill contract.
- Seven core skills.
- Initial reviewer protocol.
- Four P0 engineering standards.
- Standard output templates.
- Finding severity and resolution model.
- Evidence and traceability conventions.
- Basic evaluation cases.
- Initial host compatibility validation.

**Excluded:**

- Autonomous source-code modification.
- Automated application development.
- CI/CD integration.
- Deployment automation.
- Persistent orchestration engine.
- GUI dashboard.
- Model routing and token optimization.
- Automated multi-agent scheduling.
- Advanced performance profiling.
- Full implementation verification.
- Release management automation.

### 15.2 Future Evolution

| Release | Focus | Capabilities |
|---|---|---|
| v0.1 | Engineering foundation | Core skills, standards, review, resolution |
| v0.2 | Engineering assurance | Security, database, API, testing, reliability reviews |
| v0.3 | Implementation assurance | Code quality, implementation review, test verification |
| v0.4 | Project governance | Decision tracking, documentation drift, change impact |
| v0.5 | Engineering maturity | Scorecards, expanded evaluations, cross-project consistency |
| Future | Optional integrations | Workflow orchestrator, CI systems, agent platforms |

These are proposed milestones, not delivery commitments.

---

## 16. Key Architectural Decisions

| ID | Decision | Rationale |
|---|---|---|
| AX-ADR-001 | AXIOM is a standalone engineering framework | Prevents coupling to one execution platform |
| AX-ADR-002 | Skills use a common execution contract | Improves consistency and portability |
| AX-ADR-003 | Reviewers are logically independent from authors | Reduces confirmation bias |
| AX-ADR-004 | Standards are separate from skills | Allows reusable and independently versioned quality criteria |
| AX-ADR-005 | Human approval is mandatory for material decisions | Preserves engineering accountability |
| AX-ADR-006 | Evidence and traceability are first-class concepts | Makes decisions inspectable |
| AX-ADR-007 | Initial scope excludes source-code implementation | Prevents premature expansion |
| AX-ADR-008 | AXIOM remains independent of AI Workflow Orchestrator | Preserves modularity and standalone value |
| AX-ADR-009 | Evaluation is required before stable skill release | Prevents unverified quality claims |

These are proposed baseline decisions pending human approval.

---

## 17. Risks and Mitigation

| Risk | Impact | Mitigation |
|---|---|---|
| Skill duplication | Inconsistent behavior and maintenance overhead | Define narrow responsibilities and shared standards |
| Overly complex instructions | Poor execution and excessive context consumption | Keep core skills focused; use reference files selectively |
| Reviewer confirmation bias | Important defects remain undetected | Use independent contexts and distinct rubrics |
| Hallucinated evidence | Incorrect engineering decisions | Require source references and explicit verification status |
| Model variability | Inconsistent outputs | Use evaluation cases and explicit output contracts |
| Host incompatibility | Skills behave differently across environments | Validate each supported host |
| Scope expansion | Delayed initial release | Enforce v0.1 exclusions |
| Name collision | Brand and repository discoverability problems | Conduct naming and trademark checks before public branding |
| Standards becoming stale | Incorrect or outdated recommendations | Version standards and maintain review cycles |
| False confidence from scores | Poor quality decisions | Combine automated evaluation with expert review |

---

## 18. Definition of Done for AXIOM v0.1

AXIOM v0.1 is complete only when:

1. The common skill contract is documented and approved.
2. All seven core skills have complete instructions.
3. Each skill has a defined scope and output contract.
4. P0 standards are documented.
5. Reviewer finding and resolution contracts are implemented as reusable methodologies.
6. Evidence and traceability conventions are consistent.
7. Evaluation cases cover normal, incomplete, contradictory, and adversarial inputs.
8. The framework is tested against multiple representative software projects.
9. At least one supported AI coding environment is validated.
10. Human review confirms that the framework produces useful, technically defensible outputs.
11. Known limitations and unresolved issues are documented.

A collection of seven Markdown files alone does not qualify as a completed engineering framework.

---

## 19. Final Product Positioning

AXIOM should be developed as an engineering quality and intelligence layer that can be adopted across software projects and AI coding environments.

Its differentiator should not be the number of skills, agents, or models it supports.

Its differentiator should be the quality of its engineering methodology:

- Explicit engineering contracts.
- Reusable technical standards.
- Independent evidence-based reviews.
- Traceable decisions.
- Controlled resolution workflows.
- Measurable skill quality.
- Human-controlled engineering authority.

**Product principle:**

> AXIOM turns software engineering practices into reusable, verifiable, and model-independent intelligence workflows.

---

## 20. Approval Boundary and Next Phase

This specification defines the proposed AXIOM skill architecture and initial product boundary.

The following activities are intentionally not authorized by this document:

- Creating the actual skill files.
- Generating reviewer agent instructions.
- Writing engineering standards as separate repository artifacts.
- Modifying an existing project repository.
- Installing skills into coding agents.
- Implementing orchestration or automation.
- Modifying application source code.

Those activities require a separate approved implementation plan.

**Recommended next milestone:** Review and approve this specification, then define the AXIOM Skill Contract and Reviewer Protocol in sufficient detail to serve as the authoritative implementation baseline.

**Document End**
