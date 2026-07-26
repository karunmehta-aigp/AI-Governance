## Third-Party AI Governance

*Governing the vendor models, platforms, and tools an agentic system depends on but the organisation doesn't control.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why This Is Hard, and Why It's Usually Under-Governed

Most agentic capability enters an organisation through a vendor relationship — a foundation model API, an agent-building platform, a low-code automation tool that added agentic features in an update. None of those vendors are procured through the same scrutiny a core system would get, because "add an AI feature to our existing SaaS tool" doesn't trip the same procurement review as "buy a new system." This is the formal counterpart to the Agent Policy's shadow agent discovery: shadow agents are found after the fact; third-party governance is meant to catch the risk before procurement, so there's less to find later.

### Vendor Risk Scoring Template

The assessment questions above are qualitative; this template turns them into a comparable score across vendors, which matters once the organisation has more than one or two AI vendors and needs to prioritise review effort.

| Dimension | Weight | Scoring Guide (1=poor, 5=strong) |
|---|---|---|
| Security (SOC 2 / ISO 27001 status) | High | 5 = current SOC 2 Type II or ISO 27001; 1 = no independent attestation |
| Privacy & data residency | High | 5 = residency confirmed and contractually guaranteed; 1 = undisclosed or non-negotiable |
| Model transparency | Medium | 5 = model card/version disclosed, upgrade notice period contractual; 1 = opaque "latest model" terms |
| Retraining rights | High | 5 = contractually barred from training on our data; 1 = silent or permissive on retraining |
| Subprocessor disclosure | Medium | 5 = full subprocessor list disclosed and updated; 1 = undisclosed |
| Incident response | Medium | 5 = defined SLA and joint incident process; 1 = no committed response process |
| Right to audit | Medium | 5 = contractual audit rights; 1 = no audit provision |
| Kill-switch independence | High | 5 = access revocable independent of vendor uptime; 1 = revocation depends on vendor systems being available |

A vendor scoring below a defined threshold on any High-weight dimension is routed to Legal and the AI Governance Committee for a Direct decision before procurement proceeds — it does not average out against strong scores elsewhere, since a single high-weight failure (e.g., no kill-switch independence) is a standalone risk regardless of how well the vendor scores otherwise.

### Required Vendor Assessment Questions

| Question | Why It Matters |
|---|---|
| Can the vendor retrain or fine-tune on our data? | Determines whether our data becomes part of a model that serves other customers |
| Where is data processed and stored? | Data residency (Data Governance) obligations |
| What logging does the vendor retain, and can we access it? | Action traceability (Agent Policy §4) is incomplete if the vendor's own logs aren't available for incident investigation |
| Does the vendor hold SOC 2 Type II, ISO 27001, or equivalent? | Baseline security assurance in place of a full independent audit |
| Is there a signed Data Processing Agreement (DPA)? | Legal basis for the data relationship |
| Who are the vendor's subprocessors, and are they disclosed? | A vendor's own vendors are part of the organisation's actual exposure, not a separate concern |
| What is the vendor's model deprecation/upgrade notice period? | Feeds Model Governance's upgrade evaluation requirement — a vendor that upgrades with no notice removes the organisation's ability to re-test before a behaviour change ships |
| Can the organisation get a kill switch — i.e., immediately revoke access — independent of the vendor's own systems being available? | If the vendor's outage is the incident, the organisation still needs to be able to contain its own exposure |

### Applied to `ORG-AI-011`

The underlying foundation model, the MCP-compatible tool-calling layer, and the payment system connector are each treated as separate third-party relationships with independently answered versions of the table above — bundling them into a single "the AI vendor" assessment would miss that the payment connector vendor's data handling terms matter as much as the model vendor's.

### Where This Sits in the Lifecycle

This assessment is required evidence at Agent Lifecycle Stage 2 (Business Approval) — before Risk Assessment, not after — because the answers here (especially retraining rights and data residency) directly change the risk score a system receives.

### Related Documents

- [Agentic Risk Classification Addendum](../04-risk-framework/agentic-risk-classification-addendum.md) — how vendor assessment answers feed into a system's risk score

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
