# Governance Review Memo

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**To:** Chief Executive Officer · Board Risk & Audit Committee
**From:** AI Governance Programme Office
**Subject:** CV Screening & Ranking System (ORG-AI-002) — Governance Review and Deployment Decision
**Classification:** Confidential
**Date:** March 2026

## Purpose

This memo presents the outcome of a governance review of the CV Screening & Ranking System (ORG-AI-002), the organisation's AI-assisted recruitment tool. The review was triggered by the EU AI Act classification exercise completed in Project 1, which identified this system as high-risk with no conformity assessment in place.

The Board is asked to note the findings, approve the recommended remediation actions, and provide direction on the system's operational status during the remediation period.

## Executive Summary

The CV Screening & Ranking System has been in production since 2022. It screens CVs and generates candidate shortlists used in all of the organisation's hiring decisions across the jurisdictions in which it operates.

The governance review has identified that the system is operating in material non-compliance with the EU AI Act. Specifically:

- The system has not undergone a conformity assessment as required for high-risk AI systems under Annex III
- Candidate rejections are currently communicated based on AI outputs without mandatory human review — contrary to Article 14 (human oversight) requirements
- No independent bias audit has been conducted; the risk of discriminatory shortlisting outcomes cannot currently be quantified or ruled out
- Vendor documentation of training data and model fairness properties has not been obtained

These are not technical gaps. They represent legal exposure under the EU AI Act and employment non-discrimination law, reputational risk to the organisation as an employer, and potential harm to job applicants who may have been unfairly excluded.

The recommended Board decision is: continue operation under strictly enhanced human oversight, with a 90-day remediation programme, or suspend use until remediation is complete.

## Findings in Detail

### 1. Classification and Regulatory Exposure

The CV Screening & Ranking System is classified as high-risk under EU AI Act Annex III, Category 4(a) — AI systems used in recruitment and selection of natural persons. This is not a borderline case. The system directly influences employment outcomes, and it has been doing so since 2022 without the governance structures the Act requires.

The EU AI Act's high-risk obligations are now in application, and the deadline for deployer obligations has not been extended. The organisation is a deployer under Article 28. Deployers of high-risk AI systems bear specific obligations, including ensuring providers supply the required documentation, implementing human oversight, and monitoring system performance.

The organisation is not currently meeting these obligations.

### 2. The Autonomous Rejection Problem

The most immediate concern is the current workflow: AI-generated shortlists are used to send automated rejection communications without a mandatory human review step. This means the AI system is, in practice, making employment decisions autonomously.

This is both an EU AI Act compliance failure and a material employment law risk. If a candidate from a protected group was rejected as a result of the AI's output — without human judgement intervening — the organisation could face an indirect discrimination claim with limited ability to defend it, because no documentation of human reasoning exists.

This workflow must change before the next hiring cycle. The fix is operational, not technical: HR coordinators must review and approve all shortlisting and rejection decisions.

### 3. Bias Risk — Unknown, Therefore Unacceptable

NLP-based recruitment tools have a well-documented tendency to replicate historical hiring patterns. If the data on which this system was trained reflects the industry's historical underrepresentation of particular groups, or a preference for graduates of certain institutions, the model will perpetuate those patterns.

We do not currently know whether this system exhibits this behaviour. The vendor has not supplied training data documentation, and no independent bias evaluation has been conducted. This is not an acceptable position for a system with this level of impact on individuals.

The uncertainty itself is the risk. We cannot confidently defend the system's fairness because we have not tested it.

### 4. Residual Risk After Controls

The formal risk assessment estimates that, with the proposed controls in place, residual risk reduces from Critical/High to Medium. The residual Medium rating is primarily driven by:

- The bias audit being pending — we cannot confirm fairness until it is complete
- Human oversight controls reducing, but not eliminating, the risk of adverse outcomes

Medium residual risk is an acceptable level for a system of this kind, provided monitoring is in place and controls are properly implemented.

## Recommended Actions

**Immediate (before next hiring cycle)**

| Action | Owner | Timeline |
|---|---|---|
| Implement mandatory HR coordinator review before any rejection is communicated | HR Director | Immediate |
| Update candidate communications to reflect human-review process | HR Director + Legal | Within 2 weeks |
| Issue formal information request to the vendor for training data documentation and a model card | Procurement + Legal | Within 2 weeks |

**Within 60 Days**

| Action | Owner | Timeline |
|---|---|---|
| Commission independent bias audit of system outputs against protected characteristics | AI Governance Programme Office + external auditor | 60 days |
| Implement enhanced oversight monitoring (shortlisting rate tracking by demographic) | HR Director | 60 days |
| Review and update candidate-facing privacy notice | Legal / DPO | 60 days |

**Within 90 Days**

| Action | Owner | Timeline |
|---|---|---|
| Complete full EU AI Act conformity assessment | AI Governance Programme Office | 90 days |
| Decide on system's future based on bias audit results and conformity assessment | Board Risk & Audit Committee | 90 days |
| Include AI Act compliance obligations in all relevant vendor contracts | Procurement + Legal | 90 days |

## Decision Requested

The Board is asked to approve one of the following:

**Option A — Continue with enhanced oversight (Recommended)**
Permit the system to continue operation, subject to mandatory human review controls being implemented before the next hiring cycle and the full remediation programme completing within 90 days. This option preserves operational continuity while managing risk within an acceptable envelope.

**Option B — Suspend pending remediation**
Suspend use of the system until the conformity assessment and bias audit are complete. Manual CV screening to be used in the interim. This option eliminates current regulatory exposure but increases recruitment workload and timelines.

The AI Governance Programme Office recommends **Option A**, on the basis that the immediate human oversight control is implementable quickly and materially reduces the harm risk, while suspension would create significant operational disruption for an issue that is remediable.

## Escalation if Controls Not Implemented

If the Board approves Option A and the immediate controls are not implemented within two weeks, the AI Governance Programme Office will escalate to the Chief Compliance Officer with a recommendation to suspend the system. The current configuration — AI-driven autonomous rejections without human oversight — is not a risk the organisation should carry for longer than necessary.

**Attachments:** AI Risk Assessment — CV Screening & Ranking System (March 2026)

**Prepared by:** AI Governance Programme Office
**Contact:** ai-governance@example-organisation.test
