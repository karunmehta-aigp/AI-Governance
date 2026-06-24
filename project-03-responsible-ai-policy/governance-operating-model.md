# AI Governance Operating Model

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**Organisation:** The organisation
**Version:** 1.0
**Effective Date:** May 2026

---

## Overview

This document describes the organisation's AI governance operating structure: the committees, roles, reporting lines, and interactions that make responsible AI governance an operating reality rather than an aspiration recorded in a policy document.

Governance does not happen inside a policy. It happens in the decisions that get made, the conversations that take place before those decisions, and the processes that connect one to the other. This model defines who makes which decisions, who advises whom, on what timeline, and how AI oversight connects into the organisation's pre-existing governance architecture rather than sitting beside it as a separate, disconnected structure.

---

## Governance Structure Diagram

```
┌─────────────────────────────────────────────────────────────────────┐
│                    BOARD RISK & AUDIT COMMITTEE                      │
│                                                                      │
│  • Annual AI governance programme review                            │
│  • Approval of high-risk AI systems (where escalated)               │
│  • Oversight of material AI incidents                               │
└─────────────────────────────┬───────────────────────────────────────┘
                              │ Reports to / escalates to
                              │
┌─────────────────────────────▼───────────────────────────────────────┐
│                      AI GOVERNANCE COMMITTEE                         │
│                                                                      │
│  Chair: Chief Risk Officer                                          │
│  Members: CTO · DPO · General Counsel · CISO · CFO (observer)       │
│  Meets: Quarterly (+ extraordinary sessions for high-risk approvals) │
│                                                                      │
│  • Approves high-risk AI system deployments                         │
│  • Reviews quarterly AI governance dashboard                        │
│  • Owns the Responsible AI Policy                                   │
│  • Reviews material AI incidents                                    │
│  • Escalation point for governance disputes                         │
└──────────┬────────────────────────────────────────┬─────────────────┘
           │                                        │
           │ Directs / resources                    │ Reviews / escalates
           │                                        │
┌──────────▼──────────────────────┐     ┌──────────▼──────────────────┐
│  AI GOVERNANCE PROGRAMME OFFICE │     │   FUNCTIONAL AI CHAMPIONS   │
│                                 │     │                             │
│  • Programme coordination       │     │  • One per business unit    │
│  • Use case triage & review     │     │  • First point of contact   │
│  • AI System Inventory          │     │    for AI use case queries  │
│  • Training programme           │     │  • Facilitate local AUCR    │
│  • Regulatory monitoring        │     │    submissions              │
│  • Incident coordination        │     │  • Monitor local AI use     │
│  • Reporting to Committee       │     │                             │
└──────────┬──────────────────────┘     └─────────────────────────────┘
           │
           │ Consults / coordinates review
           │
┌──────────▼──────────────────────────────────────────────────────────┐
│                      REVIEW PANEL (per system)                       │
│                                                                      │
│  Assembled per high-risk review. Drawn from:                        │
│                                                                      │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌───────────┐  │
│  │   Legal /   │  │  Data       │  │ Information │  │    ML     │  │
│  │ Compliance  │  │  Protection │  │  Security   │  │ Engineer- │  │
│  │             │  │  Officer    │  │  (CISO      │  │  ing /    │  │
│  │ • Regulatory│  │             │  │  delegate)  │  │  Data     │  │
│  │   opinion   │  │ • GDPR      │  │             │  │  Science  │  │
│  │ • Contract  │  │   review    │  │ • Adversar- │  │           │  │
│  │   review    │  │ • AI Act    │  │   ial       │  │ • Techni- │  │
│  │             │  │   data      │  │   robustness│  │   cal     │  │
│  │             │  │   governance│  │             │  │   review  │  │
│  └─────────────┘  └─────────────┘  └─────────────┘  └───────────┘  │
└─────────────────────────────────────────────────────────────────────┘
           │
           │ Accountable for individual systems
           │
┌──────────▼──────────────────────────────────────────────────────────┐
│                         SYSTEM OWNERS                                │
│                                                                      │
│  One per AI system. Named in the AI System Inventory.               │
│                                                                      │
│  • Accountable for the system's ongoing governance                  │
│  • Responsible for implementing and maintaining oversight controls   │
│  • Escalates material issues to the AI Governance Programme Office  │
│  • Attests annually to compliance with the Responsible AI Policy    │
│  • Manages vendor relationships for vendor-supplied systems         │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Committee and Role Descriptions

### Board Risk & Audit Committee

**Mandate:** Strategic oversight of the organisation's risk framework, with AI governance recognised explicitly as a material and rapidly evolving risk category requiring standing Board attention rather than ad hoc updates.

**AI Governance responsibilities:**
- Annual review of the AI Governance Programme Report, presented by the Chief Risk Officer
- Receives notification of material AI incidents and any regulatory action concerning the organisation's AI systems
- Approves the AI governance programme's budget and resourcing plan
- Reviews and formally endorses the Responsible AI Policy on an annual basis

**Meeting frequency:** Quarterly, with AI governance as a standing agenda item at a minimum of one meeting per year, and any material incident or escalated decision added to the agenda as it arises rather than held for the next scheduled cycle.

---

### AI Governance Committee

**Mandate:** Operational oversight of the AI governance programme as a whole. This is the primary decision-making body for AI governance matters below Board level, and the body with actual authority to approve or block a high-risk system, not merely to advise on one.

**Members:**
- **Chair:** Chief Risk Officer
- **CTO** — technology and engineering perspective
- **Data Protection Officer** — GDPR and EU AI Act data governance obligations
- **General Counsel** — legal and regulatory interpretation
- **CISO** — cybersecurity and information security
- **CFO (observer)** — commercial and financial impact; observer status reflects that financial impact is a relevant input to the Committee's deliberations but the CFO does not hold a governance vote on system approval

**Quorum:** Chair plus any two other members.

**AI Governance responsibilities:**
- Approves high-risk AI system deployments, with the discretion to delegate limited-risk approvals to the AI Governance Programme Office where appropriate
- Reviews and acts on the quarterly AI Governance Dashboard presented by the AI Governance Programme Office
- Reviews material AI incidents (Severity 1 and 2) within 30 days of closure
- Approves updates to the Responsible AI Policy before they go to the Board for endorsement
- Serves as the escalation point for disputes between a system owner and the AI Governance Programme Office
- Provides direction on emerging governance issues — new regulation, new categories of AI capability, or sector-wide incidents that warrant a proactive review of the organisation's own exposure

**Meeting frequency:** Quarterly scheduled sessions, plus extraordinary sessions convened as needed — typically within 5 business days for a high-risk approval request or a material incident, so that the Committee's own process does not become the bottleneck the rest of the operating model is designed to avoid.

---

### AI Governance Programme Office (AGPO)

**Mandate:** Coordinate and operationalise the AI governance programme on a day-to-day basis. The AGPO is the institutional memory and the operational engine of the programme — the Committee sets direction and makes the highest-stakes decisions, but the AGPO is what makes the programme exist between meetings.

**Responsibilities:**
- Maintain the AI System Inventory as the single authoritative record of every AI system in the organisation
- Receive, triage, and coordinate the review of every AI Use Case Request
- Produce risk assessments for Standard Review use cases directly
- Coordinate Enhanced Review panels for high-risk use cases, assembling the right cross-functional reviewers for each system
- Monitor regulatory developments — EU AI Act implementing measures, regulatory guidance, and enforcement actions relevant to the organisation's sector
- Deliver the AI governance training programme across the organisation
- Maintain the AI incident log and coordinate the organisation's AI incident response
- Produce the quarterly AI Governance Dashboard for the Committee
- Produce the annual AI Governance Report for the Board

**Staffing:** An AI Governance Lead (full-time) plus a 0.5 FTE analyst initially, with staffing levels reviewed after 12 months based on actual programme volume — a deliberately modest initial footprint, consistent with the operating model's design principle of fitting a mid-sized regulated organisation rather than assuming the resourcing of a much larger one.

**Reports to:** Chief Risk Officer.

---

### Functional AI Champions

**Mandate:** Embedded governance contacts within each business unit, who make the governance programme locally accessible rather than something that only exists as a distant central function.

**Responsibilities:**
- First point of contact for AI use case queries within their business unit
- Facilitate AUCR submissions — helping business owners complete the request accurately rather than leaving them to interpret governance terminology unaided
- Maintain working awareness of which AI systems are actually deployed or in use within their business unit, including informally adopted tools that have not yet been through the governance process
- Escalate informal or "shadow" AI use to the AGPO — for example, where staff have begun using a generative AI tool for a business purpose without it ever having been submitted for review
- Attend a quarterly AI Champions forum convened by the AGPO, both to receive programme updates and to surface emerging local concerns

**Appointment:** One Champion per business unit, nominated by the relevant business unit head and confirmed by the Chief Risk Officer. The role is typically a part-time addition (10–20% of working time) to an existing role, not a standalone position.

**Currently required in:** Retail Lending · Financial Crime Compliance · Customer Operations · Customer Experience · Marketing · Human Resources / Operations · Finance · Compliance.

---

### System Owners

**Mandate:** Personal accountability for the governance and performance of one individual AI system, for the full duration of that system's operational life.

**Responsibilities:**
- Ensure the system operates within its approved scope and within the bounds of the Responsible AI Policy
- Maintain and actively enforce the system's human oversight procedures — not merely confirm at approval that a procedure exists, but verify periodically that it is still functioning as intended
- Monitor the system's performance against the thresholds approved for it
- Escalate material issues, incidents, or proposed changes to the AGPO without delay
- Manage the vendor relationship directly for vendor-supplied systems, and ensure the contractual AI governance obligations set out in the Responsible AI Policy are actually being met in practice, not merely present in the contract's text
- Complete an annual written attestation of policy compliance
- Ensure that all relevant staff working with the system have completed the required training before they begin using it in a way that affects oversight or decision-making

**Nomination:** The system owner is proposed by the business owner at the point of AUCR submission, and formally confirmed at the point of approval. The role must sit with a senior manager or above who holds genuine operational responsibility for the system — not a junior team member nominated because no one more senior volunteered.

---

## Decision Authority Matrix

| Decision | System Owner | AGPO | AI Governance Committee | Board R&A |
|---|---|---|---|---|
| Approve minimal-risk system | Recommends | **Approves** | Notified | — |
| Approve limited-risk system | Recommends | **Approves** (with Legal and DPO sign-off) | Notified | — |
| Approve high-risk system | Recommends | Coordinates review | **Approves** | Notified |
| Suspend system due to incident | **Immediate suspension authority** | Notified immediately | Informed within 24h | — |
| Reject use case | — | **Decides** (with Committee endorsement required for High Risk) | **Endorses** rejection of High Risk cases | — |
| Update Responsible AI Policy | — | Drafts | **Approves** | **Endorses** |
| Escalate to a regulator | — | Recommends | **Decides** | Informed |

A deliberate feature of this matrix, worth making explicit: **the system owner holds immediate, unilateral suspension authority** for their own system in the event of an incident. This is not an oversight or an inconsistency relative to the more layered approval process above it — the asymmetry is intentional. Approving a system into production should be deliberate and cross-functional, because the cost of a wrongful approval is borne gradually and is at least partially reversible. Suspending a system that may be actively causing harm should not wait for a committee's quorum to assemble — the cost of an unnecessary suspension (some operational disruption, quickly reversed once the concern is investigated) is materially lower than the cost of continued harm during the time it would take to convene a decision-making body. Governance speed should be asymmetric to the asymmetry of the underlying risk.

---

## Interaction with Existing Governance Structures

AI governance is designed to integrate with the organisation's pre-existing governance architecture, not to duplicate it or to operate as a parallel, disconnected structure:

| Existing Function | AI Governance Interface |
|---|---|
| **Enterprise Risk Management** | AI risk is treated as a sub-category of operational and conduct risk. The AI Governance Committee reports into the broader Enterprise Risk Management framework, and the AI System Inventory feeds the enterprise risk register directly for any AI system carrying material risk. |
| **Data Governance / DPO** | The DPO sits as a full member of the AI Governance Committee. Every AUCR involving personal data is co-reviewed by the DPO, and a Data Protection Impact Assessment is coordinated as a single combined exercise alongside the AI risk assessment wherever both are independently required, rather than as two disconnected processes that happen to cover overlapping ground. |
| **Information Security / CISO** | The CISO, or a named delegate, sits on every Enhanced Review panel. Adversarial robustness and cybersecurity requirements for AI systems are owned by Information Security, with AI Governance providing programme-level oversight of how consistently that ownership is exercised across systems. |
| **Legal and Compliance** | Legal provides the regulatory interpretation underlying every classification decision and reviews vendor contracts for AI-specific terms. Compliance separately monitors EU AI Act developments and sector-specific regulatory change relevant to the organisation's AI portfolio. |
| **Procurement** | The AGPO provides Procurement with a standing AI governance assessment checklist for use in any vendor selection process. Procurement, in turn, is required to notify the AGPO of any AI-related vendor selection before contract signature, not after. |
| **Internal Audit** | Internal Audit includes AI governance programme effectiveness in its annual audit plan as a standing item, not an occasional special review. The AGPO provides Internal Audit with direct access to the AI System Inventory, risk assessments, and approval documentation to support that audit work. |

---

## Reporting Calendar

| Report | Frequency | Owner | Audience |
|---|---|---|---|
| AI Governance Dashboard | Quarterly | AGPO | AI Governance Committee |
| AI Incident Summary | Quarterly (or ad hoc, immediately, for any Severity 1 incident) | AGPO | AI Governance Committee |
| High-Risk System Review | Annual, per system | AGPO | AI Governance Committee |
| AI Governance Programme Report | Annual | Chief Risk Officer | Board Risk & Audit Committee |

---

*Questions about this operating model: ai-governance@example-organisation.test*
