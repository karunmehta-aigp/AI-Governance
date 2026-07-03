# Incident Reporting Procedure

**Doc ID:** EUAI-008 · **Version 1.0**
**Author:** Anju K. · AIGP (AI Governance Professional)

---

**Disclaimer:** *This document is a portfolio artefact created for demonstration and educational purposes only. It does not represent the policies, systems, or practices of any real organisation. This template does not constitute legal advice and should not be relied upon for regulatory compliance without review by qualified counsel.*

---

## Purpose

Operationalises Article 73's serious incident reporting obligation for providers of High-Risk AI systems, and sets the internal process for any AI-related incident regardless of whether it meets the formal "serious incident" threshold.

## 1. What Counts as a "Serious Incident"

Under Article 3(49), a serious incident is one that directly or indirectly leads, might have led, or might lead to any of the following:

- The death of a person, or serious harm to a person's health
- A serious and irreversible disruption of the management or operation of critical infrastructure
- The infringement of obligations under EU law intended to protect fundamental rights
- Serious harm to property or the environment

Any incident meeting this definition must be reported regardless of whether the provider believes the AI system caused it — the trigger is the incident occurring in connection with the system's use, not confirmed causation.

## 2. Internal Escalation — All Suspected Incidents

Any suspected AI-related incident, whether or not it meets the serious-incident threshold, follows this internal path first:

| Step | Action | Timeframe | Owner |
|---|---|---|---|
| 1 | Incident identified and reported to AI Governance Office | Within 24 hours of discovery | Any employee |
| 2 | Initial triage: does it meet the serious incident definition? | Within 24 hours of report | AI Governance Office + Legal |
| 3 | Containment: pause/restrict the system if risk is ongoing | Immediate, if warranted | System technical owner + Chair or CISO/General Counsel (per Committee Charter emergency suspension authority) |
| 4 | Investigation and root cause analysis initiated | Within 3 business days | AI Governance Office |

## 3. Regulatory Reporting Timeline (Serious Incidents)

| Trigger | Deadline |
|---|---|
| Serious incident involving death | Immediately, and no later than 2 days after establishing the causal link (or suspected link) |
| Serious incident involving critical infrastructure disruption or fundamental rights infringement | No later than 10 days after becoming aware |
| Other serious incidents | No later than 15 days after becoming aware |
| Initial notification incomplete | A complete report must follow without undue delay once full information is available |

**Note:** these are regulatory maximums, not targets. Internal triage in Section 2 should complete well within these windows so Legal has time to prepare a complete, accurate notification rather than a rushed one at the deadline.

## 4. Regulatory Notification Content

| Field | Response |
|---|---|
| Provider/deployer identification | |
| System identification (name, version) | |
| Description of the incident | |
| Description of harm or potential harm | |
| Corrective/mitigating action taken or planned | |
| Point of contact for follow-up | |

## 5. Notification Recipients

| Recipient | When |
|---|---|
| National market surveillance authority (member state where incident occurred) | All serious incidents |
| Notified body (if one was involved in conformity assessment) | All serious incidents |
| Affected individuals (where a right to notification applies under other law, e.g. data protection) | Per applicable law |
| Internal: AI Governance Committee | All serious incidents, and any incident escalated per Committee Charter thresholds |

## 6. Root Cause Analysis and Remediation

1. Conduct a structured root cause analysis (e.g. 5 Whys) — do not stop at the proximate technical cause; trace back to governance/process gaps.
2. Document remediation actions with owners and target dates.
3. Update the system's risk classification if the incident reveals the original classification was incorrect.
4. Feed lessons learned into the Quarterly Governance Review and, where relevant, the AI Policy or Framework.

## 7. Record-Keeping

All incidents — reported to a regulator or not — are logged in the AI Incident Log (see AI Risk Assessment Toolkit) and retained per the organisation's record retention schedule, minimum aligned to Article 12 logging requirements.
