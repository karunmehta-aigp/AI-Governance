<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/25539ef5-b640-42e8-9394-8f54dec7b5ee" />

AI Governance in Practice
Enterprise AI Governance – Investment Research Agent
Investment Management

Author:
Karun Mehta · AIGP (AI Governance Professional)

Business Context

Financial institution deploying a GenAI + RAG research summarization tool for its investment research team.
AI reads internal research, filings, news, market data, and client holdings, then produces summaries and insights for ~220 analysts (~3,200 briefs/month) globally.
Objective: Cut research turnaround time while keeping analysts — not the model — accountable for what goes into client-facing investment decisions.

Governance Challenge

Prevent factual errors ("hallucinations") in AI-generated research from reaching analysts and, downstream, clients.
Ensure research outputs remain fair, balanced, and not misleading, as SEC/FINRA requires of all investment research regardless of who or what produced it.
Close a live gap: the system had been in production 10 months with no performance or drift monitoring, no bias testing, and no formal risk assessment before this review.

Governance Decision

Evaluated the system's existing informal governance against a formal risk assessment before deciding how to proceed.

Rejected

Continued ad-hoc review with no formal risk assessment or bias testing (the state the system was found in — unacceptable for a production high-risk system).
Full Go with no conditions (8 of 50 test prompts produced hallucinated financial facts — too high a rate to approve without remediation).

Selected

Conditional Go — analyst-in-the-loop model, formalized rather than ad hoc.
Outputs influence investment decisions but do not autonomously drive them; go-live is contingent on closing all Critical findings and completing High-risk controls first.

Operational Governance Controls

Preventive: prompt guardrails & content filters, source allow-list for RAG, data minimization & redaction, analyst training on AI use, change management for model updates.
Detective: output factuality testing, bias testing (demographic parity), prompt injection tests, data leakage scanning, human review sampling.
Corrective: analyst escalation workflow, correct & retract process, model rollback plan, incident response runbook, vendor escalation & SLAs.

AI Validation & Testing

Factuality testing — 8 of 50 test prompts produced hallucinated financial facts; rated Critical and gated go-live.
Bias and fairness evaluation — demographic parity testing identified as a gap; no baseline existed prior to this assessment.
Data leakage and prompt-injection testing — no controls implemented or tested in production prior to this review.
Citation and traceability testing — outputs lacked source citations, creating both a factuality risk and an SEC/FINRA recordkeeping gap.
Vendor dependency testing — a prior (2024) vendor model update was found to have changed output and caused policy misrepresentation, establishing precedent for ongoing vendor-update monitoring.

Framework & Regulatory Alignment

NIST AI RMF — Map • Measure • Manage • Govern, used as the assessment method end-to-end.
EU AI Act — Annex III high-risk classification (investment research used in investment decisions); obligations deferred to 2 Dec 2027 under the Amended Digital Omnibus, but the system is being designed to Articles 9, 10, 13, 14, 26, and 43 now rather than waiting for the deadline.
GDPR — Article 22 (no solely automated decisions with legal or similarly significant effect without human intervention); DPIA required under Article 35.
SEC / FINRA — research that influences investment decisions must be fair, balanced, and not misleading, with recordkeeping obligations.
NYC Local Law 144 — annual bias audit and public summary apply where outputs touch hiring-related research or comparisons.
Colorado AI Act (SB 26-189) — watch item; notice and explanation obligations begin 1 Jan 2027 for covered decisions.

Key Trade-offs

Research speed vs. factual reliability.
Analyst productivity vs. mandatory human review of AI-influenced research.
Vendor-model flexibility vs. governance control over unannounced model changes.
Regulatory readiness now vs. deferred EU AI Act enforcement dates.

Decision

We accepted a remediation delay — no full production Go until factuality guardrails, bias testing, and leakage controls were in place — in exchange for a defensible SEC/FINRA and EU AI Act posture, rather than approving a system already shown to hallucinate financial facts in 16% of test prompts.

Business Outcomes (Illustrative Example)

Formal risk register replaces ad-hoc review, with 1 Critical and 4 High findings tracked to named owners and target dates.
Conditional Go structure keeps the research pipeline moving while critical remediation is completed on a defined timeline (05–26 Sep 2026).
Quarterly reassessment cadence established (next full review 15 Oct 2026), closing the monitoring gap that existed at intake.
Illustrative observation: weekly factuality testing and monthly bias testing were adopted as ongoing KPIs rather than one-time deployment gates, so drift is caught between formal reviews rather than only at them.

Key Takeaway

A GenAI research tool doesn't need to be autonomous to be high-risk — SEC/FINRA's fair-and-balanced standard and the EU AI Act's Annex III classification both attach to what the output is used for, not how much autonomy the system has. This use case demonstrates governing a single-system, analyst-in-the-loop GenAI+RAG tool against the same NIST AI RMF / EU AI Act discipline applied elsewhere in this portfolio, while showing what a Conditional Go decision looks like when Critical findings exist but the business case for continued operation is strong enough to justify a time-bound remediation path instead of a hard stop.

Disclaimer

This is an illustrative AI Governance use case created for professional learning, portfolio development, and discussion. Any scenarios, metrics, or examples are illustrative and intended to demonstrate governance design concepts rather than represent production results. This material is not legal or regulatory advice. Organizations should consult their legal, compliance, risk, and information security teams when designing or implementing AI governance programs.
