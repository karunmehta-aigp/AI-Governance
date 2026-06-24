# AI Governance Law & Standards Reference

> **⚠️ Disclaimer:** This is a fictional case study portfolio created for educational purposes. This specific document, however, is a generic professional reference and is not tied to the fictional organisation used elsewhere in this portfolio. It summarises real, publicly available laws, regulations, and standards as understood at the time of writing (June 2026). It is provided for educational and portfolio purposes only and is **not legal advice**. Laws and standards in this space are evolving rapidly — always verify current obligations and deadlines against primary sources (official gazettes, regulator publications, and standards bodies) before relying on this document for a real compliance decision.

**Document Type:** Standalone professional reference, applicable beyond this portfolio
**Prepared by:** Anju Karun · AIGP (AI Governance Professional)
**Last Updated:** June 2026

---

## Purpose

This document is a working reference of the laws, regulations, and standards that an AI governance professional is expected to know and apply day to day. It is organised the way a practitioner actually uses this knowledge — by jurisdiction and by framework — rather than as a simple alphabetical list, and it is written to be kept current rather than treated as a one-time snapshot: each section notes not just what the rule says, but where it currently stands in terms of implementation and any pending change a governance professional should be tracking.

---

## Part 1 — The EU AI Act (Regulation (EU) 2024/1689)

### 1.1 Status and Timeline (as of June 2026)

The EU AI Act entered into force on 1 August 2024 and is being phased in over several years, not applied all at once. As of this writing, the timeline itself is a live, moving target — important for any governance professional to track actively rather than assume is fixed:

| Provision | Status |
|---|---|
| Prohibited practices (Article 5) and AI literacy obligations | Applicable since 2 February 2025 |
| Governance rules and obligations for general-purpose AI (GPAI) models | Applicable since 2 August 2025 |
| Transparency obligations (Article 50) | Scheduled for 2 August 2026 |
| High-risk AI system obligations (Annex III, use-based) | **Materially delayed.** Under the original text, scheduled for 2 August 2026. Following a political agreement on the "Digital Omnibus on AI" reached 7 May 2026, this has been pushed to **2 December 2027** |
| High-risk AI embedded in regulated products (e.g., machinery, medical devices, toys) | Pushed to **2 August 2028** under the same Digital Omnibus agreement |
| Member State national AI regulatory sandboxes (Article 57) | Deferred by one year, from 2 August 2026 to 2 August 2027 |
| New prohibition: AI-generated non-consensual intimate imagery and CSAM | Takes effect 2 December 2026, added by the Digital Omnibus amendments to Article 5 |

**Practitioner note:** the Digital Omnibus package is a genuine, material amendment to the Act's timeline and a small number of substantive provisions — it is not a renegotiation of the Act's underlying structure or risk tiers. A governance professional should track its final formal adoption (anticipated mid-to-late 2026 at the time of writing) rather than treat either the original or the delayed timeline as settled until the amending instrument is actually published in the Official Journal.

### 1.2 Structure of the Act

The Act is organised into Titles, most relevantly:

- **Title II (Article 5)** — Prohibited AI practices: social scoring, certain forms of biometric categorisation, manipulative or exploitative AI, and (as amended) AI-generated non-consensual intimate imagery and CSAM
- **Title III** — High-risk AI systems, including: Chapter 1 (classification rules, Article 6, and the Annex III list of high-risk use cases); Chapter 2 (requirements for high-risk systems, Articles 8–15); Chapter 3 (obligations of providers, deployers, and other actors, Articles 16–29); Chapter 4 (notifying authorities and conformity assessment bodies); Chapter 5 (conformity assessment and CE marking, Articles 43–49)
- **Title IV (Article 50)** — Transparency obligations for certain AI systems (chatbots, emotion recognition, biometric categorisation, synthetic content)
- **Title V** — Obligations specific to general-purpose AI (GPAI) models, including additional obligations for GPAI models with systemic risk
- **Title VI–VII** — Governance (the EU AI Office, national authorities, the AI Board), and post-market monitoring, information sharing, and market surveillance
- **Title IX (Article 73)** — Serious incident reporting obligations
- **Title XII** — Penalties: up to €35 million or 7% of global annual turnover for prohibited-practice violations; up to €15 million or 3% for other violations

### 1.3 Key Articles a Governance Professional Should Know Cold

| Article | Subject |
|---|---|
| Article 5 | Prohibited practices |
| Article 6 | Classification rules for high-risk AI systems |
| Article 9 | Risk management system |
| Article 10 | Data and data governance |
| Article 11 + Annex IV | Technical documentation |
| Article 12 | Record-keeping (logging) |
| Article 13 | Transparency and provision of information to deployers |
| Article 14 | Human oversight |
| Article 15 | Accuracy, robustness, and cybersecurity |
| Article 17 | Quality management system (provider-side) |
| Article 26 | Obligations of deployers of high-risk AI systems |
| Article 28–29 | Further deployer obligations and the roles of other actors in the AI value chain |
| Article 43 | Conformity assessment procedures |
| Article 47 + Annex V | EU declaration of conformity |
| Article 50 | Transparency obligations for certain AI systems |
| Article 71 | EU database registration for high-risk systems |
| Article 73 | Reporting of serious incidents |

### 1.4 Annex III — The High-Risk Use-Case List

As of the Commission's May 2026 draft guidance, Annex III organises high-risk use cases into eight areas, including (non-exhaustively): biometric identification and categorisation; critical infrastructure; education and vocational training; employment, worker management, and access to self-employment (the category covering recruitment and CV-screening tools); access to essential private and public services, including creditworthiness assessment; law enforcement; migration, asylum, and border control management; and administration of justice and democratic processes.

A practitioner point worth holding onto: the Commission's draft guidance confirms that whether a system "materially influences decision-making" is assessed on the system's actual function and how it is positioned (instructions for use, marketing, technical documentation read together) — a provider cannot avoid high-risk classification merely by disclaiming high-risk use in its terms of service if the product's actual positioning suggests otherwise. The guidance also clarifies that the *presence or absence of human review* does not itself determine whether a system is high-risk; it is only relevant to which obligations apply once a system is already classified as high-risk.

---

## Part 2 — Other Major Jurisdictions and Frameworks

### 2.1 United States — A Sectoral and State-Level Patchwork, Not a Single Federal Law

The United States, unlike the EU, has no single comprehensive federal AI law as of this writing. The governance landscape is instead built from:

- **The NIST AI Risk Management Framework (AI RMF 1.0)** — voluntary, not law, but increasingly referenced by sector regulators (the FTC, CFPB, FDA, SEC, and EEOC have each cited NIST AI RMF principles when assessing whether an organisation's AI practices meet a reasonable standard of care)
- **State-level legislation**, which varies significantly and changes quickly. As one illustrative example: Colorado's original 2024 AI Act (SB 24-205) offered an affirmative legal defence to organisations that could demonstrate alignment with NIST AI RMF or ISO/IEC 42001 — but that law was repealed and replaced (by SB 26-189, signed May 2026) before it ever took effect, and the replacement statute does not carry forward the same framework-alignment safe harbour. This is a useful illustration of a broader practitioner lesson: state AI law in the US is genuinely volatile, and a control built around "compliance with State X's AI law" can become outdated faster than a control built around the more stable underlying frameworks (NIST, ISO) that such laws often reference.
- **Sector-specific guidance**, such as the U.S. Treasury's AI risk management guidance for financial institutions (February 2026), which translates NIST principles into a large set of sector-specific control objectives rather than creating new freestanding obligations.
- **Local and city-level law** addressing specific use cases, such as automated employment decision tool (AEDT) bias audit requirements in some major US cities, which apply narrowly to hiring-related AI specifically.

### 2.2 United Kingdom

The UK has, to date, taken a "pro-innovation," principles-based regulatory approach rather than a single cross-sectoral AI Act, relying on existing sector regulators (the ICO for data protection, the FCA for financial services, and others) to apply AI-specific guidance within their existing remits, supplemented by UK GDPR's automated decision-making provisions.

### 2.3 Other Notable Frameworks

- **China** has its own AI regulatory regime, including specific rules for generative AI services and algorithmic recommendation systems, administered through its cyberspace and market regulators.
- **Canada** has progressed AI-specific legislative proposals (such as the Artificial Intelligence and Data Act, AIDA) through its legislative process, with the framework's final form and timeline subject to ongoing parliamentary process.
- **G7 and international coordination** — the Hiroshima AI Process and related G7 commitments represent voluntary, high-level international coordination rather than binding law, but are relevant context for any organisation operating across G7 jurisdictions.

**Practitioner takeaway:** a genuinely global organisation cannot build a single "AI compliance" programme aimed at one jurisdiction's law. The practical approach — and the one modelled throughout this portfolio — is to build internal controls around the more stable underlying frameworks (NIST AI RMF, ISO/IEC 42001) and then map each specific binding law (the EU AI Act, applicable US state law, etc.) onto that common control base, rather than building a separate compliance programme per jurisdiction from scratch.

---

## Part 3 — NIST AI Risk Management Framework

### 3.1 Core Framework

**NIST AI RMF 1.0**, released January 2023, is voluntary and cross-sectoral. It organises AI risk management into four functions:

| Function | Focus |
|---|---|
| **GOVERN** | Cultivating a risk-aware culture, organisational structures, and policies |
| **MAP** | Establishing context and identifying risks |
| **MEASURE** | Analysing, assessing, and tracking risks |
| **MANAGE** | Prioritising and acting on risks, including incident response |

The full framework is structured into 19 categories and roughly 72 subcategories beneath the four functions, providing granular, checkable actions rather than only high-level principles.

### 3.2 The Generative AI Profile (NIST AI 600-1)

Published July 2024, this is a "profile" — a specific application of the core RMF functions to a particular technology context, in this case generative AI and large language models. It identifies 12 risks unique to or significantly exacerbated by generative AI, including confabulation (hallucination), data privacy leakage, information security risks such as prompt injection, intellectual property concerns, over-reliance by human users, and information integrity risks (including synthetic content misuse). Each risk is mapped back to the four core RMF functions, so an organisation already using the core RMF can layer this profile on top rather than adopting a wholly separate framework for generative AI systems specifically.

### 3.3 Emerging Profiles to Track

NIST continues to extend the RMF through additional profiles rather than rewriting the core framework itself:

- A **Critical Infrastructure Profile** (concept note released April 2026) — tailoring the RMF for critical infrastructure operators, with emphasis on safety, resilience, and continuity of operations
- Emerging **agentic AI** governance work, following NIST's Center for AI Standards and Innovation (CAISI) announcing an AI Agent Standards Initiative in February 2026, addressing risks specific to autonomous, multi-step AI agents that core AI RMF 1.0 and the Generative AI Profile do not fully cover — including the risk of an agent initiating an irreversible action before any human observes an error, and the accountability challenges that arise when an orchestrating agent spawns sub-agents to handle parts of a task. A dedicated AI Agent Interoperability Profile is anticipated later in 2026.

**Practitioner takeaway:** treat the core RMF as the stable foundation and expect new profiles to keep appearing as new categories of AI capability (generative, agentic, embedded-in-critical-infrastructure) mature — building an internal control library mapped to the four core functions, rather than to any single profile, is what keeps an organisation's governance programme from needing to be rebuilt every time NIST issues a new profile.

---

## Part 4 — ISO/IEC AI Standards

### 4.1 ISO/IEC 42001:2023 — AI Management Systems

The world's first certifiable AI management system standard, structured using the same Harmonized Structure (Annex SL) as ISO 27001 and ISO 9001, which is precisely why organisations already certified to those standards tend to find ISO 42001 the most natural standard to add. Its ten clauses follow a Plan-Do-Check-Act cycle:

| Clauses | PDCA Stage | Content |
|---|---|---|
| 1–3 | (Scope, references, definitions) | Not independently auditable requirements |
| 4 — Context of the Organization | Plan | Understanding internal/external context, interested parties, AIMS scope |
| 5 — Leadership | Plan | Top management commitment, the AI policy, roles and responsibilities |
| 6 — Planning | Plan | AI risk assessment, AI system impact assessment, AI objectives |
| 7 — Support | Do | Resources, competence, awareness, communication, documented information |
| 8 — Operation | Do | Operational planning and control across the AI lifecycle — design, development, testing, deployment, decommissioning |
| 9 — Performance Evaluation | Check | Monitoring, measurement, internal audit, management review |
| 10 — Improvement | Act | Nonconformity, corrective action, continual improvement |

All seven of Clauses 4 through 10 are mandatory for certification; an organisation cannot exclude a clause from its AI management system the way it can select which Annex A controls apply based on risk. **Annex A** contains 42 control objectives organised into 9 control categories (A.2 through A.10), covering responsible AI development, deployment, use, monitoring, and improvement — these are risk-selected, meaning an organisation justifies which controls are applicable to its own AI systems via its risk assessment, similar in spirit to ISO 27001's Statement of Applicability.

### 4.2 Companion ISO/IEC Standards Worth Knowing

| Standard | Subject |
|---|---|
| **ISO/IEC 22989** | AI concepts and terminology — the definitional foundation referenced throughout 42001 and most other AI standards |
| **ISO/IEC 23894** | AI risk management — a detailed technical methodology that organisations can use to satisfy 42001's risk assessment requirements (Clauses 6 and 8) in practice |
| **ISO/IEC 38507** | Governance implications of AI for governing bodies (boards, executive leadership) — addresses the strategic oversight layer that complements 42001's operational management-system focus |
| **ISO/IEC 42005** | AI system impact assessment — added as a core standard within the IAPP's own AIGP body of knowledge as of the most recent update, reflecting its growing practical importance specifically for the impact-assessment obligations found in both Article 27 of the EU AI Act and Clause 6.1.4 / 8.4 of ISO 42001 |

### 4.3 How ISO 42001 Relates to Binding Law

A clean way to express this relationship to a non-specialist: ISO 42001 does not, by itself, make an organisation legally compliant with the EU AI Act or any other binding law. What it does is give an organisation an auditable, certifiable *management system* whose normal operation tends to produce most of the artefacts (risk assessments, technical documentation, monitoring records) that binding laws like the EU AI Act separately require. Certification is evidence of a mature *process*; it is not itself a legal compliance certificate, and a governance professional should never represent it as one.

---

## Part 5 — OECD AI Principles

Adopted in 2019 and updated since, the OECD AI Principles are high-level, government-endorsed principles rather than binding law or a certifiable standard. They are organised around five values-based principles (inclusive growth, sustainable development and well-being; human-centred values and fairness; transparency and explainability; robustness, security, and safety; and accountability) plus five recommendations to policymakers. Their practical value to a governance professional is as the shared ethical vocabulary underneath the EU AI Act, NIST AI RMF, and ISO 42001 — each of those three more detailed frameworks can be read as a different jurisdiction's or standards body's attempt to make the same OECD-level values operational and checkable in its own context.

---

## Part 6 — How These Frameworks Relate to Each Other (Summary)

| | Legal status | Certifiable? | Jurisdiction | Specificity |
|---|---|---|---|---|
| **EU AI Act** | Binding law | No certification of the *organisation*; conformity assessment of individual *systems* | EU (and extraterritorial reach for providers placing systems on the EU market) | Very high — numbered articles, specific deadlines, specific penalties |
| **NIST AI RMF** | Voluntary | No | Originated in the US; referenced globally | High — functions, categories, and subcategories, but no certification mechanism |
| **ISO/IEC 42001** | Voluntary (unless mandated by contract or sector regulator) | Yes — full management-system certification | Global | High — auditable clauses and controls |
| **OECD AI Principles** | Non-binding policy principles | No | Adopted by OECD member and partner governments | Low — high-level values |

A governance professional's job is rarely to pick one of these. It is to understand that they answer different questions — *what am I legally required to do* (EU AI Act, applicable national law), *how mature are my actual practices* (NIST AI RMF), *can I prove my management system is sound to an external auditor* (ISO 42001), and *what underlying values is all of this ultimately in service of* (OECD) — and to build one coherent internal control set that can answer all four questions at once, rather than running four separate, redundant compliance exercises.

---

## Keeping This Document Current

This space changes quickly enough that any AI governance reference document has a genuine shelf life. At minimum, a governance professional should re-check:

- The EU AI Act's implementation timeline (currently in flux via the Digital Omnibus process) at least quarterly
- The IAPP AIGP Body of Knowledge version number whenever preparing any certification-aligned materials, since the BoK itself is revised on a regular cycle
- NIST's published profiles list, since new profiles are being added to extend the core RMF to new AI capability categories (generative, agentic, sector-specific) rather than through a full RMF rewrite
- Any jurisdiction-specific state or national legislation relevant to the organisation's specific footprint, given how quickly state-level law in particular can change (as the Colorado example in Part 2.1 illustrates)

---

*This document is part of the Reference Library accompanying this AI Governance Portfolio. It is maintained alongside the AIGP Knowledge Map and the Regulatory and Standards Crosswalk, and — unlike those two documents — is written to stand on its own as a general-purpose professional reference, independent of this portfolio's fictional case study.*

---

*Author: Anju Karun · AIGP (AI Governance Professional)*
