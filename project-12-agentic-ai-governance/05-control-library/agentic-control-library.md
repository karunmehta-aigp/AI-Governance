## Agentic AI Control Library

*Extends Project 10's controls library with a dedicated set for agentic systems, numbered for evidence tracking.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Control Categories

Matching the category scheme used across this project's diagrams: AI Governance & Oversight, Data Governance, Model Governance, Agent Governance, Prompt Governance, Tool & MCP Governance, Runtime Governance, Security & Privacy, Monitoring & Observability, Audit & Evidence.

### Control Register

| Control ID | Category | Description | Owner | Frequency | Evidence | Risk Addressed | Automatable |
|---|---|---|---|---|---|---|---|
| AI-CNTRL-A01 | Security & Privacy | Every agent has a unique, scoped non-human identity; no shared credentials across agents | Engineering | Continuous, reviewed quarterly | Identity/access log export | Excessive agency, lateral compromise | Yes |
| AI-CNTRL-A02 | Security & Privacy | Credential scope matches documented action scope in Inventory Register; any mismatch is a finding | AI Governance Committee | Quarterly | Inventory Register vs. IAM policy diff | Privilege creep | Yes |
| AI-CNTRL-A03 | Agent Governance | Human checkpoint exists and is enforced in the execution path for any action above the value/impact threshold | System owner | Pre-deployment + annual | Architecture review record | Unreviewed high-impact action | Partial |
| AI-CNTRL-A04 | Agent Governance | Kill switch tested within the last 90 days for every Active-status agent | System owner | Quarterly | Kill Switch Tested field, Inventory Register | Inability to contain a runaway agent | Yes |
| AI-CNTRL-A05 | Audit & Evidence | Action logs capture triggering input, decision/plan step, action taken, and outcome — not output alone | Engineering | Continuous | Log schema validation | Unauditable agent behaviour | Yes |
| AI-CNTRL-A06 | Runtime Governance | Policy enforcement point sits in the execution path (gateway/policy engine), not solely in the system prompt | Engineering + AI Governance Committee | Pre-deployment + on architecture change | Architecture diagram + enforcement point test | Prompt injection bypassing intended constraints | Partial |
| AI-CNTRL-A07 | AI Governance & Oversight | Recurring shadow agent discovery scan across vendor tools, low-code platforms, and dev environments | Security function | Quarterly | Discovery scan report | Ungoverned agentic capability | Yes |
| AI-CNTRL-A08 | Agent Governance | Oversight posture (in-loop / on-loop / over-loop) matches the required mapping for the system's autonomy level | AI Governance Committee | Annual audit | Human Oversight Framework compliance check | Oversight-autonomy mismatch | No |
| AI-CNTRL-A09 | AI Governance & Oversight | Autonomy multiplier applied to base risk score before final risk tier is assigned | System owner, verified by committee | Pre-deployment + on scope change | Risk register entry | Under-classification of low-visibility, high-autonomy systems | Partial |
| AI-CNTRL-A10 | Audit & Evidence | Incident containment procedure for agentic systems includes credential revocation, not only interface disablement | Security function | Tested annually via tabletop exercise | Incident response test record | Agent continuing to act via scheduled/event-triggered execution post-"disable" | No |
| AI-CNTRL-A11 | Model Governance | Third-party model/vendor approval completed before Lifecycle Stage 2 sign-off | Legal + Privacy | Pre-deployment + on vendor terms change | Third-Party AI Governance assessment | Uncontrolled data/retraining exposure via vendor | No |
| AI-CNTRL-A12 | Prompt Governance | Prompt changes go through version control, testing, and approval before production | Engineering + AI Governance Committee | Continuous, reviewed at each change | Prompt Governance registry diff | Unreviewed behavioural change via prompt edit | Yes |
| AI-CNTRL-A13 | Data Governance | No persistent agent memory without classification-at-write and a tested deletion path | AI Governance Committee | Pre-approval for any persistent memory feature | Memory Governance sign-off | Unerasable PII, memory poisoning | No |
| AI-CNTRL-A14 | Tool & MCP Governance | MCP servers and tools are explicitly allow-listed; no default-allow | Security function | Continuous, reviewed quarterly | MCP Governance tool registry | Malicious or unapproved tool/server access | Yes |
| AI-CNTRL-A15 | Monitoring & Observability | Runtime drift (prompt, behavioural, cost) monitored against a defined baseline with alerting | Engineering | Continuous | Runtime Governance dashboard export | Undetected degradation or scope creep in production | Yes |
| AI-CNTRL-A16 | Model Governance | Vendor-supplied model version is pinned in production; upgrades treated as a material change requiring re-test | Engineering | On every vendor upgrade notice | Model Governance version record | Silent behavioural change via unreviewed model upgrade | Partial |

### Runtime KPIs Monitored Against This Library

These are the metrics the Executive Dashboard (below) surfaces, each tied back to a control above:

| KPI | Tied to Control | Escalation Trigger |
|---|---|---|
| Policy violation rate | AI-CNTRL-A06 | Any violation on a Conditional/Full autonomy system |
| Human override rate | AI-CNTRL-A03, A08 | Sustained rate above baseline signals miscalibrated autonomy, not just noise |
| Kill switch test currency | AI-CNTRL-A04 | Any agent >90 days untested |
| Shadow agents found per scan | AI-CNTRL-A07 | Any finding — target is zero, not a "low" number |
| Credential scope drift | AI-CNTRL-A02 | Any mismatch flagged same-cycle |

### Related Documents

- [Exception Management](../07-ai-assurance/exception-management.md) — the sanctioned path when a control can't be met as written
- [Governance Automation](../12-implementation-guide/governance-automation.md) — which of these controls can run automatically vs. require human judgment
- [Agentic Compliance Crosswalk](./agentic-compliance-crosswalk.md) — how each control maps to NIST/EU AI Act/ISO/OWASP/MITRE ATLAS

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
