## AI Governance Operating Model

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

*The organisational blueprint — who exists, and how they interact — that the RACI's activity table and the Charter's decision rights both assume.*

---

### Why This Is a Separate Document From the RACI

The RACI answers "who is accountable for this specific activity." This document answers a step earlier: what bodies exist in the first place, what each one is *for*, and how they hand work to each other. Without it, the RACI reads as a table with no organisational context behind it — accurate, but ungrounded.

### The Bodies

| Body | Purpose | Meets |
|---|---|---|
| **Executive Steering Committee** | Sets AI risk appetite and strategic priorities for the governance programme; the AI Governance Committee escalates here for decisions with material business, legal, or reputational exposure beyond a single system | Quarterly, plus on-trigger for the most severe Charter §6 escalations |
| **AI Governance Committee** | Cross-functional decision body; holds Direct decision rights under the Charter for new systems, scope changes, and escalations | Monthly, plus on-trigger for Charter §6 escalations |
| **Architecture Review Board** | Technical gatekeeper at Lifecycle Stage 4 — confirms credential scoping, policy-enforcement placement, and integration design before a system proceeds to security review | Per intake, as systems reach Stage 4 |
| **AI Risk Committee** | Owns the risk methodology itself (Risk Classification Addendum), independent of any single system's approval — reviews whether the autonomy multiplier and thresholds are still calibrated correctly across the whole portfolio | Quarterly |
| **Security** | Executes Lifecycle Stages 5 and 6 (security review, red team); owns Agent Identity Governance and MCP Governance in production | Continuous; represented on the Governance Committee |
| **Privacy** | Executes data classification sign-off (Data Governance); consulted on any persistent memory approval | Per intake; represented on the Governance Committee |
| **Legal** | Vendor contract review (Third-Party AI Governance), regulatory interpretation feeding the Compliance Crosswalk | Per intake and on regulatory change |
| **Internal Audit** | Independent of the Governance Committee by design — executes Lifecycle Stage 11 audits and validates that the Committee's own decisions hold up against the evidence, not just against the Committee's own record of them | Annual, plus for-cause |
| **Product** | Represents the business case at Lifecycle Stages 1–2; translates business need into a scoped system request | Per intake |
| **Engineering** | Builds, instruments, and operates the agent; primary owner of Runtime Governance data | Continuous |
| **Business Owners** | Named accountable individual per deployed system (e.g., the Finance Operations Lead for `ORG-AI-011`); holds Delegated decision rights under the Charter | Continuous |

### How They Interact — The Handoff Chain

```
Business Owner / Product  →  intake request
        ↓
AI Risk Committee  →  risk classification (autonomy multiplier applied)
        ↓
Architecture Review Board  →  design sign-off (credential scoping, enforcement placement)
        ↓
Security + Privacy  →  security review, red team, data classification
        ↓
AI Governance Committee  →  Direct-decision approval
        ↓ (escalates upward only for Critical-tier or cross-system exposure)
Executive Steering Committee  →  risk appetite / strategic sign-off, when triggered
        ↓
Engineering + Business Owner  →  deployment, runtime ownership
        ↓
Internal Audit  →  independent periodic verification (separate from the Committee that approved it)
```

### The Design Choice Worth Naming

Internal Audit sits deliberately outside the approval chain rather than as a member of the Governance Committee. A body that both approves systems and audits them has no independent check on its own decisions — this separation is what makes the Evidence Library and Compliance Crosswalk credible to an external reviewer rather than self-graded.

### Related Documents

- [RACI](./agentic-ai-governance-raci.md) — activity-level detail for who does what across the bodies listed here
- [Agentic AI System Charter](../01-governance-charter/agentic-ai-system-charter.md) — the decision-rights framework these bodies operate under

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
