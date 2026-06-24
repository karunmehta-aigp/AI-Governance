# Project 2: AI Risk Assessment & Governance Review Pack

> **⚠️ Disclaimer:** This project is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed in this material.

## Scenario

**System Under Review:** CV Screening & Ranking System (ORG-AI-002)
**Organisation:** The organisation (as established in Project 1)
**Use Case:** AI-assisted recruitment — CV screening and candidate shortlisting

Following the classification exercise in Project 1, the CV Screening & Ranking System was identified as a high-risk system under Annex III Category 4(a) of the EU AI Act, currently operating in production without a conformity assessment, without a bias audit, and without a mandatory human review step before candidate rejections are communicated.

The Head of Human Resources has requested a formal governance review before a Board-level decision on the system's future. The review covers:

- A structured risk assessment identifying harms, likelihood, and impact
- Proposed mitigation measures and a resulting residual risk position
- A governance review memo addressed to the Chief Executive Officer and the Board Risk & Audit Committee

This project is the **second layer** of the portfolio. It takes the single highest-priority finding from Project 1's inventory and classification work — a high-risk system with critical compliance gaps — and subjects it to the depth of analysis that classification alone cannot provide: what could actually go wrong, how severe is it, what controls reduce it, and what decision does the organisation now need to make.

## What This Project Demonstrates

- Ability to move from classification to structured, quantified risk analysis rather than stopping at "this system is high-risk."
- Understanding of **AI-specific harms** — not just data protection risk, but bias and proxy discrimination, lack of explainability, loss of meaningful human oversight, vendor opacity, and scope creep.
- Capacity to define what **meaningful human oversight** looks like in practice, as a staged operating model rather than a single control statement — distinguishing a system that informs a decision from one that effectively makes it.
- Ability to **communicate governance analysis to senior non-technical audiences**: translating a risk register into a Board decision request with a clear recommendation, not a wall of technical findings.
- Working knowledge of the **NIST AI RMF Map and Measure functions** applied to a live, real-world use case — Map being the identification and contextualisation of risk, Measure being its rigorous quantification.
- The judgement to separate **inherent risk from residual risk**, and to be explicit about which risks controls reduce versus which risks controls cannot fully eliminate (e.g., a pending bias audit caps how far residual risk can responsibly be rated, regardless of how many procedural controls are layered on).

## Artefacts

| File | Description |
|---|---|
| `risk-assessment.md` | Full structured risk register with a likelihood/impact matrix, six identified risks, proposed controls, and residual risk position |
| `governance-review-memo.md` | Executive memo to the CEO and Board recommending a governance decision, with a defined remediation timeline |

## How the Artefacts Connect

The risk assessment is the analytical foundation. It identifies risks specific to this system, assesses each on a consistent likelihood × impact scale, applies proposed mitigation controls, and arrives at a residual risk position for every risk individually and for the system as a whole. This is technical-governance work — it is meant to be defensible to an auditor or regulator, not just persuasive to an executive.

The governance review memo translates that analysis into the format executives actually need: a short purpose statement, an executive summary that leads with the conclusion, findings written in plain business language, a defined recommendation between two clearly bounded options, and an explicit decision request with an escalation path if the conditions of approval are not met.

Together they reflect how governance actually functions in practice — rigorous analysis feeding a clear, time-bound decision, rather than analysis being used as a substitute for making one. A risk assessment that never produces a decision is just documentation; a memo without the underlying assessment is just an opinion.

## Key Decisions & Rationale

**Why does RISK-003 (absence of human oversight) score Critical while RISK-001 (bias) scores High, even though bias is arguably the more emotionally salient harm?** The risk scoring is intentionally mechanical: likelihood × impact, not "which risk sounds worse." The absence of a human oversight gate is happening *right now*, with certainty (Likelihood 5), and it is what converts every other risk in the register from theoretical to operative — without it, biased or unexplainable outputs translate directly into real rejection decisions with no checkpoint. Bias is serious, but its likelihood is assessed at 4, not 5, because no audit has yet confirmed the model is actually exhibiting biased behaviour, only that the risk is unaddressed. This distinction — between a control gap that is certain and a harm that is probable but unconfirmed — is the kind of nuance a defensible risk register has to preserve rather than flatten.

**Why does the recommended decision (Option A: continue with enhanced oversight) not simply pick the lowest-risk option (suspension)?** Because governance is not the discipline of eliminating all risk — it is the discipline of managing risk to an acceptable level proportionate to the harm and the cost of control. Suspension would eliminate the immediate exposure but at a real operational cost, and the highest-severity risk (absence of oversight) is fully addressable by an operational fix that can be implemented in days, not months. A defensible governance memo has to make and justify that trade-off explicitly, not default to the most conservative-sounding option as a way of avoiding the judgement call.

**Why is the residual risk position capped at Medium rather than Low, even after every proposed control is applied?** Because two of the controls (the bias audit, and human oversight as a risk-reducing rather than risk-eliminating measure) cannot honestly be scored as fully closing the risk until they are actually completed and their results are known. Rating a pending audit's outcome as "Low residual risk" in advance of the audit would be governance theatre — the rating has to reflect genuine uncertainty, not optimism about what the audit will probably show.

## Frameworks Applied

- **NIST AI RMF** — Map (risk identification and contextualisation) and Measure (rigorous, structured risk analysis) functions, building directly on the Govern-level gaps already identified in Project 1's RMF mapping for this system
- **EU AI Act** — Article 9 (risk management system), Article 10 (data governance), Article 13 (transparency and the right to meaningful explanation of automated decisions), Article 14 (human oversight), Article 28 (deployer obligations)
- **ISO 31000** — risk assessment structure, terminology, and the inherent-risk-to-residual-risk-via-controls model used throughout the risk register

---

*Author: Anju Karun · AIGP (AI Governance Professional)*
