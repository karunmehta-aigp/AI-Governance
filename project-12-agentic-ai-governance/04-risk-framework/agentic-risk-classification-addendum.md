## Agentic Risk Classification Addendum

*Extends Project 9's risk methodology and risk register to agentic AI systems.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer. Regulatory positions described below reflect the public state of an active, unresolved policy debate as of mid-2026 and may change.

---

### 1. Risk Tier Definitions

This project uses a five-tier risk scale, consistent across the Charter, Control Library, and every risk-scoring template in this project:

| Tier | Definition |
|---|---|
| **Critical** | Unacceptable risk as currently designed — requires redesign before any approval is possible, not just additional controls |
| **High** | High risk; strict controls and Direct-decision committee approval required |
| **Moderate** | Manageable risk with defined controls in place; typically an Advisory decision |
| **Low** | Low risk; standard controls apply, no special committee review required |
| **Minimal** | Negligible risk |

`ORG-AI-011`'s base use-case domain (internal financial operations, no customer-facing decision) scores Low under this scale before any autonomy adjustment.

### 2. The Open Question This Addendum Engages

As of mid-2026, none of the EU AI Act, NIST AI RMF, or ISO/IEC 42001 were drafted with autonomous, multi-step, tool-using agents as the primary subject. The EU AI Act's risk tiers classify by *use case domain* (credit, employment, biometric ID, and so on) — a classification logic built around a model producing a single output for a defined purpose, not around a system's degree of autonomy. This creates a live gap: two systems performing the same underlying function — say, expense claim review — could be classified identically under the Act's use-case logic whether one requires human sign-off on every action and the other executes autonomously end-to-end.

Governance bodies and vendors are actively debating how to close that gap. One proposal now circulating in industry discussion argues that agentic AI should be classified **high-risk by default**, regardless of use-case domain, purely on the basis of autonomous action-taking capability — on the reasoning that the ability to independently execute consequential actions is itself the risk factor, separate from and additive to whatever domain the agent operates in.

This addendum does not resolve that debate — no organisation's internal policy can, since it's a matter for regulators and standard-setters. What it does is show how a governance programme should position itself while the debate is open: adopt the stricter posture operationally now, so that whichever way the debate resolves, the organisation is already compliant rather than retrofitting under enforcement pressure.

### 3. Extended Risk Scoring Methodology

Project 9's risk register scores systems on likelihood × impact within a use-case domain. This addendum adds a second, independent axis specific to agentic systems: **autonomy multiplier.**

| Autonomy Level | Description | Multiplier Applied to Base Risk Score |
|---|---|---|
| Assistive | Agent drafts or recommends; human takes every action | 1.0x (no change) |
| Supervised | Agent acts, but every action is reviewed before taking effect | 1.0x (no change) |
| Conditional autonomy | Agent acts without review below a defined threshold, escalates above it | 1.5x |
| Full autonomy | Agent acts without a defined human checkpoint in the standard path | 2.0x, and requires committee Direct-decision approval regardless of underlying use-case risk tier |

`ORG-AI-011` operates at Conditional autonomy. Under Project 9's base methodology alone, its use-case domain (internal financial operations, no customer-facing decision) would likely score as Low or Minimal risk. Applying the 1.5x autonomy multiplier from this addendum raises it to the review threshold that triggers full Charter Section 4 pre-deployment requirements — which is the intended effect: **autonomy should be able to raise a system's governance obligations even when its use-case domain alone would not.**

### 4. Why This Matters Beyond Compliance Theatre

A governance programme that only classifies by use-case domain will systematically under-govern low-visibility, high-autonomy internal systems like `ORG-AI-011` — exactly the shadow-agent pattern described in the Agent Policy — because "internal expense processing" does not sound high-risk in the way "credit decisioning" does. The autonomy multiplier exists specifically to catch that blind spot before an incident does.

### 5. Position for Regulatory Change

Should the high-risk-by-default proposal (or an equivalent regulatory clarification) be formally adopted, this addendum's Conditional/Full autonomy tiers are designed to map directly onto a formal high-risk classification requiring conformity documentation, without requiring the organisation to rebuild its risk methodology under deadline pressure. That mapping is the operational value of adopting the stricter posture now.

### Related Documents

- [Agent Lifecycle](../03-agent-lifecycle/agent-lifecycle.md) — where risk classification sits in the deployment sequence (Stage 3)
- [Third-Party AI Governance](../06-runtime-governance/third-party-ai-governance.md) — vendor terms (retraining rights, residency) that feed into this classification
- [Agentic AI Control Library](../05-control-library/agentic-control-library.md) — control A09 enforces the autonomy multiplier defined here

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
