## Data Governance for Agentic Systems

*Extends the organisation's general data governance programme to the specific way agents touch data — reading, deciding, and writing in the same step.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### The Agent-Specific Difference

Standard data governance controls who can read or write a dataset. Agentic systems compress read, decide, and write into a single automated step — meaning a data governance failure (e.g., an over-classified or under-classified record) doesn't surface as a report a human reviews later; it can immediately become an executed financial or operational action, with no interval for a human to catch an error before it lands.

### Data Classification Applied to `ORG-AI-011`

| Data Element | Classification | Where It Appears | Control |
|---|---|---|---|
| Claimant name, employee ID | PII | Intake Agent (read) | Encrypted at rest and in transit; not persisted beyond session (Memory Governance) |
| Receipt images/attachments | PII (may contain incidental sensitive detail) | Intake Agent (read) | Same as above; OCR/extraction output classified at the same level as source |
| Expense policy text | Internal, non-sensitive | Policy-Compliance Agent (read) | Standard internal access control |
| Payment/bank routing detail | Financial, high sensitivity | Disbursement Agent (write) | Masked in logs; full value never written to action-trace logs, only a reference token |

### Required Controls

- **Masking in logs.** Action traceability (Agent Policy §4) requires full audit detail, which creates tension with data minimisation — resolved here by logging reference tokens for sensitive fields (e.g., a claim ID) rather than the raw sensitive value itself, so an auditor can reconstruct *what happened* without the log becoming a second copy of sensitive data.
- **Retention.** Follows the organisation's existing records schedule; agent-specific addition is that retention applies to the full action trace, not just the final decision, since the trace is the evidence base for incident investigation.
- **Residency.** Where the organisation operates across jurisdictions, the underlying model/agent platform's data residency must be confirmed and documented per system — this is frequently missed for agentic systems because the "AI feature" is procured by a business team (see Third-Party AI Governance) rather than routed through the data residency review a core system would get.
- **Consent.** For any agent processing data collected under a specific consent basis (e.g., an employee's expense data collected for reimbursement, not for AI model training), confirm the vendor's terms don't permit using that data to improve or retrain their models unless separately authorised.
- **Lineage.** Because agent decisions chain (Intake → Policy-Compliance → Disbursement), a data quality issue introduced at Intake propagates through the whole pipeline — lineage tracking here means being able to trace a bad Disbursement decision back to the specific upstream read that caused it, not just to "the system."

### Where This Connects

Feeds directly into the Compliance Crosswalk (data protection articles under the EU AI Act, ISO 42001 Annex A data controls) and into Third-Party AI Governance for any vendor-hosted component.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
