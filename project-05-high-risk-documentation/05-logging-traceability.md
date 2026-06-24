# Document 05: Logging and Traceability

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**System:** TalentBridge Screener (ORG-AI-011)
**EU AI Act Reference:** Article 12 (Record-Keeping)
**Document Type:** Provider (Vendor G) + Deployer
**Version:** 1.0 — October 2026

---

## 1. Purpose

Article 12 of the EU AI Act requires high-risk AI systems to have logging capabilities sufficient to enable traceability of the system's operation throughout its lifecycle. This document describes the logging architecture for TalentBridge Screener, designed with a specific lesson in mind from Project 4's incident response work: that incident's investigation was materially slowed in its early days by the need to reconstruct, after the fact, exactly which model version had produced which historical output. This system's logging is designed so that question never needs to be reconstructed — it is captured at the point of inference, not inferred afterward from surrounding evidence.

---

## 2. What Is Logged

| Event Category | Specific Events | Rationale |
|---|---|---|
| **System inputs** | Job description identifier; CV ingestion event; candidate identifier; submission timestamp | Enables reconstruction of exactly what data the model processed for any given case |
| **Model outputs** | Fit score; rank position; explanation text generated; model version identifier; inference timestamp | Enables review of what the AI recommended, why, and under which model version |
| **Reviewer actions** | Review session start and end; reviewer identifier; final shortlist; structured override-reason category; free-text detail if provided; time spent | Creates the accountability record that underpins the oversight effectiveness monitoring in Document 04 |
| **Candidate communications** | Communication type; trigger event (which always requires the manual coordinator action described in Document 04); timestamp | Links the AI recommendation chain to the actual decision communicated, closing the loop the predecessor system left open |
| **Special category data filter events** | Filter triggered; record routed to manual-only path; reviewer assigned | Enables audit of whether sensitive-data handling is functioning as designed |
| **Model version changes** | Version number at time of each inference; version change events with effective date | Enables correlation of any later-identified issue to a specific model version, directly addressing the reconstruction difficulty experienced in Project 4 |
| **Access and authentication** | Login/logout events; role; session duration | Standard access audit trail |

---

## 3. Logging Architecture

### 3.1 Provider Logging (Vendor G)

Vendor G maintains API-layer logs (inputs, outputs, model version) in its own secure infrastructure, with a contractual commitment to make these available to the organisation within a defined turnaround time for standard requests, and on an expedited basis for incident investigation — the expedited timeline was specifically negotiated to be faster than the predecessor system's vendor commitment, in direct response to the value an earlier, faster log retrieval would have added during Project 4's investigation.

### 3.2 Deployer Logging (the organisation)

The organisation maintains its own full audit trail covering every event category above, in its own secure infrastructure, with a 36-month retention period set to cover relevant employment dispute limitation periods and the organisation's own governance review cycle.

---

## 4. Traceability Examples

### Example: Tracing an individual candidate's outcome

A candidate who applies and is later rejected can have their full decision chain reconstructed precisely:

```
Candidate applies for an open role
  -> CV ingested at [timestamp], assigned candidate identifier
  -> Model version 2.0.4 generates a fit score and explanation text at [timestamp]
  -> Coordinator reviews at [timestamp]; review session duration recorded
  -> Coordinator selects override category "explanation text does not
     reflect relevant unlisted experience known to the coordinator,"
     adds free-text detail, and moves the candidate up the shortlist
  -> Candidate is invited to interview; communication event logged
```

This reconstruction demonstrates active, substantive human oversight rather than passive approval, and would serve as direct evidence if the organisation needed to demonstrate to a regulator that this specific decision was genuinely human-reviewed.

### Example: Investigating a possible systemic pattern

If a quarterly fairness review (Document 06) flagged an unexpected pattern — for example, a lower shortlisting rate associated with a particular demographic proxy for one specific role category — the investigation would proceed as:

```
Query: all applications for the flagged role category, across the
       relevant review period
  -> Extract: scores, model version, reviewer decisions, and override
     categories for every case
  -> Cross-reference: available demographic proxy indicators
  -> Examine: did coordinator overrides correct or compound any score-level
     disparity? (I.e., were lower-scored candidates from the affected
     group disproportionately recovered by human override, or did the
     human layer leave the model's pattern unchanged?)
  -> Examine: did the pattern correlate with a specific model version,
     suggesting a version-specific cause rather than a structural one?
```

This second example illustrates a specific analytical question this system's logging is designed to answer that a less detailed log could not: not just *whether* a disparity exists in the model's raw scores, but whether the human oversight layer is actually functioning as a corrective check against it, or merely rubber-stamping the same pattern through — which is exactly the oversight capacity erosion question named in Project 3's policy.

---

## 5. Log Integrity and Security

| Control | Implementation |
|---|---|
| Log immutability | Append-only storage; any modification requires named senior sign-off and itself creates a separate audit entry |
| Encryption at rest | Standard strong encryption for all stored logs |
| Access controls | Role-based read access limited to the AI Governance Programme Office, Data Protection Officer, Legal, and Information Security; write access is restricted to the automated logging process itself |
| Tamper detection | Cryptographic hash-chaining applied to the most safety-critical log categories — model output and reviewer decision records specifically |
| Backup | Regular backup to a geographically separate location |
| Regulatory access | Logs are producible for inspection within a committed turnaround time of any formal request |

---

## 6. Log Review and Monitoring

| Activity | Frequency | Owner |
|---|---|---|
| Override pattern review | Monthly | HR Director |
| Review-time and oversight-quality analysis | Monthly | AI Governance Programme Office |
| Score distribution analysis by role category | Quarterly | AI Governance Programme Office + ML Engineering |
| Demographic proxy parity analysis | Quarterly | AI Governance Programme Office |
| Access audit review | Quarterly | Information Security |
| Full log audit | Annual | Internal Audit |

Any anomaly surfaced through this monitoring is escalated to the AI Governance Programme Office, with the option to initiate a formal AI incident review under the procedure exercised in Project 4 if the anomaly is material enough to warrant it.

---

## 7. Acknowledged Limitations

| Limitation | Mitigation |
|---|---|
| Demographic data availability is inherently limited, since candidates are not required to disclose protected characteristics | All fairness-oriented analysis relies on imperfect proxy indicators; every monitoring report states this limitation explicitly rather than presenting proxy-based findings with unwarranted certainty |
| Provider-side logs, while available on a committed turnaround, are not real-time | For time-critical incident investigation, the organisation relies first on its own deployer-side logs, which cover every category needed for an initial assessment, and requests provider logs in parallel for deeper model-layer detail rather than waiting on them sequentially |

---

*Log architecture and retention schedules are reviewed annually as part of the system's governance review cycle. Any change to logging scope requires AI Governance Programme Office approval.*
