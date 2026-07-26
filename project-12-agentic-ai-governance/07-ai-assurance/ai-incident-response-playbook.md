## AI Incident Response Playbook — Agentic Systems

*Extends Project 4's incident response process with the steps specific to an agent that can act, not just output.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why Agentic Incidents Need an Adapted Playbook

Project 4 governs incidents where a model produced a bad output a human then acted on. An agentic incident is different in one critical way: the harm may already be executed by the time it's detected — a payment already sent, a record already modified — because there was no human step between the agent's decision and the consequence. The playbook below is sequenced to reflect that: containment comes before investigation, not after, because an agent that is still running can cause further harm while the root cause is still being determined.

### The Sequence

| Stage | Action | Owner |
|---|---|---|
| 1. Detection | Alert fires from Runtime Governance monitoring, a human escalation, or an external report | Whoever detects it — no single point of failure for detection |
| 2. Containment | Suspend the specific agent's ability to take further action — pause, not just alert | On-call incident owner |
| 3. Kill switch | If containment alone is insufficient (agent may act via scheduled/event triggers independent of the interface), execute full credential revocation per Agent Identity Governance | Security function |
| 4. Credential revocation | Confirmed independently of the agent's own execution path — the agent must not be able to observe or interfere with its own revocation | Security function |
| 5. Investigation | Pull the full action trace (Agent Policy §4) for the affected agent across the incident window | AI Governance Committee + Engineering |
| 6. Evidence preservation | Logs, prompt version at time of incident (Prompt Governance registry), model version (Model Governance record) are snapshotted before any remediation changes them | Engineering |
| 7. Root cause | Determine which control failed: identity/scope (`AI-CNTRL-A01/A02`), runtime enforcement (`A06`), oversight posture mismatch (`A08`), or an upstream data/prompt issue | AI Governance Committee |
| 8. Corrective action | Fix implemented and re-tested against Agent Lifecycle Stage 6/7 before the agent is reinstated | Engineering, sign-off from Committee |
| 9. Lessons learned | Findings folded back into the Control Library and, where relevant, the Risk Classification Addendum's autonomy multiplier if the incident reveals the current classification under-weighted the actual risk | AI Governance Committee |
| 10. Executive report | Summary to leadership: what happened, what was contained, what changed — timed to any regulatory reporting obligation (EU AI Act Art. 73 serious incident reporting, where applicable) | AI Governance Committee |

### Severity Tiers (Aligned to Charter Section 6 Escalation Triggers)

| Severity | Example | Response Time |
|---|---|---|
| Critical | Agent acted outside documented scope with financial/legal consequence | Immediate containment, kill switch within the hour |
| High | Threshold breached without human sign-off, no external harm yet confirmed | Containment within 4 hours |
| Medium | Repeated ambiguous-policy escalations signaling a policy gap, no unauthorized action | Addressed in next scheduled review, no emergency containment needed |

### What Makes This Auditable Rather Than Aspirational

Every stage above produces a named artefact that already exists elsewhere in this project — the action trace, the prompt registry entry, the model version record — rather than requiring new evidence to be invented during the incident itself. An incident response process that depends on evidence you don't already collect day-to-day isn't one you can actually execute under time pressure.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
