## End-to-End Case Study: `ORG-AI-011` From Idea to Lessons Learned

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer. This is the narrative thread; every stage below links to the reference document that actually governs it.

---

### Why This Document Exists

Every other document in this project is a reference artefact — a policy, a control, a template. None of them, read individually, show what it actually feels like to take one system through the whole framework, including the part where something goes wrong. This document is that walkthrough: one system, all 12 lifecycle stages, one real incident, told as a story rather than a schema.

---

### 1. Business Request

Finance Operations raises a request: expense claims under a defined value are taking an average of 4 business days to reimburse, almost entirely due to manual review queue backlog. They propose an automated reviewer. Product frames it as an agentic system, not a simple rules engine, because the claim-matching logic (does this receipt actually support this claim category) needs judgment a fixed rule set can't cover.

*→ Governed by: [Agent Lifecycle](../03-agent-lifecycle/agent-lifecycle.md) Stage 1, [AI Governance Operating Model](../02-operating-model/ai-governance-operating-model.md)*

### 2. Inventory Registration & Business Approval

The request is logged, scoped as `ORG-AI-011`, and the Third-Party AI Governance vendor assessment on the foundation model provider is completed before anything else proceeds — the assessment surfaces the model vendor's 30-day upgrade notice period, which later turns out to matter (see section 11).

*→ Governed by: [Agent Inventory Register](../05-control-library/agent-inventory-register.md), [Third-Party AI Governance](../06-runtime-governance/third-party-ai-governance.md) — [completed vendor assessment example](../09-examples/completed-vendor-assessment-example.md)*

### 3. Risk Assessment

Base use-case risk (internal financial operations, no customer-facing decision) scores Low. The Risk Committee applies the autonomy multiplier from the initially-proposed Full-autonomy design — which pushes the score into Moderate territory and triggers a design conversation, not just a score.

*→ Governed by: [Risk Classification Addendum](../04-risk-framework/agentic-risk-classification-addendum.md) — [completed risk assessment example](../09-examples/completed-risk-assessment-example.md)*

### 4. Architecture Review

Engineering's initial design proposes one shared service credential across all three agents, for simplicity. The Architecture Review Board rejects it — this violates least-privilege scoping and would mean a single credential compromise affects the whole pipeline. Redesigned with one scoped identity per agent.

*→ Governed by: [Agent Identity Governance](../05-control-library/agent-identity-governance.md), `AI-CNTRL-A01`*

### 5. Security Review

Red team testing against the OWASP multi-agent taxonomy finds that a claimant could, in the original prompt design, embed instructions inside a claim description that the Policy-Compliance Agent partially followed as if they were policy updates. Prompt redesigned to structurally separate trusted policy content from untrusted claim content.

*→ Governed by: [Prompt Governance](../06-runtime-governance/prompt-governance.md), Compliance Crosswalk's OWASP row*

### 6. Prompt Testing & Red Team

Full test suite run against the redesigned prompt and identity scheme; injection-resistance re-verified against the finding from Security Review. Findings closed.

*→ Governed by: [Agent Lifecycle](../03-agent-lifecycle/agent-lifecycle.md) Stage 6, Compliance Crosswalk's OWASP row*

### 7. Human Approval

Given the Moderate risk score from Stage 3, this is a Direct decision. Committee approves with the conditions in the completed risk assessment example: reviewable threshold, 90-day kill-switch testing, full re-test before any threshold increase.

*→ Governed by: [Agentic AI System Charter](../01-governance-charter/agentic-ai-system-charter.md) §3*

### 8-9. Deployment & Post-Production Validation

System goes live. Two weeks of Post-Production Validation confirm behaviour matches pre-deployment testing. Runtime Monitoring begins.

*→ Governed by: [Agent Lifecycle](../03-agent-lifecycle/agent-lifecycle.md) Stages 9–10*

### 10. Runtime Monitoring — Business as Usual

For ten weeks, the system operates within every KPI threshold. Then, on 2026-07-14, a vendor-side model upgrade — received within the contractual 30-day notice window flagged back in Stage 2 — subtly changes the model's behaviour under a specific class of ambiguous claims.

*→ Governed by: [Runtime Governance](../06-runtime-governance/runtime-governance.md), [KPI Catalog](../06-runtime-governance/ai-governance-kpi-catalog.md)*

### 11. Incident Occurs, Kill Switch Considered, Root Cause Found

The fabrication-rate metric crosses threshold after three claims are approved citing a policy clause that doesn't exist. The Disbursement Agent is suspended within 6 minutes of detection. Investigation traces the cause to the model upgrade, not a prompt or credential failure — the exact reason Stage 2's vendor assessment mattered.

*→ Governed by: [AI Incident Response Playbook](../07-ai-assurance/ai-incident-response-playbook.md) — [full completed incident report](../09-examples/completed-incident-report-example.md)*

### 12. Corrective Action & Audit Evidence

Model rolled back to the prior pinned version. Regression suite expanded. The full action trace, prompt version, and model version snapshots taken during containment become the evidence base — retrievable specifically because the [Evidence Library](../07-ai-assurance/evidence-library.md) already indexed where each of those artefacts would live, before the incident happened.

*→ Governed by: [Model Governance](../06-runtime-governance/model-governance.md), [Evidence Library](../07-ai-assurance/evidence-library.md)*

### 13. Lessons Learned & Framework Update

Two changes come out of this, and both are logged through [Framework Change Control](../07-ai-assurance/framework-change-control.md) rather than made silently:
- `AI-CNTRL-A15`'s runtime drift threshold is tightened to flag policy-citation anomalies specifically
- Model Governance's regression suite update becomes a standing requirement after *any* vendor upgrade, not a spot-check

The next scheduled [Runtime Review](../09-examples/completed-runtime-review-example.md) confirms recovery, and the system returns to standard monitoring cadence one cycle later than usual, per the Committee's own elevated-monitoring decision.

*→ Governed by: [AI Assurance Framework](../07-ai-assurance/ai-assurance-framework.md)'s Improve stage — this is the Level 5 maturity behaviour the Assurance Framework document describes in the abstract, shown here actually happening*

---

### Why This Story Matters More Than Any Single Document

Nothing in this incident was caught by a document. It was caught by a metric threshold that existed because the KPI Catalog defined it, contained by a kill-switch design that existed because Identity Governance required scoped credentials, root-caused quickly because the Evidence Library had already mapped where the evidence would be, and closed out through a change-control process that turned a bad afternoon into two permanent improvements instead of a near-miss nobody remembers by December. That chain — not any individual policy — is what "governance as an operating model" actually means.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
