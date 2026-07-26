## Agent Policy

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

**Purpose:** Where the Agentic AI System Charter defines *who decides what*, this policy defines *what every agentic system must actually do* — the operating requirements that make the charter enforceable rather than aspirational.

---

### 1. Core Principle: Govern at Runtime, Not Only at Review

Traditional AI governance largely operates at review time — a model is assessed before deployment, then periodically thereafter. That is necessary but insufficient for agentic systems, because an agent's risk is not fixed at deployment; it is expressed action-by-action, in production, often faster than a human review cycle can catch. This policy therefore requires controls that operate at the moment of action, not only at the moment of approval.

### 2. Identity & Least-Privilege Scoping

Every agent is a non-human identity and must be governed with the same discipline applied to a privileged human user account, with additional controls appropriate to its lack of judgment:

- Each agent (not each agentic *system* — each individual agent within a multi-agent pipeline) is issued its own credentials, scoped to only the systems, tables, and API endpoints its function requires. The Intake Agent in `ORG-AI-011` can read the claims queue; it cannot write to the payment system. Only the Disbursement Agent can.
- No agent is issued standing credentials broader than its documented action scope in the Agent Inventory. Scope expansion requires a Direct decision under the Charter, not a configuration change made unilaterally by engineering.
- Credentials are rotated on a fixed schedule and immediately on any personnel change affecting the system owner.

### 3. Human Checkpoints

- Every agentic system must have at least one human checkpoint positioned before any action with financial, legal, employment, or safety impact above a defined threshold.
- The checkpoint must be a genuine decision point, not a notification. A human being cc'd on an email after the action has already executed is not a checkpoint.
- Checkpoint thresholds are set by the system owner, approved by the committee under the charter's Direct decision rights, and reviewed at least annually or after any escalation event.

### 4. Action Traceability

- Every action an agent takes — every tool call, every read, every write — is logged with: the agent identity, the triggering input, the reasoning or plan step that led to the action (where the underlying architecture exposes this), the action itself, and the outcome.
- Logs must be sufficient to answer, after the fact, "why did the agent do this" — not merely "what did the agent do." An audit trail that shows only the final output, without the intermediate steps, does not meet this bar for any system above minimal risk.
- Logs are retained per the organisation's existing records retention schedule and are the primary evidence source for both internal audit and any regulatory incident reporting obligation under Project 4's incident response process.

### 5. Guardrails and Policy Enforcement

- Agentic systems are governed by policy enforced in the execution path (a policy engine, gateway, or equivalent control sitting between the agent and the systems it acts on) rather than by instructions embedded only in a prompt. A prompt is guidance the model may deprioritise under adversarial input or drift; a runtime control is not.
- Guardrails are tested against the OWASP multi-agent threat taxonomy at minimum (memory poisoning, tool misuse, inter-agent communication manipulation, privilege escalation across agents) as part of pre-deployment review and after any material change to the agent architecture.

### 6. Shadow Agent Discovery

- The organisation runs a recurring discovery process — not an assumption of absence — to identify agentic capability operating outside this policy: vendor products that added agentic features via update, business-team-procured automation tools, and development-environment agents that have gained access to production data.
- Any agent discovered outside formal governance is treated as an open finding, routed through the same intake process required for new development, and is not permitted to continue autonomous action until it meets Sections 2–4 of this policy.

### 7. Incident Handling

Agentic-system incidents follow Project 4's incident response process, with one addition specific to agents: containment for an agentic system means revoking or suspending the agent's credentials (a kill switch), not merely disabling a user-facing interface, since the agent may continue to act through scheduled or event-triggered execution independent of any interface.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
