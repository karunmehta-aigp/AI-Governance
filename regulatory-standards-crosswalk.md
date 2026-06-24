# Regulatory and Standards Crosswalk

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced throughout this portfolio are entirely fictional. No real entity is described, referenced, or disclosed.

**Document Type:** Reference layer — not tied to any single AI system
**Purpose:** To show, side by side, how the EU AI Act, the NIST AI Risk Management Framework, ISO/IEC 42001, and the OECD AI Principles each address the same underlying governance obligations, in their own vocabulary and structure — and to show where each framework is referenced across this portfolio.
**Version:** 1.0 — November 2026

---

## Why This Document Exists

A genuinely common failure in AI governance practice is treating each framework as a separate compliance project, run in parallel by different people who never compare notes — one team works through the EU AI Act article by article, another runs a NIST RMF gap assessment, and a third pursues ISO 42001 certification, and none of the three ever produces a single combined view of what they are each independently discovering about the same underlying systems. This crosswalk exists specifically to prevent that fragmentation: every row below shows the same governance obligation expressed in four different vocabularies at once, so a single control can be built once and mapped to all four frameworks, rather than four separate, redundant controls being built to satisfy each framework in isolation.

---

## Crosswalk Table

| Governance Obligation | EU AI Act | NIST AI RMF | ISO/IEC 42001 | OECD AI Principles | Demonstrated In |
|---|---|---|---|---|---|
| Establish accountability structure and AI policy | Art. 9(1)–9(2) (risk management as an organisational function) | GOVERN 1.1–1.3 | Clause 5 (Leadership) — AI policy, roles, responsibilities | Accountability | Project 3, `responsible-ai-policy.md` §6; `governance-operating-model.md` in full |
| Maintain a system inventory / register of AI systems | Art. 71 (EU database registration, for high-risk systems) | GOVERN 1.5 | Clause 4.4 (AIMS scope and systems in scope) | — | Project 1, `ai-system-inventory.csv` / `.xlsx` |
| Classify AI systems by risk level | Art. 6, Annex III | MAP 1.1, MAP 5.1 | Clause 6.1.2 (AI risk assessment), informed by ISO/IEC 23894 | — | Project 1, `eu-ai-act-classification.md` |
| Assess and document risk before deployment | Art. 9(2) (continuous risk management) | MAP, MEASURE functions in full | Clause 6.1.4 (AI system impact assessment); Clause 8.2 (AI system impact assessment in operation) | Robustness, security, and safety | Project 2, `risk-assessment.md`; Project 5, `02-risk-management-summary.md` |
| Govern training, validation, and testing data quality | Art. 10 (data and data governance) | MAP 2.3, MEASURE 2.x (data-related measurement) | Annex A.7 (data for AI systems) | Fairness and data quality | Project 1's RMF mapping data-governance gap notes; Project 5, `03-data-governance.md` |
| Produce technical documentation | Art. 11, Annex IV | GOVERN 1.2, MAP 1.1 (documentation supporting risk categorisation) | Clause 7.5 (documented information) | Transparency | Project 5, `technical-documentation.md` and `01-intended-purpose.md` |
| Logging and traceability | Art. 12 | MANAGE 4.1 (incident response relies on traceable records) | Clause 7.5; Annex A.6 (system documentation and traceability) | Transparency and accountability | Project 5, `05-logging-traceability.md` |
| Transparency to affected persons and deployers | Art. 13, Art. 50, Art. 52 | GOVERN 4.1, MAP 5.2 | Annex A.4 (transparency and provision of information) | Transparency and explainability | Project 1, `eu-ai-act-classification.md` (Art. 52 disclosure gaps); Project 5, `01-intended-purpose.md` |
| Human oversight of automated outputs | Art. 14 | GOVERN 4.2, MANAGE 2.1 | Annex A.9 (use of AI systems — human oversight controls) | Human-centred values | Project 2's recommended oversight model; Project 3, `responsible-ai-policy.md` §3.5; Project 5, `04-human-oversight.md` |
| Accuracy, robustness, and cybersecurity | Art. 15 | MEASURE 2.5–2.7, MANAGE 1.1 | Clause 8 (Operation); Annex A.8 (AI system security) | Robustness, security, and safety | Project 1's RMF maturity scoring; Project 5, `conformity-assessment.md` (Art. 15 finding) |
| Post-market monitoring | Art. 17 | MEASURE (ongoing), MANAGE 4.1–4.3 | Clause 9 (Performance Evaluation) | Accountability | Project 5, `06-performance-monitoring.md`; `human-oversight-and-monitoring-procedure.md` |
| Deployer obligations for third-party / vendor AI systems | Art. 26, Art. 28–29 | GOVERN 6.1 (third-party risk) | Annex A.10 (third-party and supplier relationships) | Accountability | Project 1's vendor-gap notes across all four high-risk systems; Project 5, `02-risk-management-summary.md` R5 |
| Conformity assessment and declaration | Art. 43, Art. 47, Annex V | (Not a direct NIST RMF equivalent — NIST RMF is voluntary and does not include a conformity declaration mechanism) | Clause 9.2 (internal audit); the certification audit itself | — | Project 5, `conformity-assessment.md` |
| Serious incident reporting | Art. 73 | MANAGE 4.3 | Clause 10.1 (nonconformity and corrective action); Annex A.6 (incident response) | Accountability | Project 4 in full |
| Continual improvement | (Implicit across Arts. 9, 17, 72) | MANAGE 4.x (feedback loops) | Clause 10 (Improvement) — the explicit "Act" stage of the AIMS's PDCA cycle | — | Project 4's lessons-learned section; Project 3's annual policy review requirement |

---

## A Structural Note on How These Four Frameworks Actually Relate

It is worth being precise about something this table can otherwise make look flatter than it is: these four frameworks are not four equivalent menus a governance professional picks from. They operate at different levels and serve different functions, and conflating them is itself a common practitioner mistake worth naming explicitly:

- The **EU AI Act** is **binding law** in its jurisdiction, with specific, numbered legal obligations and penalties for non-compliance. It tells you what you are legally required to do.
- The **NIST AI RMF** is a **voluntary framework**, not law, and has no certification or conformity mechanism at all — there is no such thing as being "NIST AI RMF certified." It tells you how mature your practices are, which is a different question from whether you are legally compliant. A system can be perfectly NIST RMF-mature and still fail an EU AI Act conformity assessment, or vice versa, because the two are answering different questions about the same system.
- **ISO/IEC 42001** is a **certifiable management system standard**, structured like ISO 27001 and ISO 9001 around a Plan-Do-Check-Act cycle (Clauses 4–6 Plan, 7–8 Do, 9 Check, 10 Act). It does not tell you what to do for any single AI system; it tells you whether your *organisation's overall system for managing AI* is sound — closer in spirit to NIST RMF's Govern function than to the EU AI Act's system-specific obligations, but auditable and certifiable in a way NIST RMF is not.
- The **OECD AI Principles** sit above all three as **high-level policy principles**, adopted by governments, that the other three frameworks can all be read as different operational translations of. They are the least specific and the most universally agreed; the EU AI Act, NIST RMF, and ISO 42001 are three different, more detailed attempts to make those same underlying values operational and checkable.

Understanding this hierarchy — legally binding, voluntary-but-structured, certifiable-management-system, and high-level-policy — is arguably more practically useful than memorising any single framework's specific clause numbers, because it is what allows a governance professional to correctly tell a stakeholder "yes, we are NIST RMF mature in this area, but that does not mean we are EU AI Act compliant, and here specifically is the gap between the two" rather than treating "governance" as one undifferentiated state a system either has or lacks.

---

## How This Crosswalk Differs From a Simple Article-Number List

A list that simply states "Article 14 = human oversight" adds little value beyond what the Act's own table of contents already provides. This crosswalk is built differently, on purpose: every row also shows *where in this specific portfolio* the obligation was actually operationalised, so the document functions as a navigational aid into the rest of the body of work, not only as an abstract reference table. A reader who wants to see this portfolio's most fully worked example of human oversight, for instance, does not need to search five project folders — this table points directly to the three artefacts where it is demonstrated, in increasing order of operational specificity.

---

*This crosswalk is maintained alongside the AIGP Knowledge Map in this reference library, and both are updated together if any underlying framework is revised.*

---

*Author: Karun · AIGP (AI Governance Professional)*
