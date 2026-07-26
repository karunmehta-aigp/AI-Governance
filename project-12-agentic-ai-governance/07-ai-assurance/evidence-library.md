## Evidence Library

*A single index of what evidence exists, where it lives, and which control or lifecycle stage it satisfies — because scattered evidence is functionally the same as missing evidence during an audit.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why an Index, Not a Repository

This document does not hold the evidence itself — architecture sign-offs, red team reports, and monitoring exports live wherever the organisation's records systems keep them. What's missing in most governance programmes isn't the evidence; it's a map of it. An auditor's first question is rarely "does this evidence exist" — it's "can you find it in under five minutes." This index is that map.

### Evidence Index

| Evidence Type | Produced At | Format | Satisfies |
|---|---|---|---|
| Business intake form | Lifecycle Stage 1–2 | Signed form | Stage gate 1–2 |
| Risk register entry (with autonomy multiplier applied) | Lifecycle Stage 3 | Risk Classification Addendum entry | `AI-CNTRL-A09` |
| Architecture review sign-off | Lifecycle Stage 4 | Review record | `AI-CNTRL-A02`, `A06` |
| Security review report | Lifecycle Stage 5 | Report | Compliance Crosswalk (OWASP row) |
| Behavioural test report | Lifecycle Stage 6 | Test results vs. documented scope | `AI-CNTRL-A03` support |
| Red team findings + remediation | Lifecycle Stage 7 | Report | Compliance Crosswalk (MITRE ATLAS row) |
| Committee approval record | Lifecycle Stage 7 | Meeting minutes / decision log | Charter §4 |
| Inventory register entry | Lifecycle Stage 8 | Agent Inventory Register row | `AI-CNTRL-A01`, `A02`, `A04` |
| Kill switch test record | Ongoing, ≤90 days | Test log | `AI-CNTRL-A04` |
| Runtime monitoring export | Continuous | Dashboard / log export | Runtime Governance |
| Third-party vendor assessment | Lifecycle Stage 2 | Completed questionnaire | Third-Party AI Governance |
| Prompt version history | Ongoing | Registry diff log | Prompt Governance |
| Model version / regression record | On upgrade | Test record | Model Governance |
| Incident response record | On incident | Playbook stages 1–10 completed | AI Incident Response Playbook |
| Audit report | Annual | Report | Lifecycle Stage 11, AI Assurance Framework (Audit stage) |
| Retirement record | On decommission | Sign-off | Lifecycle Stage 12 |

### Retrieval Discipline

Every entry above should be retrievable by two paths: by system (`ORG-AI-011` → all its evidence) and by control (`AI-CNTRL-A04` → every kill switch test across every agent). If evidence can only be found "by system," a portfolio-wide audit question ("show me every kill switch test this quarter") requires manually opening every system's folder — the second retrieval path is what actually makes continuous assurance (see AI Assurance Framework) practical rather than theoretical.

### Related Documents

- [AI Assurance Framework](./ai-assurance-framework.md) — the Govern-Validate-Monitor-Audit-Improve cycle this evidence index supports

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
