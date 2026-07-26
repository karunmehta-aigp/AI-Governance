## Governance Automation

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

*Which controls can be automated, which genuinely require human judgment, and what breaks if you get that split wrong.*

---

### The Principle Before the Tool List

Automating a control means the control now runs whether or not anyone remembers to check it — which is a real gain for consistency, but only for controls where the *check itself* is mechanical. Automating a control that actually requires judgment doesn't remove the judgment; it just hides that the judgment stopped happening. This document exists to be explicit about which side of that line each control sits on, rather than defaulting to "automate everything we can."

### Mapping Controls to Automation Potential

| Control | Automatable? | Tooling | What Stays Human |
|---|---|---|---|
| Kill switch currency (`AI-CNTRL-A04`) | Yes | ServiceNow or Jira ticket auto-generated at 90-day mark; CI pipeline (GitHub Actions/Azure DevOps) can run the actual revocation test | Deciding whether a failed test warrants suspension vs. an exception |
| Credential scope drift (`AI-CNTRL-A02`) | Yes | Automated diff between IAM policy and Inventory Register, run on a schedule | Approving a legitimate scope change vs. flagging drift |
| Runtime KPI thresholds (KPI Catalog) | Yes | LangSmith/LangFuse or equivalent observability platform feeding alerts into the SIEM | Root-causing *why* a threshold was breached |
| MCP tool registry conformance (`AI-CNTRL-A14`) | Yes | Policy-as-code (Open Policy Agent or platform-native equivalent) enforcing the allow-list at the gateway | Approving a new tool for the allow-list in the first place |
| Prompt drift detection (Prompt Governance) | Yes | Automated diff between deployed and registered prompt version on every deployment | Approving the prompt change that caused a legitimate, intended diff |
| Red team / adversarial testing (Lifecycle Stage 7) | Partial | Promptfoo or equivalent can run a standard adversarial test suite automatically | Designing novel attack scenarios specific to this system's actual action scope — automation only covers known patterns |
| Human oversight posture compliance (`AI-CNTRL-A08`) | No | — | Whether a human genuinely could have intervened is a judgment call about real operational practice, not a config check |
| Exception approval | No | Ticketing (Jira/ServiceNow) can route and track the request | The risk-and-compensating-control judgment itself |
| Incident root cause (Incident Response Playbook, Stage 7) | No | SIEM correlates signals and surfaces candidates | Determining actual causation and accountability |

### Illustrative Toolchain for `ORG-AI-011`

```
GitHub Actions / Azure DevOps  → CI checks: prompt diff, credential scope diff, kill-switch test execution
        ↓
LangSmith / Promptfoo / RAGAS  → automated eval + adversarial test suite, feeding Lifecycle Stage 6 evidence
        ↓
Open Policy Agent (or Azure/Bedrock-native equivalent) → runtime policy enforcement at the MCP gateway
        ↓
SIEM  → correlates runtime alerts, tool-call anomalies, and credential events into a single incident view
        ↓
ServiceNow / Jira  → exception tickets, audit findings, remediation tracking — the human-decision layer
```

### The Honest Limit

Automation reduces the *labor* of evidence collection; it does not reduce the *judgment* required at approval and root-cause stages. A governance programme that automates evidence collection but still routes every decision through the same under-resourced committee (see Operating Model's accountability-concentration note) hasn't actually solved its bottleneck — it's just generated more evidence for the same bottleneck to review.

### Related Documents

- [Agentic AI Control Library](../05-control-library/agentic-control-library.md) — the full control set this document sorts into automatable vs. human-judgment

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
