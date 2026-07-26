## How to Implement This Framework — A 5-Week Starting Path

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer. See [AI Governance Roadmap](./ai-governance-roadmap.md) for the fuller multi-phase, multi-year sequencing this 5-week plan is the on-ramp for.

---

### Why 5 Weeks, and Why This Order

This isn't a complete implementation — it's the minimum sequence that gets an organisation from zero to a genuinely defensible starting position, fast enough that leadership sees progress before patience runs out. Each week deliberately depends only on what the prior week produced, so the plan can survive being paused or re-prioritised without losing the work already done.

### Week 1 — Build the Inventory

Run a shadow agent discovery pass first, not last — you cannot govern what you haven't found. Populate the [Agent Inventory Register](../05-control-library/agent-inventory-register.md) for every agentic system currently in production, using the [inventory entry template](../08-templates/agent-inventory-entry-template.md). Expect this week to surface at least one system nobody remembered was agentic.

**Output:** A complete, honest inventory — including the uncomfortable entries.

### Week 2 — Classify Risk

Apply the [Risk Classification Addendum](../04-risk-framework/agentic-risk-classification-addendum.md)'s autonomy multiplier to every inventoried system, using the [risk assessment template](../08-templates/risk-assessment-template.md). Don't wait for perfect data — a defensible first-pass score you can refine beats an accurate score six months from now.

**Output:** Every system has a risk tier and a named owner.

### Week 3 — Establish Controls

Stand up the [Control Library](../05-control-library/agentic-control-library.md) against the highest-risk systems first, not all systems simultaneously. Confirm least-privilege credential scoping ([Agent Identity Governance](../05-control-library/agent-identity-governance.md)) and a tested kill switch before anything else — these are the two controls every other control depends on being able to fall back to.

**Output:** Your highest-risk systems have working, tested kill switches and scoped credentials.

### Week 4 — Implement Runtime Monitoring

Instrument the [Runtime Governance](../06-runtime-governance/runtime-governance.md) metrics from the [KPI Catalog](../06-runtime-governance/ai-governance-kpi-catalog.md) — start with override rate, policy violations, and kill-switch currency, since these three catch the most common early failures. Full observability (cost, latency, drift) can follow in later iterations.

**Output:** A dashboard that would actually tell you if something went wrong today, not just at the next audit.

### Week 5 — Start Assurance Reviews

Run the first [Periodic Audit](../03-agent-lifecycle/agent-lifecycle.md) (Lifecycle Stage 11) against whatever evidence Weeks 1-4 produced, using the [Evidence Library](../07-ai-assurance/evidence-library.md) index and the [runtime review checklist](../08-templates/runtime-review-checklist.md). Hold the first [Governance Committee meeting](../08-templates/governance-committee-agenda.md) using the standing-items agenda.

**Output:** The Govern-Validate-Monitor-Audit-Improve cycle ([AI Assurance Framework](../07-ai-assurance/ai-assurance-framework.md)) has run once, end to end, on real systems.

### What Comes After Week 5

This plan gets an organisation to roughly Maturity Level 3 (Managed) on the Assurance Framework's scale. Levels 4 (Measured) and 5 (Optimising) — full automation, continuous assurance — are the subject of the fuller [Roadmap](./ai-governance-roadmap.md) and typically span a second year, not a second month.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
