# AI Risk Assessment — AML Transaction Monitoring System

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**System:** ORG-AI-003 · AML Transaction Monitoring System
**Version Assessed:** as deployed
**Assessment Date:** April 2026
**Prepared by:** AI Governance Programme Office
**Review Status:** Draft — pending Board endorsement

## 1. System Overview

The AML Transaction Monitoring System is a vendor-supplied anomaly-detection tool used by the organisation's Financial Crime Compliance function. It analyses transaction patterns, counterparty data, and customer risk ratings to flag potentially suspicious activity, generating a risk score and routing flagged cases to a queue for review by financial crime analysts.

The system has been in production since 2020 and covers all account holders and counterparties across the organisation's transaction base.

**Deployer:** The organisation (Financial Crime Compliance function)
**Provider:** Vendor B (AML/surveillance technology provider — see Project 1 inventory)
**Affected persons:** All customers and counterparties whose transactions are processed by the system

**Classification status (carried forward from Project 1):** High Risk, on a conservative legal reading. Not a clean Annex III match; legal counsel has not yet issued a final opinion on whether the system's risk-scoring function falls within Category 5's creditworthiness/essential-services-access logic. This assessment treats the system as high-risk for governance purposes throughout, consistent with the conservative approach already adopted, while flagging which specific risks are contingent on that classification being confirmed.

## 2. Risk Assessment Methodology

Risks are assessed on two dimensions, consistent with the methodology used across this portfolio:

**Likelihood (1–5)**

| Score | Definition |
|---|---|
| 1 | Rare — unlikely to occur without deliberate action |
| 2 | Unlikely — plausible but no evidence of occurrence |
| 3 | Possible — could occur; some indicators present |
| 4 | Likely — expected to occur without intervention |
| 5 | Almost certain — evidence suggests it is occurring |

**Impact (1–5)**

| Score | Definition |
|---|---|
| 1 | Negligible — no material harm to individuals or organisation |
| 2 | Minor — limited harm; recoverable |
| 3 | Moderate — meaningful harm to individuals; reputational damage possible |
| 4 | Significant — serious harm to individuals; regulatory consequence likely |
| 5 | Severe — systemic harm; regulatory sanction; major reputational damage |

**Risk Score = Likelihood × Impact**
**Risk levels:** Low (1–6) · Medium (7–14) · High (15–19) · Critical (20–25)

A note on this assessment's structure: each risk below is tagged as either **Classification-Independent** (the risk exists and requires action regardless of how the Annex III question is ultimately resolved) or **Classification-Contingent** (the severity or applicable obligations shift materially depending on the final legal determination). This distinction is carried through the summary matrix.

## 3. Risk Register

### RISK-001 · Customer Risk-Profile Impact Without Contestability Mechanism

**Tag: Classification-Independent**

**Description:** A customer flagged repeatedly by the system, even where every individual alert is ultimately cleared by an analyst, accumulates an internal risk profile that can affect their ongoing relationship with the organisation — for example, influencing account review frequency, transaction limits, or future onboarding decisions for related accounts. There is currently no mechanism by which a customer can learn that this profile exists, understand its basis, or contest it, even though its practical effect on their access to services can be significant over time.

**Affected groups:** Customers and counterparties with transaction patterns that resemble known risk indicators for reasons unrelated to actual financial crime — for example, individuals with irregular but legitimate income patterns, recent immigrants with limited domestic transaction history, or small businesses with seasonal cash flow.

**Likelihood: 4** — Risk-scoring systems of this kind routinely generate false positives tied to legitimate but atypical financial behaviour; this is an inherent feature of anomaly detection, not a defect specific to this vendor.

**Impact: 3** — Individual harm accrues gradually rather than through a single decisive rejection, which makes it harder to detect but no less real; reputational and regulatory consequences are moderate rather than severe unless a pattern affecting a protected group emerges.

**Inherent Risk Score: 12 — MEDIUM**

**Proposed Controls:**
- Establish an internal review pathway so a customer who experiences a service restriction linked to a persistent risk flag can request a review, even though the underlying AML rationale cannot be disclosed to the customer in full
- Periodically audit accumulated risk profiles for patterns that disproportionately affect demographic or behavioural segments unrelated to genuine financial crime risk
- Define a data retention and decay policy so that cleared alerts do not indefinitely inflate a customer's internal risk profile

**Residual Risk Score (with controls): 6 — LOW**
**Control Owner:** Head of Financial Crime Compliance + Data Protection Officer

---

### RISK-002 · Alert Volume Exceeding Genuine Human Review Capacity

**Tag: Classification-Independent**

**Description:** Project 1's RMF mapping noted that "a financial crime analyst reviews every alert before action," and recorded this as a substantive human-in-the-loop control. This assessment tests that claim more closely. The control is only meaningful if analysts have sufficient time and information per alert to exercise genuine judgement. If alert volume has grown faster than review headcount — which is common as transaction volumes scale — the practical reality can shift toward time-pressured approval of system-generated risk scores rather than independent analytical review, even though every alert is nominally "reviewed" by a human.

**Likelihood: 3** — No current data confirms this is happening, but no monitoring exists to confirm it is *not* happening either; the absence of average-time-per-alert metrics is itself a gap that prevents ruling this out.

**Impact: 4** — If review has degraded into rubber-stamping, the organisation's central defence against both false positives harming customers and false negatives missing genuine financial crime is substantially weaker than it appears on paper, with direct regulatory consequence if either failure mode is later identified by a supervisor.

**Inherent Risk Score: 12 — MEDIUM**

**Proposed Controls:**
- Introduce and monitor an average-time-per-alert metric, disaggregated by analyst and alert risk tier, to detect early signs of review degradation
- Set a minimum staffing ratio tied to alert volume, reviewed quarterly
- Sample-audit a random subset of cleared alerts each month for documented analytical reasoning, not just a clearance flag
- Distinguish between routine low-risk-score alerts (which may warrant streamlined review) and high-risk-score alerts (which should always receive full analytical time), rather than treating all alerts identically

**Residual Risk Score (with controls): 6 — LOW**
**Control Owner:** Head of Financial Crime Compliance

---

### RISK-003 · Vendor Model Opacity and Undisclosed Retraining

**Tag: Classification-Independent**

**Description:** The vendor has not contractually disclosed its model retraining cadence or notification process for material model changes. The organisation has no visibility into when or how the underlying detection logic changes, which means a shift in the model's behaviour — for example, a retraining that changes which transaction patterns trigger alerts — could occur without the organisation's compliance function being aware, let alone having validated the change.

**Likelihood: 4** — Vendors retrain detection models on a regular basis as standard practice; the likelihood that this is already happening without disclosure is high, given no contractual requirement currently compels notification.

**Impact: 3** — An undisclosed model change could alter detection sensitivity in either direction (more false positives burdening customers and analysts, or missed genuine risk indicators), with consequences ranging from operational disruption to regulatory exposure if a missed detection is later identified during a supervisory examination.

**Inherent Risk Score: 12 — MEDIUM**

**Proposed Controls:**
- Request retroactive disclosure of retraining history to date as part of the upcoming contract renewal
- Negotiate a contractual requirement for advance notification of material model changes, with a defined validation window before changes go live in production
- Establish an internal model-change validation checklist to be run whenever the vendor confirms a retraining has occurred

**Residual Risk Score (with controls): 4 — LOW**
**Control Owner:** Procurement + Head of Financial Crime Compliance

---

### RISK-004 · Classification Ambiguity Creating Indefinite Governance Limbo

**Tag: Classification-Contingent (the risk itself is about the ambiguity, not about which way it resolves)**

**Description:** The system has been governed as high-risk on a conservative basis since the Project 1 classification exercise, but no fixed deadline exists for legal counsel to issue a definitive opinion. Without a deadline, there is a meaningful risk that the conservative interim position becomes the de facto permanent position — never formally confirmed, never formally ruled out, and never revisited as the regulatory and case-law landscape around Annex III's scope continues to develop. This leaves the organisation unable to state with confidence, if asked by a supervisor, whether its own classification judgement is final or provisional.

**Likelihood: 3** — Indefinite provisional states are a common organisational failure mode once an interim conservative position removes the immediate pressure to resolve the underlying question.

**Impact: 3** — An organisation unable to clearly state its own classification position under direct supervisory questioning faces a credibility and documentation risk, even if the underlying conservative treatment was reasonable.

**Inherent Risk Score: 9 — MEDIUM**

**Proposed Controls:**
- Set a fixed deadline for legal counsel to issue a definitive classification opinion, tracked as a governance action with an owner and a date, not an open-ended request
- Document the conservative interim position and its rationale formally, so the organisation's position is defensible as a reasoned judgement even before the final opinion is received
- Build a standing calendar trigger to revisit the classification if the legal opinion is not received by the deadline, escalating to the Board Risk & Audit Committee

**Residual Risk Score (with controls): 3 — LOW**
**Control Owner:** General Counsel + AI Governance Programme Office

---

### RISK-005 · Insufficient Demographic Fairness Visibility in Risk Scoring

**Tag: Classification-Contingent (severity and specific obligations depend on whether Category 5 logic is confirmed to apply)**

**Description:** No fairness review has been conducted on whether the system's risk scores vary systematically across customer segments in ways unrelated to genuine financial crime risk — for example, by nationality, country of birth, or geographic indicators that may correlate with protected characteristics. This is distinct from RISK-001: that risk concerns the *absence of contestability* once a profile exists; this risk concerns whether the scoring itself is systematically uneven in the first place.

**Likelihood: 3** — Geographic and nationality-linked indicators are common inputs to AML risk-scoring logic industry-wide, and such indicators carry well-documented potential for disparate impact, though no organisation-specific evidence currently confirms this is occurring here.

**Impact: 4** — If confirmed, disparate impact in AML risk-scoring would carry significant regulatory and reputational consequences, given the heightened scrutiny financial crime systems already attract from supervisors, and given that an affected customer would have very limited ability to identify or challenge the cause.

**Inherent Risk Score: 12 — MEDIUM**

**Proposed Controls:**
- Commission a fairness review of risk-score distributions across available demographic proxies, run by an independent function rather than the vendor
- Review which specific data inputs (particularly geographic indicators) most heavily influence the risk score, and assess whether less proxy-prone alternatives exist
- If Category 5 classification is confirmed by legal counsel, treat this control as mandatory under Article 10 data governance requirements rather than as a discretionary best practice

**Residual Risk Score (with controls): 6 — LOW**
**Control Owner:** AI Governance Programme Office + Head of Financial Crime Compliance

---

### RISK-006 · Single-Vendor Dependency for a Core Compliance Control

**Tag: Classification-Independent**

**Description:** The organisation's entire AML transaction surveillance capability depends on a single vendor's system. Unlike a customer-facing convenience tool, this system is the organisation's primary technical control against money laundering and terrorist financing risk — a regulatory obligation in its own right, independent of the AI Act. Vendor disruption, contract termination, or a significant service degradation would leave a core compliance control materially weakened with limited short-notice alternatives.

**Likelihood: 2** — The vendor is an established provider with an existing multi-year relationship, making near-term disruption unlikely, though not impossible.

**Impact: 4** — Given that this system is a primary AML control rather than a convenience feature, any gap in coverage carries direct regulatory consequence under financial crime regulation, separate from and in addition to AI Act considerations.

**Inherent Risk Score: 8 — MEDIUM**

**Proposed Controls:**
- Maintain a documented manual fallback surveillance procedure, even if more limited in scope, for use during any service disruption
- Ensure the contract specifies data portability, export rights, and a minimum notice period for service changes or termination
- Periodically assess alternative vendor options as part of standard procurement risk management, even absent any current intention to switch

**Residual Risk Score (with controls): 4 — LOW**
**Control Owner:** Procurement + Head of Financial Crime Compliance

## 4. Risk Summary Matrix

| Risk ID | Risk | Tag | Inherent Score | Level | Residual Score | Level |
|---|---|---|---|---|---|---|
| RISK-001 | Customer risk-profile impact without contestability mechanism | Classification-Independent | 12 | Medium | 6 | Low |
| RISK-002 | Alert volume exceeding genuine human review capacity | Classification-Independent | 12 | Medium | 6 | Low |
| RISK-003 | Vendor model opacity and undisclosed retraining | Classification-Independent | 12 | Medium | 4 | Low |
| RISK-004 | Classification ambiguity creating indefinite governance limbo | Classification-Contingent | 9 | Medium | 3 | Low |
| RISK-005 | Insufficient demographic fairness visibility in risk scoring | Classification-Contingent | 12 | Medium | 6 | Low |
| RISK-006 | Single-vendor dependency for a core compliance control | Classification-Independent | 8 | Medium | 4 | Low |

## 5. Residual Risk Position

With all proposed controls in place, the residual risk position for this system is assessed as **LOW**, a meaningfully different outcome from the Project 1 CV screening system, where two risks remained at Medium residual even after controls. This difference is itself informative: it reflects that this system already has a genuine human review function and an established vendor relationship to build on, rather than the near-total absence of governance structure found elsewhere in the portfolio. The work here is to strengthen and verify controls that exist in form, not to create them from nothing.

**Acceptance recommendation:** Conditional, but on materially lighter terms than Project 1's recommendation. The system may continue to operate in its current configuration provided:

1. The classification deadline (RISK-004) is formally set and tracked, so the conservative interim treatment does not become a permanent unexamined default
2. Alert review capacity monitoring (RISK-002) is implemented within the next reporting cycle, to confirm the existing human oversight control is functioning as intended rather than merely existing on paper
3. The vendor information request regarding retraining disclosure (RISK-003) is issued ahead of the next contract renewal

A fairness review of risk-score distributions (RISK-005) should be commissioned in parallel, with its priority and binding status to be confirmed once the Annex III classification question is resolved.

## 6. Recommended Human Oversight Model

Human oversight for the AML Transaction Monitoring System should be structured to verify, not merely assume, that existing oversight is meaningful:

**Verification phase (within 30 days):**
- Implement average-time-per-alert tracking by analyst and risk tier
- Sample-audit a random set of recently cleared alerts for documented analytical reasoning
- Confirm current staffing levels against current alert volume

**Strengthening phase (within 60 days):**
- Set a minimum staffing ratio tied to alert volume, with an escalation trigger if volume growth outpaces it
- Differentiate review depth requirements between routine and high-risk-score alerts
- Establish the demographic fairness review of risk-score distributions

**Governance resolution phase (within 90 days):**
- Legal counsel to deliver the definitive Annex III classification opinion
- AI Governance Programme Office to formally close or escalate the classification ambiguity depending on the opinion received
- Quarterly reporting to the AI Governance Committee on alert review capacity metrics and vendor disclosure status

This assessment is point-in-time. Risk ratings should be reviewed following any material change to the system, alert volume, vendor relationship, or the regulatory environment — and in any case, immediately upon resolution of the outstanding classification question.
