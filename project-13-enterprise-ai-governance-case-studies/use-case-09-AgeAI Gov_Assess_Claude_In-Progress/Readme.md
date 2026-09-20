# Use Case 09: Agentic AI Governance Assessment — Anthropic Claude Enterprise + Claude Code  - In-progress

> **Type:** Independent public-evidence AI Governance Assessment  
> **Subject:** Anthropic Claude Enterprise and Claude Code  
> **Purpose:** Demonstrate how an enterprise AI Governance function can move from provider assurance to deployment governance, control-effectiveness testing, action assurance, evidence-based decisions, and continuous reassessment.

---

## Executive Summary

As enterprise AI gains access to organizational data, code, files, tools, connectors, APIs, and MCP-enabled capabilities, governance must control not only **what the AI can generate**, but also **what it can access, change, and execute**.

This case assesses publicly available assurance information for Anthropic and then shifts to the deploying organization's responsibilities.

The central governance principle is:

> **Provider assurance is a foundation. It is not automatic assurance of the deployed system.**

A deployment changes the governed object. Enterprise data, configuration, identities, permissions, tools, integrations, autonomy, business context, and consequential actions can change both the risk and the evidence required to support an assurance decision.

### Governance Lifecycle

**INVENTORY → ASSESS → CONTROL → TEST → MONITOR → ASSURE → IMPROVE**

### Assurance Progression

**Control Presence → Control Effectiveness → Action Assurance → Evidence → Decision → Reassessment**

---

## 1. Assessment Scope

This assessment considers two related Anthropic offerings:

- **Claude Enterprise** — enterprise use of Claude with organizational administration and access controls.
- **Claude Code** — an agentic coding environment capable of reading files, editing code, running commands, and interacting with approved tools and services.

They are treated as related offerings, not as one identical product.

This is a **public-evidence assessment**, not a formal audit. Public provider evidence is used as an input to enterprise due diligence; deployment-specific assurance still requires evidence from the deploying organization.

---

## 2. AI System Inventory

| Attribute | Assessment |
|---|---|
| **Provider** | Anthropic |
| **Enterprise surfaces considered** | Claude Enterprise and Claude Code |
| **Typical users** | Employees, developers, engineering teams, enterprise functions |
| **Data** | Enterprise information made available through user access, files, connectors, repositories, tools, or configured integrations |
| **Capabilities** | Reasoning, content generation, code assistance, file interaction, tool use, command execution, workflow assistance |
| **Agentic surface** | Claude Code and tool-enabled workflows can move beyond generation into actions |
| **Governance implication** | Risk depends on deployed purpose, data, permissions, integrations, autonomy, and actions |

### EU AI Act Role and Use-Case Determination

Do not classify the vendor platform once and assume that classification travels unchanged into every deployment.

At **initial intake** and after **material change**, determine:

1. The specific intended purpose.
2. Whether the deployment falls into a regulated or high-risk context.
3. The organization's applicable regulatory role.
4. Whether modifications to an AI system or its intended purpose could change the organization's obligations.
5. What additional evidence or conformity activity is required.

For applicable high-risk systems, Article 25 of the EU AI Act contains circumstances in which another party can become the provider, including certain substantial modifications or changes of intended purpose.

Therefore:

> **Regulatory role determination should be a governance checkpoint, not a one-time label.**

---

## 3. Provider Assurance vs. Deployer Responsibility

Agentic AI governance operates through a **shared-responsibility model**.

### Provider Assurance — Anthropic

Publicly available Anthropic materials describe controls and assurance mechanisms including:

- Enterprise identity and administration capabilities.
- Role-based access and enterprise configuration.
- Connector and MCP permission management.
- Claude Code permission controls.
- Filesystem and network sandboxing for Claude Code.
- Model and safety evaluation activities.
- Post-deployment monitoring and safety processes.
- ISO/IEC 42001 certification of Anthropic's AI management system.
- Compliance and audit-related capabilities for enterprise customers.

These provide an important **provider-level assurance foundation**.

### Deployer Responsibility — Enterprise

The deploying organization remains responsible for governance of its actual deployment, including:

- Business purpose and use-case classification.
- Accountable business and technical owners.
- Enterprise data made available to Claude.
- User, service, and agent identities.
- Least-privilege access.
- Connectors, APIs, tools, repositories, and MCP servers.
- Action and execution boundaries.
- Human approvals.
- Runtime policy enforcement.
- Monitoring and incident response.
- Evidence retention.
- Material-change management.
- Ongoing reassessment.

> **Assurance does not automatically travel with the platform.**

A well-governed provider platform can still support a weak deployment if enterprise configuration, access, integration, oversight, or operational controls are inadequate.

---

## 4. NIST AI RMF Assessment

The following are **portfolio assessment ratings**, not official NIST scores.

| Function | Public-Evidence View | Governance Interpretation |
|---|---|---|
| **GOVERN** | 🟢 Strong | Public governance, safety, policy, and assurance structures provide a useful provider-level foundation |
| **MAP** | 🟢 Strong | Enterprise deployment still requires context-specific mapping of purpose, users, data, tools, integrations, and impacts |
| **MEASURE** | 🟡 Moderate | Public evidence supports provider evaluation activities, while deployers still need deployment-specific control and outcome testing |
| **MANAGE** | 🟢 Strong | Provider safeguards and enterprise controls can support risk treatment, but operating effectiveness must be demonstrated in the deployment |

---

## 5. ISO/IEC 42001 Public-Evidence Review

This is a focused public-evidence review. It is **not a complete ISO/IEC 42001 conformity assessment**.

| Governance Area | Assessment |
|---|---|
| **AI Policy and Leadership** | **Public Evidence** |
| **AI Management System / Independent Certification** | **Public Evidence** |
| **Security and Enterprise Administration** | **Public Evidence** |
| **Deployment-Specific Risk Assessment** | **Review Further** |
| **Tool / MCP / Integration Governance** | **Review Further** |
| **Deployment-Specific Control Effectiveness** | **Review Further** |
| **Ongoing Enterprise Assurance** | **Review Further** |

### Interpretation

**Public Evidence** means relevant information was observable in the public materials reviewed.

**Review Further** means the deploying organization should obtain additional evidence or perform deployment-specific due diligence.

> **Review Further does not indicate a confirmed deficiency in Anthropic's controls or practices.**

---

## 6. What Changes With Agentic AI

Traditional Generative AI governance often concentrates on:

- Output quality.
- Privacy.
- Bias and fairness.
- Hallucination.
- Appropriate use.
- Security.

Agentic capability expands the governance surface because AI may now interact with enterprise systems and take actions.

### Agentic Governance Surface

**Identity & Access → Data Boundaries → Tool/MCP Permissions → Execution Boundaries → Human Approval → Sandboxing/Containment → Logging → Continuous Assurance**

The governance question therefore becomes:

> **What is this AI authorized to do, under whose authority, within what boundaries, and what evidence demonstrates that those boundaries actually held?**

---

## 7. Deployer Agentic AI Control Set

The following are representative controls for governance illustration. They are not an exhaustive conformity checklist.

| Control | Expected Enterprise Control |
|---|---|
| **Agent / System Inventory** | Owner, purpose, users, autonomy, data, integrations, tools, actions, and risk documented |
| **Identity & Least Privilege** | Human, service, and agent identities are explicit; permissions are limited to approved need |
| **Data Boundaries** | Sensitive data access follows classification, purpose, retention, and access requirements |
| **Tool & MCP Governance** | Approved tools, MCP servers, and connectors are allow-listed and governed |
| **Action Boundaries** | Permitted and prohibited actions are technically and procedurally defined |
| **Human Oversight** | Consequential actions have appropriate approval, override, or escalation |
| **Runtime Enforcement** | Critical policies are enforced in the execution path rather than relying only on prompts |
| **Sandboxing / Containment** | File, network, execution, and environment boundaries limit blast radius where appropriate |
| **Logging & Traceability** | Authorization, decision, action, result, approval, and exception evidence can be reconstructed |
| **Runtime Monitoring** | Policy violations, unusual behavior, failed actions, permission changes, security events, and drift are monitored |
| **Incident / Kill Capability** | Unsafe or unauthorized behavior can be contained, disabled, and investigated |
| **Material Change Review** | Changes in model, data, configuration, integrations, permissions, tools/MCP, autonomy, or operating context trigger reassessment |

---

## 8. Agent Identity and Prompt-Injection Assurance

Least privilege is meaningful only when the organization knows **which principal is acting**.

For each agentic deployment, document:

- Invoking human identity.
- Service or workload identity.
- Agent identity where applicable.
- Inherited and delegated permissions.
- Credentials available to tools.
- Accessible systems and data.
- Permitted actions.
- Approval authority.

### Prompt-Injection Assurance

Testing should include untrusted content entering through:

- Files and documents.
- Repositories and code.
- Inbound email or messages.
- Web content.
- Tool responses.
- Connectors.
- APIs.
- MCP servers.

The assurance question is not merely whether prompt-injection protections exist.

The stronger question is:

> **Can malicious or untrusted content cause the agent to cross a permission, data, tool, or action boundary?**

---

## 9. Control Presence Is Not Control Effectiveness

A documented control answers:

> **Does the control exist?**

Assurance must also answer:

> **Does the control operate as intended?**

For example:

- A permission boundary may exist but be overly broad.
- Human approval may exist but be bypassable.
- A kill switch may exist but fail to contain credentials or active sessions.
- Logging may exist but omit authorization or action outcome.
- A tool allow-list may exist while an MCP server exposes broader capabilities than expected.

Therefore, this case distinguishes three levels of control assurance.

### 1. Design Effectiveness

**Is the control appropriately designed for the risk?**

### 2. Operating Effectiveness

**Does the control consistently operate as designed?**

### 3. Action-Boundary Effectiveness

**Did the control actually hold when the consequential action was attempted or executed?**

---

## 10. Consequential Actions

A **consequential action** is an AI-enabled action that could materially affect:

- A person or customer.
- A financial transaction.
- An enterprise system.
- Sensitive data.
- Security posture.
- A regulatory obligation.
- An important business process.

Examples include:

- Deploying code to production.
- Changing production configuration.
- Sending external communications.
- Updating customer or account records.
- Granting or changing access.
- Executing financial actions.
- Deleting or moving sensitive data.
- Invoking privileged tools.

> **Higher consequence should produce stronger authorization, testing, evidence, monitoring, and human oversight.**

---

## 11. Two Assurance Loops

Agentic AI requires assurance at both the **system level** and the **individual action level**.

### Deployment Assurance — System Level

**MONITOR → DETECT → RESPOND → REMEDIATE → REASSESS**

This loop asks whether the deployed system remains governed as conditions change.

Monitor:

- Model and version changes.
- Data and configuration.
- Integrations.
- Permissions.
- Tools and MCP servers.
- Autonomy.
- Incidents.
- Policy violations.
- Security events.
- Performance and behavioral drift.
- Operating context.

### Action Assurance — Action Level

**AUTHORITY → PERMISSIONS → CONDITIONS → BOUNDARIES → APPROVAL → EXECUTE / BLOCK → EVIDENCE**

This loop asks whether the specific action should be allowed **at the point of execution**.

For a consequential action, determine:

1. Who or what requested the action?
2. Does that principal have authority?
3. Are current permissions sufficient and appropriate?
4. Are relevant conditions still satisfied?
5. Is the action inside approved boundaries?
6. Is human approval required?
7. Was the action executed exactly as authorized?
8. Was sufficient evidence captured?

---

## 12. Evidence at the Action Boundary

For consequential actions, the evidence trail should allow an independent reviewer to reconstruct:

**Authorization → Context → Decision → Approval → Action → Outcome → Exception / Override**

Useful evidence may include:

- Identity and role.
- Timestamp.
- Policy version.
- Model/version.
- Prompt or instruction context where appropriate.
- Tool or MCP invocation.
- Permission decision.
- Relevant parameters.
- Approval identity.
- Execution result.
- System response.
- Exception or override.
- Incident reference.
- Remediation or reassessment outcome.

> **For Agentic AI, control presence is not enough. Assurance requires evidence that the control actually held at the action boundary.**

---

## 13. Example Control-Effectiveness Test

### Scenario

A Claude Code-enabled engineering workflow may prepare code changes but requires authorized human approval before a production deployment.

### Control Objective

**Prevent unauthorized AI-assisted production deployment.**

### Test Procedure

1. Attempt production deployment without approval.  
   **Expected:** Blocked.

2. Attempt approval using an unauthorized identity.  
   **Expected:** Rejected.

3. Obtain approval from an authorized approver.  
   **Expected:** Accepted.

4. Verify the deployed artifact or action matches what was approved.

5. Verify identity, approval, execution, outcome, and exceptions are logged.

6. Verify a prompt-injection attempt cannot bypass the deployment boundary.

7. Verify containment or rollback can be initiated if the action produces an unsafe result.

### Assurance Evidence

The control is not considered effective merely because an approval feature exists.

Evidence should demonstrate that:

- Unauthorized paths were blocked.
- Unauthorized approvers were rejected.
- The authorized path operated correctly.
- The executed action matched the approved action.
- Required evidence was captured.

---

## 14. Material Change and Vendor-Side Change Triggers

A previously favorable assurance conclusion should **not** be treated as permanent.

Trigger reassessment when there is a material change in:

- Provider model or model version.
- Model behavior or capability.
- Enterprise data.
- System prompt or instructions.
- Configuration.
- Connector or integration.
- Tool or MCP server.
- Permissions or identity model.
- Autonomy level.
- Action scope.
- Human-approval design.
- Regulatory classification.
- Business purpose.
- Operating environment.
- Significant incident or failure pattern.

### Vendor-Side Model Change

A provider-side model update should be evaluated for deployment impact.

Where material:

**Provider Change → Impact Assessment → Targeted Regression / Control-Effectiveness Testing → Approval → Release / Continued Use → Monitoring**

Provider assurance evidence remains useful, but the enterprise should determine whether its **own assurance claim remains valid** after the change.

---

## 15. Evidence-Sensitive Assurance Decision

Governance should produce a decision based on **current evidence at the relevant decision point**.

### Recommended Decision States

| Decision | Meaning |
|---|---|
| **PROCEED** | Evidence supports deployment or continued operation |
| **PROCEED WITH CONDITIONS** | Operation is permitted subject to defined controls, remediation, monitoring, or time-bound conditions |
| **CHANGE** | Design, configuration, or control changes are required before the assurance claim can be supported |
| **STOP** | Risk or evidence is insufficient for the proposed or continued activity |

A previously favorable decision can be **downgraded** when:

- Monitoring identifies new risks.
- Incidents occur.
- Provider capabilities change.
- Models or versions change.
- Configuration changes.
- New integrations are introduced.
- Permissions expand.
- Autonomy increases.
- Operating conditions change.

> **Governance must remain evidence-sensitive and revisable rather than becoming a one-time framework exercise.**

---

## 16. Provider and Deployer Assurance Model

### Provider Evidence Can Support

- Vendor due diligence.
- Baseline security and governance assessment.
- Certification review.
- Understanding available platform controls.
- Procurement decisions.
- Inherited-control analysis.

### Deployer Evidence Must Support

- Deployment approval.
- Use-case risk classification.
- Identity and permission design.
- Data and integration governance.
- Tool/MCP authorization.
- Action boundaries.
- Control effectiveness.
- Human oversight.
- Runtime monitoring.
- Incident response.
- Continued operation.

> **Inherited evidence should be explicitly identified. Deployment-specific evidence should be separately demonstrated.**

---

## 17. Key Deployer Considerations

| Consideration | Priority | Governance Response |
|---|---|---|
| **Tool/MCP and Enterprise-Data Governance** | High | Inventory and approve tools, connectors, MCP servers, data access, and permissions |
| **Consequential Action Controls** | High | Establish explicit action boundaries, authorization, approval, and evidence requirements |
| **Control-Effectiveness Testing** | High | Test blocked paths, authorized paths, bypass scenarios, and operating effectiveness |
| **Agent Identity and Prompt Injection** | High | Establish principal identity, least privilege, trust boundaries, and adversarial tests |
| **Runtime Monitoring and Incident Response** | High | Monitor behavior and control events; maintain containment and escalation |
| **Regulatory Role Determination** | High where applicable | Reassess role and use-case classification at intake and material change |
| **Provider / Model Changes** | Medium | Assess materiality and trigger targeted re-testing and reapproval |
| **Assurance Evidence Freshness** | Medium | Define evidence validity, review cadence, and event-driven reassessment |

> **Priority refers to deployer governance action priority, not a risk rating assigned to Anthropic.**

---

## 18. Governance Operating Model

Effective AI governance is **not owned by Program Management alone**.

| Function | Example Responsibility |
|---|---|
| **Business / Product Owner** | Purpose, value, business accountability, acceptable use |
| **AI Governance** | Classification, governance requirements, decision gates, evidence expectations |
| **Engineering** | Technical design, integration, execution boundaries, remediation |
| **Security / IAM** | Identity, least privilege, credentials, threat controls, containment |
| **Data Governance** | Data classification, access, lineage, retention |
| **Privacy / Legal / Compliance** | Privacy, contractual, regulatory, and legal requirements |
| **Operations** | Runtime procedures, monitoring, support, incident handling |
| **Risk / Assurance** | Independent challenge, control testing, assurance conclusions |
| **Internal Audit** | Independent assurance according to audit mandate |
| **Program / Delivery Management** | Owners, milestones, dependencies, decision forums, release readiness, evidence coordination, escalation |

Governance requirements become operational only when these functions work through a common lifecycle.

---

## 19. Delivery and Governance Gates

### Gate 1 — Intake

Evaluate:

- Purpose.
- Owner.
- Users.
- Data.
- Regulatory role.
- Risk.
- Provider.
- Agentic capability.

### Gate 2 — Design

Evaluate:

- Architecture.
- Identities.
- Permissions.
- Tools and MCP.
- Data boundaries.
- Action boundaries.
- Human oversight.

### Gate 3 — Pre-Production Validation

Evaluate:

- Control design.
- Control-effectiveness testing.
- Prompt-injection and adversarial scenarios.
- Unauthorized paths.
- Human approval.
- Evidence completeness.

### Gate 4 — Production Readiness

Evaluate:

- Residual risk.
- Approvals.
- Monitoring.
- Incident response.
- Rollback and kill capability.
- Ownership.
- Operational readiness.

### Gate 5 — Ongoing Assurance

Evaluate:

- Monitoring evidence.
- Incidents.
- Material changes.
- Vendor/model updates.
- Control re-testing.
- Evidence freshness.
- Reassessment.

At each relevant gate, current evidence should support a:

**PROCEED / PROCEED WITH CONDITIONS / CHANGE / STOP**

decision.

---

## 20. Overall Assessment

Anthropic's public materials provide meaningful provider-level assurance inputs, including:

- Enterprise administration and security controls.
- Claude Code permissions and sandboxing.
- Safety and evaluation practices.
- Public governance documentation.
- ISO/IEC 42001 certification of its AI management system.

However:

> **Provider assurance does not establish that every enterprise Claude deployment is adequately governed.**

Enterprise assurance depends on the specific deployment:

**Purpose + Data + Identity + Permissions + Tools/MCP + Integrations + Autonomy + Actions + Human Oversight + Runtime Controls + Evidence**

The more Claude is enabled to **act**, the more governance must move from reviewing capabilities and documented controls toward **testing operating effectiveness and proving what happened at the action boundary**.

---

## 21. Program and Delivery Management Perspective

For AI Program and Delivery Management, execution means translating governance requirements into delivery:

**Governance Requirement → Control Owner → Delivery Requirement → Dependencies → Implementation → Testing → Evidence → Approval → Release Readiness → Production Monitoring → Remediation / Reassessment**

Program Management coordinates the operating model.

It does **not** replace the accountability of:

- Engineering.
- Security.
- Privacy.
- Legal and Compliance.
- Risk.
- Data Governance.
- Operations.
- AI Governance.

This makes governance part of **delivery and operations**, rather than a separate documentation exercise.

---

## 22. Practitioner Takeaway

Three principles summarize this case:

> **1. Provider assurance is the foundation, not the final deployment assurance claim.**

> **2. Control presence is not control effectiveness.**

> **3. The strongest assurance evidence shows that the right control held for the right action at the right decision point.**

The governance objective is therefore not simply to ask:

> **“Do we have controls?”**

It is to determine:

> **“Do we have enough current evidence to proceed, proceed with conditions, change, or stop?”**

---

## 23. Portfolio Progression

This case intentionally extends the earlier assessment series.

### Use Case 07 — Microsoft 365 Copilot

**Govern the enterprise AI use case.**

Platform assurance must be translated into governance of the enterprise's specific deployment and use case.

↓

### Use Case 08 — Salesforce Agentforce

**Govern the agent, autonomy, permissions, and actions.**

Action-taking capability requires governance to move from output oversight toward action oversight.

↓

### Use Case 09 — Anthropic Claude Enterprise + Claude Code

**Test control effectiveness and demonstrate that controls held at the action boundary.**

This moves the portfolio from:

**Framework Alignment → Operational Governance → Control Effectiveness → Evidence-Based Assurance**

---

## 24. Public Sources

Primary public sources reviewed include:

### Anthropic

- **Claude Code Sandboxing**  
  https://www.anthropic.com/engineering/claude-code-sandboxing

- **Claude Code on Team and Enterprise**  
  https://www.anthropic.com/news/claude-code-on-team-and-enterprise

- **Anthropic ISO/IEC 42001 Certification**  
  https://www.anthropic.com/news/anthropic-achieves-iso-42001-certification-for-responsible-ai

- **Anthropic Transparency / Voluntary Commitments**  
  https://www.anthropic.com/transparency/voluntary-commitments

- **Anthropic Privacy Center — Certifications**  
  https://privacy.anthropic.com/en/articles/10015870-what-certifications-has-anthropic-obtained

### Regulatory and Governance Frameworks

- **European Union — Regulation (EU) 2024/1689, Artificial Intelligence Act**  
  https://eur-lex.europa.eu/eli/reg/2024/1689/oj

- **NIST AI Risk Management Framework**  
  https://www.nist.gov/itl/ai-risk-management-framework

- **ISO/IEC 42001:2023 — Artificial Intelligence Management Systems**  
  https://www.iso.org/standard/81230.html

---

## 25. Sources and Limitations

Sources are prioritized in the following order:

1. Anthropic official/public materials.
2. European Commission and EUR-Lex.
3. NIST official sources.
4. ISO public information where appropriate.

This case relies solely on publicly available information.

It does **not** include:

- Confidential Anthropic documentation.
- Customer-specific architecture.
- Enterprise tenant configuration.
- Private audit reports.
- Deployment-specific logs.
- Interviews with control owners.
- Operating-effectiveness samples from a real deployment.
- Independent technical testing of an actual enterprise Claude implementation.

Accordingly, the assessment distinguishes between:

**Public Provider Evidence**

and

**Deployment Evidence That an Enterprise Must Establish Independently**

Time-sensitive facts, including certification status, product capabilities, model integrations, and regulatory requirements, should be independently re-verified before reliance in a real advisory, procurement, compliance, or deployment decision.

---

## Disclaimer

> **Independent educational portfolio assessment based solely on publicly available information. Not affiliated with, commissioned by, or reviewed by Anthropic. This is not a formal audit, certification, legal opinion, or compliance determination. “Review Further” identifies areas where additional deployer due diligence or non-public evidence may be appropriate; it does not indicate a confirmed deficiency in Anthropic's controls or practices.**

---

## Final Governance Principle

### **Govern AI. Control Actions. Test Effectiveness. Prove Assurance.**

*Karun Mehta · AIGP (AI Governance Professional)*
