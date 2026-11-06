# AXIOM Evaluation and Benchmarking Specification

**Document ID:** AX-SPEC-004  
**Document Name:** AXIOM Evaluation and Benchmarking Specification  
**Version:** 0.1.0  
**Status:** Proposed - Pending Approval  
**Framework:** AXIOM - Engineering Intelligence Framework  
**Document Type:** Technical Specification  
**Classification:** Internal Engineering Standard

---

## 1. Purpose

This specification defines the evaluation methodology, benchmarking architecture, performance metrics, validation procedures, and acceptance criteria for AXIOM.

AXIOM is intended to improve software engineering activities through structured skills, independent review processes, engineering standards, evidence-based findings, and human-controlled approval gates.

However, the existence of these components does not establish that they work effectively.

AXIOM must be evaluated to determine whether it can:

1. Execute engineering skills according to their defined contracts.
2. Produce accurate, complete, and traceable engineering artifacts.
3. Identify genuine engineering defects and risks.
4. Avoid unsupported findings and false positives.
5. Detect seeded defects across different engineering domains.
6. Produce consistent results across repeated evaluations.
7. Verify whether proposed corrections actually resolve identified issues.
8. Enforce applicable engineering standards and approval requirements.
9. Improve engineering outcomes compared with unstructured AI assistance.
10. Operate within acceptable cost, latency, and resource constraints.

The purpose of this specification is to establish a repeatable evaluation system rather than rely on subjective impressions of output quality.

## 2. Scope

### 2.1 In Scope

This specification covers:

- Skill-level evaluation.
- Reviewer-level evaluation.
- Engineering standards compliance evaluation.
- Artifact quality assessment.
- End-to-end workflow evaluation.
- Benchmark dataset management.
- Defect detection and classification.
- False-positive and false-negative analysis.
- Reviewer consistency and reproducibility.
- Correction and resolution verification.
- Regression testing.
- Human evaluation and approval.
- Cost, latency, and resource measurements.
- AXIOM release readiness assessment.

### 2.2 Out of Scope

The following are not responsibilities of this specification:

- Training or fine-tuning foundation models.
- Developing a model orchestration platform.
- Implementing AI model routing or provider integrations.
- Guaranteeing that AI-generated engineering decisions are correct.
- Replacing human engineering approval.
- Certifying compliance with external regulatory or industry standards.
- Defining the internal implementation of every AXIOM skill.

AXIOM may use external AI providers and execution platforms, but its evaluation methodology must remain independent of any particular provider.

## 3. Evaluation Principles

AXIOM evaluation MUST follow these principles.

| Principle | Requirement |
|---|---|
| Evidence-based | Evaluation results must reference observable evidence. |
| Reproducible | The same evaluation configuration must be repeatable. |
| Measurable | Performance must be assessed through defined metrics. |
| Risk-aware | Critical engineering failures must not be hidden by aggregate scores. |
| Independent | Benchmark evaluation must avoid simply accepting the output being evaluated as its own proof. |
| Traceable | Results must connect to benchmark cases, standards, and framework versions. |
| Human-governed | Human evaluators retain authority over acceptance and risk decisions. |
| Model-independent | Evaluation must not depend on a single AI model or provider. |
| Regression-aware | Framework changes must be checked against previously validated cases. |
| Context-sensitive | Evaluation must account for project size, domain, complexity, and risk. |

### 3.1 Evidence over Confidence

An AI-generated response stating that a design is secure does not establish that it is secure.

An evaluation must examine supporting evidence, such as:

- Relevant requirements.
- Architecture decisions.
- Source code or configuration.
- Test results.
- Security controls.
- Reproducible observations.
- References to applicable standards.

Confidence scores may be recorded, but confidence must never substitute for verification.

## 4. Evaluation Architecture

AXIOM evaluation is divided into five layers.

### 4.1 Layer 1 - Skill Evaluation

Determines whether individual skills follow their contracts and produce the expected outputs.

Examples:

- Requirements discovery.
- Architecture design.
- Technical specification generation.
- Security review.
- Code review.
- Test design.
- Documentation review.

### 4.2 Layer 2 - Reviewer Evaluation

Determines whether reviewer personas can independently identify, classify, justify, and prioritize engineering issues.

Examples:

- Requirements reviewer.
- Architecture reviewer.
- Security reviewer.
- Database reviewer.
- API reviewer.
- Code quality reviewer.

### 4.3 Layer 3 - Standards Compliance Evaluation

Determines whether AXIOM correctly applies the standards defined in AX-SPEC-003.

It must verify:

- Correct standard identification.
- Correct applicability classification.
- Correct requirement interpretation.
- Correct compliance status.
- Proper handling of exceptions and waivers.
- Evidence supporting compliance decisions.

### 4.4 Layer 4 - Workflow Evaluation

Determines whether multiple AXIOM skills and reviewers work together correctly.

A representative workflow:

Requirements → Architecture → Specification → Independent Review → Finding Resolution → Verification → Human Approval.

The evaluation must detect:

- Missing workflow stages.
- Invalid transitions.
- Unresolved critical findings.
- Lost requirements.
- Inconsistent engineering decisions.
- Unauthorized implementation or approval.
- Incomplete traceability.

### 4.5 Layer 5 - Framework Evaluation

Determines whether AXIOM provides measurable improvement over a baseline engineering workflow.

It evaluates:

- Engineering artifact quality.
- Defect detection effectiveness.
- Review accuracy.
- Consistency.
- Time and cost.
- Regression stability.
- Human usefulness.
- Overall operational reliability.

## 5. Evaluation Taxonomy

AXIOM shall use the following evaluation categories.

| ID | Category | Objective |
|---|---|---|
| AX-EVAL-001 | Contract Compliance | Verify skill contract adherence. |
| AX-EVAL-002 | Artifact Quality | Assess engineering artifact quality. |
| AX-EVAL-003 | Defect Detection | Measure identification of genuine defects. |
| AX-EVAL-004 | Finding Accuracy | Measure precision and evidence quality. |
| AX-EVAL-005 | Reviewer Consistency | Assess reproducibility and agreement. |
| AX-EVAL-006 | Standards Compliance | Verify correct standards application. |
| AX-EVAL-007 | Resolution Verification | Confirm findings are genuinely resolved. |
| AX-EVAL-008 | Workflow Integrity | Validate end-to-end workflow behavior. |
| AX-EVAL-009 | Regression Stability | Detect quality degradation after changes. |
| AX-EVAL-010 | Operational Efficiency | Measure cost, latency, and resource consumption. |
| AX-EVAL-011 | Human Oversight | Verify approval and risk-acceptance boundaries. |
| AX-EVAL-012 | Robustness | Evaluate incomplete, ambiguous, and adversarial inputs. |

## 6. Benchmark Dataset Architecture

Benchmark datasets provide controlled evaluation scenarios.

AXIOM MUST maintain versioned benchmark datasets rather than relying exclusively on manually selected examples during each review.

### 6.1 Dataset Categories

| Dataset | Description | Example |
|---|---|---|
| Requirements Dataset | Requirements with known defects | Ambiguous, conflicting, or unverifiable requirements |
| Architecture Dataset | Architecture designs with known weaknesses | Single points of failure, excessive coupling |
| Security Dataset | Security-related design and implementation cases | Missing authorization, insecure secret handling |
| Database Dataset | Database designs with known defects | Missing constraints, incorrect relationships |
| API Dataset | API specifications with known defects | Missing validation, inconsistent error contracts |
| Code Dataset | Source code containing known defects | Incorrect logic, resource leaks, unsafe operations |
| Testing Dataset | Test plans with known coverage gaps | Missing boundary and failure-path tests |
| Documentation Dataset | Incomplete or inconsistent documentation | Contradictory configuration instructions |
| Workflow Dataset | Multi-stage engineering scenarios | Missing approvals or unresolved findings |

### 6.2 Benchmark Case Structure

Every benchmark case MUST contain:

1. Unique benchmark identifier.
2. Dataset category.
3. Benchmark version.
4. Scenario description.
5. Input artifacts.
6. Project context and constraints.
7. Applicable engineering standards.
8. Expected findings or expected behavior.
9. Expected severity classifications.
10. Evidence references.
11. Accepted alternative interpretations, if applicable.
12. Evaluation instructions.
13. Reference answer or expert-approved assessment criteria.
14. Known limitations and ambiguity notes.

Example benchmark identifier:

`AX-BM-SEC-001`

Example:

**Scenario:** A web application uses role-based access control but performs authorization checks only in the frontend.

Expected evaluation:

- Identify missing server-side authorization.
- Explain the security impact.
- Reference the relevant code or design evidence.
- Classify severity based on the actual exposure.
- Recommend server-side authorization enforcement.
- Verify that the recommendation addresses the identified weakness.

A finding without evidence must not receive full credit merely because its general recommendation sounds reasonable.

### 6.3 Dataset Quality Requirements

Benchmark datasets MUST:

- Contain human-reviewed reference labels.
- Record the source and provenance of benchmark cases.
- Distinguish confirmed defects from subjective preferences.
- Include multiple severity levels.
- Include positive cases without defects.
- Include ambiguous cases where a definitive conclusion is not justified.
- Be version-controlled.
- Record changes to expected findings.
- Avoid leaking benchmark answers into evaluation prompts where this would invalidate the test.

### 6.4 Dataset Splitting

Use three dataset groups:

**Development Set**
- Used to develop and refine skills.
- Feedback and expected answers may be available.

**Validation Set**
- Used to evaluate candidate changes.
- Should not be used as the primary source for prompt tuning.

**Holdout Set**
- Reserved for independent release evaluation.
- Access must be controlled to reduce benchmark overfitting.

The same cases should not be repeatedly used for prompt optimization and then presented as independent evidence of performance.

## 7. Evaluation Metrics

AXIOM MUST distinguish detection effectiveness, finding quality, artifact quality, consistency, and operational performance.

### 7.1 Defect Detection Metrics

The core classification metrics are:

**True Positive (TP):** A genuine defect correctly identified.

**False Positive (FP):** A finding reported as a defect when the evidence does not support that conclusion.

**False Negative (FN):** A genuine defect that was not identified.

**True Negative (TN):** A non-defective condition correctly left unreported.

#### Precision

Measures the proportion of reported findings that are valid.

Precision = TP / (TP + FP)

Higher precision generally indicates fewer unsupported findings.

#### Recall

Measures the proportion of known defects successfully identified.

Recall = TP / (TP + FN)

Higher recall generally indicates fewer missed defects.

#### F1 Score

Balances precision and recall.

F1 = 2 × (Precision × Recall) / (Precision + Recall)

F1 must not be used alone because a high score can conceal domain-specific weaknesses.

#### Severity-Weighted Recall

Measures whether important defects are being detected.

Critical and high-severity defects must receive greater evaluation attention than informational observations.

The severity weighting policy must be defined and versioned before benchmark execution. It must not be adjusted after seeing results to improve reported performance.

### 7.2 Finding Quality Metrics

Every finding should be assessed against:

| Dimension | Evaluation |
|---|---|
| Correctness | Is the reported issue genuine? |
| Evidence | Does the finding identify supporting evidence? |
| Impact | Is the consequence technically accurate? |
| Severity | Is the classification justified? |
| Specificity | Is the affected component or location identifiable? |
| Actionability | Is the proposed correction implementable? |
| Traceability | Can the finding be connected to a requirement or standard? |
| Confidence calibration | Does the expressed confidence reflect actual reliability? |

### 7.3 Artifact Quality Metrics

Engineering artifacts must be evaluated against:

- Correctness.
- Completeness.
- Internal consistency.
- Feasibility.
- Verifiability.
- Security.
- Maintainability.
- Traceability.
- Constraint compliance.
- Clarity.

Each dimension must have defined assessment criteria.

A technically impressive document must not pass if it contains contradictory requirements or unverified assumptions.

### 7.4 Reviewer Consistency Metrics

Evaluate reviewers using:

**Inter-reviewer agreement**

Measures whether different reviewers reach compatible conclusions.

**Intra-reviewer consistency**

Measures whether the same reviewer produces comparable results across repeated runs under equivalent conditions.

**Severity agreement**

Measures whether reviewers classify the same issue at comparable severity levels.

Cohen's Kappa may be used for two reviewers and compatible categorical labels. Fleiss' Kappa may be used for multiple reviewers. These statistics must be interpreted with the underlying label distribution and benchmark characteristics in mind.

Agreement does not automatically establish correctness. Multiple reviewers can agree and still be wrong.

### 7.5 Resolution Verification Metrics

A finding is not resolved merely because an AI system claims that a correction was applied.

Evaluation must determine:

- Whether the correction addresses the original root cause.
- Whether the correction introduces new defects.
- Whether the original finding remains reproducible.
- Whether relevant tests pass.
- Whether affected requirements remain satisfied.
- Whether documentation and implementation remain consistent.

Track:

- Verified resolution rate.
- Reopened finding rate.
- Regression defect rate.
- Incomplete resolution rate.
- Average resolution attempts.

### 7.6 Operational Metrics

Record:

- Total evaluation duration.
- Per-skill execution time.
- Per-reviewer execution time.
- Input and output token usage, where available.
- Estimated model/API cost.
- Number of review iterations.
- Number of human interventions.
- Failure and timeout rates.
- Context size and truncation events.
- Infrastructure requirements.

Operational efficiency must not be improved by silently reducing review coverage or bypassing mandatory validation.

## 8. Skill Evaluation Protocol

Every AXIOM skill MUST undergo contract-level and output-level testing.

### 8.1 Contract Compliance

Verify that the skill:

1. Activates under the correct conditions.
2. Identifies required inputs.
3. Detects missing information.
4. Requests clarification when essential.
5. Follows its defined execution procedure.
6. Applies relevant engineering standards.
7. Produces the expected output structure.
8. Respects safety boundaries.
9. Does not exceed its authorized scope.
10. Communicates limitations and unverified assumptions.

### 8.2 Skill Test Cases

Each skill should be evaluated using:

- Normal input.
- Incomplete input.
- Ambiguous input.
- Conflicting requirements.
- Out-of-scope requests.
- Invalid input.
- Large input.
- Adversarial input.
- Repeated execution.
- Expected failure conditions.

### 8.3 Skill Acceptance Criteria

A skill can pass only when:

- Mandatory contract requirements are satisfied.
- No critical safety or authorization violation occurs.
- Required output fields are present.
- Applicable standards are correctly interpreted.
- Unsupported claims are identified.
- Known limitations are communicated.
- Benchmark results meet the approved thresholds.

A skill must not pass solely because its output is well formatted.

## 9. Reviewer Evaluation Protocol

Reviewer evaluation is a central part of AXIOM.

Reviewers must demonstrate both defect-detection capability and restraint.

### 9.1 Reviewer Test Categories

Each reviewer should be tested against:

1. Known genuine defects.
2. Valid engineering decisions that should not be flagged.
3. Defects with incomplete evidence.
4. Severity classification challenges.
5. Duplicate findings.
6. Contradictory design decisions.
7. Incorrect assumptions.
8. Cross-domain defects.
9. False or misleading source references.
10. Changes intended to resolve earlier findings.

### 9.2 Reviewer Finding Contract

Every reported finding should contain:

| Field | Description |
|---|---|
| Finding ID | Unique identifier |
| Title | Short issue description |
| Severity | Critical, High, Medium, Low, Informational |
| Category | Relevant engineering domain |
| Location | Affected artifact, component, or code location |
| Evidence | Specific supporting evidence |
| Explanation | Technical description of the issue |
| Impact | Consequences if not addressed |
| Recommendation | Proposed correction |
| Standard Reference | Applicable AXIOM standard, if relevant |
| Confidence | Calibrated confidence or uncertainty |
| Status | Open, Accepted, Rejected, Resolved, Verified, Reopened |

### 9.3 Reviewer Acceptance Criteria

A reviewer must:

- Detect required benchmark defects.
- Avoid unsupported findings.
- Provide evidence for each substantive finding.
- Apply severity consistently.
- Distinguish defects from optional improvements.
- Identify uncertainty.
- Avoid duplicate findings.
- Respect the scope of the review.
- Avoid treating its own conclusions as independent verification.

### 9.4 Independent Review

For selected high-risk benchmark cases, use independent reviewers.

Where practical:

- Use separate review contexts.
- Avoid sharing one reviewer's findings with another before initial assessment.
- Use different reviewer criteria.
- Consider different models or providers when available.
- Compare findings against the benchmark reference.

Different models do not automatically provide independence. The evaluation must also consider shared training data, similar reasoning patterns, and common blind spots.

## 10. Standards Compliance Evaluation

This evaluation verifies the application of AX-SPEC-003.

### 10.1 Compliance States

Use the following states:

| State | Meaning |
|---|---|
| PASS | Requirement is satisfied with sufficient evidence. |
| FAIL | Requirement is demonstrably violated. |
| PARTIAL | Some, but not all, applicable conditions are satisfied. |
| NOT_VERIFIED | Insufficient evidence to determine compliance. |
| NOT_APPLICABLE | Requirement does not apply to this project or scenario. |
| WAIVED | An authorized exception has been granted. |

### 10.2 Evaluation Requirements

The evaluator must verify:

- Correct standard version.
- Correct applicability classification.
- Correct interpretation of mandatory and recommended requirements.
- Supporting evidence.
- Correct compliance status.
- Authorized waiver or exception.
- Residual risk.
- Expiry or review condition for exceptions.

`NOT_VERIFIED` must never be converted into `PASS` simply because no defect was found.

`NOT_APPLICABLE` must include a justification.

`WAIVED` must identify the authorized approval and residual risk.

## 11. End-to-End Workflow Benchmarking

AXIOM must be evaluated as an integrated engineering process.

### 11.1 Reference Workflow

1. Project discovery.
2. Requirements analysis.
3. Requirements validation.
4. Architecture design.
5. Architecture review.
6. Technical specification.
7. Specification review.
8. Finding classification.
9. Human decision.
10. Finding resolution.
11. Independent verification.
12. Final engineering approval.

### 11.2 Workflow Validation Scenarios

The benchmark must include scenarios where:

- A mandatory requirement is omitted.
- Architecture conflicts with requirements.
- A security defect survives initial review.
- A reviewer reports a false positive.
- A correction introduces a regression.
- A critical finding remains unresolved.
- An approval is missing.
- A user attempts to bypass a mandatory approval gate.
- A project constraint changes during execution.
- An earlier decision becomes invalid.

### 11.3 Workflow Acceptance Criteria

The workflow must:

- Preserve requirement-to-design traceability.
- Prevent invalid stage transitions.
- Preserve findings and their resolution history.
- Identify unresolved blockers.
- Require authorized human approval at designated gates.
- Detect relevant changes that invalidate earlier reviews.
- Produce a final status consistent with the actual evaluation evidence.

A workflow must not report engineering readiness when mandatory blockers remain unresolved.

## 12. Robustness and Adversarial Evaluation

AXIOM must be tested against realistic imperfect inputs.

Test conditions include:

- Missing requirements.
- Contradictory documents.
- Incorrect assumptions supplied by the user.
- Incomplete repository context.
- Misleading code comments.
- Outdated architecture documents.
- Incorrect external references.
- Large inputs with relevant information distributed across files.
- Attempts to override reviewer boundaries.
- Instructions embedded in untrusted source material.
- Unsupported requests to declare compliance or approve a release.

Expected behavior:

- Identify missing or conflicting information.
- Distinguish facts from assumptions.
- Avoid fabricating repository evidence.
- Preserve the intended scope.
- Treat external or repository content as data, not authority.
- Escalate decisions requiring human approval.

## 13. Benchmark Execution Procedure

Every formal benchmark run must follow a controlled process.

### Phase 1 - Configuration

Record:

- AXIOM version.
- Skill versions.
- Reviewer versions.
- Engineering standards version.
- Model/provider and model identifier.
- Relevant model parameters, where available.
- Benchmark dataset version.
- Evaluation configuration.
- Date and execution environment.

### Phase 2 - Input Preparation

- Select the benchmark dataset.
- Verify dataset integrity.
- Confirm the reference labels.
- Prepare the input artifacts.
- Remove unintended answer leakage.
- Record project constraints.

### Phase 3 - Execution

- Run the target skill, reviewer, or workflow.
- Capture outputs.
- Record execution failures.
- Record token usage and latency where available.
- Preserve the execution configuration.

### Phase 4 - Scoring

- Compare results against benchmark references.
- Calculate applicable metrics.
- Assess finding correctness and severity.
- Identify false positives and false negatives.
- Assess traceability and evidence quality.
- Record unresolved evaluation disagreements.

### Phase 5 - Human Review

A qualified human evaluator must review:

- Critical and high-severity findings.
- Disputed benchmark labels.
- False-positive classifications.
- Incorrect or incomplete corrections.
- Unexpected benchmark behavior.
- Potential safety or authorization violations.

### Phase 6 - Reporting

Generate a benchmark report containing:

- Overall evaluation status.
- Dataset and configuration details.
- Metric results.
- Domain-level performance.
- Failed benchmark cases.
- Critical defects.
- Regression comparison.
- Cost and latency.
- Known limitations.
- Human evaluator observations.
- Recommended corrective actions.

### Phase 7 - Approval

A designated human authority determines whether the candidate is:

- Accepted.
- Accepted with limitations.
- Rejected.
- Returned for remediation.

## 14. Baseline Comparison

AXIOM must demonstrate value against a defined baseline.

### 14.1 Required Baselines

**Baseline A - Unstructured AI Assistance**

A general AI model receives the same engineering input without AXIOM-specific skills, reviewer protocols, or standards enforcement.

**Baseline B - Structured Single-Pass AI Review**

A general AI model receives a standardized review instruction, but does not use AXIOM's independent review and resolution workflow.

**Candidate C - AXIOM**

The same engineering input is processed through the applicable AXIOM workflow.

Where feasible, all baselines should use the same model and comparable context budgets to reduce confounding variables.

### 14.2 Comparison Dimensions

Compare:

- Defect precision.
- Defect recall.
- Severity-weighted recall.
- Evidence quality.
- Artifact quality.
- Reviewer consistency.
- False-positive rate.
- Resolution verification.
- Execution time.
- Cost.
- Human intervention requirements.

### 14.3 Comparison Rules

- Use equivalent input artifacts.
- Use equivalent project constraints.
- Record model and configuration differences.
- Repeat stochastic evaluations.
- Use the same reference labels.
- Report limitations and uncertainty.
- Avoid selecting only benchmark cases favorable to AXIOM.

AXIOM should be considered valuable only when it demonstrates meaningful improvement in relevant engineering outcomes without unacceptable increases in cost, complexity, or false-positive findings.

## 15. Regression Testing

Every material change to a skill, reviewer, standard, or workflow must trigger appropriate regression evaluation.

### 15.1 Change Categories

| Change | Required Evaluation |
|---|---|
| Skill prompt change | Skill contract and relevant benchmark tests |
| Reviewer logic change | Reviewer accuracy and consistency |
| Standard update | Standards compliance regression |
| Workflow change | End-to-end workflow regression |
| Model/provider change | Compatibility and performance regression |
| Finding schema change | Output contract and data integrity tests |
| Approval policy change | Human oversight and authorization tests |

### 15.2 Regression Requirements

The regression system must detect:

- Newly missed defects.
- Newly introduced false positives.
- Severity classification degradation.
- Missing evidence.
- Broken traceability.
- Incorrect compliance decisions.
- Unauthorized workflow transitions.
- Reduced reproducibility.
- Increased operational failures.

Previous benchmark performance must be retained so that new versions can be compared against earlier approved versions.

## 16. Evaluation Thresholds and Release Gates

Thresholds are necessary, but arbitrary numerical thresholds can create false confidence.

AXIOM will initially use provisional thresholds. They must be calibrated against benchmark evidence before becoming permanent release requirements.

### 16.1 Proposed Initial Thresholds

| Metric | Proposed Threshold | Status |
|---|---:|---|
| Mandatory skill contract compliance | 100% | Proposed hard gate |
| Critical seeded defect recall | 100% | Proposed hard gate |
| High-severity defect recall | ≥ 95% | Provisional |
| Overall defect precision | ≥ 90% | Provisional |
| Overall defect recall | ≥ 90% | Provisional |
| Required evidence coverage | 100% | Proposed hard gate |
| Mandatory approval enforcement | 100% | Proposed hard gate |
| Unresolved critical blocker leakage | 0 | Proposed hard gate |
| Benchmark execution completion | ≥ 95% | Provisional |
| Regression on approved critical cases | No unexplained regression | Proposed hard gate |

These values are initial engineering targets, not demonstrated AXIOM performance.

A benchmark must also report sample size and confidence intervals. A result of 100% recall on five examples is not sufficient evidence of reliable detection.

### 16.2 Release Gates

**Gate 1 - Skill Readiness**

- Skill contract validated.
- Required input and output behavior tested.
- No critical boundary violations.

**Gate 2 - Reviewer Readiness**

- Detection performance evaluated.
- False-positive behavior assessed.
- Evidence and severity quality validated.

**Gate 3 - Standards Readiness**

- Applicable standards correctly interpreted.
- Compliance states correctly assigned.
- Waiver and exception rules enforced.

**Gate 4 - Workflow Readiness**

- End-to-end workflow tested.
- Traceability preserved.
- Approval gates enforced.
- Critical blockers correctly handled.

**Gate 5 - Release Readiness**

- Regression suite passes.
- Holdout benchmark completed.
- Known limitations documented.
- Evaluation report approved by a human authority.

Failure of a hard gate blocks release regardless of aggregate quality score.

## 17. Evaluation Reports

Every formal evaluation must produce a structured report.

### 17.1 Report Structure

1. Evaluation ID.
2. AXIOM version.
3. Target skill/reviewer/workflow.
4. Benchmark dataset and version.
5. Execution configuration.
6. Evaluation date.
7. Evaluator information.
8. Metric results.
9. Benchmark case results.
10. Critical and high-severity failures.
11. False-positive and false-negative analysis.
12. Regression comparison.
13. Cost and latency.
14. Known limitations.
15. Corrective actions.
16. Final evaluation status.
17. Human approval record.

### 17.2 Evaluation Status

| Status | Meaning |
|---|---|
| PASS | All mandatory acceptance requirements satisfied. |
| FAIL | One or more mandatory requirements failed. |
| CONDITIONAL_PASS | Approved with explicitly documented limitations. |
| INCOMPLETE | Insufficient evaluation coverage or evidence. |
| NOT_EVALUATED | No formal evaluation has been completed. |

A conditional pass must identify the approving authority, accepted limitations, residual risks, and review conditions.

## 18. Evaluation Data and Result Integrity

Evaluation records must be reliable and auditable.

AXIOM should maintain:

- Immutable evaluation identifiers.
- Versioned benchmark datasets.
- Versioned evaluation configurations.
- Original skill and reviewer outputs.
- Reference labels.
- Metric calculation results.
- Human evaluation decisions.
- Approval records.
- Regression history.

Sensitive source code, credentials, proprietary project information, and personal information must not be copied into benchmark datasets without appropriate authorization and data handling controls.

Evaluation artifacts must follow the project's security and retention requirements.

## 19. Governance and Responsibilities

| Role | Responsibility |
|---|---|
| Framework Maintainer | Maintains evaluation architecture and benchmark definitions. |
| Skill Author | Provides skill-specific test cases and resolves failures. |
| Reviewer Author | Maintains reviewer criteria and evaluation coverage. |
| Benchmark Evaluator | Assesses results against approved reference criteria. |
| Security Evaluator | Reviews security and safety-related evaluation cases. |
| Human Engineering Authority | Approves releases and accepts documented risks. |

One individual may hold multiple roles in an early-stage implementation, but high-risk release decisions should receive independent review wherever practical.

AI agents may assist in evaluation, but they cannot independently authorize their own release.

## 20. Evaluation and Benchmarking Lifecycle

The lifecycle is:

1. Define evaluation objectives.
2. Create or select benchmark cases.
3. Validate reference labels.
4. Freeze the benchmark version.
5. Configure the target AXIOM version.
6. Execute benchmark tests.
7. Calculate evaluation metrics.
8. Conduct human review.
9. Compare against baseline.
10. Perform regression analysis.
11. Document failures and limitations.
12. Apply corrective changes.
13. Repeat affected evaluations.
14. Obtain human approval.
15. Publish the approved evaluation report.

The lifecycle must be repeatable and auditable.

## 21. Initial Implementation Roadmap

The evaluation system should be implemented incrementally.

### Phase 1 - Evaluation Foundation

Deliverables:

- Evaluation taxonomy.
- Benchmark case schema.
- Evaluation report schema.
- Metric definitions.
- Manual benchmark execution procedure.
- Initial reference datasets.

Acceptance:

- A benchmark case can be created, executed, assessed, and documented consistently.

### Phase 2 - Skill and Reviewer Evaluation

Deliverables:

- Skill contract test suite.
- Reviewer benchmark suite.
- Finding validation criteria.
- Precision and recall calculations.
- False-positive and false-negative reports.

Acceptance:

- Individual AXIOM skills and reviewers can be assessed against known reference cases.

### Phase 3 - Standards and Workflow Evaluation

Deliverables:

- Standards compliance test suite.
- Workflow integrity scenarios.
- Approval gate tests.
- Finding resolution verification tests.
- Traceability validation.

Acceptance:

- AXIOM can demonstrate that its engineering workflow preserves required controls and correctly handles known failure scenarios.

### Phase 4 - Regression and Baseline Benchmarking

Deliverables:

- Version comparison.
- Regression dataset.
- Baseline evaluation configurations.
- Holdout benchmark.
- Cost and latency reporting.

Acceptance:

- AXIOM changes can be compared against previous approved versions and unstructured AI baselines.

### Phase 5 - Evaluation Automation

Deliverables:

- Automated benchmark execution where practical.
- Metric calculation pipeline.
- Evaluation result storage.
- Regression reporting.
- Release-readiness summary.

Acceptance:

- Repeated evaluations can be executed with consistent configuration and auditable results.

Automation must not eliminate human review for high-risk decisions.

## 22. Proposed Architecture Decisions

The following decisions are proposed for future formalization as AXIOM Architecture Decision Records.

| ADR | Decision |
|---|---|
| AX-ADR-031 | AXIOM requires a dedicated evaluation layer. |
| AX-ADR-032 | Benchmark datasets must be version-controlled. |
| AX-ADR-033 | Development, validation, and holdout datasets must be separated. |
| AX-ADR-034 | Evaluation must measure both false positives and false negatives. |
| AX-ADR-035 | Finding correctness requires evidence-based assessment. |
| AX-ADR-036 | Reviewer agreement must not be treated as proof of correctness. |
| AX-ADR-037 | Critical approval and safety requirements are hard release gates. |
| AX-ADR-038 | AXIOM must be compared against defined non-AXIOM baselines. |
| AX-ADR-039 | Material framework changes require regression evaluation. |
| AX-ADR-040 | AI-generated evaluation results require human oversight. |
| AX-ADR-041 | Benchmark thresholds remain provisional until empirically calibrated. |
| AX-ADR-042 | Evaluation results must identify exact framework, dataset, and configuration versions. |

## 23. Initial Acceptance Criteria for AX-SPEC-004

This specification itself is considered ready for approval when:

- Evaluation categories are defined.
- Skill, reviewer, standards, and workflow evaluation are covered.
- Benchmark dataset requirements are documented.
- Core performance metrics are defined.
- False-positive and false-negative behavior is addressed.
- Human evaluation responsibilities are defined.
- Regression requirements are documented.
- Baseline comparison methodology is specified.
- Release gates and provisional thresholds are documented.
- Evaluation report requirements are established.
- No claim of AXIOM effectiveness is made without benchmark evidence.

## 24. Known Limitations and Open Questions

The following issues require resolution before a production-grade evaluation system is implemented.

1. **Benchmark domain coverage:** Which engineering domains should be included in the first validated benchmark?
2. **Reference label authority:** Who approves the expected findings, especially where engineering judgments are subjective?
3. **Severity calibration:** How should severity be calibrated across different project types and threat models?
4. **Model variability:** How many repeated executions are required to distinguish genuine improvement from random variation?
5. **Benchmark contamination:** How will holdout cases remain protected from prompt and skill optimization?
6. **Cost boundaries:** What cost and latency limits are acceptable for each evaluation category?
7. **External standards:** How will AXIOM track applicable external standards without reproducing restricted material?
8. **Human evaluator agreement:** How will disagreements between qualified human evaluators be resolved?
9. **Benchmark maintenance:** How will outdated cases be revised without compromising historical comparisons?
10. **Release policy:** Which thresholds will become mandatory after sufficient benchmark data has been collected?

These questions must be answered through implementation evidence and governance decisions, not arbitrary assumptions.

## 25. Final Engineering Principle

AXIOM must not evaluate itself through the quality of its own explanations.

Its effectiveness must be demonstrated through controlled benchmark cases, independently assessed findings, reproducible results, verified corrections, regression testing, and measurable improvements against defined baselines.

A skill is not reliable because it follows a well-written prompt.

A reviewer is not effective because it produces a long list of findings.

A workflow is not safe because it contains approval stages in its documentation.

**AXIOM is effective only when its engineering decisions and outputs withstand evidence-based evaluation.**

---

**Document End**

**AX-SPEC-004 | Version 0.1.0 | Proposed - Pending Approval**
