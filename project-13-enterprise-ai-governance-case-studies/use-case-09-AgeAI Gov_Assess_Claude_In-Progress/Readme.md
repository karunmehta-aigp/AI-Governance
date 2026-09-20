# Use Case 09: Agentic AI Governance Assessment — Anthropic Claude Enterprise + Claude Code ** In-Progress

**Type:** Independent AI Governance Assessment (not a formal audit or compliance opinion)

**Subject:** Anthropic Claude Enterprise and Claude Code — not affiliated with, commissioned by, or reviewed by Anthropic

> Third real-subject case study in this portfolio, following Use Case 07 (Microsoft 365 Copilot) and Use Case 08 (Salesforce Agentforce). Together they show a maturity progression: Copilot focuses on enterprise generative/productivity AI, Agentforce introduces action-taking agentic AI, and Claude Enterprise + Claude Code extends the assessment into tool/MCP access, execution boundaries, control-effectiveness testing, and action assurance. Areas marked **Review Further** are deployer due-diligence considerations, not confirmed gaps in Anthropic's practices.

---

## 1. Assessment Scope

**System:** Anthropic Claude Enterprise and Claude Code. Public-evidence assessment only — no internal, NDA'd, customer-specific, or non-public sources. Not a clause-by-clause ISO/IEC 42001 conformity assessment.

This assessment asks two questions:

1. **Provider assurance:** What governance, security, safety, administration, monitoring, and independent assurance evidence is publicly available from Anthropic?
2. **Deployment assurance:** What must an enterprise independently govern and evidence when Claude is connected to its own data, users, code, tools, connectors, MCP servers, systems, and business processes?

**Assessment lifecycle:**  
`INVENTORY → ASSESS → CONTROL → TEST → MONITOR → ASSURE → IMPROVE`

**Assurance progression:**  
`CONTROL PRESENCE → CONTROL EFFECTIVENESS → ACTION ASSURANCE → EVIDENCE → DECISION → REASSESSMENT`

> **Key principle:** Provider assurance is an important foundation. It does not automatically establish assurance of the enterprise's specific deployment.

---

## 2. AI System Inventory

| | |
|---|---|
| **Provider** | Anthropic |
| **Enterprise surfaces assessed** | Claude Enterprise and Claude Code |
| **Users** | Employees, developers, engineering teams, administrators, and other authorised enterprise users |
| **Data** | Enterprise information made available through user access, files, repositories, connectors, tools, APIs, MCP servers, and configured integrations |
| **Purpose** | Enterprise productivity, reasoning, software development, workflow assistance, and approved tool-enabled tasks |
| **Agent Actions** | Claude Code and tool-enabled workflows can read files, edit code, run commands, interact with approved tools/services, and perform actions within configured permissions and execution boundaries |
| **EU AI Act posture** | Classification depends on the **specific deployed use case, intended purpose, role, and impact**, not simply the Claude product name. At intake and after material change, the deploying organisation should reassess whether the use is subject to high-risk or other applicable requirements and whether changes to the system or intended purpose affect its regulatory role. For applicable high-risk systems, Article 25 should be considered where substantial modification or changed intended purpose could cause another party to assume provider obligations. Regulatory applicability and current timelines should be verified against official EU sources before reliance in a real engagement. |

---

## 3. Provider vs. Deployer Responsibility

Agentic AI governance is a **shared-responsibility model**. Provider controls can be inherited as assurance inputs, but the deploying organisation remains accountable for risks created by its own configuration and use.

| Role | Primary Governance Responsibility |
|---|---|
| **Provider — Anthropic** | Provides the models and enterprise products; provider-level safety and evaluation practices; enterprise administration and security capabilities; Claude Code permission and sandboxing capabilities; connector/MCP controls; transparency and compliance information; and publicly documented independent assurance such as ISO/IEC 42001 certification of Anthropic's AI management system. |
| **Deployer — Enterprise using Claude** | Governs the specific business use case, regulatory role, users and agent identities, enterprise data, permissions, tools/MCP servers, integrations, action boundaries, human approvals, runtime policy enforcement, monitoring, evidence, incident response, material changes, and ongoing reassessment. |

> **Key principle:** Assurance does not automatically travel with the platform. Changes in data, configuration, integrations, permissions, model/version, tools, autonomy, authority, or operating context can change the assurance claim and the evidence required to support it.

---

## 4. NIST AI RMF Assessment

The ratings below are **portfolio assessment ratings**, not official NIST scores.

| Function | Public Evidence Reviewed | Rating |
|---|---|---|
| **GOVERN** | Public AI governance/safety policies, Responsible Scaling Policy, usage policies, enterprise governance capabilities, and ISO/IEC 42001 certification | 🟢 **Strong** |
| **MAP** | Enterprise identity/access configuration, connectors/MCP controls, data and deployment-context capabilities; deployers must still map their own purpose, users, data, tools, actions, and impacts | 🟢 **Strong** |
| **MEASURE** | Public model/safety evaluation and monitoring practices provide provider evidence, but deployment-specific control effectiveness and action-boundary testing remain the enterprise's responsibility | 🟡 **Moderate** |
| **MANAGE** | Enterprise administrative controls, Claude Code permissions/sandboxing, compliance capabilities, provider safeguards, and deployer risk-treatment mechanisms | 🟢 **Strong** |

---

## 5. ISO/IEC 42001 Evidence Review

This is a **focused public-evidence review** of governance areas relevant to Claude Enterprise and Claude Code. It is not a complete ISO/IEC 42001 conformity assessment.

| Governance Area | Public Evidence Reviewed | Assessment |
|---|---|---|
| **AI Policy & Leadership** | Public governance, safety, usage, and Responsible Scaling Policy materials | **Public Evidence** |
| **AI Management System / Independent Certification** | Public ISO/IEC 42001:2023 certification information for Anthropic's AI management system | **Public Evidence** |
| **Enterprise Administration & Security** | Public information on identity, roles/permissions, audit/compliance capabilities, retention, and enterprise controls | **Public Evidence** |
| **Deployment-Specific Risk Assessment** | Provider evidence can inform assessment, but the enterprise's intended use, data, actions, impacts, and operating context require deployment-specific evidence | **Review Further** |
| **Tool / MCP / Integration Governance** | Public controls exist for connectors, MCP permissions, tool permissions, file restrictions, and sandboxing; enterprise-specific configurations require verification | **Review Further** |
| **Deployment Control Effectiveness** | Public provider controls do not establish that the enterprise's configured controls operate effectively in its deployment | **Review Further** |
| **Ongoing Enterprise Assurance** | Provider monitoring/compliance capabilities can support assurance; deployers must establish their own monitoring, evidence, incidents, change triggers, and reassessment | **Review Further** |

**Interpretation:** **Public Evidence** means relevant governance information was observable in the public materials reviewed. **Review Further** means the deploying organisation should obtain additional assurance evidence or perform deployment-specific due diligence before relying on that area.

> Certification and provider controls provide useful assurance inputs. They do not replace governance of the enterprise's specific data, identities, permissions, integrations, tools/MCP servers, actions, and operating environment.

---

## 6. What Changes With Agentic AI

As AI moves from generating content toward using tools and executing actions, the governance surface expands.

`IDENTITY & ACCESS → DATA BOUNDARIES → TOOL/MCP PERMISSIONS → EXECUTION BOUNDARIES → HUMAN APPROVAL → CONTAINMENT → LOGGING → CONTINUOUS ASSURANCE`

| Governance Dimension | Governance Question |
|---|---|
| **Identity & Authority** | Who or what is acting, and under whose authority? |
| **Permissions** | What data, systems, files, repositories, tools, and services can the agent access? |
| **Tools / MCP** | Which connectors, APIs, tools, and MCP servers are approved? |
| **Execution Boundaries** | What actions can the agent execute, and what is prohibited? |
| **Human Oversight** | Which consequential actions require approval, override, or escalation? |
| **Containment** | How is the blast radius limited if the agent behaves unexpectedly or is compromised? |
| **Monitoring** | Can abnormal behaviour, policy violations, failed actions, and changes be detected? |
| **Auditability** | Can the enterprise reconstruct authorization, decision, action, approval, and outcome? |

---

## 7. Deployer Agentic AI Controls & Framework Mapping

*Representative controls shown for illustration. The mappings below are practical portfolio crosswalks, not official equivalence determinations or a complete regulatory/conformity mapping.*

| Control | What We Expect | NIST AI RMF | ISO/IEC 42001 | EU AI Act — Where Applicable |
|---|---|---|---|---|
| **System / Agent Inventory** | Owner, purpose, risk, autonomy, data, integrations, tools, actions, and regulatory role documented | **GOVERN / MAP** | **Clauses 4, 6 & 8** — context, planning, operation | **Arts. 6, 9, 26** — classification, risk management and deployer responsibilities for applicable high-risk use |
| **Identity & Least Privilege** | Human, service, workload, and agent identities identified; permissions limited to approved need | **GOVERN / MAP / MANAGE** | **Clauses 7 & 8** — support and operational controls | **Arts. 14, 15, 26** — oversight, robustness/security and deployer controls where applicable |
| **Data Boundaries** | Sensitive data access follows classification, purpose, retention, quality, and access requirements | **MAP / MEASURE / MANAGE** | **Clauses 6 & 8 + Annex A data controls** | **Art. 10** for applicable high-risk AI data/data-governance requirements; other privacy law may separately apply |
| **Tool / MCP Governance** | Approved tools, connectors, APIs, and MCP servers are explicitly governed | **GOVERN / MAP / MANAGE** | **Clauses 6 & 8** — risk planning and operational control | **Arts. 9, 15, 26** where the integration affects an applicable high-risk deployment |
| **Action Boundaries** | Permitted/prohibited actions and parameters are defined and technically enforced | **GOVERN / MAP / MANAGE** | **Clauses 6 & 8** | **Arts. 9, 14, 15, 26** where applicable |
| **Human Oversight** | Consequential actions have appropriate approval, override, or escalation | **GOVERN / MAP / MANAGE** | **Clauses 5, 6 & 8** | **Art. 14** and relevant **Art. 26** deployer obligations for applicable high-risk systems |
| **Runtime Enforcement** | Critical policy is enforced in the execution path, not solely through prompts | **MEASURE / MANAGE** | **Clauses 8 & 9** — operation and performance evaluation | **Arts. 9, 15, 26** where applicable |
| **Sandboxing / Containment** | Filesystem, network, execution, credential, and environment boundaries limit blast radius where appropriate | **MAP / MEASURE / MANAGE** | **Clauses 6, 8 & 9** | **Art. 15** robustness, accuracy and cybersecurity requirements for applicable high-risk systems |
| **Logging & Traceability** | Authorization, decision, approval, action, result, and exceptions can be reconstructed | **GOVERN / MEASURE / MANAGE** | **Clauses 7, 8 & 9** — documented information, operation and evaluation | **Arts. 12 & 26** where logging/deployer obligations apply |
| **Runtime Monitoring** | Policy violations, unusual behaviour, failed actions, permission changes, security events, and drift are monitored | **MEASURE / MANAGE** | **Clauses 9 & 10** — performance evaluation and improvement | **Arts. 9, 26 and 72** where applicable |
| **Incident / Kill Capability** | Unsafe or unauthorised behaviour can be contained, disabled, investigated, and remediated | **MANAGE** | **Clauses 8, 9 & 10** | **Arts. 26, 72 and 73** where applicable |
| **Material Change Review** | Model, data, prompt, configuration, integration, permission, tool/MCP, autonomy, or purpose changes trigger reassessment where material | **GOVERN / MAP / MEASURE / MANAGE** | **Clauses 6, 8, 9 & 10** | **Art. 25** role implications in specified circumstances; reassess classification and obligations when system or intended purpose materially changes |

> **Crosswalk principle:** Framework alignment does not itself demonstrate control effectiveness. The enterprise still needs evidence that the mapped control is appropriately designed, operating effectively, and holding at the relevant decision or action boundary.

---

## 8. Key Considerations for Provider and Deployer

| Consideration | Provider Assurance Input | Deployer Governance Requirement | Priority |
|---|---|---|---|
| **Enterprise Identity & Access** | Enterprise identity/admin capabilities | Map users, service/agent identities, delegated authority, credentials, and least privilege | **High** |
| **Tools / MCP / Integrations** | Connector, MCP, permission, and sandboxing capabilities | Approve specific tools/MCP servers, validate scope, and test unauthorized paths | **High** |
| **Consequential Actions** | Platform capabilities can support controlled execution | Define action thresholds, boundaries, approval requirements, and evidence | **High** |
| **Prompt Injection / Untrusted Content** | Provider safeguards and containment capabilities | Test files, repositories, messages, web content, tool responses, APIs, connectors, and MCP against permission/action boundaries | **High** |
| **Control Effectiveness** | Provider controls establish a foundation | Demonstrate design, operating, and action-boundary effectiveness in the enterprise deployment | **High** |
| **Runtime Monitoring & Incidents** | Compliance/observability capabilities can provide inputs | Establish monitoring, alerts, containment, investigation, remediation, and reassessment | **High** |
| **Regulatory Role Determination** | Provider documentation can inform classification | Reassess intended use and regulatory role at intake and material change | **High where applicable** |
| **Provider / Model Changes** | Provider releases and documentation | Assess materiality; perform targeted regression/control testing and reapproval where needed | **Medium** |
| **Evidence Freshness** | Provider assurance can be inherited as an input | Determine whether current evidence still supports the enterprise's assurance decision | **Medium** |

**Priority** means deployer governance action priority, not a risk rating assigned to Anthropic.

---

## 9. Control Presence vs. Control Effectiveness

A control being documented or configured does not demonstrate that it works when needed.

| Assurance Level | Question | Example Evidence |
|---|---|---|
| **Control Presence** | Does the required control exist? | Approval workflow, tool allow-list, sandbox, logging configuration |
| **Design Effectiveness** | Is the control appropriately designed for the identified risk? | Defined thresholds, appropriate approver, scoped permissions, enforced boundaries |
| **Operating Effectiveness** | Does the control consistently operate as designed? | Test results, sampled events, blocked attempts, monitoring records |
| **Action-Boundary Effectiveness** | Did the control actually hold when the consequential action was attempted or executed? | Authorization decision, permission check, approval, execution result, audit evidence |

> **For Agentic AI, control presence is not enough. Assurance requires evidence that the control actually held at the action boundary.**

---

## 10. Agent Identity & Prompt-Injection Assurance

Least privilege is meaningful only when the organisation knows **which principal is acting and what authority it carries**.

| Assurance Area | What to Verify |
|---|---|
| **Human Identity** | Who initiated or authorised the task? |
| **Service / Workload Identity** | Which technical identity executes the workflow? |
| **Agent Identity** | Is the agent distinguishable and attributable where applicable? |
| **Delegated Authority** | What authority has been delegated and by whom? |
| **Credentials** | What credentials/tokens are available to the workflow and tools? |
| **Permissions** | What systems, data, repositories, tools, APIs, and MCP servers can be reached? |
| **Prompt-Injection Testing** | Can untrusted content from files, code, messages, web content, tools, connectors, APIs, or MCP cause the agent to cross a permission, data, tool, or action boundary? |
| **Evidence** | Can identity, authorization, attempted action, control decision, and outcome be reconstructed? |

---

## 11. Consequential Actions & Action Assurance

A **consequential action** is an AI-enabled action that could materially affect a person/customer, financial transaction, enterprise system, sensitive data, security posture, regulatory obligation, or important business process.

Examples include production code deployment, privileged configuration changes, external communications, customer/account updates, access changes, financial actions, sensitive-data movement, or privileged tool execution.

| Action Assurance Check | Question |
|---|---|
| **Authority** | Is the agent or requesting principal authorised to perform this class of action? |
| **Permissions** | Are the current permissions valid and appropriately scoped? |
| **Conditions** | Are relevant risk, policy, data, business, and operational conditions satisfied? |
| **Boundaries** | Is the requested action within approved tools, parameters, systems, and thresholds? |
| **Approval** | Is human approval required, and was it obtained from an authorised approver? |
| **Execute / Block** | Did the system execute only the authorised action, or block the prohibited path? |
| **Evidence** | Can the authorization, decision, approval, action, outcome, and exception be reconstructed? |

---

## 12. Two Assurance Loops

| Deployment Assurance — System Level | Action Assurance — Action Level |
|---|---|
| **MONITOR → DETECT → RESPOND → REMEDIATE → REASSESS** | **AUTHORITY → PERMISSIONS → CONDITIONS → BOUNDARIES → APPROVAL → EXECUTE / BLOCK → EVIDENCE** |
| Determines whether the deployed system remains governed as models, data, configuration, integrations, permissions, tools, autonomy, incidents, and operating conditions change. | Determines whether a specific consequential action remains authorised and controlled at the point of execution. |

These loops work together: **deployment assurance evaluates the system over time; action assurance evaluates whether the control held for the specific action.**

---

## 13. Evidence at the Action Boundary

For consequential actions, evidence should allow an independent reviewer to reconstruct what happened.

| Evidence Element | Example |
|---|---|
| **Authorization** | Identity, role, delegated authority |
| **Context** | Relevant system state, policy version, model/version, data/tool context |
| **Decision** | Permission/policy decision and applicable parameters |
| **Approval** | Approver identity, timestamp, scope, conditions |
| **Action** | Tool/API/MCP invocation or execution performed |
| **Outcome** | Success, failure, blocked action, resulting change |
| **Exception / Override** | Override authority, reason, incident/escalation reference |
| **Follow-Up** | Remediation, control change, reassessment outcome |

**Evidence chain:**  
`AUTHORIZATION → CONTEXT → DECISION → APPROVAL → ACTION → OUTCOME → EXCEPTION / OVERRIDE → REASSESSMENT`

---

## 14. Material Change & Vendor-Side Change Review

A favorable assurance conclusion should not be treated as permanent.

| Change Trigger | Governance Response |
|---|---|
| **Provider Model / Version Change** | Assess materiality and deployment impact |
| **Capability / Behaviour Change** | Reassess affected risks and controls |
| **Enterprise Data Change** | Revalidate classification, access, privacy, and data boundaries |
| **Prompt / Instruction Change** | Version, test, approve, and monitor where material |
| **Configuration Change** | Revalidate control design and permissions |
| **New Connector / API / MCP / Tool** | Perform due diligence, approve scope, and test boundaries |
| **Permission / Identity Change** | Reassess least privilege and delegated authority |
| **Autonomy / Action-Scope Increase** | Reassess risk tier, oversight, action controls, and evidence |
| **Business-Purpose / Regulatory-Role Change** | Reclassify use case and applicable obligations |
| **Significant Incident / Failure Pattern** | Contain, investigate, remediate, retest, and reassess |

**Vendor/model change path:**  
`PROVIDER CHANGE → IMPACT ASSESSMENT → TARGETED REGRESSION / CONTROL TESTING → APPROVAL → CONTINUED USE / RELEASE → MONITORING`

---

## 15. Evidence-Sensitive Assurance Decision

Governance should make decisions using **current evidence at the relevant decision point**.

| Decision | Meaning |
|---|---|
| **PROCEED** | Current evidence supports deployment or continued operation |
| **PROCEED WITH CONDITIONS** | Operation is permitted subject to defined remediation, controls, monitoring, or time-bound conditions |
| **CHANGE** | Design, configuration, permission, integration, or control changes are required before the assurance claim can be supported |
| **STOP** | Risk is unacceptable or evidence is insufficient to support the proposed or continued activity |

A previously favorable assessment can be downgraded when monitoring, incidents, provider changes, configuration, integrations, permissions, autonomy, business purpose, or operating conditions change.

> **Governance is operational and revisable. The question is not whether the system passed governance once, but whether current evidence still supports the current decision.**

---

## 16. Example Control-Effectiveness Test

**Scenario:** Claude Code assists an engineering workflow that can prepare code changes, but production deployment requires authorised human approval.

| Test Step | Expected Result |
|---|---|
| Attempt production deployment without required approval | **Blocked** |
| Attempt approval using an unauthorised identity | **Rejected** |
| Obtain approval from an authorised approver | **Accepted** |
| Compare approved artifact/action with executed artifact/action | **Exact authorised scope maintained** |
| Attempt prompt-injection/bypass path | **Permission/action boundary remains enforced** |
| Review logs | **Identity, authorization, approval, execution, outcome, and exceptions reconstructable** |
| Test containment/rollback | **Unsafe result can be contained and remediated** |

The control is not considered effective merely because an approval feature exists. Evidence must demonstrate that **unauthorised paths were blocked and the authorised path operated as designed**.

---

## 17. Framework & Regulatory Traceability

This section provides a consolidated governance view. It is intended as a **practical crosswalk**, not a legal determination or official mapping issued by NIST, ISO, or the European Union.

| Governance Objective | NIST AI RMF | ISO/IEC 42001 | EU AI Act — Where Applicable |
|---|---|---|---|
| **Governance & Accountability** | GOVERN | Clauses 4–5 | Arts. 16, 26 |
| **Use-Case Context & Classification** | MAP | Clauses 4 & 6 | Arts. 6, 9, 25, 26 |
| **Risk Assessment** | MAP / MEASURE | Clauses 6 & 8 | Art. 9 |
| **Data Governance** | MAP / MEASURE / MANAGE | Clauses 6 & 8 + Annex A controls | Art. 10 |
| **Human Oversight** | GOVERN / MANAGE | Clauses 5, 6 & 8 | Art. 14 |
| **Accuracy / Robustness / Cybersecurity** | MEASURE / MANAGE | Clauses 8 & 9 | Art. 15 |
| **Logging / Traceability** | GOVERN / MEASURE | Clauses 7–9 | Arts. 12, 26 |
| **Control Testing** | MEASURE | Clauses 8 & 9 | Supports applicable risk/control obligations |
| **Monitoring** | MEASURE / MANAGE | Clause 9 | Arts. 26 & 72 where applicable |
| **Incident Response** | MANAGE | Clauses 8–10 | Arts. 26, 72 & 73 where applicable |
| **Material Change** | GOVERN / MAP / MEASURE / MANAGE | Clauses 6, 8, 9 & 10 | Art. 25 and related classification obligations where applicable |
| **Continual Improvement** | GOVERN / MEASURE / MANAGE | Clause 10 | Supports ongoing risk-management and post-market obligations where applicable |

### How to Read This Crosswalk

- **NIST AI RMF** provides the risk-management operating structure: **GOVERN → MAP → MEASURE → MANAGE**.
- **ISO/IEC 42001** provides an AI management-system structure for establishing, operating, evaluating, and continually improving AI governance.
- **EU AI Act** establishes legal obligations where its provisions apply to the organisation, role, system, and use case.
- A single enterprise control may support **multiple frameworks simultaneously**.
- Framework mapping does **not** demonstrate that a control is effective.

> **One control can support multiple governance obligations, but one evidence set should only be relied upon where it actually demonstrates the required control outcome.**

---

## 18. Governance Operating Model

Effective AI governance extends beyond AI Governance or Program Management alone.

| Function | Primary Responsibility |
|---|---|
| **Business / Product Owner** | Purpose, value, business accountability, acceptable use |
| **AI Governance** | Classification, governance requirements, controls, decision gates, evidence expectations |
| **Engineering** | Architecture, integration, execution boundaries, technical remediation |
| **Security / IAM** | Identity, least privilege, credentials, threat controls, containment |
| **Data Governance** | Data classification, access, lineage, retention |
| **Privacy / Legal / Compliance** | Privacy, contractual, regulatory, and legal requirements |
| **Operations** | Runtime procedures, monitoring, support, incident handling |
| **Risk / Assurance** | Independent challenge, control testing, assurance conclusions |
| **Internal Audit** | Independent assurance according to audit mandate |
| **Program / Delivery Management** | Owners, milestones, dependencies, governance forums, release readiness, evidence coordination, escalation |

---

## 19. Delivery & Governance Gates

| Gate | Governance Focus | Decision Evidence |
|---|---|---|
| **1 — Intake** | Purpose, owner, users, data, provider, regulatory role, risk, agentic capability | Initial classification and ownership |
| **2 — Design** | Architecture, identities, permissions, data, tools/MCP, action boundaries, oversight | Control design and accountability |
| **3 — Pre-Production Validation** | Control effectiveness, adversarial/prompt-injection testing, blocked paths, evidence | Validation results and residual risk |
| **4 — Production Readiness** | Approvals, monitoring, incidents, rollback/kill capability, operations | Release-readiness evidence |
| **5 — Ongoing Assurance** | Monitoring, incidents, material changes, vendor/model updates, evidence freshness, retesting | Continue / condition / change / stop |

---

## 20. Overall Assessment

**Posture:** Anthropic's public materials provide meaningful provider-level assurance inputs, including enterprise administration and security controls, Claude Code permissions and sandboxing, model and safety practices, compliance capabilities, and ISO/IEC 42001 certification of its AI management system. Overall, there is **strong public governance evidence at the platform level**.

**Key consideration:** Provider assurance provides an important foundation, but it does not by itself establish that a specific enterprise deployment of Claude is adequately governed. From the **deployer perspective**, assurance depends on how Claude is configured and used, including the specific **purpose, data, identities, permissions, tools/MCP, integrations, autonomy, actions, human oversight, runtime controls, and supporting evidence**.

**Assessment outcome:** From the **deployer perspective**, the more Claude is enabled to access enterprise systems and take actions, the more governance must move beyond reviewing documented controls toward **testing operating effectiveness and demonstrating that the appropriate controls held at consequential action boundaries**.

**Practical implication:** Use provider assurance as an input. Make the enterprise assurance decision using **current deployment-specific and operational evidence**.

---

## 21. Practitioner Takeaway

As enterprise AI gains access to data, code, tools, connectors, MCP servers, and external systems, governance must control not only **what the AI can generate**, but also **what it can access, change, and execute**.

For AI Governance leaders, the progression is:

**Provider Assurance → Deployment Governance → Control Effectiveness → Action Assurance → Evidence → Decision → Reassessment**

For AI Program and Delivery Managers, this means translating governance requirements into **clear ownership, control owners, milestones, dependencies, validation activities, approval gates, release readiness, evidence, escalation paths, and ongoing assurance**, while coordinating with Engineering, Security, Data, Privacy, Legal/Compliance, Risk, Operations, and Internal Audit.

The practical test is no longer simply:

> **“What controls exist?”**

It becomes:

> **“What current evidence shows the control worked at the decision or action boundary, and is that evidence sufficient to proceed, proceed with conditions, change, or stop?”**

---

## 22. Portfolio Progression

| Case Study | Governance Progression |
|---|---|
| **Use Case 07 — Microsoft 365 Copilot** | Govern the enterprise AI **use case** |
| **Use Case 08 — Salesforce Agentforce** | Agentic AI & Govern the **agent, autonomy, permissions, and actions** |
| **Use Case 09 — Anthropic Claude Enterprise + Claude Code** | Agentic AI & Govern the agent, autonomy, permissions, and actions. Test **control effectiveness** and demonstrate that controls held at the **action boundary** |

`FRAMEWORK ALIGNMENT → OPERATIONAL GOVERNANCE → CONTROL EFFECTIVENESS → EVIDENCE-BASED ASSURANCE`

---

## 23. Public Sources

**Primary Anthropic sources:**

- [Claude Code Sandboxing](https://www.anthropic.com/engineering/claude-code-sandboxing)
- [Claude Code and Admin Controls for Business Plans](https://www.anthropic.com/news/claude-code-on-team-and-enterprise)
- [Anthropic ISO/IEC 42001 Certification](https://www.anthropic.com/news/anthropic-achieves-iso-42001-certification-for-responsible-ai)
- [Anthropic Transparency Hub](https://www.anthropic.com/transparency/voluntary-commitments)
- [Anthropic Privacy Center — Certifications](https://privacy.anthropic.com/en/articles/10015870-what-certifications-has-anthropic-obtained)

**Regulatory and governance sources:**

- [European Union — Regulation (EU) 2024/1689 (AI Act)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
- [NIST AI RMF Playbook](https://www.nist.gov/itl/ai-risk-management-framework/nist-ai-rmf-playbook)
- [ISO/IEC 42001:2023 — AI Management Systems](https://www.iso.org/standard/81230.html)

---

## 24. Sources & Limitations

**Primary:** Anthropic public documentation covering Claude Enterprise, Claude Code, permissions and sandboxing, enterprise administration, safety/evaluation practices, transparency, and ISO/IEC 42001 certification · European Union AI Act · NIST AI RMF · ISO/IEC 42001 public information.

Sources are prioritised in this order: **(1) Anthropic official/public materials, (2) European Commission/EUR-Lex, (3) NIST official sources, and (4) ISO public information where appropriate.** Conclusions about Anthropic are not drawn from competitor or third-party commercial analysis.

This assessment relies solely on publicly available information. It does not include confidential Anthropic documentation, customer-specific architecture or configuration, private audit reports, deployment-specific logs, interviews with control owners, operating-effectiveness samples from a real enterprise deployment, or independent technical testing of a specific customer implementation.

**Independent educational portfolio assessment** based solely on publicly available information. Not affiliated with, commissioned by, or reviewed by Anthropic. This is not a formal audit, certification, legal opinion, or compliance determination. **Review Further** identifies areas where additional deployer due diligence or non-public evidence may be appropriate; it does not indicate a confirmed deficiency in Anthropic's controls or practices.

*Time-sensitive facts, including certification status, product capabilities, model integrations, and regulatory requirements, should be independently re-verified before reliance in a real advisory, procurement, compliance, or deployment decision.*

---

*Karun Mehta · AIGP (AI Governance Professional)*
