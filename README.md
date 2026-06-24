# Project 1: AI System Inventory & EU AI Act Classification Engine

## Scenario

**Organisation:** Halcyon Financial Group (HFG) — a mid-sized financial services group offering retail banking, consumer lending, wealth management, and insurance products. Approximately 2,100 employees. Headquartered in the EU, with operations spanning Germany, Ireland, and the Netherlands.

**Problem:** Following the EU AI Act's phased entry into application, HFG's newly appointed Head of AI Governance was asked by the Board Risk Committee to answer a deceptively simple question: *"How many AI systems do we actually have, and which ones are high-risk?"* No one could answer with confidence. AI systems had been commissioned independently by Retail Lending, HR, Compliance, Marketing, and Operations over several years — some built in-house, some bought from vendors — with no central registry, no consistent classification, and no shared definition of what even counts as an "AI system" for regulatory purposes.

**Objective:** Build a structured, authoritative AI system inventory across HFG's business units. Apply EU AI Act risk-tier classification to every system with a documented legal rationale. Cross-map each system against the NIST AI Risk Management Framework to expose governance maturity gaps that the classification exercise alone would not surface.

This project is the **foundation layer** of the portfolio. Every subsequent project — risk assessment, policy design, incident response, and high-risk conformity documentation — draws on the inventory and classifications established here.

## What This Project Demonstrates

- Ability to **design and populate a governance-grade AI inventory schema** that is usable by risk, legal, compliance, and engineering stakeholders simultaneously — not just a list, but a structured dataset with the fields a regulator, auditor, or GRC platform would expect.
- Working knowledge of the **EU AI Act's risk-based classification logic**, including correct application of Annex III high-risk categories, Article 52 transparency triggers, and the reasoning needed to justify a tier decision that would survive legal challenge.
- Practical fluency with the **NIST AI RMF's four functions (Govern, Map, Measure, Manage)** as a maturity-assessment lens distinct from, but complementary to, legal risk classification — recognising that a system can be "Limited Risk" under the EU AI Act while still being governed immaturely.
- Understanding of **proportionality** as the organising principle of AI governance: obligations and scrutiny should scale with risk, not be applied uniformly, and the classification step is what makes that scaling possible.
- The judgement to flag **ambiguous or borderline classifications** (e.g., a pilot system not yet in production) and apply a conservative governance posture pending legal confirmation, rather than deferring the question entirely.

## Artefacts

| File | Description |
|---|---|
| `ai-system-inventory.csv` | Structured inventory of all 10 AI systems identified across HFG's business units |
| `eu-ai-act-classification.md` | Risk-tier classification with legal basis, rationale, triggered obligations, and compliance gap per system |
| `nist-rmf-mapping.md` | Maturity mapping of each system against the four NIST AI RMF functions, with portfolio-level risk concentration analysis |

## Key Decisions & Rationale

**Why a CSV for the inventory, not a Word document or slide deck?** A governance inventory only has value if it is queryable, sortable, and importable into a GRC tool, model registry, or risk system of record. A narrative document hides the data inside prose. The CSV format approximates what would, in a real deployment, live in a structured system of record — and it is the artefact a risk team would actually ask for first.

**Why classify before doing a full risk assessment?** Classification is a *triage* step, not the end of the analysis. It determines the depth of due diligence a system requires before that due diligence is performed — high-risk classification is what *triggers* the deeper work done in Project 2 (risk assessment) and Project 5 (conformity documentation). Skipping straight to deep assessment on every system regardless of risk tier would be disproportionate and would not reflect how governance functions actually operate under resource constraints.

**Why map to NIST AI RMF separately from EU AI Act classification?** The two frameworks answer different questions. The EU AI Act tells you *what you are legally obligated to do*. The NIST AI RMF tells you *how mature your organisation's actual practices are* in governing that obligation. A system can be correctly classified as Limited Risk and have no statutory high-risk obligations, while still scoring poorly on RMF maturity because no one is monitoring it. Conflating the two would hide governance debt that doesn't show up in a legal risk tier alone.

**Fictional company, real logic.** Halcyon Financial Group is fictional, but every system in this inventory reflects an AI use case genuinely deployed across financial services today — credit decisioning, CV screening, transaction monitoring, voice biometrics, conversational support, and internal analytics are not hypothetical categories. The classification rationale throughout cites the specific Articles and Annex III categories that would apply to each, in the same way a real classification memo would.

## Frameworks Applied

- **EU AI Act** — Article 6 (classification rules), Article 52 (transparency obligations), Annex III (high-risk use-case categories), and the obligation chain triggered by high-risk status (Articles 9–17, 43, 71)
- **NIST AI RMF (AI RMF 1.0)** — Govern, Map, Measure, Manage functions, scored on a 1–4 maturity scale
- **ISO/IEC 42001** — referenced contextually in governance gap notes as the AI management system standard against which HFG's eventual certification posture would be benchmarked

---

*Author: Anju Karun · AIGP (AI Governance Professional)*
