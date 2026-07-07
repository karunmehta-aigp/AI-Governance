
# Project 10: Enterprise AI Governance Operating Framework (AIGOF)

> ⚠️ **Disclaimer:** This is a portfolio artifact demonstrating applied AI governance capability. It contains original governance questions, controls, and an operating model that **map to** NIST AI RMF, ISO/IEC 42001, and the EU AI Act — it does **not** reproduce proprietary standard text. Verify all clause/article references against the official published standards. Nothing here is legal advice, and fast-moving regulatory content (e.g., US state AI law) should be re-verified against primary sources before operational use.

---

## Scenario

An enterprise deploying AI across multiple business lines needs to govern those systems against three overlapping regimes at once — the **NIST AI RMF** (risk management), **ISO/IEC 42001** (management-system conformity), and the **EU AI Act** (legal obligation) — while also running the day-to-day operational governance a real program requires: inventory, risk registers, controls, committee decisions, KPIs, and audit evidence.

Most organizations tackle these in isolation, duplicating effort and leaving gaps invisible until an audit or incident surfaces them. This project is a single, consolidated toolkit that closes that gap — a 43-worksheet Excel workbook that produces framework-compliance answers *and* runs the operational program from one source of truth.

---

## What this is

A comprehensive, audit-ready Excel toolkit organized in three layers that mirror how a mature AI Governance Office actually operates:

1. **Framework layer** — a Master Crosswalk mapping all **72 NIST AI RMF subcategories** to ISO/IEC 42001 and the EU AI Act, plus detailed audit checklists (360+ testable questions)
2. **Operational layer** — lifecycle view, stage gates, SDLC, program management, data/model governance, and a deduplicated controls library
3. **Business layer** — executive summary, live dashboard (KPIs, risk heatmap, maturity radar), sector packs, and privacy/state-law overlays

---

## How to use it

1. **Operating Model** — understand the end-to-end governance flow and stage ownership
2. **AI Inventory** — catalog your AI systems and assign risk tiers
3. **Gap Assessment** — work the Master Crosswalk and framework checklists for in-scope systems
4. **Risk Register** — capture gaps as risks with owners and residual ratings
5. **Controls Library** — map which controls address each risk; track implementation
6. **Evidence Catalog** — gather the artifacts that prove each control operates
7. **Dashboard & Maturity** — roll up status, KPIs, and maturity for leadership
8. **Governance Committee** — review, decide, log decisions; then monitor and improve

---

## Worksheet index (43 tabs)

### Orientation & executive
| # | Worksheet | Purpose |
|---|-----------|---------|
| 1 | README | In-workbook orientation |
| 2 | Cover & Instructions | Purpose, scope, version history, document control |
| 3 | Executive Summary | One-page board view: live metrics, top risks, recommendations, 30/60/90-day roadmap |
| 4 | Dashboard | Coverage roll-up, KPI panel, maturity headline, risk heatmap, open vs. closed findings, charts |

### Operating structure
| # | Worksheet | Purpose |
|---|-----------|---------|
| 5 | Operating Model | End-to-end flow mapped to owner, deliverables, frameworks, controls, outputs |
| 6 | Lifecycle View | Controls mapped by lifecycle stage |
| 7 | Governance Roadmap | 7-phase implementation plan with owners, durations, dependencies, status |
| 8 | Stage Gates | G1–G7 gates with entry/exit criteria and pass/fail decision |
| 9 | Framework Mapping Matrix | Which frameworks govern each activity |

### Framework assessment
| # | Worksheet | Purpose |
|---|-----------|---------|
| 10 | Master Crosswalk | 72 NIST subcategories × ISO 42001 × EU AI Act, with state, evidence, gap, risk, recommendation, owner, status |
| 11 | EU AI Act Full Assessment | 35 articles, general provisions through GPAI and penalties |
| 12 | ISO 42001 Full Assessment | Full clause structure (4–10) plus Annex A control families |
| 13 | Audit Checklist – NIST | 151 testable audit questions |
| 14 | Audit Checklist – EU AI Act | 106 testable audit questions |
| 15 | Audit Checklist – ISO 42001 | 104 testable audit questions |

### Responsible AI, guardrails & GenAI
| # | Worksheet | Purpose |
|---|-----------|---------|
| 16 | Responsible AI | Principle-level checklist across nine principles |
| 17 | Guardrails – Foundational | Input / model / output / operational guardrails |
| 18 | Guardrails – Technical | 36 distinct technical guardrail controls |
| 19 | GenAI Controls | Prompt injection, jailbreak, RAG grounding, citation, agentic tool permissions |

### Operational governance
| # | Worksheet | Purpose |
|---|-----------|---------|
| 20 | Data Governance | Quality, lineage, metadata, consent, retention, residency |
| 21 | Model Governance | Model cards, registry, validation, drift, retraining, retirement |
| 22 | AI SDLC | Controls by development phase (Intake → Retirement) |
| 23 | Program Management | Steering committee, RACI, RAID, KPIs, exception management |

### Registers & artifacts
| # | Worksheet | Purpose |
|---|-----------|---------|
| 24 | AI Inventory | System catalog: criticality, model version, risk tier, environment, review dates, frameworks |
| 25 | AI Risk Register | Risks with likelihood, impact, inherent/residual rating, owner, status |
| 26 | AI Incident Register | Hallucinations, bias, security, drift, incorrect outputs |
| 27 | Exception Register | Governance exceptions with risk accepted, compensating controls, expiration |
| 28 | Controls Library | Deduplicated master index (preventive/detective/corrective), mapped and cross-referenced |
| 29 | Model Card Template | Per-model documentation template |
| 30 | Evidence Catalog | Requirement → expected evidence → location → owner |
| 31 | Vendor Assessment | AI vendor due diligence (SOC 2, ISO certs, residency, transparency, sub-processors) |
| 32 | RACI Matrix | Responsibility mapping across governance activities |
| 33 | Committee Decision Log | Decisions, risks accepted, exceptions, action items |
| 34 | KPI Catalog | Governance metrics with definitions, targets, owners |
| 35 | Maturity Assessment | 1–5 maturity by domain with auto-derived scoring and radar chart |

### Compliance & sector overlays
| # | Worksheet | Purpose |
|---|-----------|---------|
| 36 | GDPR & Privacy | Privacy checklist mapped to GDPR articles |
| 37 | US State AI Laws | State-law tracker (time-sensitive — re-verify before relying) |
| 38 | Financial Services Pack | Region-neutral: model risk, AML/KYC, trading surveillance, fraud, reporting |
| 39 | Sector – Healthcare | Healthcare-specific AI controls |
| 40 | Sector – Insurance | Insurance-specific AI controls |
| 41 | Sector – Employment | Employment/HR AI controls |
| 42 | Sector – Public Sector | Government/public-sector AI controls |

### Reference
| # | Worksheet | Purpose |
|---|-----------|---------|
| 43 | Framework Reference | Extended legend: NIST functions/categories, ISO clauses, EU AI Act articles, RAI principle definitions, guardrail taxonomy, model-risk concepts |

---

## Key features

- **Framework crosswalk** — one assessment produces answers across NIST, ISO, and EU AI Act simultaneously
- **Three levels of depth** — executive crosswalk → detailed audit checklists → operational registers
- **Live automation** — 127 formulas driving compliance %, maturity scoring, open findings, and coverage roll-ups
- **Executive-ready visuals** — dashboard with KPIs, risk heatmap, open/closed findings, maturity radar, and charts
- **Data validation & conditional formatting** — dropdowns and Red/Amber/Green coding throughout
- **Sector and privacy overlays** — financial services, healthcare, insurance, employment, public sector, GDPR, US state laws
- **Operational artifacts** — inventory, registers, controls library, RACI, decision log, evidence catalog, model cards, vendor assessment

---

## Design principles

- **Substance over volume.** The Master Crosswalk is 72 rows because NIST AI RMF has exactly 72 subcategories — the full set, not a padded number. Domain depth lives in dedicated tabs (data, model, security, monitoring, vendor) rather than by inflating the crosswalk.
- **Deduplicated controls.** The Controls Library is a master index that cross-references where each control is tested in detail — the way GRC platforms separate a control catalog from test procedures — rather than re-listing controls in multiple places.
- **Original content that maps to standards.** Questions and controls are written in original language and reference clause/article numbers for traceability, without reproducing proprietary standard text.

---

## Files in this project

- `README.md` — this documentation
- `Enterprise_AI_Governance_Operating_Framework_AIGOF.xlsx` — the 43-tab toolkit
