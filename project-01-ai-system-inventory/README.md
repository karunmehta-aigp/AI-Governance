# Project 1: AI System Inventory & Classification Engine

## Scenario

**Organisation:** NorthStar Financial Services — a mid-sized fintech
operating across retail banking, lending, and insurance verticals.
Approximately 1,400 employees. Regulated in the EU.

**Problem:** NorthStar's Chief Risk Officer has initiated an AI governance
programme following the EU AI Act entering application. A preliminary
internal survey revealed that AI systems have been deployed across multiple
business units without central oversight or classification. The
organisation does not have a single authoritative inventory of its AI
systems.

**Objective:** Produce a structured AI system inventory and apply EU AI Act
risk classification to each identified system. Map each system to the NIST
AI RMF's four core functions to identify governance gaps — not just whether
a system is classified correctly, but whether the organisation actually has
the controls in place to meet the obligations that classification implies.

## What this demonstrates

- Ability to take a vague governance mandate ("we don't know what AI we're
  running") and turn it into a structured, repeatable artefact
- Working knowledge of EU AI Act Annex III categories and Article 50
  transparency obligations, applied to specific systems rather than recited
  in the abstract
- Working knowledge of the NIST AI RMF's four functions, used as a gap
  analysis tool rather than just a glossary
- Judgement on the cases that don't resolve cleanly — see NS-AI-002 in
  particular, where the obvious classification is wrong
- Capacity to structure governance data in a format usable by risk, legal,
  and engineering teams

---

## Artefacts

| File | Description |
|---|---|
| [`ai-system-inventory.csv`](./ai-system-inventory.csv) | Structured inventory of NorthStar's 10 AI systems |
| [`eu-ai-act-classification.md`](./eu-ai-act-classification.md) | Classification rationale for each system under the EU AI Act, citing specific articles and Annex III entries |
| [`nist-rmf-mapping.md`](./nist-rmf-mapping.md) | Mapping of each system to the NIST AI RMF's four functions, with a gap analysis and cross-cutting findings |

---

## Key Decisions & Rationale

**Why a CSV for the inventory?** A structured data format (rather than a
narrative document) makes the inventory queryable, sortable, and importable
into GRC tooling. In practice this would live in a system of record — the
CSV approximates that structure without requiring a real platform for a
portfolio project.

**Why classify before doing a full gap analysis?** Classification
determines the *level of due diligence* required. It's a triage step:
high-risk classification is what makes the NIST RMF gap analysis worth doing
in depth for a system, and what would trigger deeper documentation work in
a conformity assessment. This mirrors real governance workflows, where
classification gates everything that follows it.

**Why include a system the classifier gets "obviously" wrong at first
glance (NS-AI-002)?** Because that's the case worth being able to talk
through in an interview. A clean inventory where every system slots
neatly into the tier its surface features suggest doesn't demonstrate
anything beyond having read the regulation's headline categories. The fraud
detection system looks high-risk on every dimension except the one that
actually matters — the specific exclusion clause tied to its stated
purpose. Being able to explain *why* the exclusion applies, not just that
it does, is the actual skill.

**Fictional company, real logic.** NorthStar is fictional, but every system
in the inventory reflects a genuine AI use case present in financial
services today. The classification rationale cites specific articles and
annexes from the EU AI Act, and the gap analysis reflects governance
failure patterns (vendor assumption gaps, pipeline risk, pilot-stage
deferral) that show up repeatedly in real organisations, not invented
problems designed to pad out the document.

---

## Frameworks Applied

**EU AI Act**
- Article 5 — prohibited practices (checked against, none triggered in this
  inventory)
- Article 6 and Annex III — high-risk classification criteria
- Article 50 — transparency obligations for systems interacting directly
  with natural persons
- Articles 9–17 (referenced, not fully documented here — see
  `project-05-high-risk-documentation` for the full conformity pack for one
  of these systems)

**NIST AI Risk Management Framework**
- GOVERN — accountability structures and policy ownership per system
- MAP — context, purpose, and risk already captured via the inventory and
  EU AI Act classification
- MEASURE — whether performance, fairness, and reliability testing actually
  exists, or is merely assumed
- MANAGE — whether a defined response process exists for when something
  goes wrong

## How this connects to the next project

This inventory is the foundation the rest of the portfolio builds on.
The four systems classified HIGH-RISK here (NS-AI-001, NS-AI-004, NS-AI-006,
NS-AI-010) are the candidates carried into `project-02-risk-assessment` for
a full structured risk assessment, and one of them is carried further into
`project-05-high-risk-documentation` for a complete EU AI Act conformity
documentation pack.
