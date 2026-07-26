## Prompt Governance

*The system prompt and instructions are a governed artefact, not an engineering implementation detail.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why a Prompt Change Is a Governance Event

A system prompt encodes the boundaries an agent is instructed to operate within — which policy it applies, what it's told never to do, how it's told to handle ambiguity. Changing it can change agent behaviour as materially as changing the underlying model, but because it's usually a text edit rather than a code deployment, it's the control most likely to bypass a change-management process entirely. This document exists to close that gap.

### Requirements

| Requirement | Detail |
|---|---|
| Prompt registry | Every production system prompt is version-controlled in a single registry, not scattered across code repositories or, worse, edited directly in a vendor console |
| Ownership | Each prompt has a named owner accountable for its content and its change history |
| Approval | Any change to a production prompt for a Conditional/Full-autonomy agent goes through the Charter's Advisory decision-rights process at minimum; a change that alters action scope is a Direct decision |
| Version history | Full diff history retained — "what did the agent's instructions say on the date of an incident" must be answerable |
| Testing before promotion | Prompt changes are tested against the same behavioural test suite used at Agent Lifecycle Stage 6 before reaching production, not tested informally and shipped |
| Rollback | A tested path to revert to the prior approved prompt version |
| Drift detection | Runtime Governance's prompt-drift monitoring exists specifically to catch a deployed prompt diverging from the registered version — whether through an unreviewed hotfix or a configuration error |
| Risk classification | Prompts are reviewed for injection resistance — how clearly they distinguish trusted instructions from untrusted input (e.g., the content of an expense claim itself, which a claimant could attempt to manipulate) |

### `ORG-AI-011` Illustration

The Policy-Compliance Agent's prompt explicitly separates "expense policy rules" (trusted, from the internal policy database) from "claim content" (untrusted, submitted by the claimant) — a claimant cannot embed an instruction inside a claim description that the agent would treat as a policy update. This separation is exactly what prompt-injection-resistance testing at Lifecycle Stage 6 verifies, and what this governance layer requires to be re-verified on every prompt change.

### Connection to Other Artefacts

Tied to `AI-CNTRL-A06` (runtime enforcement, not prompt-only) and to Runtime Governance's drift monitoring. Prompt Governance is the change-management discipline; Runtime Governance is the detection mechanism that catches a failure of that discipline.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
