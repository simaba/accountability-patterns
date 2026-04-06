# AI Accountability Design Patterns

[![NIST AI RMF](https://img.shields.io/badge/NIST%20AI%20RMF-Aligned-0055A4?style=flat-square)](https://airc.nist.gov/home)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)
[![Discussions](https://img.shields.io/badge/Discussions-Join-7289da?style=flat-square&logo=github)](https://github.com/simaba/ai-accountability-design-patterns/discussions)

A catalog of design patterns for building accountable AI systems in regulated industries.
Each pattern provides a problem statement, solution structure, implementation guidance,
and mapping to NIST AI RMF and EU AI Act requirements.

---

## What Is AI Accountability?

AI accountability means that individuals and organizations can be held responsible
for the outcomes of AI systems — that there are clear lines of ownership, transparent
decision processes, and mechanisms for redress when things go wrong.

The NIST AI RMF defines accountability as one of seven characteristics of trustworthy AI:
> *"AI actors should be accountable for the development, deployment, and impacts of AI
> systems, including supporting human oversight."*

---

## Pattern Catalog

### Governance Patterns

| Pattern | Problem | Solution |
|---|---|---|
| **Model Inventory** | No central registry of AI systems in production | Maintain a versioned, owner-assigned inventory of all deployed models |
| **Ownership Assignment** | Unclear who is responsible when an AI system fails | Assign a named technical owner and business owner to every AI system |
| **AI Policy Cascade** | Governance policies not reaching practitioners | Publish policy as code — embed governance rules in CI/CD pipelines |
| **Governance Gate** | AI systems deployed without appropriate review | Require signed-off checklists at defined lifecycle milestones |

### Transparency Patterns

| Pattern | Problem | Solution |
|---|---|---|
| **Model Card** | No documentation of model capabilities and limitations | Create a structured model card for every production model |
| **Decision Log** | AI decisions not auditable after the fact | Log inputs, outputs, model version, and confidence for every decision |
| **Confidence Surfacing** | Users cannot tell when AI is uncertain | Surface confidence scores and uncertainty estimates in the UI |
| **Explanation on Demand** | Stakeholders cannot understand AI decisions | Implement on-demand SHAP/LIME explanations for high-stakes decisions |

### Human Oversight Patterns

| Pattern | Problem | Solution |
|---|---|---|
| **Human-in-the-Loop Gate** | High-stakes decisions made autonomously | Require human review before action for decisions above a risk threshold |
| **Override Mechanism** | Operators cannot override erroneous AI decisions | Implement a documented, audited override pathway with reason capture |
| **Escalation Ladder** | Edge cases fall through without review | Define a tiered escalation path for low-confidence or novel inputs |
| **Sunset Clause** | Models remain in production past their useful life | Set mandatory model review dates; require affirmative renewal to continue |

### Redress Patterns

| Pattern | Problem | Solution |
|---|---|---|
| **Adverse Action Explanation** | Affected individuals cannot understand why they were denied | Generate plain-language explanations with specific contributing factors |
| **Appeal Pathway** | No mechanism for contesting AI decisions | Implement a formal appeal process with human review and documented outcomes |
| **Impact Audit** | Unknown whether AI system is causing disproportionate harm | Conduct regular disparate impact audits by protected characteristics |

---

## NIST AI RMF Mapping

See [docs/nist-rmf-mapping.md](docs/nist-rmf-mapping.md) for a full mapping of each
pattern to NIST AI RMF functions and subcategories.

---

## Ecosystem

| Repository | Purpose |
|---|---|
| [enterprise-ai-governance-playbook](https://github.com/simaba/enterprise-ai-governance-playbook) | End-to-end governance playbook |
| [ai-release-readiness-checklist](https://github.com/simaba/ai-release-readiness-checklist) | Release gate framework + CLI |
| [ai-risk-taxonomy](https://github.com/simaba/ai-risk-taxonomy) | Structured AI risk taxonomy |
| [nist-ai-rmf-implementation-guide](https://github.com/simaba/nist-ai-rmf-implementation-guide) | NIST AI RMF practitioner guide |
| [awesome-ai-governance](https://github.com/simaba/awesome-ai-governance) | Curated governance resources |

*Maintained by [Sima Bagheri](https://github.com/simaba) · Connect on [LinkedIn](https://www.linkedin.com/in/simabagheri)*
