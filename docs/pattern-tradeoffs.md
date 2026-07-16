# Accountability Pattern Trade-offs

Accountability is not created by adding a human reviewer, a confidence number, or a larger audit log. A control can shift responsibility, conceal uncertainty, or make redress harder if its decision purpose and failure modes are not explicit.

Use this guide to review any pattern before adopting it.

## Pattern review questions

For each proposed control, record:

| Question | Why it matters |
|---|---|
| Decision purpose | The pattern should support a named decision, right, or responsibility. |
| Accountable owner | Someone must own the control’s effectiveness, not only operate it. |
| Affected people | Users and subjects may experience harms that operators do not see. |
| Evidence | The control needs observable evidence of operation and outcome. |
| Failure mode | Controls can fail silently, be bypassed, or produce false assurance. |
| Incentives | People may optimize for passing the control rather than reducing risk. |
| Data cost | Logging and review can create privacy, security, and retention risk. |
| Human factors | Reviewers may be rushed, under-informed, or biased toward automation. |
| Redress | Affected people need a usable path to contest, correct, or appeal. |
| Expiry | Controls and approvals should be revisited when the system or context changes. |

## Ownership assignment

### Useful when

- the owner has authority and resources to change the system;
- responsibilities are linked to concrete lifecycle decisions;
- escalation and transfer rules are defined;
- performance of the ownership model is reviewed.

### Common failure modes

- one person is named but cannot control budget, data, model, or deployment;
- “business owner” absorbs all accountability while technical and control owners remain vague;
- accountability is assigned after an incident rather than designed before launch;
- responsibility is split across committees so no one can make or stop a decision.

### Evidence

- decision-rights matrix;
- named control and incident owners;
- examples of exercised stop, rollback, exception, and escalation authority;
- owner changes recorded with effective dates.

## Human review

### Useful when

- the reviewer sees the evidence needed to make the decision;
- review time and workload support meaningful attention;
- approval, correction, refusal, and escalation are practical;
- the reviewer’s authority and accountability are explicit;
- review quality and automation bias are measured.

### Common failure modes

- the human rubber-stamps a preselected answer;
- the interface hides uncertainty, alternatives, or source evidence;
- the review occurs after an irreversible action;
- responsibility is shifted to a frontline operator without authority or training;
- disagreement with the model is penalized or operationally costly.

### Evidence

- review-time and workload distribution;
- override, correction, deferral, and disagreement rates with context;
- sampled review-quality assessment;
- outcome comparison when humans accept versus reject recommendations;
- reviewer feedback and escalation usability.

## Uncertainty communication

A model-provided confidence score should not be displayed as probability unless it is calibrated for the relevant task and population.

### Better patterns

- state limitations and missing evidence;
- show source coverage and contradiction;
- distinguish deterministic validation from predictive uncertainty;
- use calibrated risk or probability estimates where validation supports them;
- present an action rule such as review, abstain, or request more information;
- test how users interpret the communication.

### Common failure modes

- users interpret a softmax score or self-reported confidence as correctness probability;
- a precise number increases automation bias;
- one aggregate confidence hides a critical unsupported claim;
- uncertainty is shown but the workflow provides no safe alternative action.

## Audit events and decision provenance

Log the minimum information required for a stated accountability, security, quality, or legal purpose.

### Prefer

- event type and timestamp;
- principal and authorization context;
- system, model, prompt, tool, and policy versions;
- input and output references or hashes where full content is unnecessary;
- decision, reviewer, and disposition;
- control result and exception path;
- retention and access classification.

### Avoid by default

- copying all prompts, documents, personal data, or tool results indefinitely;
- logging secrets and credentials;
- treating an opaque chain-of-thought transcript as an accountability record;
- collecting data without a retention, access, and deletion policy;
- assuming more logs automatically mean better explainability.

Auditability requires reconstructable events and decisions, not maximal surveillance.

## Explanation and contestability

An explanation should serve the affected person’s or operator’s decision need.

Possible purposes include:

- understand the factors and evidence used;
- detect incorrect input or identity matching;
- correct a record;
- challenge an outcome;
- understand the applicable policy or rule;
- obtain human review;
- reproduce or investigate an operational decision.

A generic feature-attribution chart may not meet those needs. For complex systems, explanation may require source evidence, decision rules, limitations, and a route to correction rather than a single algorithmic explanation technique.

## Appeals and redress

A redress mechanism should define:

- who may appeal and how they are authenticated;
- which outcomes are appealable;
- accessible submission channels;
- evidence the appellant can see or provide;
- review independence;
- service-level objectives;
- temporary protections while review is pending;
- correction and downstream remediation;
- communication of outcome and rationale;
- trend analysis without discouraging legitimate appeals.

An appeal button without authority, timelines, or correction capability is not meaningful redress.

## Policy-as-code and automated gates

Automated controls are useful for stable, observable rules. They are weaker for ambiguous legal, ethical, or contextual judgment.

Record:

- source policy and version;
- executable rule and test cases;
- scope and known non-covered cases;
- owner and exception authority;
- false-positive and false-negative review;
- bypass and emergency process;
- evidence that the control runs in the actual deployment path;
- change-management and retirement process.

Do not present a CI check as proof that the underlying policy objective is achieved.

## Review outcome

For every pattern, conclude with one of:

- adopt as designed;
- adopt with conditions;
- pilot and measure;
- redesign;
- reject because the control creates unacceptable secondary risk;
- defer pending evidence.

Record the owner, evidence required, review date, and changes that invalidate the conclusion.
