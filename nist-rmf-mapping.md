# NIST AI RMF Mapping — "Organisation" (Fictional Case Study)

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**Framework Reference:** NIST AI Risk Management Framework (AI RMF 1.0)
**Mapping Date:** March 2026

## Purpose

This document maps each AI system in the organisation's inventory against the four core functions of the NIST AI RMF. It records which governance practices currently exist, which are absent, and where the most significant maturity gaps sit — independent of, but read alongside, the EU AI Act legal classification in the companion document.

The four functions are:

| Function | Core Question |
|---|---|
| **GOVERN** | Are the right accountability structures, policies, and culture in place? |
| **MAP** | Have we identified and contextualised the risks associated with this system? |
| **MEASURE** | Have we analysed and assessed those risks in a rigorous, documented way? |
| **MANAGE** | Are we actively treating risks, monitoring systems, and ready to respond? |

Maturity is rated on a 1–4 scale:

| Level | Description |
|---|---|
| 1 | Initial — ad hoc or absent |
| 2 | Developing — some practices exist but applied inconsistently |
| 3 | Defined — documented, repeatable processes in place |
| 4 | Optimised — continuously improved with active feedback loops |

## System Mappings

### ORG-AI-001 · Credit Decisioning System (High Risk)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| GOVERN | Named owner (Director of Credit Risk). No AI-specific governance charter references this system. | No formal model risk escalation path for AI-driven credit decisions. | 2 |
| MAP | Risk context understood informally by the model build team. | No formal risk-mapping document; affected population not documented with demographic breakdown. | 2 |
| MEASURE | Explainability layer exists in early form. No structured fairness testing against protected groups. | Bias audit required; no defined accuracy/drift thresholds for ongoing monitoring. | 2 |
| MANAGE | Informal performance monitoring by the model team. | No documented model drift response procedure; no AI-specific incident classification. | 1 |

**Overall Maturity: 1.75 (Developing)**
**Priority Actions:** Conduct a structured bias audit; produce a formal risk-mapping document; define drift and fairness thresholds; create an AI incident response procedure for this system.

---

### ORG-AI-002 · CV Screening & Ranking System (High Risk)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| GOVERN | HR Director is nominal owner but has not received AI governance training. | No AI governance policy; no Board-level visibility of this system's risk classification. | 1 |
| MAP | Use case documented in procurement records only. | No formal risk-identification exercise; proxy-discrimination risk not assessed. | 1 |
| MEASURE | No bias evaluation performed on vendor model. Outcomes not tracked by demographic group. | No fairness metrics; no documentation of vendor training data provenance. | 1 |
| MANAGE | No AI-specific monitoring. Auto-rejection runs without human checkpoint. | No incident response capability; no override mechanism for disputed rejections. | 1 |

**Overall Maturity: 1.0 (Initial)**
**Priority Actions:** Immediate — disable or gate auto-rejection pending mandatory human review. Near-term — require vendor to supply training data documentation and an independent bias audit; conduct full risk assessment before continued production use.

---

### ORG-AI-003 · AML Transaction Monitoring System (High Risk — conservative)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| GOVERN | Named owner (Head of Financial Crime Compliance). Vendor relationship managed through procurement. | No AI-specific governance layer beyond standard vendor management. | 2 |
| MAP | Use case and alert-handling workflow well understood operationally. | Risk mapping not formalised in AI governance terms. | 2 |
| MEASURE | Vendor provides periodic performance metrics on alert precision. | No independent validation of vendor-reported metrics; no fairness review of risk scoring across customer segments. | 2 |
| MANAGE | Human analyst reviews every alert before action; documented escalation path exists. | No AI-specific incident classification; vendor retraining cadence undisclosed. | 2 |

**Overall Maturity: 2.0 (Developing)**
**Priority Actions:** Request retraining cadence and model change disclosure from vendor; formalise risk-mapping document; commission independent validation of vendor performance claims.

---

### ORG-AI-004 · Voice Biometric Authentication System (High Risk)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| GOVERN | Head of Customer Operations accountable. Vendor relationship managed through procurement. | No biometric-specific governance protocol; no AI policy reference for this system. | 1 |
| MAP | Enrolment and authentication flow understood operationally. | No formal risk mapping addressing biometric data sensitivity or fallback-path fairness. | 1 |
| MEASURE | Authentication match-rate tracked by vendor. | No independent accuracy testing across demographic groups (e.g. accent, voice variation); no DPIA-linked metric set. | 1 |
| MANAGE | Fallback to human agent exists on authentication failure. | No formal monitoring of fallback-path usage rates or outcomes; no AI-specific incident procedure. | 1 |

**Overall Maturity: 1.0 (Initial)**
**Priority Actions:** Commission a biometric-specific DPIA cross-referenced to Article 10 AI Act requirements; audit fallback authentication path for fairness and accessibility; establish ongoing accuracy monitoring disaggregated by demographic group.

---

### ORG-AI-005 · Customer Service Virtual Assistant (Limited Risk)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| GOVERN | Head of Digital Customer Experience accountable. Vendor managed through standard SaaS procurement. | No formal AI governance policy reference; chatbot performance not reviewed at governance committee level. | 3 |
| MAP | Use case and failure modes (misinformation, escalation triggers) well understood. | Risk mapping remains informal rather than documented. | 3 |
| MEASURE | Customer satisfaction and escalation rates tracked; web disclosure compliance monitored. | Mobile disclosure compliance not yet measured, since the control itself is incomplete. | 3 |
| MANAGE | Automated escalation to human agent on low-confidence responses; complaints process covers chatbot interactions. | No formal AI-specific incident category in the complaints taxonomy. | 3 |

**Overall Maturity: 3.0 (Defined)**
**Priority Actions:** Implement persistent mobile disclosure; add a dedicated AI-incident tag to the complaints management framework.

---

### ORG-AI-006 · Generative Marketing Content Tool (Limited Risk)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| GOVERN | Head of Brand Marketing accountable. Vendor relationship managed through Marketing procurement. | No AI governance sign-off step in the campaign approval workflow. | 2 |
| MAP | Use case understood; synthetic-content risk (mistaken authenticity) identified informally. | No documented risk assessment of labelling failure scenarios. | 2 |
| MEASURE | Campaign performance tracked. Labelling presence not systematically audited across channels. | No measurement of labelling compliance rate; no review of brand/reputational risk from mislabelled content. | 2 |
| MANAGE | Marketing Ops applies labelling manually per campaign. | No automated or enforced labelling control; no incident process if unlabelled synthetic content is published. | 1 |

**Overall Maturity: 1.75 (Developing)**
**Priority Actions:** Build an automated Article 50 labelling check into the publishing workflow; audit historical campaign output for labelling compliance; define an incident procedure for unlabelled synthetic content reaching the public.

---

### ORG-AI-007 · Employee Productivity Monitoring Tool (Limited Risk)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| GOVERN | VP of Operations accountable. In-house analytics team manages the system. | No AI governance policy reference; no formal sign-off on individual-level flagging feature. | 2 |
| MAP | General monitoring risk understood; individual-flag feature risk not formally mapped. | Works Council consultation on individual-level flagging incomplete. | 2 |
| MEASURE | Aggregate dashboard usage tracked. | No fairness review of individual flagging thresholds across employee demographics or roles. | 2 |
| MANAGE | Manager review required before any action on a flagged employee. | No formal incident process for disputed or contested flags. | 2 |

**Overall Maturity: 2.0 (Developing)**
**Priority Actions:** Complete Works Council consultation before continuing individual-level flagging; review flagging thresholds for disparate impact across roles and teams; document a contestability/appeal process for flagged employees.

---

### ORG-AI-008 · Internal Portfolio Analytics Tool (Minimal Risk)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| GOVERN | CFO accountable; standard Finance data governance applies. | No AI-specific governance layer — appropriate given risk level. | 3 |
| MAP | Low risk profile documented informally; data is aggregated and anonymised prior to model use. | Minimal gaps given classification. | 3 |
| MEASURE | Forecast accuracy tracked against actuals as a routine finance practice. | No AI-specific fairness assessment — not warranted at this risk tier. | 3 |
| MANAGE | Standard Finance change-control process applies to model updates. | No AI-specific management gaps identified at this risk tier. | 3 |

**Overall Maturity: 3.0 (Defined)**
**Priority Actions:** None immediate. Maintain standard annual review cadence.

---

### ORG-AI-009 · Regulatory Monitoring Tool (Minimal Risk)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| GOVERN | CCO accountable; vendor managed through standard procurement. | No AI-specific governance layer — adequate at this risk level. | 3 |
| MAP | Internal use, low stakes; compliance team validates all output. | No gaps identified at this risk level. | 3 |
| MEASURE | Alert relevance and false-positive rate tracked informally by the compliance team. | Informal tracking is proportionate to risk profile. | 3 |
| MANAGE | All outputs reviewed by compliance staff before action; vendor SLA in place. | No AI-specific gaps identified. | 3 |

**Overall Maturity: 3.0 (Defined)**
**Priority Actions:** None. Annual review sufficient.

---

### ORG-AI-010 · Workforce Scheduling Assistant (Minimal Risk — pilot)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| GOVERN | Head of Branch Operations accountable for the pilot; HR Systems team responsible for the model. | No formal governance sign-off on pilot scope or expansion criteria. | 1 |
| MAP | Pilot risk assessment in progress; scope intentionally limited to one jurisdiction. | Risk mapping incomplete; no documented criteria for what scope change would trigger reclassification. | 1 |
| MEASURE | Scheduling accuracy and conflict rate tracked during pilot. | No fairness review of recommended rosters across employee groups. | 1 |
| MANAGE | All rosters require manager approval before publication. | No production monitoring framework defined for post-pilot rollout. | 1 |

**Overall Maturity: 1.0 (Initial)**
**Priority Actions:** Define explicit governance gate criteria, including reclassification triggers, before any expansion beyond the pilot jurisdiction; complete risk mapping; establish a fairness review of roster recommendations prior to wider rollout.

## Portfolio-Level Summary

| System | EU AI Act Tier | RMF Maturity | Action Priority |
|---|---|---|---|
| ORG-AI-001 Credit Decisioning System | High Risk | 1.75 | Critical |
| ORG-AI-002 CV Screening & Ranking System | High Risk | 1.0 | Critical — immediate |
| ORG-AI-003 AML Transaction Monitoring System | High Risk (conservative) | 2.0 | High |
| ORG-AI-004 Voice Biometric Authentication System | High Risk | 1.0 | Critical |
| ORG-AI-005 Customer Service Virtual Assistant | Limited Risk | 3.0 | Low |
| ORG-AI-006 Generative Marketing Content Tool | Limited Risk | 1.75 | Medium |
| ORG-AI-007 Employee Productivity Monitoring Tool | Limited Risk | 2.0 | Medium |
| ORG-AI-008 Internal Portfolio Analytics Tool | Minimal Risk | 3.0 | Monitor |
| ORG-AI-009 Regulatory Monitoring Tool | Minimal Risk | 3.0 | Monitor |
| ORG-AI-010 Workforce Scheduling Assistant | Minimal Risk (pilot) | 1.0 | Monitor — reassess on scope change |

**Portfolio risk concentration:** Four of the organisation's ten AI systems are classified High Risk under the EU AI Act, and three of those four (Credit Decisioning, CV Screening, Voice Biometric Authentication) are in active production with RMF maturity scores at or below 1.75 — meaning the highest-consequence systems in the portfolio are also the least governed. This is the inverse of where governance effort should be concentrated, and it represents material regulatory exposure ahead of supervisory scrutiny. A remediation programme prioritising these three systems should be initiated immediately, with the AML Transaction Monitoring System's provisional classification resolved by legal counsel in parallel.

**Next review:** September 2026, or immediately upon any new AI system deployment or material change to an existing system's scope.
