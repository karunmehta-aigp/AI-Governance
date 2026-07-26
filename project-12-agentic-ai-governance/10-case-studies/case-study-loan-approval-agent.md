## Case Study: `ORG-AI-012` — Loan Pre-Approval Agent (Financial Services)

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why This Case Study Is a Better Test of the Framework Than a Second Copy of `ORG-AI-011`

`ORG-AI-011`'s risk profile is *created* by autonomy — an ordinary internal process becomes governed-as-high-priority because the autonomy multiplier pushes it there. `ORG-AI-012` is the opposite case: credit-worthiness assessment is explicitly named as high-risk under the EU AI Act's Annex III regardless of how much autonomy the system has, and separately triggers rights under GDPR Article 22 and disclosure obligations under the U.S. Equal Credit Opportunity Act (Regulation B) the moment an automated system materially drives a credit decision. This case study exists to show the framework handles a system that's high-risk *by regulatory classification*, not just by behaviour — a genuinely different governance problem, not a re-skin of the first.

### Scenario

The organisation deploys `ORG-AI-012`, a three-agent pipeline supporting (not replacing) the consumer lending team's pre-approval process:

- **Document Intake Agent** — reads submitted income verification, credit bureau pull, and application data
- **Creditworthiness Assessment Agent** — scores the application against lending policy and produces a recommendation with supporting rationale
- **Decision-Support Agent** — drafts the approval, denial, or counter-offer communication, including any legally required adverse action notice

Critically, this system never autonomously issues a final credit decision. It produces a fully-reasoned recommendation; a licensed loan officer makes the actual decision. This is not a design preference — it's a legal requirement this case study treats as non-negotiable.

### How Risk Classification Differs From `ORG-AI-011`

| | `ORG-AI-011` (Expense Reviewer) | `ORG-AI-012` (Loan Pre-Approval) |
|---|---|---|
| Base use-case risk tier | Low | **High — by regulatory classification (EU AI Act Annex III), independent of autonomy** |
| What raises the risk score | The autonomy multiplier | Already high before any multiplier is applied — the multiplier is compounding, not the primary driver |
| Oversight posture required | Determined by autonomy level (Human Oversight Framework mapping) | **Human-in-the-loop is mandatory regardless of autonomy level** — a legal floor, not a governance choice |
| Autonomy level permitted | Up to Conditional, with defined thresholds | **Assistive only** — the system may never autonomously finalise a credit decision |

This distinction matters in practice: teams sometimes assume "we'll just keep autonomy low" is sufficient risk mitigation for any system. `ORG-AI-012` shows a case where that assumption is wrong — even at Assistive autonomy, this system carries obligations (explainability, adverse action notice accuracy, fairness testing) that a Low-tier system like `ORG-AI-011` never triggers at any autonomy level.

### Controls Specific to This System (Beyond the Standard Control Library)

| Requirement | Detail | Regulatory Hook |
|---|---|---|
| Explainability | Every recommendation includes the specific factors driving it, in terms a loan officer (and ultimately a denied applicant) can understand — not just a score | EU AI Act Art. 13 (transparency), GDPR Art. 22 |
| Adverse action notice accuracy | Denial/counter-offer communications drafted by the Decision-Support Agent are checked against the specific reasons regulation requires be disclosed — a generic "did not meet criteria" is not sufficient | ECOA / Regulation B |
| Fairness / disparate impact monitoring | Recommendation outcomes monitored on a recurring basis across protected-class proxies for statistically significant disparity, not just aggregate accuracy | Fair lending laws; extends the KPI Catalog's Quality section with a fairness-specific metric this project's other systems don't need |
| Human-in-the-loop enforcement at the architecture level | The Decision-Support Agent's output cannot reach the applicant without a loan officer's action — enforced as a hard architectural gate, not a process instruction a human could bypass under time pressure | Human Oversight Framework, escalated beyond its standard mapping given the legal floor above |
| Bureau data handling | Credit bureau data carries its own regulatory handling requirements (FCRA in the U.S.) distinct from general PII — governed as its own classification tier within Data Governance, not folded into the standard PII category | FCRA |

### Illustrative Runtime Finding

Six weeks into operation, the fairness monitoring metric flags a statistically significant disparity in recommendation rates correlated with applicant zip code — a common proxy risk in lending models. Because this metric exists as a named, monitored KPI rather than something only discovered in a periodic fair-lending audit, it's caught and routed to the AI Risk Committee within the same monitoring cycle that produces every other runtime finding in this project, rather than requiring a separate specialised fair-lending review process bolted on afterward. The Creditworthiness Assessment Agent's feature weighting is reviewed and adjusted; the correction and its rationale are logged through Framework Change Control, the same as the `ORG-AI-011` incident lesson was.

### What This Case Study Demonstrates

That the framework built for one system generalises to a structurally different one without needing to be rebuilt — the Charter, Lifecycle, Control Library, and Assurance cycle all apply unchanged; what changes is the risk inputs and the specific compliance obligations layered on top. That's the actual test of whether a governance framework is a framework or just documentation for one system that happens to be reused.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
