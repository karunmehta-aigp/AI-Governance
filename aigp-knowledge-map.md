# AIGP Knowledge Map — Portfolio Cross-Reference

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced throughout this portfolio are entirely fictional. No real entity is described, referenced, or disclosed.

**Document Type:** Reference layer — not tied to any single AI system
**Purpose:** To map every artefact in this portfolio explicitly to the IAPP AIGP Body of Knowledge (BoK v2.1, effective February 2026), so a reader assessing this work against the certification it supports can see exactly where each domain and competency is demonstrated, rather than having to infer it.
**Version:** 1.0 — November 2026

---

## Why This Document Exists

Most AI governance portfolios show *what* was built. This document exists to show *why* it was built this way, against a specific, named professional standard — the four-domain structure the IAPP uses to define AIGP competence. A portfolio that happens to look thorough is less valuable than one that can be checked, item by item, against the actual body of knowledge a credentialed professional is expected to know. This document is that check.

It is deliberately not folded into any single project, because its value is in showing the relationships *across* all five — a Domain III competency demonstrated in Project 3's policy work only fully makes sense alongside the Domain IV competency demonstrated in Project 5's deployment monitoring, and this document is where that relationship is made explicit rather than left for the reader to assemble themselves.

---

## The Four Domains, in Brief

| Domain | Focus | Approximate Weight |
|---|---|---|
| **I — Foundations of AI Governance** | What AI governance is; AI risk and harm types; responsible AI principles; organisational readiness | ~21% |
| **II — Laws, Standards, and Frameworks** | Existing law applied to AI (data protection, non-discrimination); AI-specific law (the EU AI Act); industry standards (NIST AI RMF, ISO/IEC 42001 and 42005) | ~25% |
| **III — Governing AI Development** | Risk and impact assessment during design and build; data governance; testing and validation; release readiness | ~27% |
| **IV — Governing AI Deployment and Use** | Deployment risk evaluation; vendor and third-party risk; ongoing monitoring; incident management; decommissioning | ~27% |

---

## Domain I — Foundations of AI Governance

| Competency Area | Where Demonstrated | How |
|---|---|---|
| Identifying AI risk and harm types (bias, opacity, misalignment, scale) | Project 1, `eu-ai-act-classification.md`; Project 4, `incident-scenario.md` | The classification rationale for each system names the specific harm mechanism (e.g., proxy discrimination via geographic variables), not just a generic "risk" label; Project 4 narrates a harm type — indirect discrimination via a facially neutral feature — playing out in practice |
| Responsible AI principles (fairness, transparency, accountability, safety, human oversight) | Project 3, `responsible-ai-policy.md` | Each of the five principles is paired explicitly with the operational practice that makes it checkable, rather than left as an aspirational statement |
| Organisational readiness and cross-functional collaboration | Project 3, `governance-operating-model.md` | The full committee structure, decision authority matrix, and integration table showing how AI governance connects to existing risk, legal, security, and audit functions rather than duplicating them |
| AI lifecycle policies | Project 3, `ai-review-process.md` | The full submission-to-decommissioning lifecycle, with a proportionate Standard/Enhanced review split |

**A note on this domain's relative weight in this portfolio:** Domain I is foundational and necessary, but this portfolio deliberately spends more of its own "weight" on Domains III and IV than a study guide would — consistent with the general practitioner observation that real governance work, and the harder parts of the actual exam, concentrate there. Foundational principles appear throughout the portfolio, but are demonstrated through application (Projects 1–5) rather than through a standalone definitional document, on the view that showing fairness operationalised in a real risk register is stronger evidence of foundational understanding than restating the definition of fairness on its own.

---

## Domain II — Laws, Standards, and Frameworks

| Competency Area | Where Demonstrated | How |
|---|---|---|
| Existing data protection law applied to AI (notice, lawful basis, automated decision-making rights) | Project 1, `eu-ai-act-classification.md` (Article 52 transparency); Project 5, `03-data-governance.md` (lawful basis analysis for candidate data) | Each artefact distinguishes the AI-specific obligation from the underlying data protection obligation it sits alongside, rather than treating "compliance" as one undifferentiated category |
| The EU AI Act specifically — risk tiers, Annex III, Articles 9–17, 28, 43, 50, 52, 73 | Every project | Project 1 establishes the classification vocabulary; Projects 2 through 5 each engage a different cluster of articles relevant to their stage of the lifecycle, shown explicitly in each project's "Frameworks Applied" section |
| NIST AI RMF — the four functions (Govern, Map, Measure, Manage) | Project 1 (Map/Measure baseline); Project 2 (Map/Measure applied); Project 3 (Govern); Project 4 (Manage) | The portfolio is structured so each NIST function gets its own dedicated project-level demonstration, rather than all four being gestured at superficially in every document |
| ISO/IEC 42001 (AI management systems) and the broader ISO standards landscape | Referenced throughout; most explicit in Project 5's `README.md` and the companion `regulatory-standards-crosswalk.md` in this reference library | See the crosswalk document for the detailed clause-level mapping, kept separate from individual projects because ISO 42001 compliance is a property of the whole management system, not of any single artefact |

---

## Domain III — Governing AI Development

| Competency Area | Where Demonstrated | How |
|---|---|---|
| Risk and impact assessment during design | Project 2, `risk-assessment.md`; Project 5, `02-risk-management-summary.md` | Both use a consistent likelihood-times-impact methodology, but Project 5 shows the same methodology applied *before* a system goes live, demonstrating the distinction between assessing a deployed system's risk and assessing a proposed system's risk pre-build |
| Data governance, including training data quality and bias evaluation | Project 5, `03-data-governance.md` | Includes a deliberately specific question about whether synthetic data used to fill an underrepresented category can itself introduce bias through a different mechanism than historical data bias — a more advanced data governance question than a basic "was the data lawfully sourced" check |
| Testing, validation, and release readiness | Project 5, `02-risk-management-summary.md` Section 3 (pre-deployment risk evaluation, with an explicit go-live gate) | Shows a structured gate — every required evaluation must be complete and signed off by four separate named functions before deployment proceeds — rather than an informal "testing happened" assertion |
| Model and system documentation (model cards, technical documentation) | Project 5, `technical-documentation.md` and `01-intended-purpose.md` | `technical-documentation.md` in particular is built around the principle that documenting a known limitation honestly is more valuable than omitting it to look more complete |

---

## Domain IV — Governing AI Deployment and Use

| Competency Area | Where Demonstrated | How |
|---|---|---|
| Deployment risk evaluation | Project 2 in full | An entire project dedicated to assessing a system already in production, distinct from Domain III's pre-deployment risk assessment |
| Vendor and third-party risk, including contractual controls | Project 1, `eu-ai-act-classification.md` (vendor contract gaps flagged per system); Project 3, `responsible-ai-policy.md` Section 5; Project 5, `02-risk-management-summary.md` R5 | The portfolio shows the same vendor-risk lesson being learned the hard way in one project (undisclosed retraining cadence) and then applied proactively in a later one (a 60-day contractual notice requirement negotiated in advance) — demonstrating the difference between identifying a risk and institutionalising the fix |
| Ongoing monitoring and maintenance | Project 5, `06-performance-monitoring.md` | Goes beyond the legal minimum with original fairness metrics (an override-correction-rate-by-group metric not found in standard industry templates) specifically designed to detect a failure mode — oversight that looks present but isn't actually correcting model-level disparity — that a single parity metric would miss |
| Incident management | Project 4 in full | A complete detection-to-closure incident lifecycle, including the specific judgement calls (when to disclose, to which of four separate regulatory regimes, on what timeline) that a written incident *policy* alone cannot fully convey without a worked example |
| Decommissioning and system retirement | Project 3, `responsible-ai-policy.md` Section 4.5; Project 1's inventory, which records systems still in Pilot status explicitly as not-yet-fully-deployed | Decommissioning is treated as a defined lifecycle stage with its own owner and obligations, not an afterthought to deployment |

---

## A Cross-Cutting Observation: Bias Appears in Every Domain, Differently

One of the more advanced study insights about the AIGP body of knowledge is that the same underlying concept resurfaces across domains in a different register each time, and recognising that shift is itself part of the competency being tested. This portfolio was built with that pattern deliberately in view:

- In **Domain I** terms, bias is a foundational *harm type* — something that can occur, in the abstract, and needs to be named in any inventory of AI risks (Project 1's classification work).
- In **Domain II** terms, bias becomes a specific *legal exposure* — indirect discrimination under non-discrimination law, triggering particular obligations under specific Articles (Project 1 and Project 4's regulatory analysis).
- In **Domain III** terms, bias is a *design-time question* to be tested for before a system goes live — a bias audit, a proxy analysis, a synthetic-data review (Project 5's data governance work).
- In **Domain IV** terms, bias is an *ongoing monitoring problem* — something that can emerge or drift after deployment even in a system that passed every pre-launch check, requiring continuous measurement rather than a one-time clearance (Project 5's monitoring plan; Project 4's incident, which is precisely a Domain III gap surfacing as a Domain IV failure years later).

Recognising that all four of these are "the same risk" viewed through four different professional lenses — not four separate risks — is, in this author's view, one of the more practically important judgements an AIGP-credentialed professional needs to be able to make, and this portfolio was structured specifically to demonstrate it across Projects 1 through 5 rather than asserting it in the abstract.

---

*This document is maintained alongside the rest of the reference library and updated if the underlying AIGP Body of Knowledge is revised.*

---

*Author: Karun · AIGP (AI Governance Professional)*
