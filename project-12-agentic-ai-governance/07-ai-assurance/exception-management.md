## Exception Management

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

*What happens when a system needs to operate outside a control this project defines — because a policy without a real exception path just gets quietly ignored under deadline pressure instead.*

---

### Why Exceptions Need Their Own Process

A governance framework with no sanctioned way to request an exception doesn't produce more compliance — it produces undocumented workarounds, which is strictly worse than a documented, time-bound, reviewed exception. This process exists so that "we need to deviate temporarily" has a legitimate path that leaves an audit trail, instead of becoming a shadow-agent-style gap.

### The Process

```
Policy Exception Requested
        ↓
Risk Review — what does this deviation actually expose us to?
        ↓
Approval — Direct decision, AI Governance Committee (Charter §3)
        ↓
Compensating Controls — what offsets the risk while the exception is active?
        ↓
Expiration — every exception has a hard end date, never open-ended
        ↓
Renewal (if still needed) — requires a fresh Risk Review, not an automatic extension
        ↓
Closure — exception lapses, control resumes, closure logged in Evidence Library
```

### Required Fields for Any Exception Request

| Field | Purpose |
|---|---|
| Control being excepted | Reference to the specific `AI-CNTRL-A0X` control |
| Business justification | Why the control can't be met as written, right now |
| Risk exposure | What specifically becomes possible that the control would otherwise prevent |
| Compensating control | The offsetting measure in place for the exception's duration — an exception with no compensating control is a rejected request, not an approved one |
| Expiration date | Mandatory; no exception is issued without one |
| Approver | AI Governance Committee, logged with the same rigor as a Direct decision under the Charter |

### Illustration Against `ORG-AI-011`

If the Disbursement Agent's kill switch testing (`AI-CNTRL-A04`) were to lapse past 90 days during a platform migration, the correct response under this process is a logged exception — with the compensating control being a temporary human-in-the-loop requirement on all disbursements until the kill switch is re-verified — rather than either quietly leaving the agent Active with a stale kill switch, or suspending the agent without a documented reason.

### Why an Expired-but-Unrenewed Exception Is Itself a Finding

An exception that passes its expiration date without either renewal or closure is treated as equivalent to an undocumented control gap — it goes straight into the Evidence Library as an open item and surfaces in the next Periodic Audit (Lifecycle Stage 11) regardless of whether anyone remembered to flag it.

### Related Documents

- [Agentic AI Control Library](../05-control-library/agentic-control-library.md) — the controls an exception request is filed against

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
