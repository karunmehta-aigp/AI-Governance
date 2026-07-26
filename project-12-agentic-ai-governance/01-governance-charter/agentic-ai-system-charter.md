## Agentic AI System Charter

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

**Applies to:** All agentic AI systems — defined below — operated by or on behalf of the organisation, including internally built agents, vendor-embedded agents, and low-code/no-code agent workflows.

**Effective:** Fictional illustrative date — Q3 2026
**Review cadence:** Annual, plus on-trigger review following any Severity ≥ Medium incident or any change in the system's autonomy level or action scope

---

### 1. Definitions

**Agentic AI system:** A system in which one or more AI components plan and execute multi-step actions — including calling tools, querying or writing to systems of record, or transacting — with limited or no human review of individual steps, in pursuit of a goal defined at a higher level than the individual action.

This charter distinguishes an agentic system from a standard model deployment by one test: **can the system change the state of another system (a database, a payment rail, an inbox, a ticketing system) without a human approving that specific action first?** If yes, it is in scope of this charter regardless of how it is described internally ("automation," "workflow," "copilot," "bot").

### 2. Scope

This charter governs `ORG-AI-011` (Autonomous Expense & Reimbursement Reviewer) and applies by default to any future agentic system, including agents introduced through:
- New internal development
- Vendor product updates that add agentic capability to an existing, already-approved tool
- Business-team-procured low-code or no-code automation platforms

The third category is explicitly included because it is the organisation's primary blind spot: agentic capability that arrives through a channel that was never treated as an "AI decision" requiring governance intake — the shadow agent problem.

### 3. Governance Structure & Decision Rights

Agentic systems are governed by the existing AI Governance Committee (established in Project 6), with decision rights split three ways rather than treated as a single approval gate. This split is deliberate: a committee that must personally approve every prompt change on every agent will either become a bottleneck the business routes around, or will rubber-stamp without real scrutiny. Neither outcome is governance.

| Decision Rights | Examples | Held By |
|---|---|---|
| **Direct** (committee decides) | Approval of any new agentic system before production; approval of any expansion of an agent's action scope (e.g., raising the autonomous-approval threshold); approval of removing a human checkpoint | AI Governance Committee |
| **Advisory** (committee advises, owner decides) | Choice of underlying model or agent framework within an approved architecture; prompt/instruction changes that do not alter action scope | System owner, with committee consultation |
| **Delegated** (named owner decides within pre-approved bounds) | Day-to-day monitoring threshold tuning within the approved risk band; routine tool/API credential rotation | Named system owner (`ORG-AI-011`: Finance Operations Lead) |

### 4. Mandatory Pre-Deployment Requirements

Before any agentic system reaches production, the system owner must provide to the committee:
1. A completed entry in the Agent Inventory (see Section 5), including the system's autonomy level and full action scope
2. A completed risk classification per the Risk Classification Addendum
3. Evidence of least-privilege credential scoping (see Agent Policy, Section 2)
4. A named human checkpoint for any action above the defined value/impact threshold
5. A rollback and kill-switch procedure, tested prior to go-live

### 5. Agent Inventory (Extension to Project 1's System Inventory)

Agentic systems require inventory fields that standard model entries do not:

| Field | `ORG-AI-011` Entry |
|---|---|
| System ID | ORG-AI-011 |
| System name | Autonomous Expense & Reimbursement Reviewer |
| Agent count / roles | 3: Intake Agent, Policy-Compliance Agent, Disbursement Agent |
| Autonomy level | Conditional autonomy — autonomous action permitted only below a defined claim value threshold; all claims above threshold routed to human reviewer |
| Action scope | Read: expense claim submissions, receipt attachments, expense policy database. Write: claim status, reimbursement instruction to payment system (capped at threshold) |
| Non-human identity / credentials | Dedicated service identity per agent, scoped to named systems only, rotated every 90 days |
| Escalation path | Any claim above threshold, any policy-ambiguous claim, any failed policy-compliance check → routed to Finance Operations Lead |
| Owning function | Finance Operations |
| Governance status | Approved with conditions — see Section 4 |

### 6. Escalation Triggers

Any of the following triggers an out-of-cycle committee review, not just a note in the next quarterly meeting:
- The agent takes an action outside its documented action scope
- The autonomous-approval threshold is breached without human sign-off
- A downstream system (payment rail, HR system, customer record) is modified in a way the agent cannot explain when its action log is queried
- Three or more claims are escalated for the same ambiguous policy interpretation within 30 days (signal that the policy itself, not just the agent, needs review)

### Related Documents

- [Operating Model](../02-operating-model/ai-governance-operating-model.md) — the bodies this Charter assigns decision rights to
- [Agent Lifecycle](../03-agent-lifecycle/agent-lifecycle.md) — where Charter approval gates sit in the deployment sequence

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
