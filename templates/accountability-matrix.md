# AI Accountability Matrix

Use this template to define who is accountable for an AI system, what decisions they own, and how users or operators can challenge or escalate outcomes.

## 1. System Metadata

| Field | Value |
|---|---|
| System / model name | `[TBD]` |
| Version | `[TBD]` |
| Use case | `[TBD]` |
| Risk tier | `[low / medium / high]` |
| Environment | `[development / staging / production]` |
| Review date | `[TBD]` |

## 2. Named Ownership

| Role | Named owner | Accountable for | Backup owner |
|---|---|---|---|
| Business owner | `[TBD]` | user/business outcome, acceptable use, benefit-risk tradeoff | `[TBD]` |
| Technical owner | `[TBD]` | model behavior, technical validation, system reliability | `[TBD]` |
| Data owner | `[TBD]` | data quality, lineage, retention, permitted use | `[TBD]` |
| Risk / governance owner | `[TBD]` | risk controls, policy adherence, escalation rules | `[TBD]` |
| Operations owner | `[TBD]` | monitoring, incident handling, runbook execution | `[TBD]` |

## 3. Decision Rights

| Decision | Decision owner | Required evidence | Escalation trigger |
|---|---|---|---|
| Approve development start | `[TBD]` | intake form, initial risk screen | unclear owner or high-risk use case |
| Approve staging release | `[TBD]` | validation report, model card draft, risk assessment | failed required gate |
| Approve production release | `[TBD]` | release gate review, monitoring plan, rollback plan | unresolved high-impact risk |
| Override AI output | `[TBD]` | reason code, human review note | repeated overrides or high-risk case |
| Retire or suspend system | `[TBD]` | monitoring evidence, incident record, business need review | severe incident or sustained degradation |

## 4. Human Oversight and Escalation

| Trigger | Required human action | Owner | SLA | Evidence retained |
|---|---|---|---|---|
| Low confidence | `[review / approve / reject]` | `[TBD]` | `[TBD]` | `[TBD]` |
| High-risk output | `[TBD]` | `[TBD]` | `[TBD]` | `[TBD]` |
| User appeal | `[TBD]` | `[TBD]` | `[TBD]` | `[TBD]` |
| Safety, privacy, legal, or fairness concern | `[TBD]` | `[TBD]` | `[TBD]` | `[TBD]` |

## 5. Redress and Appeal Pathway

| Step | Description | Owner | Target time |
|---|---|---|---|
| Intake | affected user or operator submits challenge | `[TBD]` | `[TBD]` |
| Triage | classify severity and assign reviewer | `[TBD]` | `[TBD]` |
| Review | human reviews evidence and system output | `[TBD]` | `[TBD]` |
| Decision | uphold, correct, reverse, or escalate | `[TBD]` | `[TBD]` |
| Feedback loop | update controls, training, UX, or monitoring if needed | `[TBD]` | `[TBD]` |

## 6. Audit Trail Requirements

Minimum records to retain:

- system and model version
- input summary or reference ID
- output summary
- confidence or quality signal
- decision owner
- override or appeal decision
- reviewer name or role
- timestamp
- final outcome
- control update, if any

## 7. Accountability Review

| Review question | Answer |
|---|---|
| Is every high-impact decision assigned to a named owner? | `[TBD]` |
| Is there a documented override path? | `[TBD]` |
| Is there a documented appeal path? | `[TBD]` |
| Are escalation SLAs defined? | `[TBD]` |
| Are audit records sufficient to reconstruct a decision? | `[TBD]` |
| Are unresolved accountability gaps tracked as risks? | `[TBD]` |

## 8. Open Accountability Gaps

| Gap | Severity | Owner | Required action | Due date |
|---|---|---|---|---|
| `[TBD]` | `[low/medium/high]` | `[TBD]` | `[TBD]` | `[TBD]` |
