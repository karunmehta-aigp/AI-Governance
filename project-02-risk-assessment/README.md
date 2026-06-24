# Project 2: AI Risk Assessment & Governance Review Pack

> **⚠️ Disclaimer:** This project is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed in this material.

## Scenario

**System Under Review:** AML Transaction Monitoring System (ORG-AI-003)
**Organisation:** The organisation (as established in Project 1)
**Use Case:** Anti-money laundering transaction surveillance and suspicious activity alerting

Project 1's classification exercise placed this system in an unusual position: it was classified as **High Risk on a conservative legal reading**, rather than a clean Annex III match — the organisation's legal counsel had not yet confirmed whether the system's risk-scoring function falls within the creditworthiness/essential-services-access logic of Category 5, or sits outside Annex III entirely. The RMF mapping separately scored its governance maturity at 2.0 (Developing) — better than the portfolio's worst performers, but still short of where a financial-crime system processing every customer's transaction data should sit.

The Head of Financial Crime Compliance has asked the AI Governance Programme Office to produce a formal risk assessment that does two things at once: resolve, as far as governance analysis can, whether the conservative high-risk treatment is the right call to carry forward; and assess the operational risks that exist regardless of how that classification question is ultimately settled by legal counsel. The Board needs both an answer and a decision.

This project is the **second layer** of the portfolio. It takes a borderline, judgement-call system from Project 1 — not the obvious headline case, but the harder one — and shows what governance analysis looks like when the legal classification itself is still unsettled, not just the system's compliance posture.

## What This Project Demonstrates

- Ability to conduct a structured risk assessment **under classification uncertainty** — producing a defensible governance position without waiting for a legal opinion that may take months to arrive.
- Understanding of the **harm profile specific to financial crime surveillance systems**: customer risk-profiling effects, vendor model opacity, alert fatigue and analyst override patterns, and the tension between detection sensitivity and false-positive burden on legitimate customers.
- Capacity to distinguish **a system's classification risk from its operational risk** — and to show, concretely, why an organisation cannot use "we're not sure if this is technically high-risk" as a reason to delay fixing gaps that would need fixing under almost any plausible classification outcome.
- Ability to communicate a **conditional governance position** to a Board: what we are confident about, what remains genuinely open, and what action is warranted regardless of how the open question resolves.
- Working knowledge of the **NIST AI RMF Map and Measure functions**, applied to a system already scored at 2.0 maturity in Project 1 — demonstrating that even "Developing" maturity can mask specific, serious unaddressed risks once a formal risk register is applied.

## Artefacts

| File | Description |
|---|---|
| `risk-assessment.md` | Structured risk register for the AML Transaction Monitoring System, addressing both classification uncertainty and operational risk |
| `governance-review-memo.md` | Executive memo to the CEO and Board, recommending a governance position and a path to resolving the outstanding classification question |

## How the Artefacts Connect

The risk assessment does something the Project 1 classification document could not: it works *forward* from uncertainty rather than waiting for it to be resolved. It separates risks that depend on the final classification outcome from risks that exist under any outcome, and scores each on the same likelihood/impact methodology used throughout this portfolio, so the analysis remains comparable across projects even though the legal question underneath it is different in kind from anything Project 1 had to resolve.

The governance review memo then converts that structured uncertainty into something a Board can actually act on. Boards are not well served by "we don't know yet, come back later" — the memo's job is to say, in effect, "here is what we are confident requires action now, here is the specific open question, here is who is resolving it and by when, and here is the decision we need from you in the meantime." This is the part of governance work that a risk register alone cannot do: converting analytical honesty about uncertainty into an operational decision with an owner and a date.

## Key Decisions & Rationale

**Why assess a system whose classification isn't even settled, instead of waiting for legal counsel?** Because in practice, governance work rarely gets the luxury of a clean starting point. Waiting for a definitive legal opinion before doing any risk analysis would leave the system's genuine operational gaps — vendor opacity, alert review capacity, model retraining transparency — unexamined for months. The assessment is structured so that its core findings hold regardless of which way the classification question resolves, which is itself a governance skill: knowing which parts of an analysis are contingent on an open question and which parts are not.

**Why does this risk register treat "alert fatigue" as a genuine AI governance risk, not just an operational efficiency problem?** Because in a financial-crime monitoring context, an under-resourced or overwhelmed human review function is functionally equivalent to having no human oversight at all — the Article 14 requirement for meaningful human oversight is not satisfied by a human nominally sitting in the loop if that human is rubber-stamping hundreds of alerts a day without genuine capacity to review them. This is a distinct failure mode from the CV screening system's problem in Project 1 (no human checkpoint existed at all) — here a checkpoint exists on paper, but its real-world effectiveness is the open question, which is a more subtle and arguably more common governance failure in mature organisations.

**Why does the memo recommend resolving the classification question on a fixed timeline rather than leaving it open indefinitely?** An unresolved classification is itself a governance risk, separate from the operational risks of the system. A Board cannot indefinitely operate a system on a "we'll treat it as high-risk just in case" basis without ever actually confirming the position — that approach works as a short-term conservative holding pattern, but it offloads a legal judgement onto an operational team indefinitely, which is not sustainable governance. Putting a date on the legal opinion converts a permanent ambiguity into a temporary, managed one.

## Frameworks Applied

- **NIST AI RMF** — Map (risk identification and contextualisation) and Measure (rigorous, structured risk analysis) functions, extending the Govern-level maturity score of 2.0 already established for this system in Project 1
- **EU AI Act** — Article 6 (classification methodology and the proportionality principle underlying a conservative classification approach), Article 9 (risk management system), Article 14 (human oversight, including the question of whether oversight is meaningful in practice, not just present on paper), Article 28 (deployer obligations regarding vendor-supplied systems)
- **ISO 31000** — risk assessment structure and the explicit treatment of uncertainty as a risk factor in its own right, not merely a gap in the analysis

---

*Karun · AIGP (AI Governance Professional)*
