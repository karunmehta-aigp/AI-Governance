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
Corrective: analyst escalation workflow, correct & retract process, model rollback plan,
