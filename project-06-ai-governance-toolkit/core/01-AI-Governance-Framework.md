# AI Governance Framework

*Core Toolkit — Foundational Document 1 of 8*
**Doc ID:** AIGV-CORE-001 · **Version 1.0**

---

**Disclaimer:** *This document is a portfolio artefact created for demonstration and educational purposes only. It does not represent the policies, systems, or practices of any real organisation, and no organisation, vendor, or individual named or implied within it refers to an actual entity. All identifiers (e.g. ORG-AI-0XX) are fictional and used solely to illustrate a coherent governance scenario. This template does not constitute legal advice and should not be relied upon for regulatory compliance without review by qualified counsel and subject-matter experts.*

 KARUN. · AIGP (AI Governance Professional)**

---

## 1. Purpose and Scope

This Framework establishes the organisation's approach to governing the design, development, procurement, deployment, and retirement of artificial intelligence (AI) systems. It applies to all AI and automated decision-making (ADM) systems used, built, or procured by the organisation, including systems embedded within third-party software (Vendor A, Vendor B, Vendor C) and AI capabilities delivered through cloud platforms.

The Framework is designed to be regulation-agnostic at its core, with mapping layers to specific regimes — the EU AI Act, NIST AI Risk Management Framework (AI RMF 1.0), ISO/IEC 42001, and the OECD AI Principles — so that governance activity performed once can be evidenced against multiple obligations.

## 2. Governance Objectives

- Ensure every AI system in use is known, classified, and owned (see AI System Inventory, AIGV-CORE-004).
- Prevent deployment of unacceptable-risk or non-compliant AI systems.
- Provide proportionate oversight calibrated to risk tier, avoiding blanket bureaucracy for low-risk systems.
- Maintain audit-ready documentation to support regulatory examination, customer due diligence, and internal assurance.
- Build organisational capability so governance is owned by business and technical teams, not solely by a central function.

## 3. Guiding Principles

| Principle | What it means in practice |
|---|---|
| Accountability | Every AI system has a named business owner and a named technical owner recorded in the inventory. |
| Proportionality | Oversight intensity scales with risk tier — minimal-risk systems are logged, high-risk systems undergo full conformity review. |
| Transparency | Affected individuals and internal stakeholders can obtain a meaningful explanation of how a system reaches its outputs. |
| Human oversight | High-risk and legal/significant-effect systems retain a documented human-in-the-loop or human-on-the-loop control point. |
| Lifecycle coverage | Governance activity spans intake, design, pre-deployment validation, monitoring, incident response, and decommissioning. |
| Evidence-first | Governance decisions are recorded, not verbal — every gate produces an artefact. |

## 4. Regulatory and Standards Alignment

This Framework is structured so that a single governance activity generates evidence usable across frameworks. The [Regulatory and Standards Crosswalk](../../reference-library/regulatory-standards-crosswalk.md) provides the detailed clause-level mapping; the summary below shows how the Framework's structure maps at a high level.

| Framework element | EU AI Act | NIST AI RMF | ISO/IEC 42001 | OECD AI Principles |
|---|---|---|---|---|
| AI System Inventory & Classification | Art. 6, Annex III | GOVERN 1.1, MAP 1 | Clause 4.1, 8.2 | 1.2 Human-centred values |
| Governance Committee & RACI | Art. 9(2), Art. 26 | GOVERN 2, GOVERN 3 | Clause 5.3, 9.3 | 1.4 Accountability |
| Risk & Use Case Assessment | Art. 9, Art. 27 (FRIA) | MAP 2–5, MEASURE 1–2 | Clause 6.1, 8.1 | 1.3 Transparency, 1.4 |
| Human Oversight Procedures | Art. 14 | GOVERN 4, MANAGE 2 | Annex A.6.2.4 | 1.4 Accountability |
| Incident Response & Escalation | Art. 62, Art. 73 | MANAGE 4 | Clause 10.1–10.2 | 2.5 Accountability |
| Monitoring & Quarterly Review | Art. 72 (post-market) | MEASURE 3–4, MANAGE 1–2 | Clause 9.1, 9.3 | 1.3 |

## 5. Governance Structure

Detailed committee composition, terms of reference, and decision authority are defined in the AI Governance Committee Charter (AIGV-CORE-003). At a summary level, governance operates across three tiers:

### 5.1 Strategic Tier — AI Governance Committee
Cross-functional body (legal, risk, technology, data privacy, business unit leads) that approves the AI Policy, sets risk appetite, reviews high-risk system approvals, and owns escalations that cannot be resolved at the operational tier.

### 5.2 Operational Tier — AI Governance Office
Day-to-day administration: maintains the inventory, runs intake and use case assessments, tracks remediation actions, prepares committee papers, and coordinates incident response.

### 5.3 Delivery Tier — System Owners and Technical Teams
Business owners and technical/ML owners named against each inventory entry are accountable for day-to-day compliance of their system, including monitoring, documentation currency, and flagging material changes that could shift risk classification.

## 6. AI Risk Classification Model

All systems are classified into one of four tiers at intake and re-assessed on material change. This classification determines which controls in Sections 7–9 apply.

| Tier | Definition | Example trigger | Control intensity |
|---|---|---|---|
| Unacceptable | Prohibited practice under applicable law (e.g. social scoring, real-time biometric categorisation in prohibited contexts) | Any use matching an EU AI Act Art. 5 prohibited practice | Not permitted — system blocked at intake |
| High | Significant effect on health, safety, fundamental rights, employment, credit, or access to essential services | Credit decisioning, recruitment screening, biometric authentication for access control | Full conformity pack, FRIA where applicable, committee approval, quarterly review |
| Limited | Direct interaction with individuals or content generation where transparency obligations apply | Customer-facing chatbot, AI-generated content, emotion recognition (non-prohibited contexts) | Transparency notice, use case assessment, annual review |
| Minimal | No material effect on rights or safety | Internal productivity tools, spam filters, demand forecasting | Logged in inventory; light-touch annual attestation |

## 7. Lifecycle Controls

### 7.1 Intake
1. Any new AI system, model, or significant use case (including vendor-embedded AI) is logged in the AI System Inventory before procurement approval or production deployment.
2. The AI Use Case Assessment Form (AIGV-CORE-005) is completed by the proposing business owner.
3. The AI Governance Office performs an initial risk tier determination within 10 business days.

### 7.2 Pre-Deployment
1. High-risk systems undergo the full documentation and conformity process (see project-05-high-risk-documentation for the artefact set: technical documentation, risk management file, data governance statement, human oversight procedure, instructions for use, conformity declaration).
2. Limited-risk systems complete a transparency and use case review; minimal-risk systems are confirmed and logged.
3. No high-risk system enters production without AI Governance Committee sign-off recorded in committee minutes.

### 7.3 Monitoring
1. Business and technical owners complete the Quarterly Governance Review Template (AIGV-CORE-008) for high- and limited-risk systems.
2. Material changes (retraining, new data sources, new use context, performance drift beyond defined thresholds) trigger re-classification.

### 7.4 Incident Response
1. Suspected incidents (bias, safety, security, or rights-impacting failures) are escalated per the Incident Response and Regulatory Escalation procedure (see project-04-incident-response).

### 7.5 Decommissioning
1. Retired systems are marked in the inventory with retirement date, retention obligations for records, and confirmation that dependent processes have been transitioned.

## 8. Roles and Responsibilities

| Role | Key responsibilities |
|---|---|
| AI Governance Committee | Approves policy, risk appetite, high-risk deployments; owns escalated decisions |
| AI Governance Office / Lead | Maintains inventory, runs intake and assessments, secretariat to committee, coordinates incidents |
| Business System Owner | Accountable for business justification, use case currency, and operational compliance of their system |
| Technical / ML Owner | Accountable for model performance, monitoring, documentation, and technical remediation |
| Data Protection / Privacy Lead | Reviews data governance and DPIA/FRIA overlap for systems processing personal data |
| Legal & Compliance | Interprets regulatory obligations, reviews conformity documentation, advises on incident disclosure |
| Internal Audit | Independent assurance over the governance program's design and operating effectiveness |

## 9. Review and Maintenance

This Framework is reviewed at least annually by the AI Governance Committee, and on-demand following material regulatory change (e.g. the EU AI Act Digital Omnibus amendments), a significant AI incident, or a material shift in the organisation's AI risk profile. Version history and approval records are retained in the governance office's document register.
