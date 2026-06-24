# EU AI Act Risk Classification — "Organisation" (Fictional Case Study)

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**Classification Date:** March 2026
**Prepared by:** AI Governance Programme Office
**Review Due:** September 2026

## Classification Framework

The EU AI Act establishes four risk tiers, and the tier assigned to a system determines the compliance obligations that attach to it. This document records the classification decision and supporting rationale for every AI system in the organisation's inventory, so that the basis for each decision is defensible to internal audit, the Board Risk Committee, or a supervisory authority.

## Risk Tier Overview

| Tier | Regulatory Treatment |
|---|---|
| Unacceptable Risk | Prohibited outright. System must not be deployed under any circumstance. |
| High Risk | Strict pre-deployment obligations. Conformity assessment, technical documentation, logging, human oversight, and registration mandated. |
| Limited Risk | Transparency obligations. Affected persons must be informed they are interacting with, or viewing output from, an AI system. |
| Minimal Risk | No AI Act–specific obligations. General data protection and sectoral rules continue to apply. |

## Classification Decisions

### ORG-AI-001 · Credit Decisioning System
**Classification: HIGH RISK**

**Legal Basis:** EU AI Act Annex III, Category 5(b) — AI systems intended to be used to evaluate the creditworthiness of natural persons or establish their credit score.

**Rationale:** This system produces a numerical creditworthiness score and a decision recommendation that functions as the primary input into the organisation's lending workflow — it is not advisory output sitting alongside human judgement, it *is* the decision engine that a credit officer is expected to follow absent an explicit override. The model ingests postcode and employment status, both of which carry well-documented proxy-discrimination risk for protected characteristics, which heightens rather than lowers the scrutiny this system requires.

**Obligations Triggered:**
- Conformity assessment before continued deployment (Article 43)
- Technical documentation (Article 11, Annex IV)
- Logging and traceability (Article 12)
- Human oversight measures (Article 14)
- Accuracy, robustness, and cybersecurity requirements (Article 15)
- Registration in the EU database (Article 71)

**Current Compliance Gap:** An explainability layer exists but has not been validated or documented to the standard Article 13 requires for information provided to deployers. No formal conformity assessment has been completed since the system's go-live. **Priority: Critical.**

---

### ORG-AI-002 · CV Screening & Ranking System
**Classification: HIGH RISK**

**Legal Basis:** EU AI Act Annex III, Category 4(a) — AI systems intended to be used for recruitment or selection of natural persons, including screening or filtering applications and evaluating candidates.

**Rationale:** This system ranks and, below a defined threshold, auto-rejects candidates based on parsed CV and application data. This directly and materially affects individuals' access to employment opportunities. NLP processing of unstructured CV text introduces real risk of proxy discrimination through correlations with educational institution, employment gaps, or language patterns that track protected characteristics — and without a bias audit, this risk cannot be ruled out, only assumed away.

**Obligations Triggered:**
- All high-risk obligations as set out under ORG-AI-001 above
- Article 10 (data and data governance) — training data bias assessment required from the vendor
- Article 14 (human oversight) — auto-rejection below threshold must not occur without a qualified human review step

**Current Compliance Gap:** No conformity assessment has been performed. No bias audit exists. The auto-rejection mechanism currently operates without mandatory human review, which is a direct gap against Article 14, not merely a documentation shortfall. Not registered in the EU database. **Priority: Critical — immediate remediation required.**

---

### ORG-AI-003 · AML Transaction Monitoring System
**Classification: HIGH RISK (conservative reading)**

**Legal Basis:** Not explicitly named under Annex III in the AML context, but classified high-risk on a conservative legal reading given its proximity to Category 5(a)/(b) creditworthiness and essential-services-access logic, pending final confirmation from external counsel.

**Rationale:** This system flags transactions for human review rather than autonomously freezing accounts or filing reports — every alert is reviewed by a financial crime analyst before any consequential action (such as a Suspicious Activity Report) is filed, which is a substantive, not nominal, human-in-the-loop control. However, the system's risk scoring can influence a customer's perceived risk profile in ways that affect their ongoing access to financial services, which is the reasoning basis for treating it conservatively as high-risk pending a definitive legal opinion, rather than defaulting to a lower tier by omission.

**Obligations Triggered (provisional, pending confirmation):**
- Same obligation set as ORG-AI-001, applied provisionally
- Article 28 — deployer obligations regarding vendor-supplied high-risk systems

**Current Compliance Gap:** The vendor has not contractually disclosed its model retraining cadence, which limits the organisation's ability to evidence ongoing accuracy and robustness under Article 15. Legal opinion on final classification has been requested but not yet received. **Priority: High — pending legal confirmation, governed as high-risk in the interim.**

---

### ORG-AI-004 · Voice Biometric Authentication System
**Classification: HIGH RISK**

**Legal Basis:** EU AI Act Annex III, Category 1 — AI systems intended to be used for biometric identification or categorisation of natural persons, including verification systems using biometric data.

**Rationale:** This system uses voice biometric matching to authenticate customers, replacing manual knowledge-based security questions. Biometric data is a special category of personal data, and the EU AI Act treats biometric verification systems as high-risk irrespective of whether the underlying business purpose (here, fraud-resistant authentication) is itself benign — the sensitivity of the data type, not the friendliness of the use case, drives the classification.

**Obligations Triggered:**
- All high-risk obligations as set out under ORG-AI-001 above
- Article 10 — specific data governance requirements for biometric training and enrolment data
- A dedicated Data Protection Impact Assessment under Article 35 GDPR, cross-referenced against Article 10 AI Act requirements

**Current Compliance Gap:** No documented DPIA specific to biometric processing has been completed since launch. The fallback authentication path (for customers who fail voice match) has not been audited for fairness or accessibility. Enrolment consent flow has not been reviewed by legal since launch. **Priority: Critical.**

---

### ORG-AI-005 · Customer Service Virtual Assistant
**Classification: LIMITED RISK**

**Legal Basis:** EU AI Act Article 52(1) — providers and deployers of AI systems intended to interact directly with natural persons must ensure those persons are informed they are interacting with an AI system, unless this is obvious from the circumstances.

**Rationale:** This chatbot handles informational customer queries and routes complex cases to human agents; it does not make or materially influence decisions about credit, employment, or access to services. It falls outside every Annex III category. The applicable obligation is transparency, not the high-risk obligation chain.

**Obligations Triggered:**
- AI disclosure to end users (Article 52(1)) — currently partially implemented

**Current Compliance Gap:** Disclosure is persistent on the web channel but only shown at session start on the mobile app, which is a weaker form of the "informed" standard the Article expects on an ongoing basis. **Priority: Low — straightforward remediation.**

---

### ORG-AI-006 · Generative Marketing Content Tool
**Classification: LIMITED RISK**

**Legal Basis:** EU AI Act Article 50 — providers of AI systems generating synthetic image, audio, video, or text content must ensure outputs are marked as artificially generated or manipulated, in a machine-readable format, where the content could otherwise be mistaken for authentic.

**Rationale:** This tool generates synthetic marketing images and ad copy. This use case is squarely within Article 50's transparency obligation for synthetic content rather than the high-risk regime — there is no decision being made about an individual, only content being produced and shown to a general audience.

**Obligations Triggered:**
- Machine-readable labelling of AI-generated image assets (Article 50)

**Current Compliance Gap:** Labelling is applied inconsistently across output channels — present in some campaign exports, absent in others depending on the publishing workflow used by Marketing Ops. **Priority: Medium.**

---

### ORG-AI-007 · Employee Productivity Monitoring Tool
**Classification: LIMITED RISK**

**Legal Basis:** Not an Annex III high-risk category, but classification was deliberately scrutinised given the employment context, which the AI Act treats with heightened sensitivity even outside the explicit high-risk list.

**Rationale:** This tool aggregates productivity signals primarily at team level, with an individual-level flagging feature for unusually low activity. It does not evaluate, rank, or make employment decisions about individuals directly — managers retain full discretion over any resulting action — which keeps it below the Annex III recruitment/HR threshold. However, the individual-level flag feature was reviewed carefully, since employee-monitoring tools sit close to a risk boundary that could shift the classification upward if functionality expanded toward automated performance scoring.

**Obligations Triggered:**
- No EU AI Act high-risk obligations at current functionality
- Works Council consultation obligations under applicable national employment law (parallel, not AI Act–derived)

**Current Compliance Gap:** Employee notice of general monitoring exists, but consultation with the relevant Works Council specifically on the individual-level flagging feature has not been completed. **Priority: Medium — legal/employment-law gap, monitor for AI Act reclassification if scope expands.**

---

### ORG-AI-008 · Internal Portfolio Analytics Tool
**Classification: MINIMAL RISK**

**Legal Basis:** Not listed in Annex III. No Article 52 or Article 50 transparency trigger applies.

**Rationale:** This tool operates entirely on aggregated, anonymised portfolio data for internal management forecasting. No natural person, customer or employee, is directly or indirectly affected by its output, which is consumed only by internal finance management.

**Obligations Triggered:** None under the EU AI Act.

**Current Compliance Gap:** None identified. **Priority: Monitor.**

---

### ORG-AI-009 · Regulatory Monitoring Tool
**Classification: MINIMAL RISK**

**Legal Basis:** Not listed in Annex III. Internal-use system with no external natural-person impact.

**Rationale:** This tool surfaces regulatory intelligence for internal review; every output is validated by a qualified compliance officer before any action is taken. There is no automated decision affecting any individual.

**Obligations Triggered:** None under the EU AI Act.

**Current Compliance Gap:** None identified. **Priority: Monitor.**

---

### ORG-AI-010 · Workforce Scheduling Assistant
**Classification: MINIMAL RISK (provisional — pilot)**

**Legal Basis:** Not listed in Annex III in its current scope. Classification held under active review.

**Rationale:** This tool optimises shift rosters based on availability, qualifications, and demand — it is a logistics optimisation tool, not an evaluative tool, and every recommended roster requires manager approval before publication. The classification is explicitly provisional: if the scope expands to link scheduling outcomes to individual performance scoring, this system would need to be re-evaluated against the Annex III employment-management category and could move to High Risk.

**Obligations Triggered:** None under current scope. To be reassessed if scope expands.

**Current Compliance Gap:** None identified at current pilot scope. Governance review trigger has been logged for any scope expansion. **Priority: Monitor — reassess on scope change.**

## Classification Summary

| System | Classification | Compliance Status | Priority |
|---|---|---|---|
| ORG-AI-001 Credit Decisioning System | High Risk | Partial — conformity assessment and Article 13 documentation outstanding | Critical |
| ORG-AI-002 CV Screening & Ranking System | High Risk | Non-compliant — no conformity assessment, no bias audit, no mandatory human review | Critical |
| ORG-AI-003 AML Transaction Monitoring System | High Risk (conservative) | Partial — pending legal confirmation of final tier | High |
| ORG-AI-004 Voice Biometric Authentication System | High Risk | Non-compliant — no biometric DPIA, no fallback path audit | Critical |
| ORG-AI-005 Customer Service Virtual Assistant | Limited Risk | Partial — mobile disclosure gap | Low |
| ORG-AI-006 Generative Marketing Content Tool | Limited Risk | Partial — inconsistent synthetic content labelling | Medium |
| ORG-AI-007 Employee Productivity Monitoring Tool | Limited Risk | Partial — Works Council consultation outstanding | Medium |
| ORG-AI-008 Internal Portfolio Analytics Tool | Minimal Risk | Compliant | Monitor |
| ORG-AI-009 Regulatory Monitoring Tool | Minimal Risk | Compliant | Monitor |
| ORG-AI-010 Workforce Scheduling Assistant | Minimal Risk (provisional) | Compliant at current scope | Monitor |

This classification record should be reviewed annually, or immediately upon any material change to a system's design, purpose, scope, or deployment context. Classification is a point-in-time legal judgement, not a permanent label.
