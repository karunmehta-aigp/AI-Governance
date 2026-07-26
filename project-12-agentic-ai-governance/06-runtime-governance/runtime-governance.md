## Runtime Governance

*What is watched while the agent is actually running — as opposed to what was reviewed before it was allowed to.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why Runtime Governance Is Its Own Document

Every other document in this project governs a decision point — deploy or don't, approve or don't. Runtime governance is different: it's continuous, has no single approval gate, and its whole job is catching the failure modes that only exist in production — drift, cost overruns, and behaviour no pre-deployment test could have surfaced because it depends on real user input at scale.

### What Is Monitored Live

| Signal | What It Catches | Alert Threshold (illustrative) |
|---|---|---|
| Policy engine decisions (allow/deny/escalate per call) | Whether runtime enforcement (Agent Policy §5) is actually firing, not just configured | Any deny-then-retry-then-succeed pattern — signals probing |
| Tool call volume & type per agent | Scope creep — an agent calling tools outside its Inventory-documented action scope | Any call to an undocumented tool, zero-tolerance |
| Memory access patterns | Unexpected reads of another agent's memory or a data store outside documented scope | Any cross-agent memory read |
| Prompt drift | System prompt or instructions changing without going through Prompt Governance | Any diff between deployed prompt and registered version |
| Agent behavioural drift | Output/action distribution shifting from the tested baseline over time | Statistical deviation beyond a defined band, reviewed monthly |
| Hallucination / factual-error rate | Agent acting on a fabricated premise (e.g., approving a claim citing a policy clause that doesn't exist) | Any instance on a Conditional/Full-autonomy system triggers review |
| Human override rate | How often a human intervenes or reverses an agent decision | Sustained rise — see Human Oversight Framework |
| Escalation volume | Load on the human checkpoint — too high signals a miscalibrated threshold, too low may signal the checkpoint isn't being exercised in practice | Both directions are findings |
| Cost per transaction | Runaway loops, retries, or an agent quietly calling an expensive model tier | Deviation from budget baseline |
| Latency | Agent stalling in a way that leads a human operator to manually intervene, bypassing the checkpoint | p95 latency breach |

### Where This Plugs Into Existing Artefacts

- Feeds the Executive Dashboard directly — every metric above is a dashboard tile
- Findings above threshold become Agent Lifecycle Stage 11 (Periodic Audit) inputs, or trigger the Charter's Section 6 out-of-cycle review if severe
- A live policy engine is the enforcement mechanism required by `AI-CNTRL-A06` — this document is where that control's evidence is actually generated

### Honest Limitation

Runtime monitoring is only as good as the instrumentation the underlying agent framework exposes. Where an agent architecture doesn't expose intermediate plan/reasoning steps (only final actions), drift and hallucination detection degrade to output-pattern analysis rather than true root-cause visibility — worth stating plainly rather than implying a monitoring capability that exceeds what the toolchain actually provides.

### Related Documents

- [AI Governance KPI Catalog](./ai-governance-kpi-catalog.md) — canonical definitions and thresholds for every metric monitored here
- [Agentic AI Control Library](../05-control-library/agentic-control-library.md) — control A15 requires the drift monitoring this document describes

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
