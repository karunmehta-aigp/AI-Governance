# Governance Review Memo

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**To:** Chief Executive Officer · Board Risk & Audit Committee
**From:** AI Governance Programme Office
**Subject:** AML Transaction Monitoring System (ORG-AI-003) — Governance Position and Classification Resolution Plan
**Classification:** Confidential
**Date:** April 2026

## Purpose

This memo presents the outcome of a governance review of the AML Transaction Monitoring System (ORG-AI-003), triggered by two open items from Project 1's classification exercise: an unresolved Annex III classification question, and a governance maturity score of 2.0 (Developing) that warranted closer operational examination.

Unlike the governance review the Board considered for the CV Screening & Ranking System, this review does not surface a critical, unaddressed compliance failure. It surfaces a system whose controls are largely present but unverified, and a legal question that has been left open longer than it should have been. The Board is asked to approve a resolution plan on both fronts.

## Executive Summary

The AML Transaction Monitoring System has operated in production since 2020 and is the organisation's primary technical control against money laundering risk, covering all customer and counterparty transactions.

The governance review's findings differ in character from the CV screening review. Rather than a single dominant failure, this review identifies a pattern: controls that exist on paper but whose real-world effectiveness has not been independently verified, alongside a legal classification question that has remained unresolved since February without a deadline attached to it.

Specifically:

- The system's Annex III classification has been treated as "high-risk, conservatively" for several months, with no fixed date for legal counsel to issue a final opinion
- The system's human review function — repeatedly cited as a key control — has never been measured for actual review capacity against alert volume, leaving open the possibility that review has become procedural rather than substantive as volumes have grown
- The vendor has not disclosed its model retraining practices, leaving the organisation unable to confirm that the detection logic in production today matches what was originally validated
- No fairness review has tested whether the system's risk scoring varies in ways unrelated to genuine financial crime risk across customer segments

None of these findings, individually, rises to the severity of the autonomous-rejection failure identified in the CV screening review. Collectively, however, they describe a system whose governance has been allowed to rest on assumptions rather than evidence for longer than is appropriate for a control of this importance.

The recommended Board decision is: approve a structured verification and resolution plan, with the system continuing to operate throughout, rather than a continue/suspend choice — because the underlying controls are not currently known to be failing, only unverified.

## Findings in Detail

### 1. An Open Legal Question Without a Closing Date

The Annex III classification question — whether this system's risk-scoring function falls within the creditworthiness/essential-services-access logic of Category 5 — was identified as unresolved during the Project 1 classification exercise. Months have passed without a definitive opinion from legal counsel, and no deadline was ever attached to that request.

This is not, in itself, a compliance failure: a conservative interim classification is a defensible governance position. But an interim position without an end date risks becoming a permanent unexamined default, and the organisation should not be in a position where, if asked directly by a supervisor, it cannot say whether its own classification judgement is final or still pending.

### 2. Human Oversight That Has Not Been Verified, Only Assumed

Project 1's RMF mapping recorded that "a financial crime analyst reviews every alert before action" as a substantive control. This review tested that claim and found it has never actually been measured. There is no data on average review time per alert, no minimum staffing benchmark tied to alert volume, and no periodic audit of whether cleared alerts carry documented analytical reasoning or simply a clearance flag.

This matters because a human oversight control that exists in name but has degraded into time-pressured rubber-stamping under volume growth provides materially less protection than the organisation currently believes it has — for both the customers who may be wrongly flagged and the genuine financial crime risks the system exists to catch.

### 3. Vendor Opacity on Model Changes

The vendor has not contractually disclosed when or how its detection model is retrained. This means the organisation cannot currently confirm whether the system's behaviour today matches what was last validated, or has shifted through one or more undisclosed retraining cycles since deployment in 2020.

### 4. An Untested Assumption of Fairness

No review has been conducted on whether the system's risk scores vary systematically across customer segments for reasons unrelated to genuine financial crime indicators. Geographic and nationality-linked data inputs are common in AML risk-scoring generally and carry documented potential for disparate impact. The organisation does not currently know whether this system is affected — the assumption that it is fair has not been tested either way.

## Recommended Actions

**Within 30 Days**

| Action | Owner | Timeline |
|---|---|---|
| Implement average-time-per-alert tracking by analyst and risk tier | Head of Financial Crime Compliance | 30 days |
| Sample-audit recently cleared alerts for documented analytical reasoning | Head of Financial Crime Compliance | 30 days |
| Set a fixed deadline for legal counsel's definitive Annex III classification opinion | General Counsel | 30 days |

**Within 60 Days**

| Action | Owner | Timeline |
|---|---|---|
| Establish minimum staffing ratio tied to alert volume, with an escalation trigger | Head of Financial Crime Compliance | 60 days |
| Issue formal information request to vendor for retraining history and change-notification terms | Procurement + Legal | 60 days |
| Commission independent fairness review of risk-score distributions across customer segments | AI Governance Programme Office | 60 days |

**Within 90 Days**

| Action | Owner | Timeline |
|---|---|---|
| Legal counsel delivers definitive classification opinion | General Counsel | 90 days |
| Formally close or escalate the classification question to the Board depending on the opinion received | AI Governance Programme Office | 90 days |
| Negotiate contractual model-change notification requirement at next renewal | Procurement + Legal | 90 days |

## Decision Requested

The Board is asked to approve the following:

**Recommended Position — Continue operation with a structured verification and resolution plan**
The system continues to operate without interruption. The 30/60/90-day plan above converts unverified assumptions into measured facts, and converts an open-ended legal question into one with a firm closing date. This is not a continue/suspend decision in the way the CV screening review required, because no control has been shown to be failing — the task here is verification, not remediation of a known failure.

The AI Governance Programme Office recommends this position on the basis that suspending a primary AML control would itself create regulatory risk under financial crime obligations independent of the AI Act, and that the findings above describe a verification gap rather than a demonstrated harm.

## Escalation if Plan Is Not Delivered

If the 30-day actions are not completed on schedule, or if legal counsel's classification opinion is not delivered within the 90-day window, the AI Governance Programme Office will escalate to the Board Risk & Audit Committee directly, with a recommendation to commission an external review of both the classification question and the alert review function. An unresolved legal question and an unverified control should not be allowed to persist indefinitely simply because no single finding in this review was, on its own, severe enough to force the issue.

**Attachments:** AI Risk Assessment — AML Transaction Monitoring System (April 2026)

**Prepared by:** AI Governance Programme Office
**Contact:** ai-governance@example-organisation.test
