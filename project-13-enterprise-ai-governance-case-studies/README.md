# Enterprise AI Governance Case Studies
**Author:** Karun Mehta · AIGP (AI Governance Professional)

An ongoing collection of illustrative enterprise AI governance use cases — each one working through a real governance decision, the alternatives considered and rejected, operational controls, validation testing, framework alignment, and outcomes.

New use cases are added over time as practical, portfolio-ready examples of applying AI governance principles to real-world scenarios across financial services, healthcare, hiring, and other high-risk domains. This project now covers both single-system and multi-agent case studies — see the table below for which is which.

**A note on subject type:** Use Cases 01–06 analyse a fictional organisation and fictional AI systems, built to illustrate governance methodology in depth without referencing any real company. Use Case 07 is different by design — it is an independent, public-evidence assessment of a real, named product, demonstrating the same frameworks applied externally, the way a vendor risk reviewer or procurement team would. The **Subject** column below makes this distinction explicit for every entry.

## Use Cases

| # | Use Case | Sector | Subject | Agentic? | Frameworks Covered |
|---|---|---|---|---|---|
| 1 | [Wealth Management – AI Financial Advisor](./use-case-01-wealth-management-ai-financial-advisor/README.md) | Financial Services | Fictional org (ORG-AI-013) | No — single system, human-in-the-loop | NIST AI RMF, EU AI Act, ISO/IEC 42001, ISO/IEC 27001, GDPR, SEC/FINRA |
| 2 | [Investment Research Agent](./use-case-02-investment-research-agent/README.md) | Investment Management | Fictional org | No — single GenAI+RAG system, analyst-in-the-loop | NIST AI RMF, EU AI Act, GDPR, SEC/FINRA, NYC LL144 |
| 3 | [Autonomous Expense & Reimbursement Reviewer](./use-case-03-expense-reimbursement-agent/README.md) | Finance Operations | Fictional org | Yes — three-agent pipeline, autonomous execution below threshold | NIST AI RMF, internal AI control library |
| 4 | [Loan Pre-Approval Agent](./use-case-04-loan-pre-approval-agent/README.md) | Consumer Lending | Fictional org | Yes — three-agent pipeline, human-in-the-loop by regulatory requirement | EU AI Act, GDPR, ECOA/Regulation B, FCRA |
| 5 | [Agentic Investment Management System](./use-case-05-agentic-investment-management/README.md) | Wealth Management | Fictional org | Yes — 15-component, 9-phase multi-agent orchestration, Critical risk tier | NIST AI RMF, EU AI Act, ISO/IEC 42001, GDPR, SEC/FINRA |
| 6 | [AI Demand Intake, Prioritization & Capacity Orchestration Agent](./use-case-06-ai-demand-intake-prioritization-agent/README.md) | Enterprise AI Portfolio Management | Fictional org | Yes — 4-agent + 2 deterministic-engine pipeline, human-in-the-loop governance gate, Moderate risk tier | NIST AI RMF, EU AI Act, ISO/IEC 42001, GDPR, internal AI control library (A01–A16) |
| 7 | [Public AI Governance Assessment — Microsoft 365 Copilot](./use-case-07-public-ai-governance-assessment/microsoft-copilot-benchmark.md) | Enterprise Productivity / Cross-Sector | **Real, named product** — independent public-evidence review, not affiliated with or reviewed by Microsoft | No — single external product assessment | NIST AI RMF, EU AI Act, ISO/IEC 42001 |

---

*Use Cases 01–06 are illustrative examples created for professional learning and portfolio development. Metrics and scenarios are illustrative and not production data. Use Case 07 is an independent assessment based solely on publicly available materials about a real product; it is not a comprehensive account of that product's internal governance, and time-sensitive facts within it should be independently re-verified before reliance. Nothing in this repository is legal or regulatory advice.*
