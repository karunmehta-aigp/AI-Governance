# Post-Market Monitoring Plan

**Doc ID:** EUAI-007 · **Version 1.0**
**Author:** Anju K. · AIGP (AI Governance Professional)

---

**Disclaimer:** *This document is a portfolio artefact created for demonstration and educational purposes only. It does not represent the policies, systems, or practices of any real organisation. This template does not constitute legal advice and should not be relied upon for regulatory compliance without review by qualified counsel.*

---

## Purpose

Satisfies Article 72's requirement that providers of High-Risk AI systems establish and document a post-market monitoring system proportionate to the nature of the AI technology and the risks of the system, actively and systematically collecting, documenting, and analysing relevant data on performance throughout the system's lifetime.

## 1. System Reference

| Field | Response |
|---|---|
| System ID | ORG-AI-0__ |
| System name | |
| Deployment date | |
| Monitoring plan owner | |

## 2. Data Collection

| Data collected | Source | Frequency | Owner |
|---|---|---|---|
| System outputs and confidence scores | | | |
| Human override / disagreement rate | | | |
| Performance metrics (accuracy, false positive/negative rate) | | | |
| Subgroup performance (where relevant to fairness) | | | |
| User/deployer feedback | | | |
| Input data drift indicators | | | |
| Downstream complaints or appeals related to system output | | | |

## 3. Analysis Cadence

| Activity | Frequency | Responsible |
|---|---|---|
| Automated performance metric review | | |
| Manual sample review of outputs | | |
| Formal quarterly governance review (see Quarterly Governance Review Template) | Quarterly | AI Governance Office |
| Full re-validation against original test set | Annual or on material change | |

## 4. Thresholds and Triggers

| Metric | Threshold | Action if breached |
|---|---|---|
| Accuracy drop below baseline by ___ % | | Trigger review; consider re-training or suspension |
| Subgroup performance disparity exceeds ___ % | | Trigger bias investigation |
| Override rate change of ___ % | | Investigate for automation bias or model degradation |
| Complaint volume exceeds ___ per period | | Escalate to Incident Reporting Procedure |

## 5. Reporting

| Report | Audience | Frequency |
|---|---|---|
| Monitoring summary | AI Governance Committee | Quarterly |
| Serious incident report (if triggered) | Market surveillance authority | Per Incident Reporting Procedure timelines |
| Annual system performance summary | Internal audit, Legal | Annual |

## 6. Relationship to Other Post-Market Obligations

- Monitoring data feeds directly into the Quarterly Governance Review process (see AIGV-CORE-008).
- Any finding meeting the serious-incident definition is routed immediately to the Incident Reporting Procedure (EUAI-008), not held for the next scheduled report.
- Monitoring data retention period: matches the system's record-keeping requirement under Article 12, minimum 6 months post-decommissioning unless a longer period applies under sector-specific law.

## 7. Review

| Field | Response |
|---|---|
| Plan owner | |
| Last reviewed | |
| Next review due | |
