# Project 3: Responsible AI Policy & Operating Model

> **⚠️ Disclaimer:** This project is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed in this material.

## Scenario

**Organisation:** The organisation (as established in Project 1)
**Context:** Following the classification work in Project 1 and the risk assessment work in Project 2, the Board has approved the formal establishment of an AI governance programme. Until now, AI governance at the organisation has existed as a set of one-off exercises performed in response to specific problems — a classification sweep here, a risk assessment there. The Board's direction is unambiguous: this cannot continue to be a series of reactive projects. It needs to become a standing capability with its own structure, its own rules, and its own decision rights.

The AI Governance Programme Office has been asked to produce two foundational documents that, together, convert that direction into something operational: a **Responsible AI Policy** that states what the organisation believes and commits to, and a **Governance Operating Model** that defines who actually makes which decisions, on what timeline, and with what authority. A third artefact — the **AI Use Case Review and Approval Process** — sits between the two, translating the policy's principles and the operating model's structure into the actual workflow a business owner follows from the moment they have an idea for an AI system to the moment it goes live and beyond.

This project is the **third layer** of the portfolio, and a deliberate shift in kind from Projects 1 and 2. Those projects analysed specific systems that already existed. This project builds the standing machinery that should have existed before any of those systems were ever deployed — the structure that, if it had been in place in 2020, would have caught the gaps Project 1 and Project 2 had to discover after the fact.

## What This Project Demonstrates

- Understanding that responsible AI principles only have governance value once they are translated into **process** — a policy that states a commitment to fairness without defining who checks for bias, when, and against what threshold is not a governance control, it is a statement of intent.
- Ability to design a **proportionate governance operating structure**: committees, roles, escalation paths, and decision rights that scale review intensity to risk, rather than applying uniform bureaucracy to every system regardless of its actual potential for harm.
- Working knowledge of how the **NIST AI RMF Govern function** operationalises in practice — not as an abstract category, but as a specific set of committees, named roles, a decision authority matrix, and a reporting calendar that a real organisation could stand up within a single quarter.
- Understanding of the **full AI lifecycle** as a governance object in its own right: submission, triage, review (proportionate to risk), approval (with conditions where appropriate), deployment, and — critically, and often the weakest link in real organisations — ongoing monitoring and the triggers that force an out-of-cycle review.
- Ability to connect legal, data protection, information security, risk, and engineering functions into a **single coherent governance structure** that integrates with an organisation's existing risk and assurance architecture rather than duplicating it or operating in parallel to it.
- The judgement to design escalation paths and quorum rules that are specific and testable (a named quorum, a named timeline, a named fallback authority) rather than vague gestures toward "appropriate oversight" that would collapse under any real dispute.

## Artefacts

| File | Description |
|---|---|
| `responsible-ai-policy.md` | The organisation's Responsible AI Policy — five principles, each paired with the specific practices that operationalise it, plus lifecycle governance requirements, vendor obligations, training requirements, and breach handling |
| `ai-review-process.md` | The end-to-end AI use case submission, triage, review, and approval workflow, including a proportionate Standard/Enhanced review split and a materiality test for when an approved system must be re-reviewed |
| `governance-operating-model.md` | The governance structure itself — committee mandates, named roles, a decision authority matrix, integration with existing risk functions, and the reporting calendar that keeps the whole structure accountable |

## Design Principles for This Project

**Principles without process are decoration.** Many organisations publish a page of AI principles that reads well and changes nothing about how a system actually gets approved. Every principle in the Responsible AI Policy here is written with its operational consequence directly underneath it — not "we are committed to fairness" as a standalone sentence, but a description of exactly which systems require a bias evaluation, before what event, assessed by whom, and what happens if the evaluation finds a problem.

**Governance is a risk-allocation exercise, not a uniform checkpoint.** A minimal-risk internal analytics tool and a high-risk credit decisioning system should not pass through the same review. The review process is built around a deliberate fork: lightweight triage for everything, then a fast Standard Review track for minimal/limited-risk systems and a slower, cross-functional Enhanced Review track for high-risk systems. Proportionality is not a slogan here — it is the actual shape of the workflow.

**Structure should reflect the organisation that actually exists, not an idealised one.** This operating model is built for a mid-sized regulated financial services firm: it assumes a Chief Risk Officer, a Data Protection Officer, a General Counsel, and a CISO already exist and already have full-time jobs unrelated to AI — it does not assume a 50-person dedicated AI ethics function, nor does it assume governance can be handled informally by one engineer with good intentions. The model re-purposes committees and roles that already exist in most organisations of this size, rather than inventing a parallel governance universe.

**Every commitment needs an owner, a timeline, and a consequence for non-delivery.** Throughout all three artefacts, deliberately avoid governance language that sounds rigorous but cannot actually be enforced — "regular review," "appropriate escalation," "as needed." Every recurring obligation in this project has a named frequency; every escalation path has a named recipient and a timeframe; every approval condition has an owner and a due date. This is the difference between a policy that reads well and a policy that an auditor could actually test compliance against.

## Frameworks Applied

- **NIST AI RMF** — the Govern function in full: accountability structures, organisational culture and incentives, policies that translate into process, and the integration of AI risk into the organisation's broader risk taxonomy
- **EU AI Act** — Article 9 (risk management system as a continuous, iterative process rather than a one-time exercise), Article 14 (human oversight, including the distinction between nominal and meaningful oversight that the policy makes explicit), Articles 26 and 28 (deployer obligations, including the specific contractual and operational requirements placed on vendor-supplied high-risk systems)
- **OECD AI Principles** — human-centred values and well-being, transparency and explainability, robustness and safety, and accountability, used as the underlying ethical architecture beneath the policy's five operational principles
- **ISO/IEC 42001** — the AI management system standard's emphasis on a structured, auditable, continuously improving management system as the model for how the policy, operating model, and review process should function together as a single system rather than three disconnected documents

---

*Karun · AIGP (AI Governance Professional)*
