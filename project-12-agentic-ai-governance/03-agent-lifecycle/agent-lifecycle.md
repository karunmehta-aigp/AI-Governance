## Agentic AI Lifecycle

*The gates an agent passes through from idea to retirement — and what evidence each gate produces.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why Document the Lifecycle Separately From the Charter

The Charter tells you *who decides*. This document tells you *what has to be true before that decision can even be requested* — the sequence, and the artefact each stage must produce before the next stage can start. A lifecycle without required evidence at each gate is just a flowchart; the evidence is what makes it auditable.

### The Lifecycle

| Stage | Gate Question | Evidence Produced | Owner |
|---|---|---|---|
| 1. Idea | Is there a named business owner and a defined problem? | One-page intake form | Business sponsor |
| 2. Business Approval | Does the business case justify the governance overhead of an agentic (vs. assistive) system? | Signed intake form | Business unit lead |
| 3. Risk Assessment | What is the autonomy-adjusted risk score? (Risk Classification Addendum) | Completed risk register entry | System owner + AI Governance Committee |
| 4. Architecture Review | Is credential scoping least-privilege per agent? Is there a policy-enforcement point in the execution path, not just in the prompt? | Architecture review sign-off | Engineering + AI Governance Committee |
| 5. Security Review | Has the design been checked against the OWASP multi-agent threat taxonomy (memory poisoning, tool misuse, inter-agent manipulation, privilege escalation)? | Security review report | Security function |
| 6. Prompt Testing (incl. Red Team) | Does the agent behave within its documented action scope under adversarial and edge-case input? Can it be induced to act outside scope, exfiltrate data, or escalate privilege across agents? | Test report with pass/fail against defined scope, plus red team findings and remediation status | Engineering + Security function |
| 7. Human Approval | Direct-decision sign-off per the Charter | Committee approval record | AI Governance Committee |
| 8. Deployment | Inventory entry created, kill switch tested pre-launch | Agent Inventory Register entry | System owner |
| 9. Post-Production Validation | Does the agent's real production behaviour, over an initial defined window, match what pre-deployment testing predicted? A pre-deployment test suite is necessarily a sample of possible inputs — this stage checks that live traffic hasn't surfaced a gap the sample missed | Post-implementation review report | System owner + Engineering |
| 10. Runtime Monitoring | Are the runtime KPIs (see Runtime Governance, Control Library) within threshold on an ongoing basis? | Monitoring dashboard, continuous | System owner |
| 11. Periodic Audit | Annual, or on-trigger per Charter Section 6 escalation criteria | Audit report | Internal audit / AI Governance Committee |
| 12. Retirement | Credentials revoked, inventory status updated, logs retained per records schedule | Retirement record | System owner |

### Why Post-Production Validation Is Its Own Gate, Not Folded Into Monitoring

Runtime Monitoring (Stage 11) is ongoing and threshold-based — it tells you when something crosses a line. Post-Production Validation (Stage 10) is a single, bounded, deliberate review shortly after go-live, asking a different question: not "did anything breach a threshold" but "did the system's actual behaviour match what we predicted it would do." Most enterprises run this as a formal post-implementation review; folding it into ongoing monitoring loses the deliberate compare-to-prediction exercise, which is often where an unanticipated pattern is caught before it's had time to become a monitored, thresholded metric at all.

### The Gate That's Usually Missing

Most governance lifecycles treat "Deployment" as the last governed stage and "Monitoring" as operations' problem, not governance's. That split is exactly how shadow agents and drift-related incidents happen — the agent that was compliant at Stage 8 is not guaranteed to still be compliant at month six, because prompts get tuned, tools get added, and thresholds get adjusted by engineers who reasonably don't think of a config change as a governance event. This lifecycle treats Stage 9 as a governed stage with the same evidentiary weight as Stage 7, not an afterthought.

### Related Documents

- [Agentic Risk Classification Addendum](../04-risk-framework/agentic-risk-classification-addendum.md) — Stage 3's risk assessment methodology
- [Agentic AI Control Library](../05-control-library/agentic-control-library.md) — the controls verified at Stages 4-7 and 11

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
