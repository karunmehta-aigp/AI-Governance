# Use Case 07: Public AI Governance Assessment — Microsoft 365 Copilot

> **⚠️ Scope & Disclaimer:** Unlike Use Cases 01–06 in this portfolio (fictional organisation, fictional systems), this is an independent, third-party **assessment** — not a formal audit — of a real, publicly documented product: Microsoft 365 Copilot. "Assessment" is used deliberately rather than "audit": an audit implies a formal assurance engagement with direct access, sampling, and evidence testing. This uses only publicly available materials. Every claim below is either directly sourced (see **Sources & Limitations**) or explicitly marked as a public evidence limitation. Not affiliated with or reviewed by Microsoft.

**System reference:** `EXT-BENCHMARK-01` (kept outside the `ORG-AI-0XX` fictional-case-study numbering used elsewhere in this portfolio)

**Why this exists:** the rest of this portfolio proves I can *build* governance from the inside. This proves I can *assess* it from the outside, using only what a regulator, customer, or procurement reviewer would ever get to see — the exact skill vendor due diligence and third-party AI risk review require.

**What this is (precisely):** three connected assessment activities, not three interchangeable "frameworks" — an AI system inventory (a governance capability, not a standard), an assessment against the NIST AI Risk Management Framework, and an evidence review against the ISO/IEC 42001:2023 standard.

```
              PUBLIC AI PRODUCT
             (Microsoft 365 Copilot)
                      ↓
   ┌──────────────────────────────────┐
   │  1. AI SYSTEM INVENTORY           │
   │  Product · Provider · Users ·     │
   │  Data · EU AI Act classification  │
   └────────────────┬───────────────────┘
                      ↓
   ┌──────────────────────────────────┐
   │  2. NIST AI RMF ASSESSMENT        │
   │  GOVERN → MAP → MEASURE → MANAGE  │
   │  Risk → Control → Finding         │
   └────────────────┬───────────────────┘
                      ↓
   ┌──────────────────────────────────┐
   │  3. ISO/IEC 42001 EVIDENCE REVIEW │
   │  Public evidence → Requirement →  │
   │  Observed / Limitation → Opportunity│
   └────────────────┬───────────────────┘
                      ↓
        FINDINGS & RECOMMENDATIONS
```

---

## 1. AI System Inventory

- **System:** Microsoft 365 Copilot — AI assistant integrated across Word, Excel, Outlook, Teams, SharePoint; includes Copilot Chat and custom agents built in Copilot Studio
- **Provider:** Microsoft
- **Deployer (typical):** any enterprise licensing Copilot for its workforce
- **Users affected:** employees directly; customers/counterparties indirectly, since Copilot can surface their data if an employee already has access to it
- **Underlying model(s):** multi-model — OpenAI models remain the default; Anthropic Claude models (Sonnet and Opus family) were added starting with the Researcher agent and Copilot Studio in September 2025, with Copilot Chat rollout following through early–mid 2026. Anthropic is onboarded as a Microsoft subprocessor under Microsoft's standard Data Protection Addendum. Availability differs by region: on by default in most commercial tenants; **off by default in EU/EFTA/UK**, requiring admin opt-in; not available in Government/Sovereign cloud tenants.
- **Data inputs:** only content the requesting user is already permitted to access, via Microsoft Graph
- **Purpose:** general productivity — drafting, summarising, searching, reasoning over content the user already has rights to
- **Not intended for:** standalone regulated decisions (credit, hiring, etc.) unless a custom agent is purpose-built for that specific use case
- **Status:** generally available; independently recertified as recently as March–May 2026

**EU AI Act classification:**

- **Base-product posture:** Microsoft 365 Copilot is not inherently an Annex III high-risk AI system simply because it is a general enterprise assistant. Applicable EU AI Act obligations depend on the specific provider/deployer role, the underlying GPAI models involved, the functionality in use, and the intended use — this is a determination made case by case, not a fixed label.
- Microsoft, as a GPAI provider, owes technical documentation, a copyright policy, and a training-data summary under Article 53 (in force since August 2025)
- **Watch-point:** if an enterprise builds a *custom* Copilot Studio agent for an actual Annex III use case (e.g., HR screening, credit-adjacent decisioning), the deploying organisation may assume deployer status — and, depending on how substantially the system is modified or how it is placed into use, potentially additional AI Act obligations specific to that use case
- **Timeline note (verify independently before relying on this in a real engagement):** prohibitions in force since February 2025; GPAI/transparency obligations in force now; Annex III high-risk obligations were deferred by the EU's Digital Omnibus on AI to December 2, 2027 (standalone high-risk systems) and August 2, 2028 (systems embedded in regulated products). A meaningful share of public commentary still cites the original August 2026 date. This document reflects the post-Omnibus timeline as understood at the time of writing; the European Commission's own AI Office pages are the authoritative source and should be checked directly before any real compliance decision is made on this basis.

---

## 2. NIST AI RMF Assessment

### GOVERN
- **Risk:** responsible-AI claims are marketing language, not enforced process
- **Public evidence:** Microsoft's Responsible AI Standard v2 (published June 2022) translates six principles into 17 defined goals with specific requirements; a named accountable body (Office of Responsible AI) is referenced in Microsoft's public materials
- **Finding:** Strong — publishing requirement-level detail, not just principles, is uncommon among commercial AI vendors

### MAP
- **Risk:** users and admins don't know what data Copilot can actually touch
- **Public evidence:** Copilot only accesses content the requesting user already has permission to see, enforced through existing SharePoint/OneDrive permissions and Microsoft Purview sensitivity labels/DLP controls
- **Finding:** Strong, but the control is inherited from pre-existing Microsoft 365 permission architecture rather than purpose-built for Copilot specifically

### MEASURE
- **Risk:** no independent way to check for bias or unsafe outputs
- **Public evidence:** Microsoft's open-source Responsible AI Toolbox includes Fairlearn (fairness assessment) and InterpretML (model interpretability), usable by third parties independent of Microsoft
- **Finding:** Strong on tooling availability. Live monitoring results and product-specific fairness metrics for Copilot itself are a **public evidence limitation** — the commitment and tooling are visible; the outcomes are not published

### MANAGE
- **Risk:** certification claims outliving actual practice
- **Public evidence:** Microsoft 365 Copilot and Copilot Chat received ISO/IEC 42001:2023 certification in March 2025 and were independently recertified for a second consecutive year (audit conducted March 2026, publicly announced May 28, 2026) with zero non-conformities and zero improvement observations, per Microsoft's own announcement and independent trade press coverage
- **Finding:** the strongest evidence in this assessment — one of the few claims backed by a stated third-party audit outcome rather than self-attestation alone

---

## 3. ISO/IEC 42001 Evidence Review

**Public evidence reviewed:** Responsible AI Standard v2; ISO/IEC 42001:2023 certification and recertification announcements (issued by Mastermind, an IAS-accredited certification body); Microsoft's annual Responsible AI Transparency Report.

**Framing note:** Copilot is actually **certified**, not merely "policy on paper." Microsoft's own recertification announcement states explicitly that the certification covers Microsoft's AI management system — governance, risk assessment, data management, transparency, human oversight, and supplier management — and does **not** certify the state of any individual customer's tenant content, permissions, or agent configuration. That distinction, stated by Microsoft itself, is the central fact this evidence review is built around: a clean certificate confirms an audited process at Microsoft's end; it says nothing about how a specific customer has configured or governed their own deployment.

| Requirement area | Evidence Observed Publicly | Public Evidence Limitation |
|---|---|---|
| AI policy & leadership | Standard public since 2022; named accountable body referenced | Board-level AI risk reporting cadence and content not published |
| Risk assessment | Impact Assessment framework and template are public and stated as mandatory | The completed impact assessment specific to Copilot is not published |
| Data governance | Encryption, tenant isolation, EU Data Boundary documented in detail | Full prompt-log retention/deletion timelines described generally, not exhaustively |
| Supplier oversight | Multi-model providers (OpenAI, Anthropic) and subprocessor status publicly disclosed | Underlying contractual governance terms between Microsoft and model providers are not public |
| Independent audit | Recertification outcome (zero non-conformities) publicly stated by Microsoft and covered independently | The full audit report and evidentiary detail behind that outcome is not public |
| Continual improvement | Standard is described as a living document; annual Transparency Report exists | Granular before/after metrics tied to specific improvement actions are not published |

**Top 5 Public Evidence Limitations / Transparency Opportunities** *(these describe what an outside reviewer cannot verify — not confirmed gaps in Microsoft's actual practice)*:

1. A clean certificate is the strongest available evidence, but it is also the least independently inspectable — the audit report itself is not public
2. Impact assessments are required by policy; the completed assessment for Copilot specifically is not published
3. Fairness/interpretability tooling is public; live results from applying it to Copilot are not
4. It would be easy for a customer to wrongly assume Copilot's certification extends to their own custom Copilot Studio agents — Microsoft's own announcement clarifies it does not
5. Public secondary commentary on Copilot's EU AI Act posture is inconsistent — some sources still cite the pre-Digital-Omnibus August 2026 deadline

**Recommended actions for a company deploying Copilot** (opportunities, not corrections to Microsoft):

- Treat every custom Copilot Studio agent as its own governance object, classified independently — do not extend Copilot's certification to cover it
- Request Microsoft's product-specific Responsible AI Impact Assessment summary or equivalent assurance documentation directly during procurement
- Maintain internal, ongoing review of Purview/DLP configuration governing Copilot's actual data-access footprint
- Track EU AI Act implementation dates directly from the European Commission's AI Office rather than secondary sources

---

## Findings & Recommendations

**Overall assessment:** based solely on public evidence, Microsoft 365 Copilot shows a comparatively low residual governance risk profile at the platform level — a detailed public standard, an independently recertified ISO/IEC 42001 certification with a stated clean result, and open-source fairness tooling that most commercial AI vendors do not release. The residual risk this assessment identifies sits almost entirely on the **deployer's side**: what a customer builds on top of the platform, and the inherent limit that a certificate cannot be independently inspected past its stated headline result.

| Finding | Severity (deployer-side risk exposure) |
|---|---|
| A customer over-extends Copilot's certification to cover its own custom agents | High |
| Product-specific impact assessment not published | Medium |
| Live monitoring outcomes not publicly visible | Medium |
| Outdated EU AI Act deadline still circulating in secondary commentary | Medium |
| Model-provider contract terms undisclosed | Low |

**Remediation roadmap (for a deploying organisation):**

| Timeframe | Action | Owner |
|---|---|---|
| 0–30 days | Inventory every Copilot Studio agent in use; classify each independently under EU AI Act risk tiers | AI Governance |
| 30–60 days | Request vendor assurance documentation (impact assessment summary, DPA, subprocessor list) during procurement | Procurement + AI Governance |
| 60–90 days | Establish quarterly review of Purview/DLP configuration governing Copilot's data access | IT Security / Data Governance |
| Ongoing | Maintain a live EU AI Act deadline tracker sourced from the European Commission's AI Office | AI Governance |

**What this case study demonstrates:**
- Ability to assess AI governance from the outside, using only public evidence — the core skill behind vendor due diligence and AI supply-chain risk review
- Precise use of terminology: an inventory is a capability, NIST AI RMF and ISO/IEC 42001 are frameworks/standards, and an "assessment" is not an "audit"
- Consistent separation of "not evidenced publicly" from "does not exist," applied throughout rather than as a one-time disclaimer
- Understanding that a certification confirms an audited process, not independent verifiability — and citing Microsoft's own stated certification-scope limits as the basis for that point, rather than asserting it unprompted
- Ability to distinguish stable governance evidence from time-sensitive regulatory and product information that requires periodic re-verification

---

## Sources & Limitations

**Primary/official sources:**
- Microsoft Responsible AI Standard, v2 (General Requirements), publicly released June 2022
- Microsoft Tech Community, ISO/IEC 42001:2023 recertification announcement, May 28, 2026
- Microsoft Learn documentation: Copilot data protection, privacy, and security architecture
- Anthropic Claude / Microsoft 365 Copilot integration announcements (Microsoft Business & Industry Copilot blog, September 2025 onward; Microsoft Message Center notice on Copilot Chat rollout)
- European Commission, AI Office public guidance on GPAI obligations and the AI Act implementation timeline

**Independent secondary sources (used for corroboration, not as primary evidence):**
- Help Net Security, "Microsoft 365 Copilot ISO 42001 certification," May 2026
- Neowin, coverage of the March 2026 recertification and expanded certification scope
- UC Today and CO/AI, coverage of the September 2025 Anthropic Claude integration announcement

**Methodology limitations:**
- This assessment relies entirely on materials Microsoft has chosen to publish. It cannot confirm anything about internal processes, audit findings, or control effectiveness beyond what is publicly stated.
- Time-sensitive facts (certification dates, model rollout details, regulatory deadlines) should be independently re-verified before this document is relied upon in any real advisory or procurement context — they are accurate as of the research conducted for this write-up, not guaranteed current at the time of reading.
- No claim in this document should be read as an assertion that Microsoft has an undisclosed governance gap. Where evidence was not found publicly, that is stated as a limitation of this review, not a finding about Microsoft's actual practice.

---

*Karun · AIGP (AI Governance Professional)*
