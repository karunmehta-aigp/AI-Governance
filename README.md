## The Narrative Thread (Projects 1–5)

Every narrative project in this portfolio operates on the same fictional organisation and the same AI system inventory, established in Project 1 (systems `ORG-AI-001` through `ORG-AI-010`). This is a deliberate design choice: real governance work is never a series of unrelated exercises — a risk assessment references a classification that was already made, an incident response draws on a system that was already known to have gaps, and a conformity pack closes out remediation that an earlier project first identified. The portfolio is built to demonstrate that connected reasoning explicitly, not just to produce five separate-looking documents.

A short version of the thread:

- **Project 1** inventories ten AI systems and classifies four of them as High Risk, including a credit decisioning system, a CV screening tool, an AML transaction monitor, and a voice biometric authenticator — and finds that the highest-risk systems also have the *lowest* governance maturity.
- **Project 2** takes the AML transaction monitor — a system whose classification was itself left ambiguous in Project 1 — and shows what risk analysis looks like when the legal question and the operational gaps have to be worked through in parallel, not sequentially.
- **Project 3** builds the governance programme that should have existed before any of this — a policy, a review process, and an operating model — directly informed by the specific failure patterns (oversight that exists on paper but not in practice; vendor opacity) that Projects 1 and 2 already surfaced.
- **Project 4** simulates the credit decisioning system's bias finally being caught — not by a regulator or a journalist, but by the bias audit the Project 3 governance programme made standard practice — and walks through detection, containment, regulatory disclosure, remediation, and a root cause analysis that traces the failure back to the absence of governance, not just to one bad feature.
- **Project 5** documents two contrasting conformity scenarios: the voice biometric system's conformity pack, built honestly around gaps still being remediated, and a brand-new replacement recruitment system, procured and documented correctly from day one specifically because the original CV screening tool's failures were so well understood by that point.

---

## The Toolkits (Projects 6–11)

Projects 6–11 step outside the fictional narrative deliberately. Where Projects 1–5 show governance applied to one organisation's specific systems, Projects 6–11 are **generic, industry-agnostic, reusable toolkits and instruments** — the kind of starting kit an organisation would stand up *before* any of the Project 1–5 work becomes possible.

Projects 6–9 are **focused toolkits**, each going deep on a single discipline or framework. Project 10 is the **consolidated counterpart** — a single enterprise operating framework that brings the crosswalk, controls, registers, and operating model together into one workbook. Project 11 is the **technical counterpart** — it closes the gap between governance paperwork and actual ML/LLM engineering practice, mapping real evaluation tooling directly to the evidence it produces. Read 6–9 to see each discipline in isolation; read 10 to see how they combine into one governance programme; read 11 to see how that programme's evidence requirements actually get satisfied by day-to-day engineering work.

| Project | Toolkit | Focus |
|---|---|---|
| 6 | AI Governance Toolkit | Foundational program: Framework, Policy, Committee Charter, Inventory, Use Case Assessment, Maturity Assessment, Roadmap, Quarterly Review — plus 4 industry overlays (Financial Services, Healthcare, HR & Recruitment, Public Sector) |
| 7 | EU AI Act Compliance Toolkit | Applicability assessment through risk classification, conformity documentation, human oversight, post-market monitoring, and incident reporting |
| 8 | ISO/IEC 42001 Toolkit | Gap assessment, AIMS policy, context worksheet, risk & opportunity register, objectives/KPIs, internal audit, management review, corrective action |
| 9 | AI Risk Assessment Toolkit | Risk methodology, risk register, scoring matrix, treatment plans, vendor risk assessment, incident log, live monitoring dashboard |
| 10 | Enterprise AI Governance Operating Framework (AIGOF) | A single 43-worksheet workbook consolidating the above into one operating framework: a master crosswalk across NIST AI RMF, ISO/IEC 42001 & the EU AI Act, detailed audit checklists, controls library, registers (risk, incident, exception), executive dashboard, maturity scoring, and sector/privacy overlays |
| 11 | AI Governance Technical-Control Mapping Reference | Maps real LLM engineering tooling — RAGAS, LangSmith, Promptfoo, a full LangChain pipeline — directly to the EU AI Act / NIST AI RMF / ISO 42001 / SR 11-7 requirement each one evidences, alongside a full enterprise governance program layer (inventory, RACI, incidents, KPIs, master control register, crosswalk) |

Full details for each: see that project's own `README.md`.

---

## The Projects

| # | Project | Primary Framework | Key Artefact |
|---|---|---|---|
| 1 | [AI System Inventory & EU AI Act Classification Engine](./project-01-ai-system-inventory/) | EU AI Act · NIST AI RMF | Inventory (CSV + Excel) + classification rationale |
| 2 | [AI Risk Assessment & Governance Review Pack](./project-02-risk-assessment/) | NIST AI RMF (Map, Measure) | Risk register + executive governance memo |
| 3 | [Responsible AI Policy & Operating Model](./project-03-responsible-ai-policy/) | NIST AI RMF (Govern) | Policy, review process, and operating model |
| 4 | [AI Incident Response & Regulatory Escalation](./project-04-incident-response/) | NIST AI RMF (Manage) · EU AI Act | Incident timeline + root cause analysis |
| 5 | [High-Risk AI Documentation & Conformity Pack](./project-05-high-risk-documentation/) | EU AI Act (Articles 9–17) | Full conformity documentation, two systems |
| 6 | [AI Governance Toolkit](./project-06-ai-governance-toolkit/) | EU AI Act · NIST AI RMF · ISO/IEC 42001 · OECD | Reusable core toolkit + 4 sector overlays |
| 7 | [EU AI Act Compliance Toolkit](./project-07-eu-ai-act-compliance-toolkit/) | EU AI Act | Applicability through conformity documentation |
| 8 | [ISO/IEC 42001 Toolkit](./project-08-iso-42001-toolkit/) | ISO/IEC 42001 | Full AIMS resource package |
| 9 | [AI Risk Assessment Toolkit](./project-09-ai-risk-assessment-toolkit/) | NIST AI RMF · Internal risk practice | Risk register, scoring, dashboard |
| 10 | [Enterprise AI Governance Operating Framework (AIGOF)](./project-10-enterprise-governance-toolkit/) | EU AI Act · NIST AI RMF · ISO/IEC 42001 | 43-worksheet consolidated operating framework |
| 11 | [AI Governance Technical-Control Mapping Reference](./project-11-ai-governance-technical-control-mapping/) | EU AI Act · NIST AI RMF · ISO/IEC 42001 · SR 11-7 | LLM engineering-tool-to-regulatory-evidence crosswalk |

---

## Reference Library

Sitting outside all eleven numbered projects, the **Reference Library** organises and cross-references the whole portfolio against external standards:

| File | Description |
|---|---|
| `aigp-knowledge-map.md` | Maps every artefact in this portfolio explicitly to the four domains of the IAPP AIGP Body of Knowledge (v2.1) |
| `regulatory-standards-crosswalk.md` | A side-by-side summary crosswalk of the EU AI Act, NIST AI RMF, ISO/IEC 42001, and OECD AI Principles, tied to Projects 1–5 |
| `regulatory-standards-crosswalk-project6-addendum.md` | The same crosswalk structure extended to Project 6's reusable templates |
| `regulatory-standards-crosswalk-detailed.md` | Article- and clause-level detail behind the summary crosswalk, for citation in technical documentation or audit responses |
| `ai-law-and-standards-reference.md` | A standalone reference covering the EU AI Act's structure and implementation timeline, the US/UK/global regulatory landscape, NIST AI RMF, the ISO/IEC AI standards family, and the OECD AI Principles |

---

## How to Use This Repository

Each project folder contains:

- **`README.md`** — scenario context, objectives, key design decisions, and how the project's artefacts connect both to the underlying frameworks and to the rest of the portfolio
- **Artefacts** — the actual governance documents themselves: inventories, risk registers, policies, incident records, conformity documentation, and (for Projects 6–11) reusable templates and instruments

Projects 1–5 are designed to be read in order — each builds on the governance maturity and specific findings established by the one before it — but every project is also fully standalone. Projects 6–11 and the Reference Library can be used independently of the narrative at any time. If you are preparing for a specific interview or assessing fit for a specific role, navigate directly to the project most relevant to that conversation; each README explains its scenario in full without assuming you have read the others.

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
- That **classification, risk assessment, policy, incident response, and conformity documentation are not five separate disciplines** but connected views of the same underlying governance responsibility, which is why the same systems and the same findings recur deliberately across Projects 1–5
- That **honest documentation of an unresolved gap is more valuable, and more credible, than documentation that asserts a premature compliance position** — several artefacts in this portfolio explicitly state that a requirement is not yet met, with a remediation date attached, rather than rounding up to "compliant"
- That **proportionality is the organising discipline of good governance** — minimal-risk systems throughout this portfolio are governed lightly and explicitly are not over-engineered, while high-risk systems receive the full weight of scrutiny the framework intends
- That governance capability is **portable** — Projects 6–11 show the same disciplines demonstrated narratively in Projects 1–5 distilled into reusable foundations any organisation, in any sector, could stand up from day one
- That governance and engineering **can and should share a common evidence language** — Project 11 shows the same regulatory obligations Projects 6–10 document at the policy level, satisfied directly by specific, real evaluation tooling output

---

## About

Built to demonstrate that AI governance competence is operational, not theoretical — and that a governance programme should be judged by whether its artefacts could actually survive contact with a regulator, an auditor, or a board, not by whether they look complete on the page.

**Author:** Karun · AIGP (AI Governance Professional)
