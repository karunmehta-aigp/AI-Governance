# Conformity Assessment — Voice Biometric Authentication System

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**System:** ORG-AI-004 · Voice Biometric Authentication System
**Assessment Status:** In Progress — Conditional Declaration Pending Remediation
**Prepared by:** AI Governance Programme Office, with Legal and Information Security
**Date:** September 2026

---

## 1. Purpose of This Assessment

This document records the organisation's conformity assessment of the Voice Biometric Authentication System against the EU AI Act's high-risk system requirements, and sets out the basis on which a Declaration of Conformity will, or will not yet, be issued.

A conformity assessment is not a formality completed to produce a certificate. It is a structured, evidence-based determination of whether a specific system, as actually built and operated, meets each applicable legal requirement — and where it does not, an honest assessment says so, with a remediation commitment, rather than asserting compliance to close the paperwork.

---

## 2. Assessment Route: Self-Assessment versus Third-Party Assessment

Biometric identification and verification systems fall within Annex III, Category 1. Whether a given biometric system requires third-party (notified body) conformity assessment, rather than internal self-assessment, depends on the specific sub-category and intended purpose of the biometric function in question — verification (confirming a claimed identity, the function this system performs) is treated differently under the framework than identification (determining an unknown person's identity from a wider population), with verification generally subject to a different assessment pathway than one-to-many identification use cases.

**Determination:** Based on the system's function as a one-to-one verification tool (confirming that a caller is the specific account holder they claim to be, not searching to identify an unknown individual against a wider population), the organisation's Legal function has determined that internal conformity assessment via the organisation's own quality management system is the applicable route, rather than mandatory third-party assessment by a notified body.

This determination is recorded as a **reasoned legal position, not an automatic default**, and is subject to revisiting if the system's function changes — for example, if it were ever extended to a one-to-many identification use case, which would be a material change requiring a fresh classification and assessment route determination under the process established in Project 3.

---

## 3. Requirement-by-Requirement Assessment

### Article 9 — Risk Management System

**Requirement:** A continuous, iterative risk management process must be established and maintained throughout the system's lifecycle, not as a one-time pre-deployment exercise.

**Assessment:** **Partially met.** Project 1 established an initial risk classification and RMF maturity baseline for this system. Project 4's incident response work (for a different system) prompted a lateral review process that this system has not yet undergone. A dedicated, system-specific risk management file, updated on an ongoing basis, does not yet exist.

**Remediation commitment:** A dedicated risk management file for this system will be established by the AI Governance Programme Office, incorporating the gaps identified throughout this conformity pack, by 31 October 2026.

---

### Article 10 — Data and Data Governance

**Requirement:** Training, validation, and testing data must be subject to appropriate data governance practices, including examination for possible bias.

**Assessment:** **Not met.** As documented in `technical-documentation.md` Section 3, the demographic composition of the vendor's training data has been requested but not received, and no bias examination specific to demographic accuracy variation has been conducted on the organisation's own operational data.

**Remediation commitment:** A formal information request has been issued to the vendor. An independent fairness evaluation of authentication outcomes by available demographic proxy will be commissioned by the AI Governance Programme Office. Target completion: 31 December 2026.

---

### Article 11 and Annex IV — Technical Documentation

**Requirement:** Technical documentation must be drawn up before the system is placed on the market and kept up to date.

**Assessment:** **Substantially met, as of this assessment.** The companion `technical-documentation.md` document constitutes this system's Annex IV–aligned technical documentation. It is explicitly versioned as a draft pending closure of the gaps identified within it, which is itself consistent with the requirement to keep documentation up to date — a document that asserted final, complete status while material gaps remained open would not actually satisfy this requirement in substance, regardless of its formatting.

**Remediation commitment:** The technical documentation will be formally finalised once the Article 10 and Article 15 remediation items below are closed.

---

### Article 12 — Logging and Traceability

**Requirement:** The system must enable the automatic recording of events ("logs") over its lifetime, to a degree consistent with the system's intended purpose, to ensure traceability.

**Assessment:** **Partially met.** Authentication outcomes (match score, pass/fail/escalate result, and timestamp) are logged. However, the system does not currently log sufficient detail to reconstruct, after the fact, why a specific borderline-score case was routed to the supplementary verification step rather than passing or failing outright — limiting the organisation's ability to audit borderline-decision consistency retrospectively.

**Remediation commitment:** Information Security and the vendor will scope an enhanced logging specification capturing the specific threshold band a given authentication attempt fell into, by 30 November 2026.

---

### Article 13 — Transparency and Provision of Information to Deployers

**Requirement:** The system must be accompanied by instructions for use that enable deployers to understand and appropriately use the system, including its capabilities, limitations, and the human oversight measures required.

**Assessment:** **Partially met.** The vendor provides a technical summary and operating instructions. However, the vendor's documentation does not disclose demographic accuracy variation (because, per Article 10 above, this has not been tested), meaning the organisation cannot currently give its own Customer Operations staff complete information about the system's limitations as the Article intends.

**Remediation commitment:** Once the Article 10 fairness evaluation is complete, its findings will be incorporated into updated internal guidance for Customer Operations staff, regardless of outcome.

---

### Article 14 — Human Oversight

**Requirement:** High-risk AI systems must be designed to allow for effective human oversight, including the ability to understand the system's outputs and to decide not to use the system or to override its output.

**Assessment:** **Partially met.** A fallback path to human verification exists structurally. However, consistent with the "oversight capacity erosion" risk first identified in Project 2 of this portfolio, the actual throughput and effectiveness of that fallback path — how long agents spend on fallback verification, whether they have adequate information and training to do it well, and whether the fallback path itself performs consistently across customer groups — has not been measured.

**Remediation commitment:** Detailed in full in `human-oversight-and-monitoring-procedure.md`. Summary: a fallback-path throughput and quality audit will be conducted by 30 November 2026.

---

### Article 15 — Accuracy, Robustness, and Cybersecurity

**Requirement:** High-risk AI systems must achieve an appropriate level of accuracy, robustness, and cybersecurity, and perform consistently throughout their lifecycle.

**Assessment:** **Not met, pending verification.** No independent validation of the vendor's claimed accuracy has been performed (Section 4.3 of the technical documentation). "Appropriate level of accuracy" cannot be confirmed for a metric that has never been independently measured, regardless of how confidently the vendor states it.

**Remediation commitment:** Independent validation of accuracy, including disaggregated accuracy testing, will be commissioned as part of the Article 10 fairness evaluation work above, given the substantial overlap between the two requirements' evidence needs.

---

### Article 17 — Post-Market Monitoring

**Requirement:** Providers (and, by extension, deployers with monitoring obligations) must establish a post-market monitoring system proportionate to the nature of the AI technologies and the risks of the high-risk AI system.

**Assessment:** **Not met.** No structured post-market monitoring plan currently exists for this system beyond the vendor's periodic aggregate match-rate report. This is addressed in full in the companion monitoring procedure document.

**Remediation commitment:** A post-market monitoring plan will be implemented per `human-oversight-and-monitoring-procedure.md`, operational no later than 31 December 2026.

---

## 4. Summary of Conformity Status

| Requirement | Status | Target Closure Date |
|---|---|---|
| Article 9 — Risk management system | Partially met | 31 October 2026 |
| Article 10 — Data governance | Not met | 31 December 2026 |
| Article 11 / Annex IV — Technical documentation | Substantially met | Final sign-off pending other items |
| Article 12 — Logging and traceability | Partially met | 30 November 2026 |
| Article 13 — Transparency to deployers | Partially met | Pending Article 10 closure |
| Article 14 — Human oversight | Partially met | 30 November 2026 |
| Article 15 — Accuracy, robustness, cybersecurity | Not met, pending verification | Pending Article 10 closure |
| Article 17 — Post-market monitoring | Not met | 31 December 2026 |

---

## 5. Declaration of Conformity — Current Status

**Determination:** A full, unconditional EU Declaration of Conformity **cannot be issued at this time.** Three requirements (Articles 10, 15, and 17) are assessed as not met, and a Declaration asserting otherwise would misrepresent the system's actual state.

**Interim governance position:** Per the AI Governance Committee's decision authority as established in Project 3, the system may **continue limited operation** under the following conditions, pending full conformity:

1. The fallback verification path remains operational and is prioritised for the throughput and quality audit described above as the most urgent open item, given its direct connection to customer-facing fairness outcomes
2. All remediation items above are tracked with named owners and the dates specified, reported to the AI Governance Committee quarterly until closed
3. If the Article 10 fairness evaluation, once completed, reveals a material accuracy disparity across demographic groups, the AI Governance Committee will reconvene immediately to determine whether continued operation remains appropriate pending a fix, rather than waiting for the next scheduled quarterly report

**Target date for full Declaration of Conformity:** 31 January 2027, contingent on all remediation items above closing on schedule.

This conditional position is itself documented and dated, consistent with the principle — established across this portfolio — that an honest, time-bound interim position is more defensible to a regulator than either premature certification or indefinite silence.

---

*Approved for interim operation by the AI Governance Committee, with full Declaration of Conformity pending the remediation programme above.*
