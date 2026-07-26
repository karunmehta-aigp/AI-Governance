## Agentic AI Governance RACI

*Who is Responsible, Accountable, Consulted, and Informed — across the artefacts in this project.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Roles

| Role | Represents |
|---|---|
| Executive Steering Committee | Ultimate accountability for AI risk appetite; escalation point for Critical-tier or cross-system decisions |
| AI Governance Committee | Cross-functional body from Project 6, holds Direct decision rights under the Charter |
| Legal | Regulatory interpretation, contract review (Third-Party AI Governance) |
| Risk | Enterprise risk taxonomy alignment, Risk Classification Addendum methodology |
| Security | Red team, credential/identity controls, incident containment |
| Privacy | Data classification, consent, residency (Data Governance) |
| Engineering | Architecture, implementation, runtime instrumentation |
| System Owner | Named accountable owner for a specific agentic system (Finance Operations Lead for `ORG-AI-011`) |
| Internal Audit | Independent periodic verification (Lifecycle Stage 11) |
| Business Unit | System sponsor, day-to-day operational use |

### RACI by Activity

| Activity | Exec Steering | AI Gov Committee | Legal | Risk | Security | Privacy | Engineering | System Owner | Internal Audit | Business Unit |
|---|---|---|---|---|---|---|---|---|---|---|
| New agentic system approval | I | A | C | C | C | C | R | R | I | C |
| Risk classification (incl. autonomy multiplier) | I | A | I | R | C | I | C | R | I | I |
| Architecture / security review | I | A | I | I | R | C | R | C | I | I |
| Least-privilege credential scoping | I | I | I | I | A | I | R | C | I | I |
| Prompt approval (scope-altering) | I | A | I | I | I | I | R | C | I | I |
| MCP server / tool approval | I | A | I | I | R | I | R | C | I | I |
| Third-party vendor assessment | I | C | A | I | C | R | I | R | I | I |
| Runtime monitoring thresholds | I | C | I | C | I | I | R | A | I | I |
| Kill switch testing | I | I | I | I | A | I | R | R | I | I |
| Incident containment | I | I | I | I | A | I | R | R | I | I |
| Incident root cause & lessons learned | I | A | C | C | R | C | R | R | C | I |
| Periodic audit | I | C | I | I | I | I | I | R | A | I |
| Control Library maintenance | I | A | I | C | C | C | C | I | C | I |

*R = Responsible, A = Accountable, C = Consulted, I = Informed*

### Note on Accountability Concentration

The AI Governance Committee holds Accountability for the majority of decision points here, which is intentional under the Charter's Direct-decision-rights model, but it's worth naming as a design tension: accountability concentrated this heavily requires the Committee to have genuine bandwidth and technical fluency, not just a rubber-stamp role, or this table becomes decorative rather than operative. The Advisory/Delegated tiers in the Charter exist specifically to relieve that pressure for lower-stakes decisions.

### Related Documents

- [Operating Model](./ai-governance-operating-model.md) — the organisational blueprint this table assumes
- [Agent Lifecycle](../03-agent-lifecycle/agent-lifecycle.md) — the stages this RACI's activities map onto

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
