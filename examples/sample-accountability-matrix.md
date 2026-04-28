# AI Accountability Matrix

This example is generic and illustrative. It does not describe a real production system.

## 1. System Metadata

| Field | Value |
|---|---|
| System / model name | Support Routing Assistant |
| Version | 0.4.0 |
| Use case | classify support tickets and recommend routing path |
| Risk tier | Medium |
| Environment | Staging |
| Review date | 2026-04-26 |

## 2. Named Ownership

| Role | Named owner | Accountable for | Backup owner |
|---|---|---|---|
| Business owner | Example Support Lead | user/business outcome, acceptable use, benefit-risk tradeoff | Example Operations Lead |
| Technical owner | Example ML Owner | model behavior, validation, reliability | Example Platform Owner |
| Data owner | Example Data Steward | data quality, lineage, retention, permitted use | Example Privacy Analyst |
| Risk / governance owner | Example Risk Owner | risk controls, policy adherence, escalation rules | Example Compliance Lead |
| Operations owner | Example Operations Owner | monitoring, incident handling, runbook execution | Example Support Manager |

## 3. Decision Rights

| Decision | Decision owner | Required evidence | Escalation trigger |
|---|---|---|---|
| Approve development start | Business owner | intake form, initial risk screen | unclear owner or high-risk use case |
| Approve staging release | Technical owner + governance owner | validation report, model card draft, risk assessment | failed required gate |
| Approve production release | Product owner + governance owner | release gate review, monitoring plan, rollback plan | unresolved high-impact risk |
| Override AI output | Human reviewer | reason code, human review note | repeated overrides or high-risk case |
| Retire or suspend system | Business owner + operations owner | monitoring evidence, incident record, business need review | severe incident or sustained degradation |

## 4. Human Oversight and Escalation

| Trigger | Required human action | Owner | SLA | Evidence retained |
|---|---|---|---|---|
| Low confidence | review and approve routing decision | Support Lead | 1 business day | task ID, confidence, reviewer decision |
| High-risk output | immediate human review | Risk Owner | 4 hours | ticket category, escalation note, final action |
| User appeal | human review of original decision and supporting evidence | Support Manager | 5 business days | appeal record, reviewer rationale, outcome |
| Safety, privacy, legal, or fairness concern | escalate to governance owner | Risk Owner | same day | incident record, severity rating, remediation action |

## 5. Redress and Appeal Pathway

| Step | Description | Owner | Target time |
|---|---|---|---|
| Intake | affected user or operator submits challenge | Support Operations | same day |
| Triage | classify severity and assign reviewer | Support Manager | 1 business day |
| Review | human reviews evidence and system output | Human Reviewer | 3 business days |
| Decision | uphold, correct, reverse, or escalate | Support Manager | 5 business days |
| Feedback loop | update controls, training, UX, or monitoring if needed | Risk Owner | next governance review |

## 6. Audit Trail Requirements

Minimum records to retain:

- system and model version
- ticket reference ID
- output category and route recommendation
- confidence or quality signal
- decision owner
- override or appeal decision
- reviewer role
- timestamp
- final outcome
- control update, if any

## 7. Accountability Review

| Review question | Answer |
|---|---|
| Is every high-impact decision assigned to a named owner? | Yes |
| Is there a documented override path? | Yes |
| Is there a documented appeal path? | Yes |
| Are escalation SLAs defined? | Partially, production SLAs need final confirmation |
| Are audit records sufficient to reconstruct a decision? | Yes for staging, retention policy requires approval before production |
| Are unresolved accountability gaps tracked as risks? | Yes |

## 8. Open Accountability Gaps

| Gap | Severity | Owner | Required action | Due date |
|---|---|---|---|---|
| Production retention policy not finalized | Medium | Data owner | confirm log retention and masking policy | 2026-05-03 |
| Appeal process not tested with realistic cases | Medium | Support Manager | run tabletop review with sample appeal cases | 2026-05-10 |
| High-risk escalation SLA needs governance approval | High | Risk Owner | approve final escalation SLA before production gate | 2026-05-05 |
