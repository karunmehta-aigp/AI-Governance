
<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/25539ef5-b640-42e8-9394-8f54dec7b5ee" />
## Case Study: `ORG-AI-014` — Investment Research Agent Risk Assessment Framework

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer. A practical end-to-end evaluation using NIST AI RMF, ISO/IEC 42001, and applicable law.

**Assessment Date:** 15 Jul 2026 · **Review Date:** 30 Jul 2026 · **Next Review:** 15 Oct 2026
**Method:** NIST AI RMF 1.0
**Criteria:** NIST AI RMF 1.0 · ISO/IEC 42001:2023 · EU AI Act 2024/1689 · SEC/FINRA
**Assessment Version:** 1.0

### Governance Lifecycle

`1 Intake → 2 Context → 3 Regulatory → 4 Risk Identification → 5 Risk Analysis → 6 Control Design → 7 Validation → 8 Decision → 9 Monitoring → 10 Continuous Improvement`

---

### Step 1 — Assessment Metadata

| Field | Value |
|---|---|
| Assessor | AI Governance Team |
| Organization / Business Unit | Org1 (Research Technology) |
| Document Owner | AI Risk Lead |
| Scope | High-Risk AI System in Production |
| Criteria | NIST AI RMF 1.0, ISO/IEC 42001:2023, EU AI Act 2024/1689, SEC/FINRA |
| Review Frequency | Quarterly |
| Assessment Version | 1.0 |

### Step 2 — AI System Profile

| Field | Value |
|---|---|
| System Purpose | AI Investment Research Summarizer |
| Business Owner | Research Technology (Head of Research) |
| System Type | GenAI (LLM) + RAG over proprietary research library |
| What It Does | Summarizes internal & external research and generates insights |
| Decision Authority | Analyst-in-the-loop — outputs influence investment decisions; no autonomous decision-making |
| Users / Scale | ~220 analysts · ~3,200 briefs/month · Global |
| Key Data Inputs | Internal research, filings, news, market data, client holdings |
| Deployment | Production · Deployed 10 months ago |
| Training Data | Proprietary + vendor models. No fine-tuning |
| Monitoring | No performance or drift monitoring in place |
| Governance to Date | Ad-hoc review. No formal risk assessment or bias testing |

### Step 3 — Applicable Regulations & Standards

| Regulation / Framework | Applies? | Why It Applies / What It Demands |
|---|---|---|
| EU AI Act 2024/1689 (Amended Digital Omnibus) | ✅ | Investment research tools used in investment decisions are Annex III high-risk. Obligations from 2 Dec 2027 (deferred). Design for requirements now (Arts. 9, 10, 13, 14, 26, 43). |
| UK GDPR / GDPR | ✅ | Art. 22 — no solely automated decisions with legal or similarly significant effects without human intervention. DPIA required (Art. 35). |
| SEC / FINRA | ✅ | Research that influences investment decisions must be fair, balanced, and not misleading. Recordkeeping required. |
| Title VII / ADEA / ADA | ✅ | If model output is used in hiring-related research or comps, disparate-impact risk items exist. |
| NYC Local Law 144 | ✅ | Annual bias audit, publish summary of results, notify candidates within 10 business days. |
| Colorado AI Act (SB 26-189) | ⚠️ WATCH | Notice + explanation obligations from 1 Jan 2027 for covered decisions. |

**AI Classification (EU AI Act):** ☑ High Risk (Annex III, Arts. 6–49) — Unacceptable (Art. 5), Limited Risk (Transparency, Arts. 50–52), and Minimal Risk not applicable.

**Assessed Against:** ☑ NIST AI RMF 1.0 · ☑ ISO/IEC 42001:2023 · ☑ EU AI Act · ☑ ISO/IEC 23894 · ☑ Internal AI Policy · ☐ AIUC-1

### Step 4 — Risk Register (with Precedents)

| # | Risk | NIST Function | Real-World Precedent |
|---|---|---|---|
| 1 | Hallucinated Financial Facts | MEASURE | Org1 chatbot (2023) provided incorrect information on ESG funds, causing client confusion and reputational damage. |
| 2 | Biased Framing of Sectors / Companies | MAP | Org1 study (2016) showed algorithmic bias in risk scoring due to biased historical data and opaque features. |
| 3 | Data Leakage via Prompts | MANAGE | Org1 engineers (2023) leaked proprietary source code to a chatbot through prompts; data exposure risk. |
| 4 | Lack of Citations & Traceability | GOVERN | Org1 enforcement action (2024) — firm failed to disclose AI use and produced misleading research summaries. |
| 5 | Vendor Dependency & Model Updates | MANAGE | Org1 chatbot case (2024) — vendor model update changed output and caused policy misrepresentation. |

### Step 5 — Risk Analysis & Rating

Scale: Low 1–4 · Medium 5–8 · High 9–14 · Critical 15–25

| # | Risk | Likelihood (1–5) | Impact (1–5) | Score (L×I) | Level |
|---|---|---|---|---|---|
| 1 | Hallucinated Financial Facts | 4 | 5 | 20 | 🔴 CRITICAL |
| 2 | Biased Framing of Sectors | 4 | 4 | 16 | 🟠 HIGH |
| 3 | Data Leakage via Prompts | 4 | 4 | 16 | 🟠 HIGH |
| 4 | Lack of Citations & Traceability | 3 | 5 | 15 | 🟠 HIGH |
| 5 | Vendor Dependency & Updates | 5 | 3 | 15 | 🟠 HIGH |

*Note: rows 3–4 were reconstructed from a partially legible source poster — verify the exact Likelihood × Impact split against your original working file before treating this as final.*

### Step 6 — Controls & Framework Mapping

**Preventive controls (stop problems):** prompt guardrails & content filters · source allow-list for RAG · data minimization & redaction · analyst training on AI use · change management for models

**Detective controls (find issues):** output factuality testing · bias testing (demographic parity) · prompt injection tests · data leakage scanning · human review sampling

**Corrective controls (fix issues):** analyst escalation workflow · correct & retract process · model rollback plan · incident response runbook · vendor escalation & SLAs

| Risk | NIST AI RMF | ISO/IEC 42001 | EU AI Act |
|---|---|---|---|
| Hallucinated Facts | Measure | A.7, A.8, A.10 | Art. 9, 13, 14 |
| Biased Framing | Map | A.6, A.7 | Art. 10, 13 |
| Data Leakage | Manage | A.5, A.8 | Art. 9, 26 |
| Lack of Citations | Govern | A.2, A.7 | Art. 13, 26 |
| Vendor Dependency | Manage | A.5, A.15 | Art. 26, 43 |

### Step 7 — Formal Audit Findings (Top 3)

| ID | Condition (Observed) | Criteria (Should Be) | Cause | Severity |
|---|---|---|---|---|
| F-01 | Hallucinated facts in 8 of 50 test prompts | Outputs must be accurate and grounded | Analysts may rely on incorrect data, leading to poor decisions | CRITICAL |
| F-02 | No bias testing performed | Bias testing before deployment and periodically thereafter | No bias validation process defined or executed | HIGH |
| F-03 | No prompt-injection or data-leakage controls in production | Security controls must protect data and system integrity | Controls not implemented, no testing performed | HIGH |

### Step 8 — Recommendations & Action Plan

| # | Recommendation | Owner | Priority | Target Date |
|---|---|---|---|---|
| 1 | Implement factuality guardrails and citation enforcement | AI Engineering | CRITICAL | 05 Sep 2026 |
| 2 | Run AI bias assessment & quarterly testing | Data Science | HIGH | 12 Sep 2026 |
| 3 | Deploy data leakage prevention & prompt security | Security Ops | HIGH | 12 Sep 2026 |
| 4 | Establish monitoring & drift alerts | AI Operations | HIGH | 19 Sep 2026 |
| 5 | Vendor contract update & SLA alignment | Vendor Management | HIGH | 26 Sep 2026 |

### Step 9 — Governance Decision & Sign-Off

**Decision:** ✅ Conditional Go — subject to remediation of all critical findings (F-01) and completion of high-risk controls (F-02, F-03).

**Conditions:**
- All critical findings closed with evidence
- Bias testing baseline completed
- Monitoring & alerting live
- Analyst training completed
- Vendor SLA & rollback plan validated

| Role | Signature | Date |
|---|---|---|
| Business Owner (Research Technology) | Signed | 30 Jul 2026 |
| AI Risk Lead | Signed | 30 Jul 2026 |
| Compliance Officer | Signed | 30 Jul 2026 |
| Legal Counsel | Signed | 30 Jul 2026 |

### Step 10 — Monitoring & Evidence

- **Next full risk review:** 15 Oct 2026 (Quarterly)
- **Ongoing monitoring:** weekly factuality tests · monthly bias tests · active and tested incident response plan
- **Key KPIs:** hallucination rate · bias metrics · analyst override rate
- **Evidence artifacts (maintain & retain):** risk register · control validation pack · test reports · bias & fairness report · approval record · monitoring reports · incident logs · training records

### Step 11 — Governance Principles

- **Evidence before assurance** — every control decision is backed by verifiable evidence.
- **Human accountability over AI autonomy** — humans remain accountable for outcomes.
- **Risk-based, not risk-blind** — focus on material risks and real business impact.
- **Continuous governance, not one-time approval** — monitor, learn, and improve as models, data, and regulations evolve.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
