# AI Accountability Design Patterns

[![NIST AI RMF](https://img.shields.io/badge/NIST%20AI%20RMF-Informed-0055A4?style=flat-square)](https://airc.nist.gov/home)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)

A practitioner pattern catalog for assigning decision responsibility, designing meaningful human review, preserving decision provenance, and providing correction, appeal, and redress.

The repository treats accountability as an operating property that must be evidenced. Naming an owner, inserting a human, displaying a confidence score, or collecting more logs does not by itself make a system accountable.

## Start here

| Artifact | Use it for |
|---|---|
| [`docs/pattern-tradeoffs.md`](docs/pattern-tradeoffs.md) | reviewing control purpose, evidence, human factors, privacy cost, and failure modes |
| [`templates/accountability-matrix.md`](templates/accountability-matrix.md) | assigning decision, control, incident, and redress responsibilities |
| [`examples/sample-accountability-matrix.md`](examples/sample-accountability-matrix.md) | fictional worked example |
| [`docs/nist-rmf-mapping.md`](docs/nist-rmf-mapping.md) | practitioner cross-reference to selected NIST AI RMF concepts |

## The accountability test

For any important outcome, another reviewer should be able to determine:

1. who was authorized to make or approve the decision;
2. which system, model, policy, data, and tool versions contributed;
3. what evidence and uncertainty were visible at the decision point;
4. which controls ran and whether exceptions were used;
5. who could stop, override, correct, or reverse the outcome;
6. how an affected person or operator could contest it;
7. who owned remediation and downstream correction;
8. when the decision or control would be reviewed again.

An audit trail without usable ownership or redress is only observability. Ownership without authority is only attribution.

## Pattern catalog

### 1. Decision-rights map

**Problem:** responsibility is distributed across product, engineering, operations, legal, safety, privacy, and executive forums, but no one knows who can make, stop, or accept a decision.

**Pattern:** document decision types separately from job titles. For each decision, record the accountable owner, required reviewers, evidence package, escalation path, and transfer rule.

**Evidence:** approved matrix, exercised decisions, owner changes, and examples of stop/exception authority.

**Failure modes:** committee accountability, nominal owners without authority, and unclear transfer during incident or organizational change.

### 2. Lifecycle inventory with accountable state

**Problem:** an inventory lists systems but does not show whether ownership and controls are active.

**Pattern:** maintain versioned records for purpose, prohibited use, owner, risk context, deployment state, model/tool versions, review status, next review trigger, and retirement path.

**Evidence:** reconciliation with deployed systems, stale-record review, and owner attestations.

**Failure modes:** inventory as spreadsheet theater, duplicate systems under different names, and retired entries that remain operational.

### 3. Evidence-bearing approval gate

**Problem:** approval is recorded as a checkbox without showing what was reviewed or which uncertainty remains.

**Pattern:** require a versioned evidence package and distinguish:

- hard-gate result;
- evidence gap;
- blocker;
- required action;
- condition;
- exception;
- accepted residual risk.

**Evidence:** signed decision record, source versions, named owner, expiry, and re-evaluation trigger.

**Failure modes:** approval detached from evidence, weighted averages overriding failed controls, and permanent approval for a changing system.

### 4. Meaningful human review

**Problem:** a human is nominally in the loop but lacks time, information, authority, or a usable correction path.

**Pattern:** define the decision the human makes, the evidence displayed, review timing, permitted actions, and consequences of approval, rejection, delay, and no response.

**Evidence:** review time, override and correction behavior, sampled review quality, disagreement analysis, and reviewer feedback.

**Failure modes:** rubber-stamping, automation bias, frontline responsibility without authority, and review after irreversible execution.

### 5. Calibrated uncertainty and limitation communication

**Problem:** users cannot distinguish supported results from weak, incomplete, or conflicting evidence.

**Pattern:** communicate limitations, source coverage, contradiction, and action guidance. Display numerical confidence as probability only when calibration and user-interpretation evidence support that meaning.

**Evidence:** calibration data where applicable, comprehension testing, and analysis of how the display changes decisions.

**Failure modes:** self-reported model confidence presented as correctness probability, precise numbers that increase automation bias, and uncertainty displays with no safe alternative action.

### 6. Minimal decision provenance

**Problem:** an important action cannot be reconstructed after the fact.

**Pattern:** retain the minimum privacy-aware event record needed to reconstruct principal, authorization, system and policy versions, relevant inputs or references, tool actions, reviewer decisions, control results, and disposition.

**Evidence:** reconstruction exercises, access controls, retention/deletion tests, and sampled event completeness.

**Failure modes:** logging everything indefinitely, secrets or personal data in logs, opaque records with no decision meaning, and assuming chain-of-thought is an accountability artifact.

### 7. Explanation for action

**Problem:** an affected person or operator receives an outcome but cannot understand, correct, or challenge the basis.

**Pattern:** design the explanation around the next legitimate action: inspect evidence, correct data, understand the rule, seek review, or appeal. Use source evidence and decision logic where feature attribution is not meaningful.

**Evidence:** user comprehension, correction success, appeal outcomes, and accessibility review.

**Failure modes:** generic explanations, technical plots with no actionable meaning, and disclosure that exposes sensitive data or enables gaming without considering alternatives.

### 8. Override and safe interruption

**Problem:** operators cannot stop or reverse an unsafe, incorrect, or unauthorized path.

**Pattern:** provide bounded stop, defer, correction, rollback, and escalation actions with clear authority and verification of the resulting state.

**Evidence:** exercised stop and recovery tests, completion verification, and incident records.

**Failure modes:** UI stop that does not cancel delegated work, overrides that are not logged, and correction without downstream remediation.

### 9. Appeal and redress

**Problem:** an affected person cannot contest an outcome or obtain correction.

**Pattern:** define eligibility, accessible channels, evidence rights, independent review, service objectives, temporary protection, correction, downstream remediation, and communication of the result.

**Evidence:** completion time, accessibility, overturn and correction patterns, unresolved cases, and downstream repair.

**Failure modes:** appeal button with no authority, burdensome evidence requirements, review by the original decision-maker, and correction that does not propagate.

### 10. Executable control with exception governance

**Problem:** policy statements do not consistently reach deployed workflows.

**Pattern:** automate stable and observable rules while preserving source policy, scope, test cases, exception authority, false-positive/negative review, bypass monitoring, and change control.

**Evidence:** tests in the actual deployment path, exception records, bypass detection, and control-version provenance.

**Failure modes:** “policy as code” claims for contextual judgment, CI checks disconnected from production, and emergency bypasses that become permanent.

### 11. Sunset and renewal

**Problem:** systems and approvals persist after purpose, evidence, ownership, or context changes.

**Pattern:** define expiry, renewal evidence, inactivity or drift triggers, retirement owner, data/memory disposition, and dependency cleanup.

**Evidence:** completed renewal and retirement records, access revocation, and post-retirement verification.

**Failure modes:** automatic renewal, orphaned credentials and data, and review dates with no consequence.

## Applying a pattern

For each use, record:

- decision or right the pattern supports;
- accountable owner and authority;
- affected people and representatives;
- evidence expected;
- control and human-factor failure modes;
- privacy and security cost;
- exception and escalation path;
- review date or invalidation trigger.

See [`docs/pattern-tradeoffs.md`](docs/pattern-tradeoffs.md) for detailed review prompts.

## Relationship to other repositories

| Repository | Distinct role |
|---|---|
| [`governance-playbook`](https://github.com/simaba/governance-playbook) | organizational forums and lifecycle operating model |
| [`release-governance`](https://github.com/simaba/release-governance) | release-stage evidence and decisions |
| [`multi-agent-governance`](https://github.com/simaba/multi-agent-governance) | authority propagation and containment across agents and tools |
| [`agent-eval`](https://github.com/simaba/agent-eval) | evaluation validity and decision semantics |

## Maturity and scope

This is a practitioner pattern catalog, not a certified accountability framework, legal assessment, or regulatory determination. The patterns should be adapted to the actual decision authority, rights, user population, jurisdiction, and harm model.

References to NIST AI RMF or EU AI Act concepts are practitioner mappings and should be checked against official sources and qualified review.

---

*Maintained by [Sima Bagheri](https://github.com/simaba).*
