# AI Policy (Master)

*Core Toolkit — Foundational Document 2 of 8*
**Doc ID:** AIGV-CORE-002 · **Version 1.0**

---

**Disclaimer:** *This document is a portfolio artefact created for demonstration and educational purposes only. It does not represent the policies, systems, or practices of any real organisation, and no organisation, vendor, or individual named or implied within it refers to an actual entity. All identifiers (e.g. ORG-AI-0XX) are fictional and used solely to illustrate a coherent governance scenario. This template does not constitute legal advice and should not be relied upon for regulatory compliance without review by qualified counsel and subject-matter experts.*

**Karun. · AIGP (AI Governance Professional)**

---

## 1. Policy Statement

The organisation is committed to developing, procuring, and deploying artificial intelligence responsibly. This Policy sets mandatory requirements for anyone who designs, builds, procures, configures, or operates an AI or automated decision-making (ADM) system on behalf of the organisation. It operationalises the principles set out in the AI Governance Framework (AIGV-CORE-001).

## 2. Scope and Applicability

This Policy applies to:
- AI systems developed in-house, including models built on top of third-party foundation models.
- AI capabilities embedded in procured software (Vendor A, Vendor B, Vendor C) or delivered as a managed service.
- Generative AI tools used by employees for internal productivity, content drafting, or code generation.
- Pilots, proofs-of-concept, and shadow-IT AI usage discovered outside formal procurement.

It does not apply to simple rule-based automation with no learned or probabilistic component (e.g. static if/then business logic), though such systems should still be logged if they materially affect individuals.

## 3. Mandatory Requirements

### 3.1 Prohibited Uses
- Systems performing social scoring of individuals for unrelated purposes.
- Real-time remote biometric identification in public spaces for law enforcement purposes, except narrow exemptions defined in applicable law and pre-approved by Legal.
- Subliminal or manipulative techniques designed to materially distort a person's behaviour in a way that causes harm.
- Inferring emotion in the workplace or education settings, except for safety or medical purposes with documented legal basis.

### 3.2 Intake Before Use
1. No AI system may be used in a business process, or to make or support a decision about an individual, until it is logged in the AI System Inventory and has a completed AI Use Case Assessment Form.
2. Procurement of any product with embedded AI capability requires the AI Governance Office to be notified before contract signature.

### 3.3 Human Oversight
1. High-risk systems must have a named individual empowered and able to override, pause, or stop the system's output before it takes effect on an individual, or promptly thereafter where real-time override is not feasible.
2. Automated decisions producing legal or similarly significant effects on an individual must offer a route to request human review, except where an applicable legal exemption is documented.

### 3.4 Data Governance
1. Training and fine-tuning data must have a documented lawful basis and provenance record.
2. Personal data used in AI systems is subject to the organisation's data protection policy and, where required, a Data Protection Impact Assessment or Fundamental Rights Impact Assessment.

### 3.5 Transparency
1. Individuals interacting with a limited-risk system (e.g. chatbot, AI-generated content) must be informed they are interacting with or receiving output from an AI system, unless obviously apparent from context.

### 3.6 Third-Party and Vendor AI
1. Vendor AI capabilities are assessed using the Vendor AI Risk Assessment before onboarding, covering the vendor's own risk classification, sub-processing of data, and evidence of the vendor's own governance controls.
2. Contracts with AI vendors must include audit rights, incident notification obligations, and change-notification requirements for material model updates.

### 3.7 Monitoring and Incident Reporting
1. Any suspected AI-related incident — bias, safety failure, security compromise, or unexpected rights-impacting behaviour — is reported to the AI Governance Office within 24 hours of discovery.
2. High- and limited-risk systems are subject to quarterly performance and compliance review.

## 4. Employee Use of Generative AI Tools

- Only organisation-approved generative AI tools may be used with confidential, proprietary, or personal data.
- Outputs from generative AI must be reviewed by a human before being relied upon for a business decision, publication, or communication to a third party.
- Employees must not input client-identifiable data, trade secrets, or regulated data categories into public/consumer-grade generative AI tools.

## 5. Non-Compliance

Failure to comply with this Policy may result in suspension of system access, escalation to the AI Governance Committee, and disciplinary action in line with the organisation's standard conduct policies. Deliberate circumvention of intake or classification requirements is treated as a governance incident in its own right.

## 6. Related Documents

| Document | Doc ID |
|---|---|
| AI Governance Framework | AIGV-CORE-001 |
| AI Governance Committee Charter | AIGV-CORE-003 |
| AI System Inventory Template | AIGV-CORE-004 |
| AI Use Case Assessment Form | AIGV-CORE-005 |
| AI Incident Response and Regulatory Escalation Procedure | See project-04-incident-response |

## 7. Policy Ownership and Review

**Owner:** AI Governance Committee, delegated to the AI Governance Office for maintenance. Reviewed at least annually and upon material regulatory or organisational change. Exceptions to this Policy require documented AI Governance Committee approval, time-bound, with a remediation plan.
