## Model Governance

*Governing the foundation model underneath the agents — separate from governing the agents themselves.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why This Is Distinct From Agent Governance

Everything else in this project governs what an agent is *permitted to do*. This document governs the thing making the agent's decisions — the underlying foundation model — which the organisation does not control and cannot fully test in the way it tests its own code. A model upgrade pushed by a vendor can change agent behaviour without the organisation changing a single line of its own configuration, which is the core risk this document exists to manage.

### Model Governance Requirements

| Requirement | Detail |
|---|---|
| Model approval | No agent is deployed against an unapproved model; approval requires a benchmark run against the agent's specific task (claims review, in this case) not just a general capability benchmark |
| Version pinning | Production agents are pinned to a specific model version, not a "latest" alias, so a vendor-side upgrade cannot silently change behaviour |
| Upgrade evaluation | Before moving to a new model version, re-run the Agent Lifecycle's Stage 6 (prompt/behavioural testing, including red team) against the new version — an upgrade is treated as a material change, not a patch |
| Regression testing | A fixed set of test cases (including edge cases and prior red-team findings) must pass on the new version before it replaces the pinned one |
| Rollback | A tested path to revert to the last-approved model version if the new one underperforms in production |
| Benchmarking | Task-specific accuracy, plus governance-relevant metrics: rate of the model deviating from its system instructions, rate of tool-call errors, rate of the model fabricating a policy citation |
| Ownership | A named model owner (distinct from the system owner) accountable for tracking vendor model lifecycle — deprecation notices, upgrade timelines, capability changes |

### `ORG-AI-011` Model Record (Illustrative)

| Field | Value |
|---|---|
| Model owner | AI Governance Committee, delegated to Engineering lead |
| Current pinned version | Vendor model, version pinned at deployment — tracked in live registry, not this document, since version currency has the shortest shelf life of anything in this project |
| Last regression test | Tied to Agent Lifecycle Stage 6 record |
| Rollback tested | Tied to Agent Lifecycle Stage 11 procedures |

### Connection to the Rest of the Portfolio

This extends Project 11's technical-control mapping principle — connecting governance paperwork to actual model/eval tooling — specifically to the model-selection and upgrade decision, which Project 11 didn't cover because it predates the agentic use case.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
