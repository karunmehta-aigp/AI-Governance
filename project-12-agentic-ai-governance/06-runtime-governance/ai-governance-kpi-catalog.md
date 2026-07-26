## AI Governance KPI Catalog

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

*The single canonical source for every metric referenced elsewhere in this project. Runtime Governance, the Control Library, and the Executive Dashboard all pull from this catalog rather than each maintaining their own list — a metric's definition and threshold should have exactly one home.*

---

### Risk

| KPI | Definition | Target |
|---|---|---|
| High-risk AI % | Share of inventoried systems classified High or Critical post-autonomy-multiplier | Tracked, no fixed target — the number itself isn't the goal, coverage is |
| Critical findings (open) | Unresolved findings from red team, audit, or incident review rated Critical | Zero, always |
| Open exceptions | Approved policy exceptions currently active (see Exception Management) | Tracked against expiration dates, not a raw count |

### Operations

| KPI | Definition | Target |
|---|---|---|
| Human override rate | % of agent actions/recommendations a human reverses or intervenes on | Stable or declining; a sustained rise signals miscalibrated autonomy per the Human Oversight Framework, not "the agent is worse" |
| Runtime enforcement failures | Instances where the policy engine should have blocked/escalated an action and didn't | Zero tolerance — any instance is a Critical finding |
| Policy violation rate | Actions taken outside documented action scope | Zero tolerance on Conditional/Full-autonomy systems |

### Quality

| KPI | Definition | Target |
|---|---|---|
| Hallucination / fabrication rate | Agent acting on a fabricated premise (e.g., citing a nonexistent policy clause) | Any instance on a Conditional/Full-autonomy system triggers review |
| Prompt drift | Deployed prompt diverging from the registered version (Prompt Governance) | Zero — this should be structurally impossible, not just monitored |
| Model drift | Behavioural distribution shift from tested baseline (Model Governance) | Reviewed monthly against a defined statistical band |

### Governance

| KPI | Definition | Target |
|---|---|---|
| Audit completion rate | Scheduled audits (Lifecycle Stage 11) completed on time | 100% |
| Review SLA | Time from intake to Governance Committee decision | Tracked; a persistently missed SLA is itself a governance finding — it signals the Committee lacks bandwidth (see Operating Model's accountability-concentration note) |
| Inventory completeness | Agents confirmed against shadow agent discovery scans vs. agents formally inventoried | 100% — any gap is by definition a shadow agent |

### Financial

| KPI | Definition | Target |
|---|---|---|
| Cost per transaction | Average model/tool spend per agent action, tracked against a budget baseline | Within baseline; deviation flags a runaway loop or unplanned model-tier escalation (Runtime Governance) |
| Cost variance by system | Month-over-month change in per-system AI spend | Investigated if it moves outside a defined band, since spend spikes often correlate with scope creep before other metrics catch it |
| Automation ROI | Cost saved (labor-hours or cycle-time) vs. cost incurred (model, tooling, oversight) per governed system | Tracked per system as part of the business case review at Lifecycle Stage 2 |

### Vendor

| KPI | Definition | Target |
|---|---|---|
| Vendor risk score | Weighted score per the Third-Party AI Governance scoring template | No High-weight dimension below threshold |
| Vendor assessment currency | Time since last vendor reassessment | Within the vendor's defined review cadence (Third-Party AI Governance) |
| Subprocessor disclosure completeness | Whether every vendor's subprocessor list is current and disclosed | 100% |
| Upgrade notice compliance | Whether vendor-side model/tool upgrades were received within the contractually agreed notice window | Tracked per vendor; a breach is routed to Legal regardless of whether the upgrade itself caused any issue |

### How the Other Documents Should Reference This Catalog

Rather than each downstream artefact repeating its own metric definitions:
- **Runtime Governance** should monitor the Operations and Quality sections above in real time
- **Executive Dashboard** should visualise a subset of all four sections for leadership
- **Control Library** (`AI-CNTRL-A15` specifically) should cite this catalog as the definition source for "runtime drift," rather than defining it independently

This is a deliberate single-source-of-truth design: when a threshold changes, it changes once, here.

### Related Documents

- [Runtime Governance](./runtime-governance.md) — where the Operations and Quality metrics below are monitored live
- [Agent Governance Dashboard v2](../11-architecture/agent-governance-dashboard-v2.svg) — the executive-facing visualisation of a subset of this catalog

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
