# AI Governance Toolkit — Core + Industry Overlays

**Project 6 of the AI Governance Portfolio**
**Author:** Anju K. · AIGP (AI Governance Professional)

## Disclaimer

This project is a portfolio artefact created for demonstration and educational purposes only. It does not represent the policies, systems, or practices of any real organisation. All organisations referenced are generic ("the organisation"); all vendors are Vendor A/B/C; all systems use the fictional numbered identifier scheme ORG-AI-0XX. Nothing in this toolkit constitutes legal advice — it should not be relied upon for actual regulatory compliance without review by qualified counsel and subject-matter experts.

## What This Is

A complete, ready-to-use foundation for standing up an AI governance program, plus four industry-specific overlays that layer sector risk taxonomy, regulatory anchors, and worked use cases on top of the core.

## Structure

```
project-06-ai-governance-toolkit/
├── README.md
├── core/
│   ├── 01-AI-Governance-Framework.md
│   ├── 02-AI-Policy-Master.md
│   ├── 03-AI-Governance-Committee-Charter.md
│   ├── 04-AI-System-Inventory-Template.xlsx
│   ├── 05-AI-Use-Case-Assessment-Form.md
│   ├── 06-AI-Governance-Maturity-Assessment.xlsx
│   ├── 07-Implementation-Roadmap.md
│   ├── 07-Implementation-Roadmap.xlsx
│   └── 08-Quarterly-Governance-Review-Template.md
└── overlays/
    ├── financial-services/
    │   ├── AIGV-FIN-001-Sector-Overlay.md
    │   └── AIGV-FIN-001-Use-Case-Register.xlsx
    ├── healthcare/
    │   ├── AIGV-HLC-001-Sector-Overlay.md
    │   └── AIGV-HLC-001-Use-Case-Register.xlsx
    ├── hr-recruitment/
    │   ├── AIGV-HR-001-Sector-Overlay.md
    │   └── AIGV-HR-001-Use-Case-Register.xlsx
    └── public-sector/
        ├── AIGV-PUB-001-Sector-Overlay.md
        └── AIGV-PUB-001-Use-Case-Register.xlsx
```

Narrative and template documents are markdown for in-repo readability; structured/working data (inventories, scored assessments, task trackers) stays in `.xlsx`, matching the convention used in `project-01-ai-system-inventory`.

## Core Toolkit (8 artefacts)

| # | Artefact | Format | Purpose |
|---|---|---|---|
| 1 | AI Governance Framework | md | Principles, risk tiering, lifecycle controls, roles — mapped to EU AI Act, NIST AI RMF, ISO/IEC 42001, OECD |
| 2 | AI Policy (Master) | md | Mandatory organisation-wide requirements, prohibited uses, generative AI usage rules |
| 3 | AI Governance Committee Charter | md | Membership, decision rights, operating rhythm |
| 4 | AI System Inventory Template | xlsx | Live register with risk tier, owners, DPIA flags, summary dashboard |
| 5 | AI Use Case Assessment Form | md | Intake form completed before any new system is deployed |
| 6 | AI Governance Maturity Assessment | xlsx | 20 sub-capabilities across 10 domains, scored 1–5, radar chart |
| 7 | Implementation Roadmap | md + xlsx | 4-phase, 26-week rollout plan with a live task tracker and progress dashboard |
| 8 | Quarterly Governance Review Template | md | Recurring review form for high/limited-risk systems |

## Industry Overlays (4 verticals)

Each overlay supplements — does not replace — the core toolkit with sector risk taxonomy, regulatory anchors specific to that sector, 3 worked use case examples, and sector-specific control considerations.

- **Financial Services** — credit decisioning, AML monitoring, algorithmic trading, insurance pricing
- **Healthcare & Life Sciences** — clinical decision support, diagnostic imaging triage, medical-device/AI Act overlap
- **HR & Recruitment** — screening, performance scoring, video interview analysis, bias-audit obligations
- **Public Sector** — benefits eligibility, resource allocation, due process and public transparency obligations

## How to Use

1. Start with the Core Toolkit — approve the Framework and Policy, stand up the Committee, populate the Inventory.
2. Layer on the relevant industry overlay(s) for your sector once the core is in place.
3. Use the Maturity Assessment to baseline where you are, and the Implementation Roadmap to sequence the build-out.
4. Run the Quarterly Review cycle once high-risk systems are in production.

## Regulatory Frameworks Referenced

EU AI Act (including the May 2026 Digital Omnibus amendment extending Annex III high-risk deadlines to December 2027), NIST AI Risk Management Framework 1.0, ISO/IEC 42001, OECD AI Principles. For article/clause-level detail, see `regulatory-standards-crosswalk-detailed.md` in the Reference Library.
