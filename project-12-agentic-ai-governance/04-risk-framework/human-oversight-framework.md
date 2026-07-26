## Human Oversight Framework

*Deepens Agent Policy Section 3 into a standalone, gradated framework.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why "Human in the Loop" Is Not One Thing

"Human oversight" is often written into policy as a single checkbox — present or not present. That's too coarse for agentic systems, where the *position* of the human relative to the action matters as much as their presence. This framework defines three distinct oversight postures and requires every agentic system to state, explicitly, which one it operates under — and requires that posture to match the system's autonomy level from the Risk Classification Addendum, not just its business owner's preference.

### The Three Postures

**Human-in-the-loop.** The agent proposes or drafts; a human approves each individual action before it takes effect. This is the required posture for any action above the Charter's defined value/impact threshold, and for any Full-autonomy-tier system by default until proven otherwise. Slowest, but the only posture appropriate when a single wrong action is high-consequence and hard to reverse.

**Human-on-the-loop.** The agent acts autonomously within pre-approved bounds; a human monitors in near-real-time and can intervene, but does not approve each action individually. This is the posture `ORG-AI-011`'s Disbursement Agent operates under below its claim-value threshold: it acts, but the Finance Operations Lead has live visibility and can suspend it at any point. Appropriate for Conditional-autonomy systems where individual actions are low-consequence but cumulative drift needs a watching eye.

**Human-over-the-loop.** The agent acts autonomously with no real-time human monitoring; oversight is exercised through periodic audit, monitoring dashboards, and after-the-fact review of logs. This is the weakest posture and is only appropriate for Assistive or Supervised-autonomy systems with no write access to consequential systems. It is explicitly **not** an approved posture for any system with Conditional or Full autonomy under this framework — a system with the ability to independently take consequential action cannot be governed purely retrospectively.

### Required Mapping

| Autonomy Level (Risk Addendum) | Minimum Required Oversight Posture |
|---|---|
| Assistive | Human-over-the-loop acceptable |
| Supervised | Human-on-the-loop minimum |
| Conditional autonomy | Human-on-the-loop minimum, human-in-the-loop above value threshold |
| Full autonomy | Human-in-the-loop required — Full autonomy with only on-loop or over-loop oversight is non-compliant under this framework regardless of business justification |

### Why This Belongs in Governance, Not Just Engineering

A system architected as "human-on-the-loop" can quietly become "human-over-the-loop" in practice if the monitoring dashboard is not actually watched — the architecture diagram says one posture, the operational reality says another. This framework's audit requirement (Agent Lifecycle Stage 11) explicitly tests for that gap: not "does a monitoring dashboard exist," but "is there evidence a human looked at it and could have intervened."

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
