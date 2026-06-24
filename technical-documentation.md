# Technical Documentation — Voice Biometric Authentication System

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**System:** ORG-AI-004 · Voice Biometric Authentication System
**Document Status:** Draft v0.9 — pending closure of identified gaps before formal sign-off
**Prepared by:** AI Governance Programme Office, with Information Security and the system vendor
**Date:** September 2026
**Structured to align with:** EU AI Act Annex IV

---

## 1. General Description of the System

### 1.1 Intended Purpose

The Voice Biometric Authentication System verifies the identity of customers contacting the organisation's telephone banking service, by comparing a live voice sample against a previously enrolled voiceprint template. It replaces manual knowledge-based security questions (such as a memorable password or date of birth) as the primary authentication method for this channel.

### 1.2 Intended Users and Affected Persons

**Intended users:** Customer Operations staff, indirectly — the system operates automatically and presents a pass/fail/escalate outcome to the contact centre system, rather than being operated directly by an employee in real time.

**Affected persons:** Retail customers who use telephone banking and have enrolled in voice authentication. As of this document's preparation, enrolment is opt-in but is presented as the default authentication pathway during onboarding to telephone banking, a framing addressed further in Section 6.

### 1.3 Provider and Deployer

**Provider:** Vendor C (biometric technology provider — see Project 1 inventory for vendor classification)
**Deployer:** The organisation (Customer Operations function)

The organisation is a deployer, not the provider, of this system. The obligations described in this document reflect the deployer obligations that attach to the organisation under the EU AI Act, alongside the separate set of obligations that rest with the provider and are addressed contractually rather than documented in full here, since the organisation does not have direct visibility into the provider's internal development process beyond what is contractually disclosed.

---

## 2. System Design and Architecture

### 2.1 High-Level Functional Description

1. **Enrolment:** A customer opting into voice authentication provides several voice samples (typically during a telephone banking session or a dedicated enrolment call), from which the system generates a voiceprint template — a mathematical representation of the customer's vocal characteristics, not a stored audio recording of the enrolment call itself.
2. **Authentication:** On a subsequent call, the customer is prompted to speak a passphrase or respond to a short prompt. The system compares the resulting voice sample against the customer's stored voiceprint template and produces a match score.
3. **Decision:** If the match score exceeds a defined confidence threshold, authentication passes and the call proceeds with full account access. If the score falls below a second, lower threshold, authentication fails outright and the call is routed to a human agent for manual identity verification. Scores falling between the two thresholds trigger an additional verification step (typically a supplementary knowledge-based question) before a final pass/fail decision.

### 2.2 Model Type

The voiceprint comparison function is a vendor-proprietary neural embedding model; the organisation does not have access to the model's internal architecture beyond the vendor's published technical summary. This is recorded explicitly as a documentation limitation in Section 7 — the organisation's technical documentation for a vendor-supplied system is necessarily bounded by what the vendor discloses, and that boundary itself must be visible to anyone relying on this document, not silently absorbed into a confident-sounding description.

### 2.3 Integration Architecture

The system operates as an API-based service integrated into the organisation's contact centre telephony platform. Voice samples are transmitted to the vendor's processing environment for matching; the match result (a score and a pass/fail/escalate flag) is returned to the organisation's systems. Raw voice recordings used in live authentication calls are processed transiently and are not retained beyond the duration required for the match operation, per the vendor's data processing terms — this retention claim is noted in Section 7 as a vendor representation that has not yet been independently verified by the organisation.

---

## 3. Data and Data Governance

### 3.1 Training Data

The underlying voiceprint matching model is trained and maintained by the vendor on a dataset the vendor has not disclosed to the organisation in full. The organisation has requested, but not yet received, documentation of the training data's demographic composition — specifically, whether it adequately represents the range of accents, speech patterns, and voice characteristics present in the organisation's own customer base.

### 3.2 Enrolment and Operational Data

Data processed in the organisation's own deployment of the system includes: enrolment voice samples (processed into a voiceprint template and not retained as raw audio after template generation), live authentication voice samples (processed transiently per Section 2.3), and authentication outcome metadata (match score, pass/fail/escalate result, timestamp).

Voice data is treated as a special category of biometric personal data under applicable data protection law, triggering enhanced data governance obligations beyond those applicable to non-biometric personal data.

### 3.3 Data Governance Gaps Identified

Consistent with Project 1's findings for this system, the following gaps are recorded honestly rather than omitted:

- No dedicated Data Protection Impact Assessment specific to biometric processing has been completed for this system since its original launch
- The vendor's data retention representation (Section 2.3) has not been independently verified
- The demographic composition of the vendor's training data has been requested but not yet supplied

These gaps are treated in the conformity assessment (see `conformity-assessment.md`) as open items with assigned remediation owners and dates, not as items that block this technical documentation from being produced — the documentation's job is to describe the system as it actually is, including what remains unverified.

---

## 4. Performance Metrics and Validation

### 4.1 Metrics Tracked

The vendor reports an aggregate authentication match rate to the organisation on a periodic basis. This is the only performance metric currently tracked for this system in production.

### 4.2 Metrics Not Currently Tracked, and Why This Matters

The following metrics are not currently tracked, and their absence is itself a material finding of this documentation exercise:

- **Accuracy disaggregated by demographic group** — no data exists on whether match accuracy varies systematically by accent, regional speech pattern, gender, age, or any other characteristic. Voice biometric systems are documented in the wider technical literature to exhibit measurable accuracy variation across these dimensions in many implementations; the absence of organisation-specific data means this system's own performance on this dimension is genuinely unknown, not confirmed to be acceptable.
- **Fallback-path outcome tracking** — there is no current tracking of how frequently customers are routed to the fallback verification path, nor whether that routing rate itself varies by demographic group in a way that would indicate the primary biometric match is systematically less reliable for some customers than others.
- **False acceptance and false rejection rates separately** — the vendor's "aggregate match rate" metric does not distinguish between a false acceptance (a security risk) and a false rejection (a customer experience and potential fairness issue), which is a meaningful gap given that the appropriate response to each differs substantially.

### 4.3 Validation Status

No independent validation of the vendor's claimed accuracy has been conducted by the organisation. This is recorded as an open conformity item.

---

## 5. Human Oversight Measures

A full operational description of the human oversight procedure for this system is provided in the companion document `human-oversight-and-monitoring-procedure.md`. In summary, for the purpose of this technical documentation: the system's fallback path routes uncertain or failed authentications to a human agent for manual verification, providing a human checkpoint for the population the automated system cannot confidently authenticate. The adequacy of that fallback path itself — its fairness, its accessibility, and its actual usage patterns — is addressed in Section 4.2 above and in the companion oversight document.

---

## 6. Known Limitations and Risks

This section is deliberately the most extensive in this document, consistent with the principle that honest documentation of limitations is more valuable, and more genuinely protective of the organisation, than a document that minimises them to appear more conformant than the system currently is.

- **Default-pathway framing at enrolment.** Voice authentication enrolment is technically opt-in, but is presented during telephone banking onboarding as the default or recommended pathway, which may not constitute the standard of freely given, informed consent that biometric data processing should require. This is flagged as a priority remediation item.
- **Unverified accuracy across demographic groups.** As described in Section 4.2, the system's accuracy by demographic group is genuinely unknown. This is the single most significant open item in this documentation pack.
- **Unaudited fallback path.** The fairness and accessibility of the fallback verification path — the experience of customers who do not authenticate successfully via voice — has not been audited, despite this population very plausibly being non-randomly distributed across demographic groups.
- **Vendor model opacity.** The organisation's understanding of the underlying matching model is limited to what the vendor discloses; this constrains how thoroughly this document, or any future audit, can characterise the model's actual behaviour.
- **Data retention claims unverified.** The vendor's representation regarding transient processing and non-retention of raw voice recordings has not been independently verified by the organisation.

---

## 7. Documentation Provenance and Limitations

This document was prepared by the AI Governance Programme Office based on a combination of: direct knowledge of the organisation's own deployment and integration of the system, the vendor's published technical summary and data processing terms, and the findings of Project 1's classification and RMF mapping exercises for this system. Sections describing the vendor's internal model architecture, training data, and data retention practices are based on vendor representations that have not been independently verified, and this is noted explicitly at each relevant point above rather than presented with unwarranted confidence.

This document is versioned as a **draft pending closure of identified gaps**, consistent with the conformity assessment's conclusion that several Article 10, 13, and 15 requirements are not yet fully met. It will be formally finalised once the remediation items tracked in `conformity-assessment.md` are closed.
