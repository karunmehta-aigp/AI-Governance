# AI Governance Technical-Control Mapping Reference

**Project 11 of the AI Governance Portfolio**
**Author:** Karun Mehta · AIGP (AI Governance Professional)
**Version:** 6 (Enterprise, Audit-Ready, Adoption-Ready)

## Disclaimer

This project is a portfolio artefact created for demonstration and educational purposes only. It does not represent the policies, systems, or practices of any real organisation. This is a professional reference and self-assessment instrument, not certification or legal advice. Confirm current framework text and sector-specific obligations against primary sources before relying on this for a real compliance decision.

## What This Is

Where every other project in this portfolio operates at the policy, process, and register level, this project closes the gap between governance paperwork and actual ML/LLM engineering practice. It maps specific, real evaluation and observability tooling — **RAGAS**, **LangSmith**, **Promptfoo**, and a full **LangChain** pipeline — directly to the regulatory and standards requirement each one provides evidence for, alongside a full enterprise governance program layer (inventory, RACI, incidents, KPIs, control register, crosswalk).

This is the artefact to point to when the question is "how does your day-to-day engineering work actually produce the evidence your governance program needs?" — rather than "what does your policy say?"

## Structure — 34 Tabs

| Group | Tabs | Contents |
|---|---|---|
| **Engineering-tool mapping** | 1–4 | RAGAS, LangSmith, Promptfoo metrics/controls mapped to EU AI Act / NIST AI RMF / ISO 42001 / SR 11-7; full 21-component LangChain ingestion-to-continuous-improvement pipeline |
| **Governance program tabs** | 5–9 | Model inventory & risk tiering, approval/change management, third-party AI risk, incident management, monitoring KPIs |
| **Principles & lifecycle** | 10–12 | Responsible AI principles, OWASP LLM Top 10, full AI lifecycle map cross-referencing every other tab |
| **Reference & scoring** | 13–14 | Additional frameworks (ISO 23894, NIST SP 800-53/61, OECD, AI Verify, Colorado AI Act, NYDFS); self-assessed v1→v2 scorecard per tab |
| **Operating artefacts** | 15–22 | RACI matrix, governance committees, documentation inventory, risk tier matrix, control objectives, evidence examples, AI SDLC deliverables, metrics dashboard |
| **Regulatory & advanced** | 23–25 | Regulatory applicability, agentic AI governance, emerging references |
| **Master indices** | 26–28 | Master Control Register (consolidated control index), Crosswalk Matrix (every control cross-referenced to every framework), maturity levels |
| **Operating model** | 29–32 | Operating model overview, control testing matrix, AI policy library, governance roadmap |
| **Reference** | 34 | Glossary |

## Frameworks Referenced

EU AI Act (Regulation (EU) 2024/1689), NIST AI RMF 1.0, ISO/IEC 42001:2023, Federal Reserve SR 11-7 (Model Risk Management), sector-specific regulation (Reg B/ECOA, GDPR, FCRA, GLBA, SOX, UDAAP, HIPAA where directly relevant), plus ISO/IEC 23894, NIST SP 800-53/800-61, OWASP LLM Top 10, OECD AI Principles, Singapore AI Verify, Colorado AI Act, and NYDFS AI guidance.

## How to Use

1. Start with the **Master Control Register** (Tab 26) — the consolidated index of every control, its type, frequency, automation potential, and priority.
2. Use the **Crosswalk Matrix** (Tab 27) to see which frameworks each control satisfies simultaneously.
3. For LLM/GenAI-specific systems, work through Tabs 1–4 to map your actual evaluation tooling (or tooling you plan to adopt) to the evidence it produces.
4. Use Tabs 5–9 to run the operational governance layer — inventory, approvals, vendor risk, incidents, KPIs.
5. Use the **Scorecard** (Tab 14) to track how this instrument itself has matured version over version — a useful pattern to replicate for your own program's self-assessment.

## Relationship to the Rest of This Portfolio

This project is deliberately the most **technical** artefact in the portfolio. Projects 6–9 and Project 10 operate at the governance/compliance layer (policy, risk register, conformity documentation, crosswalks). This project answers the question those projects don't: when an engineering team actually builds and evaluates an LLM application, what specific tool output constitutes the evidence a governance program requires? It is the natural companion piece for demonstrating both AI governance fluency and hands-on familiarity with the current LLM engineering toolchain — relevant for organisations where governance and ML engineering need to speak the same language rather than operate as separate silos.
