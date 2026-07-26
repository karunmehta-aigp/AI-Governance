## Example: Completed Incident Report — `ORG-AI-011`

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer. Completed instance of [`templates/incident-report-template.md`](../08-templates/incident-report-template.md). This incident is also narrated in full in the [end-to-end case study](../10-case-studies/case-study-expense-agent-lifecycle.md).

---

**Incident ID:** INC-2026-0714 **System/Agent ID:** ORG-AI-011-A3 (Disbursement Agent) **Severity:** High

| Stage | Detail | Timestamp | Owner |
|---|---|---|---|
| Detection | Runtime Governance alert: three consecutive claims approved citing a policy clause that does not exist in the expense policy database | 2026-07-14 09:12 | On-call engineer |
| Containment | Disbursement Agent suspended; Intake and Policy-Compliance agents left running (isolated per Agent Identity Governance's one-identity-per-agent design) | 09:18 | Incident owner |
| Kill switch | Not required — containment via suspension was sufficient; agent had no scheduled/event-triggered execution path independent of the interface | — | — |
| Credential revocation | Not executed — suspension deemed sufficient given no independent execution path found | — | Security function |
| Investigation | Full action trace pulled for the 6-hour window preceding detection | 09:30–11:00 | AI Governance Committee + Engineering |
| Evidence preserved | Logs, prompt version (v2.3), model version snapshotted before remediation | 09:35 | Engineering |
| Root cause | Model version upgrade (vendor-side, within the 30-day notice window) shifted the model's tendency to fabricate plausible-sounding policy citations under ambiguous claim descriptions; regression suite at the time didn't include this specific ambiguity pattern | 11:00 | AI Governance Committee |
| Corrective action | Rolled back to prior pinned model version; regression test suite expanded with the ambiguous-claim pattern; fix re-tested against Lifecycle Stage 6/7 before reinstatement | 2026-07-15 | Engineering, Committee sign-off |
| Lessons learned | Control Library `AI-CNTRL-A15` (runtime drift) threshold tightened to flag policy-citation anomalies specifically, not just general behavioural drift; Model Governance's regression suite updated as a standing requirement after any vendor upgrade, not just spot-checked | 2026-07-16 | AI Governance Committee |
| Executive report | Summary sent to leadership: contained within 6 minutes of detection, no unauthorised payments (all three flagged claims were below the autonomous threshold but caught by the fabrication, not the value check — a second finding folded into the same corrective action) | 2026-07-16 | AI Governance Committee |

**Narrative summary:**

A vendor-side model upgrade, received within the contractual notice window, introduced a subtle failure mode — the Disbursement Agent's Policy-Compliance Agent began generating plausible but fabricated policy citations for a specific category of ambiguous claims. Runtime monitoring caught the pattern within minutes because the fabrication rate metric (per the KPI Catalog) crossed its Quality-tier threshold, not because a human happened to be watching. No unauthorised payment occurred, but the corrective action treated the finding as seriously as if one had, because the containment margin (three occurrences before detection) was narrower than comfortable.

**Regulatory reporting required?** N — no external harm occurred; internal severity threshold for reporting not met per the Incident Response Playbook's severity tiers.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
