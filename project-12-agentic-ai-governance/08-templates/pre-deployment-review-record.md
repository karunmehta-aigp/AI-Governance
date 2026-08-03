
## Template: Pre-Deployment Review Record

*The go/no-go decision record for Agent Lifecycle Stage 7 (Human Approval) — the single artefact that has to exist before Stage 8 (Deployment) can start.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why This Sits Between the Lifecycle and the Control Library

The [Agent Lifecycle](../03-agent-lifecycle/agent-lifecycle.md) names Stage 7 as a gate but doesn't specify the artefact that clears it. This template is that artefact: it pulls the pass/fail state of every control relevant to the agent's autonomy level into one page, forces a documented decision, and creates the evidence an auditor would ask for first — "show me the record that says this was allowed to ship." A lifecycle stage without a produced document is a step nobody can prove happened.

### Review Depth Is Set by Autonomy Level, Not a Separate Tier System

This project already has a tier system — the [Agentic Risk Classification Addendum](../04-risk-framework/agentic-risk-classification-addendum.md)'s autonomy multiplier. Review depth below reuses it directly rather than introducing a second, parallel scale:

| Autonomy Level | Review Required | Sign-Off Authority |
|---|---|---|
| Assistive / Supervised | Section A only | System owner |
| Conditional autonomy | Sections A + B | System owner + AI Governance Committee (Advisory) |
| Full autonomy | Sections A + B + C | AI Governance Committee (Direct-decision), per Charter §3 |

If a reviewer disagrees on which level applies, the Charter's standing rule governs: classify at the higher level.

---

### Pre-Deployment Review Record

**Agent ID:** _________________ **Parent System ID:** _________________ **Autonomy Level:** _________________

**Review Date:** _________________ **Business Owner:** _________________ **Technical Owner:** _________________ **Risk Owner:** _________________

#### Section A — Every Agent

| # | Check | Control / Reference | Evidence Seen (Y/N) |
|---|---|---|---|
| A1 | Job scope written down, including what the agent must never do | Charter §2 | |
| A2 | Named business owner and technical owner, both aware they own it | AI-CNTRL-A01 | |
| A3 | Complete tool/API/MCP inventory, no undocumented access | AI-CNTRL-A14 | |
| A4 | Kill switch exists and has a named person authorised to pull it | AI-CNTRL-A04 | |
| A5 | Data the agent can read is mapped and minimised to task need | AI-CNTRL-A13, ISO 42001 A.7 | |
| A6 | Disclosure to affected users that they are interacting with AI, where required | EU AI Act Art. 50 | |

#### Section B — Agents That Act (Conditional/Full autonomy)

| # | Check | Control / Reference | Evidence Seen (Y/N) |
|---|---|---|---|
| B1 | Agent runs under its own scoped non-human identity, not a shared or admin credential | AI-CNTRL-A01, AI-CNTRL-A02 | |
| B2 | Every untrusted-content path (email, documents, user input) is listed | OWASP LLM01 | |
| B3 | Injection testing actually attempted on those paths, with results recorded — not assumed safe | AI-CNTRL-A06, MITRE ATLAS | |
| B4 | Irreversible or high-impact actions are capped, gated, or blocked outright, with the threshold stated in numbers | AI-CNTRL-A03, EU AI Act Art. 14 | |
| B5 | Action logs capture triggering input, decision step, action taken, and outcome — not output alone | AI-CNTRL-A05 | |
| B6 | Human checkpoint enforced in the execution path for actions above the impact threshold | AI-CNTRL-A03, AI-CNTRL-A08 | |

#### Section C — Full Autonomy Only

| # | Check | Control / Reference | Evidence Seen (Y/N) |
|---|---|---|---|
| C1 | Tool calls validated against policy before execution, not reviewed after the fact | AI-CNTRL-A06 | |
| C2 | Rollback/recovery plan exists for actions already taken if the agent acts wrongly | AI-CNTRL-A10 | |
| C3 | Vendor accountability is contractually explicit — who answers when the agent fails | AI-CNTRL-A11, ISO 42001 A.10 | |
| C4 | Red-team or adversarial testing performed and proportionate to this autonomy level | AI-CNTRL-A06, MITRE ATLAS | |
| C5 | Autonomy multiplier correctly applied and verified by committee, not just self-declared | AI-CNTRL-A09 | |

*Every unchecked box for the required section becomes a finding below.*

---

### Findings

| Ref | Finding | Severity | Owner | Due |
|---|---|---|---|---|
| | | | | |
| | | | | |
| | | | | |

### Decision

☐ **GO** ☐ **CONDITIONAL GO** ☐ **NO-GO — REMEDIATE**

**Conditions and residual risks accepted (if Conditional Go):**

_________________________________________________________________

### Approval

| Role | Name | Signature | Date |
|---|---|---|---|
| Risk Owner | | | |
| Accountable Executive *(Full autonomy only, per Charter §3)* | | | |

**Next scheduled re-review:** _________________ · Completed checklist becomes the Stage 7 evidence artefact per the Agent Lifecycle. No agent proceeds to Stage 8 (Deployment) without this record.

---

### Related Documents

- [Agent Lifecycle](../03-agent-lifecycle/agent-lifecycle.md) — Stage 7 is where this record is produced; Stage 8 cannot start without it
- [Agentic AI Control Library](../05-control-library/agentic-control-library.md) — full definitions for every control ID referenced above
- [Agentic Risk Classification Addendum](../04-risk-framework/agentic-risk-classification-addendum.md) — how the Autonomy Level field is determined
- [Exception Management](../07-ai-assurance/exception-management.md) — the path if a Conditional Go's conditions can't be met on schedule

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
