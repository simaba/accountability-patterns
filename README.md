# AI Accountability Design Patterns

[![NIST AI RMF](https://img.shields.io/badge/NIST%20AI%20RMF-Informed-0055A4?style=flat-square)](https://airc.nist.gov/home)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)
[![Discussions](https://img.shields.io/badge/Discussions-Join-7289da?style=flat-square&logo=github)](https://github.com/simaba/accountability-patterns/discussions)

A catalog of design patterns for building accountable AI systems in regulated and high-accountability environments.

Each pattern provides a problem statement, solution structure, implementation guidance, and practitioner mapping to NIST AI RMF and EU AI Act concepts.

## Maturity

This is a **practitioner pattern catalog**. It is intended to help teams reason about ownership, oversight, escalation, appeal, and redress. It is not a legal determination, regulatory assessment, or certified accountability framework.

## Purpose

Use this repository when you need to define:

- named ownership for AI systems
- decision rights and approval responsibility
- human oversight and escalation paths
- override, appeal, and redress mechanisms
- audit trail expectations for AI-assisted decisions

For the broader enterprise operating model, use [`governance-playbook`](https://github.com/simaba/governance-playbook).
For release-stage gates, use [`release-governance`](https://github.com/simaba/release-governance).
For a runnable release validator, use [`release-checklist`](https://github.com/simaba/release-checklist).

## Accountability model

AI accountability means that outcomes have clear ownership, decisions can be traced, responsibilities are explicit, and affected users or operators have a path for review or redress when something goes wrong.

The NIST AI RMF identifies accountability as one characteristic of trustworthy AI. This repository translates that concept into practical design patterns and templates.

## Practical artifacts

| Artifact | Use for |
|---|---|
| [`templates/accountability-matrix.md`](templates/accountability-matrix.md) | Defining named ownership, decision rights, escalation, redress, and audit requirements |
| [`examples/sample-accountability-matrix.md`](examples/sample-accountability-matrix.md) | Reviewing a filled generic example of accountability design in practice |

## Pattern catalog

### Governance patterns

| Pattern | Problem | Solution |
|---|---|---|
| **Model Inventory** | No central registry of AI systems in production | Maintain a versioned, owner-assigned inventory of all deployed models |
| **Ownership Assignment** | Unclear who is responsible when an AI system fails | Assign a named technical owner and business owner to every AI system |
| **AI Policy Cascade** | Governance policies not reaching practitioners | Publish policy as code and embed governance rules in CI/CD pipelines |
| **Governance Gate** | AI systems deployed without appropriate review | Require signed-off checklists at defined lifecycle milestones |

### Transparency patterns

| Pattern | Problem | Solution |
|---|---|---|
| **Model Card** | No documentation of model capabilities and limitations | Create a structured model card for every production model |
| **Decision Log** | AI decisions not auditable after the fact | Log inputs, outputs, model version, and confidence for every decision |
| **Confidence Surfacing** | Users cannot tell when AI is uncertain | Surface confidence scores and uncertainty estimates in the UI |
| **Explanation on Demand** | Stakeholders cannot understand AI decisions | Provide an explanation mechanism for high-impact decisions where appropriate |

### Human-oversight patterns

| Pattern | Problem | Solution |
|---|---|---|
| **Human-in-the-Loop Gate** | High-stakes decisions made autonomously | Require human review before action for decisions above a risk threshold |
| **Override Mechanism** | Operators cannot override erroneous AI decisions | Implement a documented, audited override pathway with reason capture |
| **Escalation Ladder** | Edge cases fall through without review | Define a tiered escalation path for low-confidence or novel inputs |
| **Sunset Clause** | Models remain in production past their useful life | Set mandatory model review dates and require affirmative renewal to continue |

### Redress patterns

| Pattern | Problem | Solution |
|---|---|---|
| **Adverse Action Explanation** | Affected individuals cannot understand why they were denied | Provide plain-language explanations with specific contributing factors where applicable |
| **Appeal Pathway** | No mechanism for contesting AI decisions | Implement a formal appeal process with human review and documented outcomes |
| **Impact Audit** | Unknown whether an AI system is causing disproportionate harm | Conduct regular impact audits against relevant risk and fairness criteria |

## NIST AI RMF mapping

See [docs/nist-rmf-mapping.md](docs/nist-rmf-mapping.md) for a full practitioner mapping of each pattern to NIST AI RMF functions and subcategories.

## Scope and disclaimer

This repository is shared in a personal capacity. It is not legal advice, compliance certification, regulatory approval, safety certification, or official guidance from NIST, the EU, ISO, or any employer.

References to accountability, redress, human oversight, NIST AI RMF, EU AI Act, or regulated-industry obligations are practitioner mappings and examples. Always verify against official sources and internal requirements before using these patterns for compliance, safety, or release decisions.

## Related repositories

| Repository | Purpose |
|---|---|
| [governance-playbook](https://github.com/simaba/governance-playbook) | End-to-end governance playbook |
| [release-checklist](https://github.com/simaba/release-checklist) | Release gate framework and CLI |
| [release-governance](https://github.com/simaba/release-governance) | Lifecycle governance for AI releases |
| [nist-rmf-guide](https://github.com/simaba/nist-rmf-guide) | NIST AI RMF practitioner guide |
| [ai-prism](https://github.com/simaba/ai-prism) | Curated governance resources |

*Maintained by [Sima Bagheri](https://github.com/simaba) · Connect on [LinkedIn](https://www.linkedin.com/in/simaba/)*
