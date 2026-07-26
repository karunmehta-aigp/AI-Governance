## AI Assurance Framework

*The framework that ties every other document in this project into a repeating cycle, rather than a one-time compliance exercise.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why "Governance" Alone Isn't the Whole Model

Everything else in this project answers "what controls exist." Assurance answers a harder question: "how confident can we actually be that those controls are working, on an ongoing basis, and how do we get more confident over time." A governance programme that only ever checks its own policy documents for internal consistency can look complete while having no evidence any control is functioning in production. This framework is the five-stage cycle that closes that gap.

### The Cycle

**Govern.** Define the policy, charter, and control set — everything in this project's Charter, Agent Policy, and Control Library.

**Validate.** Confirm, before deployment, that controls are actually implemented as designed — this is the Agent Lifecycle's architecture, security, and testing gates (Stages 4–7). Validation answers "was it built correctly," not "is it still working."

**Monitor.** Continuous, in-production observation — Runtime Governance. Monitoring answers "is it working right now," and is the stage most governance programmes underinvest in relative to Govern and Validate.

**Audit.** Periodic, independent re-verification — Agent Lifecycle Stage 11, using the Control Library and Compliance Crosswalk as the checklist. Audit exists because continuous monitoring can itself drift or be misconfigured; an independent, scheduled re-check catches what monitoring silently stopped catching.

**Improve.** Findings from Monitor and Audit feed back into Govern — a control that repeatedly generates false escalations gets recalibrated (Risk Classification Addendum), a gap found in incident response (the Playbook's Lessons Learned stage) becomes a new or revised control. This is the stage that makes the cycle a cycle rather than a one-way pipeline.

### Maturity Self-Assessment

A practical use of this framework is scoring where a given system or the programme overall sits, rather than treating "governed" as binary:

| Level | Description | `ORG-AI-011` Status |
|---|---|---|
| 1 — Ad hoc | Controls exist informally, undocumented | — |
| 2 — Defined | Controls documented (policy exists) but not consistently validated | — |
| 3 — Managed | Controls documented and validated pre-deployment | — |
| 4 — Measured | Controls monitored continuously in production with defined thresholds | Current state |
| 5 — Optimising | Monitoring and audit findings systematically feed back into control and risk-methodology changes (the Improve stage functioning in practice, with evidence of at least one control revised as a result) | Target state — the autonomy multiplier in the Risk Classification Addendum is one example of a control created in response to an external finding (the industry high-risk-by-default debate), which is the pattern this level requires more of |

### Why This Belongs in a Portfolio, Not Just an Enterprise Programme

This is the artefact that signals "I think about governance as a continuously operating system, not a document set" — which is the distinction between an AI Governance Analyst and an AI Governance Architect or Program Manager role.

### Related Documents

- [Evidence Library](./evidence-library.md) — the index that makes the Audit stage of this cycle actually retrievable
- [AI Governance Roadmap](../12-implementation-guide/ai-governance-roadmap.md) — how the five maturity levels below map to a real build sequence

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
