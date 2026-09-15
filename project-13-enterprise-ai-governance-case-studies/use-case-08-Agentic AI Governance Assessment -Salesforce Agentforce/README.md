# Use Case 08: Agentic AI Governance Assessment — Salesforce Agentforce

**Type:** Independent AI Governance Assessment (not a formal audit or compliance opinion) 

**Subject:** Salesforce Agentforce, Einstein Platform, and related Trust Layer — not affiliated with, commissioned by, or reviewed by Salesforce

> Second real-subject case study in this portfolio, alongside Use Case 07 (Microsoft 365 Copilot). Together they show a maturity progression: Copilot is generative/productivity AI; Agentforce is agentic AI that plans and executes actions. Areas marked **Review Further** are deployer due-diligence considerations, not confirmed gaps in Salesforce's practices.


<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/b973c9dc-0c94-4871-a9f5-cb565f2ac4f6" />

```
INVENTORY → ASSESS → CONTROL → MONITOR → ASSURE → IMPROVE
```

---

## 1. Assessment Scope

System: Salesforce Agentforce (built on the Einstein 1 Platform), Einstein (AI Platform), and Slack AI. Public-evidence assessment only — no internal, NDA'd, or non-public sources. Not a clause-by-clause ISO/IEC 42001 conformity assessment.

## 2. AI System Inventory

| | |
|---|---|
| **Provider** | Salesforce |
| **Users** | Employees/admins configuring and invoking agents; other data subjects may be indirectly affected where their information is in content an agent can access |
| **Data** | Scoped through Data 360 policy rules; agents inherit the invoking user's own access |
| **Purpose** | Autonomous task execution across sales, service, and operational workflows |
| **Agent Actions** | Agents can reason and **execute** actions (e.g., process a case, update a record) — not only generate text |
| **EU AI Act posture** | Not inherently Annex III high-risk; classification depends on the specific use case and degree of autonomous action authorised. Action-taking capability raises governance complexity relative to a purely generative assistant. Custom agents configured for Annex III scenarios require separate classification by the deploying organisation. *(Digital Omnibus timeline: verify current deadlines directly with the European Commission's AI Office before relying on this for a real engagement.)* |

### Provider vs. Deployer Responsibility

Agentic AI governance is a shared-responsibility model. This assessment distinguishes between controls provided at the platform level and governance responsibilities created by the enterprise's specific Agentforce deployment.

| Role | Primary Governance Responsibility |
|---|---|
| **Provider — Salesforce** | Provides the Agentforce platform, platform-level security, trust, governance, monitoring, and assurance capabilities documented in Salesforce's public materials. |
| **Deployer — Enterprise using Agentforce** | Governs how agents are configured and used, including use-case classification, data and system access, permissions, action boundaries, human approval points, monitoring, evidence, incident response, and ongoing reassessment. |

**Key principle:** Platform-level assurance provides a foundation; the deploying enterprise remains responsible for governing the specific agents, actions, integrations, and business use cases it implements.

## 3. NIST AI RMF Assessment

| Function | Public Evidence | Rating |
|---|---|---|
| **GOVERN** | Trusted AI Principles and AI Acceptable Use Policy, developed with an Ethical Use Advisory Council; named accountable executive (Chief Ethical and Humane Use Officer) | 🟢 Strong |
| **MAP** | Agents inherit invoking-user permissions; Data 360 Policy-Based Governance enforces field/object/record-level rules | 🟢 Strong |
| **MEASURE** | Einstein Trust Layer includes toxicity/bias filters and data-grounding checks; a SOC 2 report is scoped to Einstein Platform and Agentforce on Hyperforce | 🟡 Moderate |
| **MANAGE** | ISO/IEC 42001 certification for Agentforce, Einstein, and Slack AI, independently audited by BDO | 🟢 Strong |

## 4. ISO/IEC 42001 Evidence Review

This is a **focused public-evidence review of six governance areas** relevant to Salesforce Agentforce. It is not a complete ISO/IEC 42001 conformity assessment.

| Governance Area | Public Evidence Reviewed | Assessment |
|---|---|---|
| **AI Policy & Leadership** | Trusted AI Principles, AI Acceptable Use Policy, and a named accountable executive | **Public Evidence** |
| **Risk Assessment** | AI Acceptable Use Policy and high-risk-use restrictions | **Review Further** |
| **Data Governance** | Einstein Trust Layer and Data 360 Policy-Based Governance documentation | **Public Evidence** |
| **Supplier Oversight** | Multi-model architecture and subprocessor disclosures | **Review Further** |
| **Independent Audit** | Public ISO/IEC 42001 certification and SOC 2 report information | **Review Further** |
| **Continual Improvement** | AI Acceptable Use Policy updates and Trust/Transparency reporting | **Review Further** |

**Interpretation:**
**Public Evidence** means relevant governance information was observable in the public materials reviewed.
**Review Further** means a deploying organisation should obtain additional assurance evidence or perform its own due diligence before relying on that area for its specific deployment.

> A certification provides useful assurance that an assessed management system exists and has undergone independent review. It does not replace governance of an individual organisation's tenant configuration, data access, integrations, or custom agents.

## 5. What Changes With Agentic AI

Agentic AI introduces additional governance dimensions because the system can take actions, not just generate content.

```
Autonomy → Permissions → Tools/Actions → Human Oversight → Monitoring → Auditability
```

- **Autonomy:** how much an agent can decide and do without a human in the loop
- **Permissions:** whether an agent's access is scoped to the invoking user, or broader
- **Tools/Actions:** what real-world actions an agent is authorised to take, not just what it can say
- **Human Oversight:** where an approval gate sits before an action executes
- **Monitoring:** whether runtime agent behaviour is observable, not just its outputs
- **Auditability:** whether an agent's action history can be reconstructed after the fact

This assessment's methodology extends to agentic systems, but not without adjustment — these six dimensions are additive to the NIST/ISO review above, not already covered by it.

## 6. Agentic AI Controls & Framework Mapping

*Representative controls shown for illustration; not an exhaustive control catalogue or conformity checklist.*

| Control | What We Expect | Framework Mapping |
|---|---|---|
| Agent Inventory & Classification | Owner, purpose, risk, and autonomy documented | NIST GOVERN/MAP · ISO risk management · EU Art. 6/Annex III* |
| Least Privilege | Only approved data, systems, and permissions | NIST MAP/MANAGE · ISO operational controls |
| Action Boundaries | Approved tools/actions only | NIST MANAGE · ISO operational controls |
| Human Oversight | Approval/override for defined high-impact actions | EU Art. 14* · ISO operational controls |
| Logging & Traceability | Agent actions and outcomes reconstructable | EU Art. 12* · ISO documented information |
| Runtime Monitoring | Behaviour, failures, policy violations, drift, robustness, and relevant security events monitored | NIST MEASURE/MANAGE · ISO monitoring & measurement · EU Art. 15* |
| Incident / Kill Switch | Ability to contain or disable unsafe agent behaviour | EU Art. 14* (stop capability) · ISO corrective action |
| Material Change Review | Reassess model, prompt, tool, data, or autonomy changes | NIST MANAGE · ISO continual improvement |

*\* EU AI Act high-risk-system requirements, where applicable to the specific deployed use case. This assessment does not assert that Agentforce itself, or every Agentforce implementation, is a high-risk AI system under Annex III. Classification depends on the specific intended use and applicable regulatory criteria.*

## 7. Continuous Monitoring & Assurance

```
DEPLOY → MONITOR → DETECT → RESPOND → REMEDIATE → REASSESS
```

What to monitor: agent actions · human overrides · failed actions · policy violations · permission changes · security events · behavioural drift · incidents

This is the operating layer that turns a one-time framework assessment into ongoing governance — the evidence that controls aren't just documented, but running.

## 8. Key Considerations for Deployers

| Consideration | Priority (for the deploying organisation) | Suggested Action | Owner |
|---|---|---|---|
| Data and integration governance across the agent ecosystem | High | Map the data, systems, APIs, and tools each agent can access, and verify governance coverage across those boundaries | AI Governance + Data Governance |
| Higher governance complexity from action-taking capability | High | Classify each deployed agent by the specific action it's authorised to take, not just by platform | AI Governance |
| Product-specific impact assessment not public | Medium | Request assurance documentation during procurement | Procurement + AI Governance |
| Audit report detail (ISO/SOC 2) not public | Medium | Treat certification as a starting point for due diligence, not a substitute for it | Procurement + AI Governance |
| Model-provider contract terms undisclosed | Low | Standard vendor confidentiality; revisit at contract renewal | Procurement |

## 9. Overall Assessment

**Posture:** Strong public governance evidence at the platform level — named accountable executive, public AI use policy, independently certified/audited controls.

**Key consideration:** action-taking capability changes what "governed" needs to mean — output oversight is no longer sufficient on its own.

**Practical implication:** certification and the Trust Layer are a credible foundation; they don't replace the deploying organisation's own action-level risk classification and oversight of each agent.

## 10. Practitioner Takeaway

When AI moves from generating content to taking actions, governance must move from output oversight to action oversight.

For AI Program Managers, this means translating autonomy and risk into clear owners, approval gates, action boundaries, controls, monitoring, evidence, and escalation paths — not just extending a content-review checklist.

## 11. Sources & Limitations

**Primary:** Salesforce Trusted AI Principles and AI Acceptable Use Policy (2023, updated since) · Salesforce newsroom, ISO/IEC 42001 certification announcement (BDO-audited) · Salesforce/Google Cloud partnership announcements on Gemini integration (Feb 2025) · European Commission AI Office public GPAI guidance

Sources are prioritised in this order: (1) Salesforce official/public materials, (2) European Commission/EUR-Lex, (3) NIST official sources, (4) ISO public information where appropriate. Conclusions about Salesforce are not drawn from competitor or third-party commercial analysis.

**Independent educational portfolio assessment** based solely on publicly available information. Not affiliated with, commissioned by, or reviewed by Salesforce. This is not a formal audit, certification, legal opinion, or compliance determination. "Review Further" identifies areas where additional deployer due diligence or non-public evidence may be appropriate; it does not indicate a confirmed deficiency in Salesforce's controls or practices.

*Time-sensitive facts, including certification status, product capabilities, model integrations, and regulatory requirements, should be independently re-verified before reliance in a real advisory, procurement, compliance, or deployment decision.*

---

*Karun · AIGP (AI Governance Professional)*
