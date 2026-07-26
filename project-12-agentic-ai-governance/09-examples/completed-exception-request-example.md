## Example: Completed Exception Request Form — `ORG-AI-011`

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer. Completed instance of [`templates/exception-request-form.md`](../08-templates/exception-request-form.md).

---

**System ID:** ORG-AI-011-A3 (Disbursement Agent) **Requested by:** Engineering Lead **Date:** 2026-09-02

| Field | Entry |
|---|---|
| Control being excepted | `AI-CNTRL-A04` — kill switch tested within 90 days |
| Business justification | Platform migration to new credential vault in progress; kill-switch test harness depends on the old vault's API and cannot run against the new one until migration completes |
| Risk exposure | If containment were needed during the migration window, the automated kill-switch test can't confirm current effectiveness — manual revocation would still be possible but slower and unverified |
| Compensating control in place | Temporary human-in-the-loop requirement on all Disbursement Agent actions (overriding the normal Conditional-autonomy threshold) for the duration of the exception, plus a manually-verified (not automated) revocation test performed once at exception start |
| Requested expiration date | 2026-09-16 (14 days — migration's committed completion window) |
| Approver | AI Governance Committee |

**Risk Review notes:**

Committee assessed that the compensating control (temporary human-in-the-loop) fully offsets the automated kill-switch gap, since a human approving every action makes autonomous runaway behaviour — the scenario the kill switch exists to contain — structurally impossible during the exception window. Approved on that basis.

**Decision:** Approved with modified compensating control (as above)

**Renewal history:**

| Renewal date | New expiration | Re-approved by |
|---|---|---|
| 2026-09-15 | 2026-09-20 | AI Governance Committee — migration ran 4 days over original estimate |

**Closure date:** 2026-09-19 **Closed by:** Engineering Lead, verified by Security function — automated kill-switch test re-confirmed against new vault, human-in-the-loop compensating control removed, system returned to Conditional autonomy per original design.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
