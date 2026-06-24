# AI Governance Portfolio

**5 Practical Projects Demonstrating Operational AI Governance**

> *"A classification spreadsheet is not a governance programme. Knowing the difference is."*

---

> **⚠️ Disclaimer:** This entire repository is a fictional case study created for portfolio and educational purposes. The organisation, all AI systems, vendors, and personnel referenced throughout are entirely fictional. No real entity is described, referenced, or disclosed at any point in this material.

This repository contains five structured projects that translate AI governance frameworks into practical, defensible artefacts. Each project simulates work that organisations are actively trying to do — and frequently struggling with — in 2026, built around a single fictional organisation and a single, deliberately interconnected set of AI systems, so that the portfolio reads as one coherent governance programme rather than five disconnected exercises.

The projects draw on two primary frameworks throughout:

- **EU AI Act** — risk-based classification, high-risk system obligations, and conformity requirements
- **NIST AI Risk Management Framework (AI RMF)** — the four core functions: Govern, Map, Measure, Manage

---

## Repository Structure

```
.
├── project-01-ai-system-inventory/        # Inventory & EU AI Act classification engine
├── project-02-risk-assessment/            # Structured risk assessment & governance memo
├── project-03-responsible-ai-policy/      # Policy, principles, and operating model
├── project-04-incident-response/          # AI failure scenario, timeline, and root cause analysis
├── project-05-high-risk-documentation/    # EU AI Act conformity documentation pack
└── README.md                              # This file
```

---

## The Narrative Thread

Every project in this portfolio operates on the same fictional organisation and the same AI system inventory, established in Project 1 (systems `ORG-AI-001` through `ORG-AI-010`). This is a deliberate design choice: real governance work is never a series of unrelated exercises — a risk assessment references a classification that was already made, an incident response draws on a system that was already known to have gaps, and a conformity pack closes out remediation that an earlier project first identified. The portfolio is built to demonstrate that connected reasoning explicitly, not just to produce five separate-looking documents.

A short version of the thread:

- **Project 1** inventories ten AI systems and classifies four of them as High Risk, including a credit decisioning system, a CV screening tool, an AML transaction monitor, and a voice biometric authenticator — and finds that the highest-risk systems also have the *lowest* governance maturity.
- **Project 2** takes the AML transaction monitor — a system whose classification was itself left ambiguous in Project 1 — and shows what risk analysis looks like when the legal question and the operational gaps have to be worked through in parallel, not sequentially.
- **Project 3** builds the governance programme that should have existed before any of this — a policy, a review process, and an operating model — directly informed by the specific failure patterns (oversight that exists on paper but not in practice; vendor opacity) that Projects 1 and 2 already surfaced.
- **Project 4** simulates the credit decisioning system's bias finally being caught — not by a regulator or a journalist, but by the bias audit the Project 3 governance programme made standard practice — and walks through detection, containment, regulatory disclosure, remediation, and a root cause analysis that traces the failure back to the absence of governance, not just to one bad feature.
- **Project 5** documents two contrasting conformity scenarios: the voice biometric system's conformity pack, built honestly around gaps still being remediated, and a brand-new replacement recruitment system, procured and documented correctly from day one specifically because the original CV screening tool's failures were so well understood by that point.

---

## The Five Projects

| # | Project | Primary Framework | Key Artefact |
|---|---|---|---|
| 1 | [AI System Inventory & EU AI Act Classification Engine](./project-01-ai-system-inventory/) | EU AI Act · NIST AI RMF | Inventory (CSV + Excel) + classification rationale |
| 2 | [AI Risk Assessment & Governance Review Pack](./project-02-risk-assessment/) | NIST AI RMF (Map, Measure) | Risk register + executive governance memo |
| 3 | [Responsible AI Policy & Operating Model](./project-03-responsible-ai-policy/) | NIST AI RMF (Govern) | Policy, review process, and operating model |
| 4 | [AI Incident Response & Regulatory Escalation](./project-04-incident-response/) | NIST AI RMF (Manage) · EU AI Act | Incident timeline + root cause analysis |
| 5 | [High-Risk AI Documentation & Conformity Pack](./project-05-high-risk-documentation/) | EU AI Act (Articles 9–17) | Full conformity documentation, two systems |

---

## How to Use This Repository

Each project folder contains:

- **`README.md`** — scenario context, objectives, key design decisions, and how the project's artefacts connect both to the underlying frameworks and to the rest of the portfolio
- **Artefacts** — the actual governance documents themselves: inventories, risk registers, policies, incident records, and conformity documentation

These are designed to be read in order — each project builds on the governance maturity and the specific findings established by the one before it — but every project is also fully standalone. If you are preparing for a specific interview or assessing fit for a specific role, navigate directly to the project most relevant to that conversation; each README explains its scenario in full without assuming you have read the others.

---

## Framework Quick Reference

### EU AI Act — Risk Tiers

| Tier | Description | Examples |
|---|---|---|
| Unacceptable | Prohibited outright | Social scoring, real-time biometric mass surveillance |
| High-Risk | Strict pre- and post-deployment obligations | Credit decisioning, recruitment screening, biometric verification |
| Limited Risk | Transparency obligations | Chatbots, synthetic/AI-generated content |
| Minimal Risk | No AI Act–specific obligations | Internal analytics, regulatory monitoring tools |

### NIST AI RMF — Core Functions

| Function | Purpose |
|---|---|
| **GOVERN** | Establish accountability structures, policies, and culture |
| **MAP** | Identify and contextualise AI risks |
| **MEASURE** | Analyse and assess AI risks rigorously and quantitatively |
| **MANAGE** | Prioritise and treat risks; respond to and recover from incidents |

---

## What This Portfolio Is Designed to Demonstrate

Beyond the specific skills listed in each project's own README, the portfolio as a whole is built to show:

- That AI governance competence is **operational**, not theoretical — every artefact here is the kind of document a risk, legal, compliance, or engineering team would actually need to act on, not a slide of abstract principles
- That **classification, risk assessment, policy, incident response, and conformity documentation are not five separate disciplines** but five connected views of the same underlying governance responsibility, which is why the same systems and the same findings recur deliberately across projects
- That **honest documentation of an unresolved gap is more valuable, and more credible, than documentation that asserts a premature compliance position** — several artefacts in this portfolio explicitly state that a requirement is not yet met, with a remediation date attached, rather than rounding up to "compliant"
- That **proportionality is the organising discipline of good governance** — minimal-risk systems throughout this portfolio are governed lightly and explicitly are not over-engineered, while high-risk systems receive the full weight of scrutiny the framework intends

---

## About

Built to demonstrate that AI governance competence is operational, not theoretical — and that a governance programme should be judged by whether its artefacts could actually survive contact with a regulator, an auditor, or a board, not by whether they look complete on the page.

**Author:** Anju Karun · AIGP (AI Governance Professional)
