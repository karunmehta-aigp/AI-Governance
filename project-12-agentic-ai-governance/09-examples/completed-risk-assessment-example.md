## Example: Completed Risk Assessment — `ORG-AI-011`

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer. Completed instance of [`templates/risk-assessment-template.md`](../08-templates/risk-assessment-template.md).

---

**System ID:** ORG-AI-011 **Assessed by:** AI Risk Committee (delegated to Risk Analyst) **Date:** 2026-05-15

| Field | Entry |
|---|---|
| Use-case domain (base risk tier) | Internal financial operations — expense reimbursement. Base tier: Low, per Project 9 methodology (no customer-facing decision, no credit/employment impact) |
| Autonomy level | Conditional autonomy — autonomous below claim-value threshold, escalates above it |
| Autonomy multiplier applied | 1.5x |
| Base risk score | 2.1 / 5 (Low) |
| Final risk score (base × multiplier) | 3.15 / 5 (raised to Moderate — crosses the review threshold) |
| Data classifications involved | PII (claimant identity), financial (payment routing) |
| Human checkpoint required? | Yes — all claims above defined value threshold route to Finance Operations Lead |
| Committee decision required? | Direct (Charter §3) — autonomy multiplier pushed this system past the Advisory-only tier |
| Reassessment due date | 2026-11-15 (6 months, per Moderate-tier cadence) |

**Assessor notes / rationale for autonomy level chosen:**

Initial design proposal from Engineering requested Full autonomy (no checkpoint) to minimise processing latency. Risk Committee rejected this — under the Human Oversight Framework, Full autonomy requires human-in-the-loop, which would have eliminated the latency benefit anyway. Conditional autonomy with a value threshold was agreed as the design that actually achieves the business goal (fast processing for low-value claims) without requiring an oversight posture the system's actual risk profile doesn't support.

**Precedent for the kill-switch and threshold conditions below:** Knight Capital Group, August 1, 2012. A dormant trading algorithm was inadvertently reactivated and generated over 4 million erroneous orders in roughly 45 minutes — the firm had no functioning kill switch to halt an automated system once it began acting outside its intended parameters, and lost approximately $440M before the losses could even be stopped, not before they were noticed. The lesson that generalises to `ORG-AI-011`: an autonomous system's *value threshold* limits the size of any single bad decision, but only a *tested, immediately usable* kill switch limits how many bad decisions it can make before a human can intervene at all. AI-CNTRL-A04's 90-day kill-switch test cadence exists specifically to prevent the Knight Capital failure mode — a kill switch nobody has verified works is functionally the same as not having one.

**Committee decision:** Approved with conditions

**Conditions:**
1. Threshold set at a value reviewed quarterly, not fixed permanently at launch
2. Kill switch tested pre-launch and every 90 days thereafter (`AI-CNTRL-A04`) — the untested-kill-switch failure mode is the single point this precedent exists to prevent
3. Full behavioural test suite re-run before any threshold increase

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
