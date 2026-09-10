# Use Case 07: Public-Evidence AI Governance Assessment — Microsoft 365 Copilot

**System reference:** `EXT-BENCHMARK-01` | **Type:** Independent public-evidence review (not a formal audit or compliance opinion) | **Subject:** Real, named product — not affiliated with, commissioned by, or reviewed by Microsoft

> This is the one real-subject case study in this portfolio (see Use Cases 01–06 for fictional-organisation examples). All claims are sourced from Microsoft's own public materials — Responsible AI Standard, Transparency Notes, ISO/IEC 42001 certification announcements. "Limited" below means *not publicly evidenced*, not a confirmed gap in Microsoft's actual practice.

```
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/2fc7d885-ff03-4176-b1aa-18223ec64b96" />


---

## 1. Assessment Scope

| | |
|---|---|
| **System** | Microsoft 365 Copilot (enterprise), incl. Copilot Chat and Copilot Studio agents |
| **Purpose of this assessment** | Demonstrate third-party AI governance evaluation using only public evidence |
| **Evidence boundary** | Public materials only — no internal, NDA'd, or non-public sources |
| **What this is not** | A clause-by-clause ISO/IEC 42001 conformity audit, or a comprehensive account of Microsoft's internal AIMS |

## 2. AI System Inventory

| | |
|---|---|
| **Provider** | Microsoft |
| **Users** | Employees directly; other data subjects may be indirectly affected where their information is contained in content the authorised user can access |
| **Underlying models** | Multi-model — OpenAI (default) plus Anthropic Claude (Researcher, Copilot Studio, rolling out to Copilot Chat since 2025–26; off by default in EU/EFTA/UK) |
| **Data accessed** | Only what the requesting user is already permitted to see (Microsoft Graph) |
| **Purpose** | General productivity — draft, summarise, search, reason over permitted content |
| **EU AI Act posture** | Not inherently Annex III high-risk; obligations depend on provider/deployer role and specific use. **Custom Copilot Studio agents used for Annex III scenarios (e.g., certain HR or credit-related uses) require separate use-case classification and governance assessment by the deploying organisation.** |

## 3. NIST AI RMF Assessment

| Function | Public Evidence | Rating |
|---|---|---|
| **GOVERN** | Responsible AI Standard v2 (17 defined goals); named accountable body (Office of Responsible AI) | 🟢 Strong |
| **MAP** | Access scoped to existing M365 permissions; Purview labels/DLP honoured | 🟢 Strong |
| **MEASURE** | Open-source Fairlearn/InterpretML tooling public; live monitoring results for Copilot not published | 🟡 Moderate |
| **MANAGE** | ISO/IEC 42001 recertified March 2026, zero non-conformities (Microsoft's own stated result) | 🟢 Strong |

## 4. ISO/IEC 42001 Evidence Review

*This is a focused sample of six governance areas selected for this public-evidence case study. It is not a complete ISO/IEC 42001 conformity assessment.*

| Area | Evidence Observed | Public Evidence Limitation |
|---|---|---|
| AI Policy & Leadership | Standard public since 2022; accountability defined | Board-level AI risk reporting detail |
| Risk Assessment | Impact Assessment framework public | Copilot-specific completed assessment not published |
| Data Governance | Encryption, tenant isolation, EU Data Boundary documented | Full log retention/deletion timelines not exhaustive |
| Supplier Oversight | Multi-model providers & subprocessor status disclosed | Underlying contract terms not public |
| Independent Audit | Recertification outcome stated & independently covered | Full audit report not public |
| Continual Improvement | Living standard; annual Transparency Report | Granular improvement metrics not published |

**Key point:** a certificate confirms an audited process occurred — it does not give an outside reviewer access to the audit itself. Microsoft's own recertification notice states the certification does not cover any individual customer's tenant content or agent configuration.

## 5. Findings & Actions

| Finding | Severity | Action | Owner |
|---|---|---|---|
| Customer may over-extend Copilot's certification to cover its own custom agents | High | Classify every Copilot Studio agent independently under EU AI Act tiers | AI Governance |
| Product-specific impact assessment not public | Medium | Request assurance documentation during procurement | Procurement + AI Governance |
| Live monitoring outcomes not public | Medium | Establish deployer-side monitoring of Copilot's data-access footprint | IT Security / Data Governance |
| Secondary sources cite outdated EU AI Act deadline | Medium | Track deadlines from the EU AI Office directly | AI Governance |
| Model-provider contract terms undisclosed | Low | Note as standard vendor confidentiality; revisit at contract renewal | Procurement |

## 6. Overall Assessment

**Governance posture:** Strong public evidence at the platform level — detailed standard, independently recertified ISO/IEC 42001 status, open-source fairness tooling.
**Primary governance consideration:** Deployer-side configuration and custom agents.
**Implication for a deploying organisation:** Certification provides useful vendor-assurance evidence, but does not replace governance of the organisation's own configuration, data access, and custom agents.

## 7. Practitioner Takeaway

- Third-party AI governance assessment using only public evidence, with consistent separation of "not evidenced publicly" from "does not exist"
- Understanding that certification confirms an audited process, not independent verifiability

## 8. Sources & Limitations

**Primary:** Microsoft Responsible AI Standard v2 (June 2022) · Microsoft Tech Community ISO/IEC 42001 recertification announcement (May 2026) · Microsoft Learn Copilot data protection documentation · EU AI Office public GPAI guidance
**Secondary (corroboration only):** Help Net Security, Neowin — ISO 42001 recertification coverage; UC Today — Anthropic/Copilot integration coverage

*This assessment reflects publicly available information at the time of writing. Time-sensitive facts (certification status, model rollout, regulatory deadlines) should be independently re-verified before reliance in any real advisory or procurement context.*

---

*Karun · AIGP (AI Governance Professional)*
