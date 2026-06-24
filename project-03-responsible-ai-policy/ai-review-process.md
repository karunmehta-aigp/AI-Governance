# AI Use Case Review and Approval Process

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**Owner:** AI Governance Programme Office
**Version:** 1.0
**Effective Date:** May 2026

---

## Overview

This document describes the end-to-end process for submitting, reviewing, and approving AI use cases at the organisation. It applies to all new AI systems and to material changes to existing systems.

The process is designed to be **proportionate**: simpler, lower-risk use cases move quickly through a lightweight track. Higher-risk systems receive substantially more rigorous, cross-functional scrutiny. The objective is appropriate governance calibrated to actual risk, not maximum friction applied uniformly regardless of what a system actually does.

---

## Process Flow

```
[1] USE CASE SUBMISSION
      |
      v
[2] INTAKE TRIAGE (5 business days)
      |
      +----> [Prohibited] --> REJECT + Notify Chief Risk Officer
      |
      +----> [Minimal/Limited Risk] --> STANDARD REVIEW (2 weeks)
      |
      +----> [High Risk] --> ENHANCED REVIEW (4-6 weeks)
      |
      v
[3] REVIEW AND ASSESSMENT
      |
      v
[4] APPROVAL DECISION
      |
      +----> [Approved] --> Proceed to deployment with conditions
      |
      +----> [Approved with conditions] --> Implement conditions, re-confirm
      |
      +----> [Deferred] --> Address gaps, resubmit
      |
      +----> [Rejected] --> Document rationale, notify submitter
      |
      v
[5] DEPLOYMENT AND REGISTRATION
      |
      v
[6] ONGOING MONITORING AND REVIEW
```

---

## Stage 1: Use Case Submission

**Who submits:** The business owner — the prospective future system owner — of the proposed AI system.

**How:** Submit an AI Use Case Request (AUCR) via the AI Governance intake form maintained by the AI Governance Programme Office.

**Required information:**

| Field | Description |
|---|---|
| Business purpose | What problem does this AI system solve, and why is an AI approach the right one for it? |
| Intended users | Who within the organisation will use this system, and how will its output factor into their decisions? |
| Affected individuals | Which external parties — customers, applicants, counterparties — will be affected by the system's outputs, directly or indirectly? |
| Data sources | What data will the system process? Personal data must be identified explicitly, not bundled into a general description. |
| Output type | What does the system produce — a recommendation, a binding decision, a numeric score, generated content, a classification? |
| Human oversight plan | How will human oversight actually be implemented? Who reviews outputs, with what authority to change them, before action is taken? |
| Vendor or internal | Is this a vendor solution or an internally developed one? If vendor, which provider, and at what stage of procurement? |
| Proposed go-live date | The requested production date, used for resourcing the review, not a commitment |
| Proposed system owner | A named individual prepared to accept governance accountability for the system if it is approved |

**Important:** Submission does not imply approval, and no activity that assumes approval — including signing a vendor contract, beginning training on production data, or communicating a go-live date externally — may proceed before intake triage is complete.

---

## Stage 2: Intake Triage

**Owner:** AI Governance Programme Office
**Timeline:** 5 business days from receipt

The AI Governance Programme Office reviews each AUCR to:

1. Confirm completeness — an incomplete AUCR is returned to the submitter for completion before the triage clock restarts
2. Apply a preliminary EU AI Act risk classification
3. Determine the review pathway — Standard or Enhanced
4. Identify any immediate red flag, including a use case that may fall within a prohibited category

**Triage Outcomes:**

| Outcome | Action |
|---|---|
| Prohibited use case | Reject. Notify the Chief Risk Officer. Document the decision and rationale. |
| Minimal or Limited Risk | Route to Standard Review. |
| High Risk (confirmed or probable) | Route to Enhanced Review. Brief the prospective system owner on the requirements ahead. |
| Unclear classification | Engage Legal and the Data Protection Officer for a classification opinion before final routing — this should be the exception, not a default escape valve used to avoid a triage decision. |

The submitter is notified of the triage outcome and the expected review timeline within the 5-business-day window.

---

## Stage 3A: Standard Review (Minimal / Limited Risk)

**Timeline:** Up to 2 weeks
**Owner:** AI Governance Programme Office

Standard Review covers:

- Confirmation of the preliminary EU AI Act risk classification
- Review of data sources against the lawful basis required under data protection law
- Confirmation of human oversight arrangements, where applicable to the system's risk profile
- For Limited Risk systems specifically: confirmation that an AI disclosure mechanism is implemented for affected individuals, and that it is implemented consistently across every channel through which the system interacts with them
- A check of the vendor's AI governance practices, where the system is vendor-supplied

**Reviewers:** AI Governance Programme Office, with the Data Protection Officer consulted wherever personal data processing is material to the use case.

**Documentation required:**
- Completed AUCR
- A privacy impact assessment where personal data is involved (which may be combined with a full DPIA where one is separately required)
- A vendor AI governance questionnaire, where the system is vendor-supplied

---

## Stage 3B: Enhanced Review (High Risk)

**Timeline:** 4–6 weeks
**Owner:** AI Governance Programme Office (coordinates); AI Governance Committee (approves)

Enhanced Review covers every Standard Review element, plus:

- A full structured risk assessment, following the methodology established in Project 2 of this portfolio
- A technical documentation review covering system description, training data provenance, and a model architecture summary
- A bias and fairness evaluation plan, specifying how fairness will be assessed, by whom, against which metrics, and on what data
- A documented, role-specific, and testable human oversight procedure — generic statements that "a human will review outputs" are not sufficient at this review tier
- A conformity assessment plan addressing the system's EU AI Act Article 43 obligations
- A monitoring and performance management plan, including the specific thresholds that will trigger an out-of-cycle review
- An AI-specific incident response procedure for the system

**Reviewers:**

| Reviewer | Contribution |
|---|---|
| AI Governance Programme Office | Coordinates the review; produces the consolidated risk assessment |
| Data Protection Officer | GDPR and AI Act data governance review |
| Legal / Compliance | Regulatory classification opinion; contractual requirements review |
| Information Security | Cybersecurity and adversarial robustness assessment |
| ML Engineering | Technical feasibility review of proposed controls |
| External auditor / independent assessor | Independent bias evaluation, for high-risk systems with material fairness implications |

**Documentation required:**
- Full AUCR
- Structured risk assessment
- Technical documentation pack, aligned to EU AI Act Annex IV
- Vendor AI due diligence pack, where the system is vendor-supplied
- A completed bias evaluation, or a defined and time-bound plan for one where it cannot be completed pre-approval
- A documented human oversight procedure
- A monitoring plan with named thresholds

---

## Stage 4: Approval Decision

**Standard Review approval:** Joint sign-off by the AI Governance Programme Office and the prospective system owner.

**Enhanced Review approval:** A formal decision by the AI Governance Committee, by majority vote, with quorum defined as the Chief Risk Officer plus at least two other Committee members.

**Approval Conditions:** Approval may be granted conditionally, requiring specific controls to be implemented before or after go-live. Every condition must be documented, assigned to a named owner, and given a defined completion date. Deployment may not proceed if a pre-go-live condition remains unmet on the proposed go-live date — the date moves, the condition does not get waived by default.

**Rejection:** A rejection decision and its rationale are documented in full, and the submitter is notified directly. A rejected system may be resubmitted following a material change to the use case or to the controls proposed for it; resubmission is not a formality and is triaged again from the start.

**Escalation:** If the AI Governance Committee cannot reach consensus, the decision escalates to the Chief Risk Officer. If the Chief Risk Officer's decision is itself contested by a Committee member, it escalates further to the Board Risk & Audit Committee. This escalation chain has exactly two steps and no informal shortcuts around it.

---

## Stage 5: Deployment and Registration

Upon approval, the system owner must, before go-live:

1. Register the system in the AI System Inventory, with the AI Governance Programme Office recording the approval date, any conditions, the confirmed risk classification, and the next scheduled review date
2. Complete every pre-go-live condition attached to the approval
3. Confirm that monitoring infrastructure is in place and operational before go-live, not scheduled for implementation shortly after
4. Confirm that human oversight procedures are operational and that relevant staff have completed the required training
5. For high-risk systems specifically: confirm that EU AI Act registration requirements are met before go-live

The AI Governance Programme Office confirms go-live readiness formally before the system is permitted to enter production.

---

## Stage 6: Ongoing Monitoring and Review

**Continuous monitoring (system owner responsibility):**
- Track performance metrics against the thresholds defined at approval
- Monitor for data drift, performance degradation, or an emerging fairness concern
- Maintain human oversight procedures in genuinely operational condition — not merely documented, but actually functioning at the volume and pace the system now operates at
- Report material issues to the AI Governance Programme Office promptly, not at the next scheduled review

**Periodic review (AI Governance Programme Office):**

| Risk Tier | Minimum Review Frequency |
|---|---|
| High Risk | Annual formal review, plus any event-driven review |
| Limited Risk | Annual check-in with the system owner |
| Minimal Risk | Biennial review, or upon material change |

**Trigger for an out-of-cycle review:**
- A material change to the system — a new model version, an expanded scope, or a new data source
- An AI incident involving the system
- A regulatory change affecting the system's classification or obligations
- A change of system owner

---

## Material Changes

A material change to an approved system requires a new AUCR or a formal change request to the AI Governance Programme Office. The following constitute a material change:

- A change to the system's purpose or scope
- Processing of a new category of personal data
- A significant model update, such as retraining on new data or an architecture change
- A change of vendor
- Deployment to a new geography
- A change of system owner

A minor change — for example, a user-interface update or a bug fix that does not affect model behaviour — may be documented without triggering a new full review, at the discretion of the AI Governance Programme Office, provided that discretion is itself documented and not assumed silently.

---

*Process queries: ai-governance@example-organisation.test*
