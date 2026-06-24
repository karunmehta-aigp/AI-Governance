# AI Risk Assessment — CV Screening & Ranking System

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**System:** ORG-AI-002 · CV Screening & Ranking System
**Version Assessed:** v2.3 (as deployed)
**Assessment Date:** March 2026
**Prepared by:** AI Governance Programme Office
**Review Status:** Draft — pending Board endorsement

## 1. System Overview

The CV Screening & Ranking System is a vendor-supplied NLP-based recruitment tool deployed by the organisation's HR department. It ingests candidate CVs and job descriptions, performs semantic matching, and generates a ranked shortlist of candidates with an individual fit score per applicant.

The tool was deployed in 2022 and is currently used in all hiring processes across all business units and geographies in which the organisation operates.

**Deployer:** The organisation (HR Department)
**Provider:** Vendor A (recruitment technology provider — see Project 1 inventory)
**Affected persons:** External job applicants

## 2. Risk Assessment Methodology

Risks are assessed on two dimensions:

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

## 3. Risk Register

### RISK-001 · Proxy Discrimination via Training Data Bias

**Description:** The CV Screening & Ranking System was trained on historical recruitment data supplied by the vendor's broader customer base. If that historical data reflects past discriminatory hiring patterns — for example, systematic underrepresentation of women in technical roles, or a preference for candidates from certain educational institutions — the model will learn and replicate those patterns. The model may use surface features such as writing style, school names, career gaps, or name inference as proxies for protected characteristics.

**Affected groups:** Applicants from protected groups, including women, ethnic minorities, older workers, and those with non-linear career histories.

**Likelihood: 4** — Historical hiring data routinely reflects discriminatory patterns, a well-documented phenomenon in NLP-based recruitment tools generally. No bias audit has been performed to demonstrate this system is an exception.

**Impact: 4** — Systemic exclusion of protected-group candidates from shortlists constitutes indirect discrimination under EU employment non-discrimination law. Regulatory and reputational consequences are significant.

**Inherent Risk Score: 16 — HIGH**

**Proposed Controls:**
- Require the vendor to supply training data provenance and bias audit documentation
- Commission an independent fairness evaluation across protected characteristics (gender, age, ethnicity proxy)
- Track shortlisting rates by demographic segment on an ongoing basis
- Implement mandatory human review of all shortlists before any candidate rejection communication is sent

**Residual Risk Score (with controls): 8 — MEDIUM**
**Control Owner:** HR Director + Chief People Officer

---

### RISK-002 · Lack of Explainability for Adverse Decisions

**Description:** Candidates who are not shortlisted currently receive no meaningful explanation for the rejection. The system produces a fit score but no human-interpretable reasoning. Under EU AI Act Article 13 and the GDPR's provisions on the right to meaningful information about automated decision-making, affected individuals have a right to understand the basis of decisions that significantly affect them.

**Likelihood: 5** — The system is currently in production with no explanation capability. Every rejection is currently unexplainable beyond a numeric score.

**Impact: 3** — Individual harm (applicants cannot meaningfully appeal or understand the rejection); regulatory risk if challenged; reputational risk if publicised.

**Inherent Risk Score: 15 — HIGH**

**Proposed Controls:**
- Require the vendor to implement or expose an explanation capability providing plain-language reasons for low scores
- Implement human review as the actual decision point — the AI shortlist is treated as an input, not the decision
- Update candidate communications to reflect that human judgement, not automated decision-making, determines rejection
- Review the candidate-facing privacy notice to ensure it accurately reflects current automated processing practices

**Residual Risk Score (with controls): 6 — LOW**
**Control Owner:** HR Director + Legal/Compliance

---

### RISK-003 · Absence of Human Oversight in Rejection Workflow

**Description:** The current workflow is: HR coordinators upload CVs → the system generates a ranked shortlist → candidates below a defined threshold score receive an automated rejection communication. There is no mandatory human review step before rejections are sent. The AI system is, in practical effect, making final employment decisions autonomously.

Under EU AI Act Article 14, high-risk AI systems must enable human oversight, including the ability for humans to override outputs and to refrain from using outputs entirely. The current workflow does not meet this requirement.

**Likelihood: 5** — This is the current, documented workflow; it is not a hypothetical risk.

**Impact: 4** — Autonomous rejection of candidates by an AI system constitutes a high-risk AI system making binding decisions without human oversight: a direct EU AI Act compliance failure, with potential discrimination and employment law liability layered on top.

**Inherent Risk Score: 20 — CRITICAL**

**Proposed Controls:**
- Immediately implement a mandatory human review gate: HR coordinators must review and approve all rejection decisions before they are communicated to candidates
- Treat the AI shortlist as a recommendation, not a decision
- Define the criteria HR coordinators must use to override the AI's ranking
- Log all instances where the human decision diverges from the AI recommendation, to provide model feedback data over time

**Residual Risk Score (with controls): 8 — MEDIUM**
**Control Owner:** HR Director
**Timeline:** Immediate — this control must be implemented before the next hiring cycle

---

### RISK-004 · Training Data Provenance and Data Quality

**Description:** The vendor has not supplied documentation of the training data used to build the model. The organisation cannot confirm what data was used, whether it was lawfully obtained, whether it incorporates the organisation's own historical candidate data (which would raise separate data protection concerns), or whether it is representative of the applicant pool the organisation actually receives.

**Likelihood: 4** — The vendor has not provided this information despite the system being in production. Gaps in documentation are probable rather than merely possible.

**Impact: 3** — Data quality issues may degrade model performance; unlawfully sourced training data creates data protection liability; non-representative training data compounds the bias risk identified in RISK-001.

**Inherent Risk Score: 12 — MEDIUM**

**Proposed Controls:**
- Issue a formal information request to the vendor for training data sources, processing basis, data subjects, fairness testing methodology, and a model card
- Include EU AI Act Article 10 compliance requirements in the next contract renewal
- If the vendor cannot provide adequate documentation, treat this as a material contract concern and initiate an alternative procurement assessment

**Residual Risk Score (with controls): 4 — LOW**
**Control Owner:** Procurement + Legal

---

### RISK-005 · Scope Creep Beyond Intended Purpose

**Description:** The system was procured for initial CV screening and shortlisting. There is a risk that, over time, its outputs are used beyond this intended scope — for example, informing interview question selection, influencing salary offer decisions, or being repurposed for internal mobility and promotion decisions. Each expansion of scope may carry a different risk profile and require a separate governance assessment.

**Likelihood: 3** — Scope creep is common with convenient AI tools, and no formal use-case boundary policy currently exists for this system.

**Impact: 3** — Expanded use in, for example, promotion decisions would constitute a different high-risk use case requiring its own conformity assessment, and using the system informally for this without review would itself be a governance failure.

**Inherent Risk Score: 9 — MEDIUM**

**Proposed Controls:**
- Document the permitted use scope formally in the system's governance record
- Require a new governance review and risk assessment before any expansion of the system's use
- HR Director to attest annually to scope adherence

**Residual Risk Score (with controls): 3 — LOW**
**Control Owner:** HR Director

---

### RISK-006 · Vendor Dependency and Continuity Risk

**Description:** The organisation's recruitment workflow is dependent on a single vendor. If the vendor ceases to operate, withdraws the product, or makes changes to the model that degrade performance, the organisation currently has no documented fallback capability.

**Likelihood: 2** — The vendor is an established provider, though a relatively small one.

**Impact: 2** — Disruption to the recruitment workflow would be inconvenient but manageable through manual screening in the interim.

**Inherent Risk Score: 4 — LOW**

**Proposed Controls:**
- Ensure the contract includes data portability and export rights
- Maintain a documented capability to revert to manual CV screening during any vendor disruption
- Include model change notification requirements in the contract

**Residual Risk Score (with controls): 2 — LOW**
**Control Owner:** Procurement

## 4. Risk Summary Matrix

| Risk ID | Risk | Inherent Score | Level | Residual Score | Level |
|---|---|---|---|---|---|
| RISK-001 | Proxy discrimination via training data bias | 16 | High | 8 | Medium |
| RISK-002 | Lack of explainability for adverse decisions | 15 | High | 6 | Low |
| RISK-003 | Absence of human oversight in rejection workflow | 20 | Critical | 8 | Medium |
| RISK-004 | Training data provenance and data quality | 12 | Medium | 4 | Low |
| RISK-005 | Scope creep beyond intended purpose | 9 | Medium | 3 | Low |
| RISK-006 | Vendor dependency and continuity risk | 4 | Low | 2 | Low |

## 5. Residual Risk Position

With all proposed controls in place, the residual risk position for this system is assessed as **MEDIUM**. Two risks (RISK-001 and RISK-003) remain at medium residual risk because:

- Bias audit results are not yet known — controls reduce the likelihood of harm but cannot eliminate the risk until the audit is actually complete
- Human oversight controls reduce, but do not eliminate, the risk of discriminatory outcomes — ongoing monitoring is required even after the control is implemented

**Acceptance recommendation:** Conditional. The system should not continue in its current configuration. It may continue to operate only if the following minimum controls are implemented immediately:

1. Mandatory human review of all shortlisting and rejection decisions (RISK-003)
2. Updated candidate-facing communications removing references to automated decision-making as the basis for rejection (RISK-002)
3. A formal information request issued to the vendor for training data documentation (RISK-004)

A full conformity assessment and an independent bias audit must be completed within 90 days. If controls 1–3 cannot be implemented before the next hiring cycle, the system should be suspended pending remediation.

## 6. Recommended Human Oversight Model

Human oversight for the CV Screening & Ranking System should be structured in three stages:

**Minimum viable oversight (immediate):**
- HR coordinator reviews the AI-generated shortlist and approves or modifies it before any candidate communication is sent
- HR coordinator records whether they accepted or modified the AI recommendation, and the reason for any modification
- No rejection communication is sent without HR coordinator approval

**Enhanced oversight (within 60 days):**
- Hiring manager reviews the shortlist in addition to the HR coordinator for roles above a defined seniority threshold
- Monthly review of shortlisting rate by demographic indicator, where data is available
- Quarterly report to the HR Director on AI recommendation acceptance/override rate and patterns

**Governance oversight (within 90 days):**
- The AI Governance Committee receives a quarterly summary of the system's performance and fairness metrics
- Annual review of the system's risk assessment by the AI Governance Programme Office

This assessment is point-in-time. Risk ratings should be reviewed following any material change to the system, its use, or the regulatory environment.
