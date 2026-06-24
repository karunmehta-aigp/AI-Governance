# Project 5: High-Risk AI Documentation & Conformity Pack

> **⚠️ Disclaimer:** This project is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed in this material.

## Scenario

**System Under Documentation:** Voice Biometric Authentication System (ORG-AI-004)
**Organisation:** The organisation (as established in Project 1)
**Use Case:** Biometric identity verification for customer authentication

Project 1 classified this system as High Risk under EU AI Act Annex III Category 1 (biometric identification and verification), and flagged a critical documentation gap: no biometric-specific Data Protection Impact Assessment, no fallback-path fairness audit, and no formal review of the enrolment consent flow since the system's 2023 launch. Project 1's NIST RMF mapping scored the system at 1.0 maturity — Initial — across every function, the lowest score of any system in the inventory tied with the CV Screening & Ranking System.

Of the four high-risk systems in the organisation's inventory, this is the one that has now reached the point where the gap can no longer be managed informally. The Chief Risk Officer has instructed the AI Governance Programme Office to produce the **actual conformity documentation pack** this system would need in order to be lawfully placed on the market and kept in continued operation as a high-risk AI system — not another assessment of how non-compliant it currently is, but the constructive work of building the documentation that closes that gap.

This project is the **final layer** of the portfolio, and a deliberate change in register from Projects 1 through 4. Those projects diagnosed problems — classification gaps, risk exposure, absent governance structure, and a live incident. This project is what a properly functioning governance programme actually *produces* once it is working: the paper trail of conformity that a high-risk AI system is legally required to have, built to the standard a notified body, a market surveillance authority, or an internal audit function would expect to see.

## What This Project Demonstrates

- Ability to produce **EU AI Act Annex IV–aligned technical documentation** for a real (if fictional) high-risk system — not a generic template, but documentation that reflects this specific system's actual architecture, data flows, and known limitations, including its unresolved gaps.
- Understanding of the **conformity assessment process** itself: what a provider or deployer must actually demonstrate, the distinction between self-assessment and third-party (notified body) assessment, and what a declaration of conformity commits an organisation to once it is signed.
- Capacity to write a **human oversight procedure that is operationally specific** rather than aspirational — naming exact override criteria, exact escalation paths, and the exact information a reviewer needs in front of them to exercise oversight that is meaningful rather than nominal, building directly on the "oversight capacity erosion" concept introduced in Project 2.
- Knowledge of the **post-market monitoring obligations** that continue after a conformity declaration is signed — a conformity pack is not a one-time certificate; it is the start of an ongoing documentation and monitoring obligation that persists for the system's entire operational life.
- The judgement to **document a system honestly, including its limitations**, rather than producing documentation that overstates the system's maturity to manufacture an appearance of conformity — a technical documentation pack that omits a known weakness is not a lesser version of conformity, it is a false one, and arguably worse than no documentation at all because it actively misleads anyone who relies on it.

## Artefacts

| File | Description |
|---|---|
| `technical-documentation.md` | Annex IV–aligned technical documentation: system description, design specifications, data and training information, performance metrics, and known limitations |
| `conformity-assessment.md` | The conformity assessment process record and resulting Declaration of Conformity, including the specific basis for self-assessment versus third-party involvement |
| `human-oversight-and-monitoring-procedure.md` | The operational human oversight procedure and post-market monitoring plan that must be functioning before, and maintained after, the system is placed on the market |

## How the Artefacts Connect

The technical documentation is the factual foundation — what the system is, how it works, what data it uses, and crucially, what its known limitations are. Everything else in the pack is built on top of an honest version of this document; a conformity assessment built on technical documentation that quietly omits a known weakness is not a real conformity assessment, it is a liability waiting to surface at the worst possible moment, typically during a regulatory investigation or in the aftermath of an incident of the kind documented in Project 4.

The conformity assessment takes that technical documentation and tests it against the EU AI Act's specific high-risk requirements one by one, reaching a documented conclusion on each — not a single yes/no but a structured walk through each requirement, because a real conformity assessment is exactly this granular. Where this assessment finds the system does not yet meet a requirement, it says so plainly, with a remediation commitment attached, rather than asserting conformity prematurely to get the documentation signed off.

The human oversight and monitoring procedure is what keeps the conformity declaration honest after the date it is signed. A high-risk system's conformity is not a fixed state achieved once; it is a standing condition that depends on the oversight and monitoring controls described in this document continuing to function exactly as documented, for as long as the system remains in production.

## Key Decisions & Rationale

**Why document a system that Project 1 already found to have critical gaps, rather than waiting until those gaps are fully closed?** Because in practice, conformity documentation is precisely the artefact that surfaces which gaps are closed, which are partially closed, and which remain open — it is the working document through which remediation gets tracked, not a certificate that can only be produced once everything is already perfect. A conformity pack that says, in effect, "here is where this system currently stands, here is what is compliant today, and here is the specific remediation commitment for what is not yet" is more useful, and more honest, than silence until an idealised future state is reached.

**Why does the human oversight procedure spend so much attention on the fallback authentication path, rather than focusing only on the primary biometric matching function?** Because Project 1 specifically flagged that the fallback path — what happens to a customer who fails voice authentication — had never been audited for fairness or accessibility. A system's fairness and safety properties are not fully captured by how well its primary function performs; they are also defined by what happens to the people for whom the primary function does not work, and that population is disproportionately likely to include people with speech differences, strong regional accents, recent illness affecting their voice, or limited proficiency in the system's primary language. A conformity pack that is silent on the fallback path has not actually documented the system's full effect on the people it serves.

**Why include a explicit "self-assessment versus third-party assessment" discussion rather than simply asserting the system is conformant?** Because which assessment route applies is itself a substantive, sometimes contested, regulatory question for biometric systems specifically, and a credible conformity pack has to show its reasoning on that question rather than skip straight to a conclusion. Treating the assessment route as a footnote rather than a reasoned decision is exactly the kind of shortcut that looks fine until a regulator or auditor asks the question directly.

## Frameworks Applied

- **EU AI Act** — Article 9 (risk management system), Article 10 (data and data governance), Article 11 and Annex IV (technical documentation), Article 12 (logging and traceability), Article 13 (transparency and information to deployers), Article 14 (human oversight), Article 15 (accuracy, robustness, and cybersecurity), Article 17 (post-market monitoring), Article 43 (conformity assessment procedures), Article 47 and Annex V (EU declaration of conformity)
- **NIST AI RMF** — the Measure and Manage functions specifically, since a conformity pack is where rigorous measurement (Measure) and an ongoing management commitment (Manage) become a single, auditable artefact
- **ISO/IEC 42001** — the AI management system standard's documentation and continual improvement requirements, used as the structural model for how the conformity pack should be maintained as a living set of documents rather than a one-time deliverable

---

*Author: Anju Karun · AIGP (AI Governance Professional)*
