# Document 01: System Description and Intended Purpose

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**System:** TalentBridge Screener
**Provider:** Vendor G (recruitment technology provider, contracted separately from the original CV Screening & Ranking System's provider)
**Deployer:** The organisation
**Document Type:** Provider documentation (supplied) + Deployer context (organisation-authored)
**EU AI Act Reference:** Article 11, Annex IV §1 and §2
**Version:** 1.0 — October 2026

---

## 1. System Identification

| Field | Value |
|---|---|
| System name | TalentBridge Screener |
| Version | 2.0.4 |
| Provider | Vendor G |
| Deployer | The organisation |
| Deployment context | Internal HR — all recruitment activity across the organisation's operations |
| EU AI Act classification | High Risk — Annex III Category 4(a) |
| Unique system identifier | ORG-AI-011 |
| Date of first deployment | Target: 1 December 2026 (pending conformity confirmation) |
| Predecessor system | CV Screening & Ranking System (ORG-AI-002), retired following the governance findings documented in Projects 1 and 2 of this portfolio |

---

## 2. General Description of the AI System

TalentBridge Screener is an AI-assisted recruitment support system that analyses candidate CVs and job descriptions to generate structured shortlists and candidate assessments. It is the organisation's deliberate, governance-led replacement for ORG-AI-002, procured specifically to be built and deployed under a formal AI governance programme from day one, rather than retrofitted with controls after years of ungoverned operation.

The system uses a transformer-based natural language processing model to extract and compare candidate qualifications, experience, and skills against role requirements. It produces:

- A structured shortlist ranked by relevance score
- A per-candidate fit assessment across defined criteria
- Plain-language explanation text for the basis of each candidate's score

The system is explicitly designed as a recommendation tool, not an autonomous decision-maker. Every shortlisting, rejection, and interview-invitation decision is made by a human HR coordinator, using the system's output as one input among several — a design choice made directly in response to RISK-003 of Project 2's risk assessment for the predecessor system, where autonomous rejection without human review was identified as the single highest-severity finding in the entire portfolio.

---

## 3. Intended Purpose

**Primary intended purpose:** To assist HR coordinators and hiring managers in the initial screening of job applications, reducing the time required to review high volumes of CVs while maintaining a structured, criteria-based, and human-reviewed assessment.

**Intended users:** Trained HR coordinators and hiring managers.

**Intended context of use:** The system is deployed within the organisation's applicant tracking system integration, for all open roles across the organisation's operations. It is not intended for, and must not be used for, any purpose other than initial CV screening and shortlisting recommendations.

**Outputs and their intended use:**
- The shortlist and scores are recommendations to the HR coordinator, never a final decision
- HR coordinators are required to review the full shortlist and exercise independent judgement before any candidate communication is sent
- The explanation output exists specifically to support meaningful human oversight, not merely to make the system appear more transparent without actually changing reviewer behaviour

**Intended operational lifespan:** 3 years, subject to annual review and performance reassessment, consistent with the review cadence established in Project 3's AI Use Case Review and Approval Process.

---

## 4. Prohibited Uses

The following uses of TalentBridge Screener are explicitly prohibited:

- Using the system's output as the sole basis for any candidate rejection without human review
- Using the system for internal promotion or performance assessment decisions
- Using the system beyond the screening and initial shortlisting phase — for example, for interview scoring or reference assessment
- Processing candidate data beyond what is contained in submitted CVs and job descriptions, without explicit candidate consent
- Allowing any individual who has not completed the system's oversight training to act as a reviewer

These prohibitions are documented in the system's governance record and communicated to all system users during onboarding, consistent with the Responsible AI Policy established in Project 3.

---

## 5. Known Limitations

| Limitation | Description | Mitigation |
|---|---|---|
| Sensitivity to career-gap framing | The model's relevance scoring shows reduced confidence when a CV contains an unexplained multi-month employment gap, regardless of the reason for that gap | Explanation text surfaces this specifically as a contributing factor to a lower score, prompting the reviewer to seek context (e.g., parental leave, illness, further study) rather than treat the gap as a negative signal on its own |
| Reduced precision for hybrid or cross-disciplinary roles | The matching model performs best against job descriptions with a clearly defined single discipline; roles spanning two distinct skill domains (for example, a combined data-and-compliance role) produce noisier relevance scores | Hiring managers are guided to write job descriptions that separate primary and secondary skill requirements explicitly, and reviewers are trained to weight the explanation text more heavily than the raw score for these roles |
| Limited support for non-chronological CV formats | Skills-based or "functional" CV formats, which present competencies grouped by theme rather than employer-by-employer history, are parsed less reliably than standard chronological formats | The system flags CVs it has classified as non-chronological for mandatory full manual review, rather than silently producing a potentially unreliable score |
| Score compression at the top of large applicant pools | For roles attracting very high application volumes, the model's top-ranked candidates often cluster within a narrow score band, providing less differentiation than the score's apparent precision would suggest | Reviewers are trained that a tight score cluster at the top of a large pool is expected behaviour, not a sign of unusually similar candidates, and are guided to rely more on the explanation text than on small score differences within that cluster |

---

## 6. EU AI Act Classification Basis

**Classification:** High Risk

**Legal basis:** EU AI Act Annex III, Category 4(a) — AI systems intended to be used for recruitment or selection of natural persons, including advertising vacancies, screening or filtering applications, and evaluating candidates in the course of the recruitment process.

TalentBridge Screener falls squarely within this category. It screens and ranks candidate applications. The consequential nature of the decisions it informs — access to employment — and the breadth of individuals affected makes this classification straightforward and non-controversial, in contrast to some of the more borderline classification judgements made elsewhere in this portfolio (for example, the AML Transaction Monitoring System assessed in Project 2).

**Conformity assessment pathway:** Internal control. The system is not a safety component in critical infrastructure and does not perform real-time biometric identification; internal conformity assessment via the organisation's own quality management system is the applicable pathway.

---

*Provider documentation sections have been supplied by Vendor G and are incorporated into this document. Deployer-specific context authored by the AI Governance Programme Office is clearly identified throughout, consistent with the organisation's practice of distinguishing vendor representations from independently verified statements, as established in `technical-documentation.md` of this project.*
