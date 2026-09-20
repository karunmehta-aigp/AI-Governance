# Use Case 07: AI Governance Assessment — Microsoft 365 Copilot


**Type:** Independent public-evidence review (not a formal audit or compliance opinion)  
**Subject:** Microsoft 365 Copilot — not affiliated with, commissioned by, or reviewed by Microsoft

> This is the one real-subject case study in this portfolio (see Use Cases 01–06 for fictional-organisation examples). The assessment uses publicly available information to demonstrate third-party AI governance evaluation. Areas marked **Review Further** indicate where a deploying organisation should perform additional due diligence; they do not represent confirmed gaps in Microsoft's practices.
>
> <img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/0ed68657-6c51-467c-9595-4fa5b21033a7" />


**INVENTORY → NIST AI RMF → ISO/IEC 42001 → DEPLOYER CONSIDERATIONS & ACTIONS**

---

## 1. Assessment Scope

| Area | Description |
|---|---|
| **System** | Microsoft 365 Copilot (enterprise), including Copilot Chat and Copilot Studio agents |
| **Purpose** | Demonstrate third-party AI governance evaluation using public evidence |
| **Evidence boundary** | Publicly available materials only; no internal, NDA'd, or non-public information |
| **Assessment approach** | AI system inventory, EU AI Act posture, NIST AI RMF assessment, focused ISO/IEC 42001 evidence review |
| **What this is not** | A formal audit, legal/compliance opinion, clause-by-clause ISO/IEC 42001 conformity assessment, or comprehensive account of Microsoft's internal AIMS |

---

## 2. AI System Inventory

| Attribute | Assessment |
|---|---|
| **Provider** | Microsoft |
| **Users** | Employees directly; other data subjects may be indirectly affected where their information is contained in content the authorised user can access |
| **Underlying models** | Multi-model architecture supporting Microsoft 365 Copilot experiences |
| **Data accessed** | Content the requesting user is authorised to access through Microsoft 365 and Microsoft Graph |
| **Purpose** | General productivity, including drafting, summarisation, search, and reasoning over permitted content |
| **EU AI Act posture** | Microsoft 365 Copilot is not inherently an Annex III high-risk system solely because it is an enterprise AI assistant. Classification depends on the intended use, functionality, and provider/deployer role. Custom Copilot Studio agents used for potentially regulated scenarios require separate use-case classification and governance assessment by the deploying organisation. |

### Deployer Governance Principle

> **Govern the use case, not just the platform.**

An organisation adopting Microsoft 365 Copilot should separately assess custom agents, integrations, data access, autonomy, and intended business use rather than relying solely on the governance posture of the underlying platform.

---

## 3. NIST AI RMF Assessment

The assessment uses the four NIST AI RMF functions as a structured governance lens.

| Function | Public Evidence Reviewed | Assessment |
|---|---|---|
| **GOVERN** | Responsible AI Standard and defined accountability structure | 🟢 Strong |
| **MAP** | Microsoft 365 permissions, data-access controls, Purview and DLP capabilities | 🟢 Strong |
| **MEASURE** | Public Responsible AI evaluation tooling; product-specific operational monitoring evidence is less externally observable | 🟡 Moderate |
| **MANAGE** | Published governance processes and ISO/IEC 42001 certification/recertification evidence | 🟢 Strong |

> **Note:** Strong and Moderate are portfolio assessment ratings used to summarise the public evidence reviewed. They are not official NIST AI RMF scores.

---

## 4. ISO/IEC 42001 Evidence Review

This is a **focused public-evidence review of six governance areas** relevant to Microsoft 365 Copilot. It is not a complete ISO/IEC 42001 conformity assessment.

| Governance Area | Public Evidence Reviewed | Assessment |
|---|---|---|
| **AI Policy & Leadership** | Responsible AI Standard and defined accountability | **Public Evidence** |
| **Risk Assessment** | Responsible AI impact-assessment framework | **Review Further** |
| **Data Governance** | Security, access, tenant and data-protection documentation | **Public Evidence** |
| **Supplier Oversight** | Model-provider and service information | **Review Further** |
| **Independent Audit** | Public ISO/IEC 42001 certification/recertification information | **Review Further** |
| **Continual Improvement** | Responsible AI Standard and transparency reporting | **Review Further** |

**Interpretation:**  
**Public Evidence** means relevant governance information was observable in the public materials reviewed.  
**Review Further** means a deploying organisation should obtain additional assurance evidence or perform its own due diligence before relying on that area for its specific deployment.

> A certification provides useful assurance that an assessed management system exists and has undergone independent review. It does not replace governance of an individual organisation's tenant configuration, data access, integrations, or custom agents.

---

## 5. Key Considerations for Deployers

The assessment is intentionally framed around **actions for deploying organisations**, rather than treating the absence of public information as evidence of a control deficiency.

| Deployer Consideration | Priority | Recommended Action | Suggested Owner |
|---|---|---|---|
| **Custom agents require separate governance** | High | Inventory and classify custom Copilot Studio agents based on intended use, data, autonomy and regulatory impact | AI Governance |
| **Product-specific assurance evidence** | Medium | Request appropriate assurance documentation during vendor due diligence and procurement | Procurement + AI Governance |
| **Deployer-side monitoring** | Medium | Establish monitoring for data access, custom agents, policy exceptions and relevant operational indicators | IT Security / Data Governance |
| **EU AI Act timelines** | Medium | Verify applicable regulatory obligations and implementation dates using official EU sources | AI Governance / Legal |
| **Model-provider terms** | Low | Review relevant provider, subprocessor and contractual terms during due diligence and renewal | Procurement |

Priority represents the **importance of the deployer's governance action**, not a risk rating assigned to Microsoft.

---

## 6. Overall Assessment

**Governance posture:** Based on the public evidence reviewed, Microsoft 365 Copilot demonstrates a strong governance foundation at the platform level.
Overall, there is strong public governance evidence at the platform level.

**Primary governance consideration:** Enterprise adopters remain responsible for governing their own configuration, data access, integrations, intended uses, and custom agents.

**Assessment outcome:** From the deployer perspective - Public certification, governance standards and supporting documentation provide useful inputs to vendor due diligence, while deployment-specific governance and assurance remain necessary.

**Practical implication:** Use platform assurance as a starting point, then **inventory → classify → configure → monitor** the organisation's own deployment.

---

## 7. Practitioner Takeaway

- Demonstrates third-party AI governance assessment using publicly available evidence
- Applies AI system inventory, EU AI Act considerations, NIST AI RMF and ISO/IEC 42001 as complementary governance lenses
- Separates public-evidence limitations from confirmed control deficiencies
- Converts governance observations into practical deployer actions and ownership
- Demonstrates the principle that platform certification does not automatically govern custom AI implementations

---

## 8. Sources & Limitations

**Primary evidence sources**

- Microsoft Responsible AI Standard
- Microsoft Responsible AI transparency materials
- Microsoft 365 Copilot data-protection and security documentation
- Microsoft ISO/IEC 42001 certification and recertification information
- Official European Union AI Act and AI Office materials
- NIST AI Risk Management Framework

**Assessment limitations**

This assessment is based solely on publicly available information. No internal Microsoft documentation, customer-specific configuration, audit workpapers, contractual evidence, operational monitoring data, or non-public control evidence was reviewed.

The assessment therefore evaluates **observable public governance evidence**, not the complete design or operating effectiveness of Microsoft's internal controls.

Time-sensitive information, including certification status, AI model availability and regulatory implementation dates, should be independently re-verified before use in an actual procurement, compliance, legal or risk-management decision.

---

*Karun · AIGP (AI Governance Professional)*
