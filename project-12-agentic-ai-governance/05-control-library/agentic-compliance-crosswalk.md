## Agentic AI Compliance Crosswalk

*Maps this project's controls to the frameworks a hiring manager or auditor would actually check against.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why a Separate Crosswalk for Agentic Controls

The Reference Library's existing crosswalks (`regulatory-standards-crosswalk.md` and its detailed counterpart) map Projects 1–5 to NIST AI RMF, the EU AI Act, ISO/IEC 42001, and OECD AI Principles. None of those four were written with autonomous action-taking as the subject, which is why this project adds two frameworks written specifically for that gap — the OWASP LLM/Agentic threat taxonomy and MITRE ATLAS — alongside the original four.

### Crosswalk

| This Project's Control | NIST AI RMF | EU AI Act | ISO/IEC 42001 | OWASP LLM Top 10 / Agentic Threats | MITRE ATLAS | GDPR | SOC 2 / NIST 800-53 |
|---|---|---|---|---|---|---|---|
| Agent Inventory Register | MAP 1.1 (context) | Art. 71 (EU database registration, for in-scope systems) | Clause 8.2 (AI system inventory) | — | Reconnaissance (asset visibility) | Art. 30 (records of processing, where agents process personal data) | CC7.1 asset inventory / NIST 800-53 CM-8 |
| Autonomy Multiplier (Risk Addendum) | MEASURE 2.1–2.3 | Annex III risk classification (use-case based; this control extends it) | Clause 6.1 (risk assessment) | — | — | Art. 35 (DPIA trigger for high-risk processing) | NIST 800-53 RA-3 |
| Least-Privilege Credential Scoping | GOVERN 1.5 | Art. 15 (accuracy, robustness, cybersecurity) | Annex A.6 (resource controls) | LLM06: Excessive Agency | Privilege Escalation (AML.T0053-adjacent) | Art. 32 (security of processing) | CC6.1 logical access / NIST 800-53 AC-6 |
| Human Checkpoints (Charter §3, Oversight Framework) | GOVERN 3.2, MANAGE 2.2 | Art. 14 (human oversight) | Clause 8.3 (operational planning) | LLM06: Excessive Agency | Human-AI Teaming controls | Art. 22 (right not to be subject to solely automated decision-making) | NIST 800-53 CA-6 |
| Runtime Policy Enforcement (Agent Policy §5) | MANAGE 1.3 | Art. 15 (accuracy, robustness) | Clause 8.2 | LLM01: Prompt Injection (runtime mitigation) | Defense Evasion mitigations | — | CC6.6 boundary protection / NIST 800-53 SC-7 |
| Action Traceability / Audit Logs | MANAGE 4.1, 4.2 | Art. 12 (record-keeping), Art. 19 (logs) | Clause 9.1 (monitoring, measurement) | — | Detection (log-based) | Art. 30 (records of processing) | CC7.2 monitoring / NIST 800-53 AU-2 |
| Shadow Agent Discovery | MAP 1.1, GOVERN 1.1 | Art. 16 (provider obligations — pre-condition for compliance) | Clause 4.1 (context, external issues) | — | Reconnaissance / Initial Access (unmanaged surface) | — | NIST 800-53 CM-8 |
| Kill Switch (Inventory gate) | MANAGE 2.4, 4.3 | Art. 14(4) (ability to intervene/interrupt) | Clause 10.1 (nonconformity, corrective action) | — | Impact mitigation | — | NIST 800-53 IR-4 |
| Incident Response (Agent Policy §7) | MANAGE 4.1 | Art. 73 (serious incident reporting) | Clause 10.1 | — | Incident Response | Art. 33-34 (breach notification, where applicable) | CC7.3 / NIST 800-53 IR-6 |

### How to Use This Table

For a specific regulatory or audit question — "show me how you satisfy human oversight under the AI Act" — the row gives the exact control and the exact artefact (Charter §3, Oversight Framework) that evidences it, rather than requiring a reader to infer coverage from prose. This is the same design principle behind Project 10's master crosswalk and Project 11's technical-control mapping, applied to the agent-specific control set this project introduces.

### Honest Gap Note

MITRE ATLAS tactic mappings above are directional, not clause-by-clause citations — ATLAS is a tactic/technique taxonomy for adversarial ML, not a compliance standard with numbered control requirements, so "mapping" it means showing which ATLAS tactic a control mitigates, not which ATLAS clause it satisfies. This distinction matters and is worth being explicit about in an interview: overstating ATLAS as a compliance framework is the kind of imprecision that a technically sharp interviewer will catch.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
