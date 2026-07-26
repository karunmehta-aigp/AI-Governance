## AI Governance Roadmap

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

*A maturity-sequenced view of how this project's artefacts would actually get built, in order, in a real organisation — not everything ships on day one.*

---

### Why Sequence Matters More Than the Checklist

A hiring manager who sees thirty governed artefacts can reasonably ask "in what order would you actually build these, with a small team and finite budget?" This roadmap is the honest answer — and it maps directly onto the AI Assurance Framework's five maturity levels, so "where are we" always has a concrete next step rather than being a vague aspiration.

### The Sequence

| Phase | Focus | Key Artefacts Established | Maturity Level (AI Assurance Framework) |
|---|---|---|---|
| **Phase 1 — Inventory** | Know what exists before governing it | Agent Inventory Register, shadow agent discovery baseline | Level 1 → 2 |
| **Phase 2 — Policy** | Establish the rules before enforcing them | Charter, Agent Policy, Human Oversight Framework | Level 2 |
| **Phase 3 — Risk** | Classify what you now know exists, against the rules you've now set | Risk Classification Addendum, AI Risk Committee stood up (Operating Model) | Level 2 → 3 |
| **Phase 4 — Controls** | Turn policy into checkable, ownable items | Control Library, Compliance Crosswalk, RACI | Level 3 |
| **Phase 5 — Runtime** | Move from pre-deployment review to continuous observation | Runtime Governance, KPI Catalog, Executive Dashboard | Level 3 → 4 |
| **Phase 6 — Automation** | Reduce manual evidence-gathering; let tooling produce evidence as a byproduct of normal operation | Governance Automation, Evidence Library | Level 4 |
| **Phase 7 — Continuous Assurance** | The Govern-Validate-Monitor-Audit-Improve loop runs on its own cadence, and Improve findings visibly change Govern | AI Assurance Framework fully operating, Exception Management, Framework Change Control | Level 5 |

### Honest Sequencing Note

Most organisations don't reach Phase 5 before their first agentic incident — Runtime Governance and the Incident Response Playbook often get built *in response to* an early incident rather than ahead of it. That's not a failure of planning; it's realistic. What separates a mature programme from an immature one isn't avoiding that gap entirely, it's how much of Phases 1–4 was already in place when the incident happened, since that determines whether the response is "here's the action trace and the owner" or "we're reconstructing what happened from scratch."

### What "Year 1" Realistically Covers

For a single high-value system like `ORG-AI-011`, Phases 1–5 are achievable within a year with a small dedicated function. Phases 6–7 (automation, continuous assurance) are typically a second-year investment, because they depend on the organisation already having enough Phase 1–5 data to know what's worth automating.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
