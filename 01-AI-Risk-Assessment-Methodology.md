# AI Risk Assessment Methodology

**Doc ID:** RISK-001 · **Version 1.0**
**Author:** Anju K. · AIGP (AI Governance Professional)

---

**Disclaimer:** *This document is a portfolio artefact created for demonstration and educational purposes only. It does not represent the policies, systems, or practices of any real organisation. This template does not constitute legal advice.*

---

## Purpose

Defines a repeatable, defensible methodology for identifying, assessing, treating, and monitoring AI-specific risk — the "how" that the Risk Register (RISK-002) and Risk Scoring Matrix (RISK-003) apply mechanically.

## 1. Risk Categories Covered

| Category | Examples |
|---|---|
| Performance risk | Accuracy degradation, drift, edge-case failure |
| Fairness/bias risk | Disparate impact on protected groups, proxy discrimination |
| Safety risk | Physical harm from system failure or erroneous output |
| Security risk | Adversarial manipulation, data poisoning, prompt injection, model theft |
| Privacy risk | Unlawful processing, re-identification, data leakage |
| Legal/regulatory risk | Non-compliance with EU AI Act or other applicable law |
| Reputational risk | Public harm from a visible AI failure |
| Third-party/vendor risk | Opacity or failure in a vendor-supplied AI component |
| Operational/dependency risk | Over-reliance on a single model, provider, or dataset |

## 2. Assessment Process

1. **Identify** — for each AI system (from the Inventory), systematically consider each risk category above. Do not limit identification to categories the system's original design already considered.
2. **Assess** — score likelihood and impact using the Risk Scoring Matrix (RISK-003). Likelihood and impact are assessed independently before combining into a risk score.
3. **Evaluate** — compare the risk score against the organisation's risk appetite (set by the AI Governance Committee) to determine if treatment is required.
4. **Treat** — select a treatment strategy (Section 4) and document it in the Risk Treatment Plan (RISK-004).
5. **Monitor** — track treated and accepted risks over time; re-assess on a defined cadence or upon material system change.

## 3. Likelihood and Impact Definitions

### Likelihood (1–5)
| Score | Definition |
|---|---|
| 1 | Rare — no known precedent, would require multiple unlikely factors to align |
| 2 | Unlikely — could occur but no history of occurrence in comparable systems |
| 3 | Possible — plausible under normal operating conditions |
| 4 | Likely — has occurred in comparable systems, or expected under known conditions |
| 5 | Almost certain — recurring issue or inherent to the system's current design |

### Impact (1–5)
| Score | Definition |
|---|---|
| 1 | Negligible — no material effect on individuals, operations, or reputation |
| 2 | Minor — limited, recoverable effect on a small number of individuals or a single process |
| 3 | Moderate — meaningful harm to individuals or a business process, recoverable with effort |
| 4 | Major — significant harm to individuals' rights/safety, or serious operational/reputational damage |
| 5 | Severe — irreversible harm to individuals, regulatory penalty exposure, or existential reputational damage |

## 4. Treatment Strategies

| Strategy | When to use |
|---|---|
| **Mitigate** | Reduce likelihood or impact through a control (e.g. additional testing, human oversight, monitoring threshold) |
| **Transfer** | Shift risk via contract (e.g. vendor liability clause, insurance) — does not eliminate accountability for AI Act purposes |
| **Avoid** | Do not proceed with the use case, or discontinue an existing one |
| **Accept** | Formally accept residual risk within appetite, with documented sign-off at appropriate authority level |

## 5. Approval Authority by Risk Level

| Risk Level (Likelihood × Impact) | Approval Required |
|---|---|
| 1–4 (Low) | System/technical owner |
| 5–9 (Medium) | Business owner + AI Governance Office |
| 10–15 (High) | AI Governance Committee |
| 16–25 (Critical) | AI Governance Committee + escalation to executive sponsor |

## 6. Review Cadence

- Full re-assessment: annually, or upon material system change (retraining, new data source, new use context).
- Light-touch review: each quarterly governance review cycle, confirming no new risk indicators have emerged.
