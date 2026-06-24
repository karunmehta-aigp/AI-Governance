# NIST AI RMF Mapping & Gap Analysis

**Organisation:** NorthStar Financial Services (fictional)
**Framework applied:** NIST AI Risk Management Framework (AI RMF 1.0) —
four core functions: Govern, Map, Measure, Manage
**Purpose:** While the EU AI Act tells us *which systems carry legal
obligations and how severe they are*, the NIST AI RMF tells us *whether we
actually have the organisational capability to manage those obligations in
practice*. This document maps each system's current state against the four
functions and calls out where the gaps are.

---

## How to read this document

For each system, this records:
- **GOVERN** — does an accountable owner and policy exist for this system?
- **MAP** — is the system's context, purpose, and risk understood and
  documented? (Largely satisfied by the inventory itself and the EU AI Act
  classification — but documented here for completeness.)
- **MEASURE** — is the system's performance, fairness, and reliability
  actually being tested, not just assumed?
- **MANAGE** — is there a defined process for responding when something
  goes wrong (drift, bias finding, incident, complaint)?

A system can be correctly classified under the EU AI Act and still fail
every NIST function — classification tells you the obligation exists, RMF
mapping tells you whether the organisation can actually meet it. That gap
is the most useful output of this exercise.

---

## NS-AI-001 — Retail Credit Scoring Model

| Function | Status | Notes |
|---|---|---|
| GOVERN | Partial | Owner identified (Head of Credit Risk) but no documented model risk policy specific to AI, distinct from traditional credit model governance |
| MAP | Met | Purpose, data, and EU AI Act high-risk classification documented |
| MEASURE | Partial | Standard credit model performance metrics exist; no documented fairness/bias testing across protected characteristics |
| MANAGE | Gap | No defined process for a customer to challenge a specific automated decision beyond the general appeals process; no model drift monitoring cadence documented |

**Priority gap:** fairness testing (MEASURE) and a documented automated-
decision challenge process (MANAGE) are both required under Art. 10 and
Art. 14 of the EU AI Act respectively — these are not optional improvements,
they are the difference between being compliant and being classified
correctly but non-compliant.

---

## NS-AI-002 — Real-Time Fraud Detection Engine

| Function | Status | Notes |
|---|---|---|
| GOVERN | Met | Clear owner; fraud model governance sits within existing financial crime risk committee structure |
| MAP | Met | Purpose and EU AI Act exclusion basis documented |
| MEASURE | Partial | False-positive rate tracked operationally (customer complaints about wrongly declined transactions), but not tracked as a formal fairness or disparate-impact metric |
| MANAGE | Met | Established escalation path when a transaction is incorrectly held; customer-facing remediation process exists |

**Note:** because this system sits outside the AI Act high-risk regime, it
would be easy to under-invest in its governance relative to NS-AI-001. That
would be a mistake — GDPR Art. 22 obligations and the operational cost of
false declines on real customers don't go away just because the AI Act
exclusion applies.

---

## NS-AI-003 — Customer Service Virtual Assistant

| Function | Status | Notes |
|---|---|---|
| GOVERN | Gap | No named internal owner found during this review beyond "Head of Digital Channels" as a general accountable executive; no one accountable specifically for the model's outputs/content |
| MAP | Met | Purpose and Art. 50 transparency basis documented |
| MEASURE | Gap | No process found for reviewing chatbot responses for accuracy, hallucination, or inappropriate content before or after deployment |
| MANAGE | Gap | No incident process specific to this system found; a customer receiving incorrect financial information from the assistant would currently be handled as a generic complaint, not flagged as an AI governance incident |

**Priority gap:** this is the weakest-governed system in the inventory
relative to its actual risk. It is classified limited-risk under the AI Act,
but a vendor LLM giving a customer wrong information about their account or
a product is a real harm that the current setup has no dedicated way to
catch or learn from. **Recommendation:** assign a named internal owner for
model output quality, not just channel ownership, and route any
LLM-output-related complaint through a tagged category so patterns can be
detected.

---

## NS-AI-004 — Recruitment CV Screening Tool

| Function | Status | Notes |
|---|---|---|
| GOVERN | Partial | Talent Acquisition owns the tool operationally; no evidence of HR, Legal, and AI Governance jointly reviewing it despite the discrimination risk this category carries |
| MAP | Met | Purpose and EU AI Act high-risk classification documented |
| MEASURE | Gap | No documented bias audit of shortlisting outcomes by protected characteristic (gender, age, ethnicity where lawfully measurable) |
| MANAGE | Gap | No process for a rejected candidate to request the basis of an automated shortlisting decision |

**Priority gap:** this is the highest-exposure gap in the entire inventory.
Recruitment AI bias is one of the most litigated and publicly scrutinised
AI harm categories globally, the tool is vendor-built (meaning NorthStar may
not have visibility into the vendor's own bias testing), and there is
currently no audit evidence to point to if challenged. **Recommendation:**
request the vendor's bias audit methodology and results as a contractual
deliverable, not an assumption, and run an independent outcome audit on
NorthStar's own application data regardless of what the vendor provides.

---

## NS-AI-005 — Marketing Offer Personalisation Engine

| Function | Status | Notes |
|---|---|---|
| GOVERN | Met | Marketing owns the system; standard marketing governance applies |
| MAP | Met | Purpose documented; correctly outside Annex III |
| MEASURE | Partial | Engagement and conversion metrics tracked; no specific monitoring for differential treatment of vulnerable customer segments |
| MANAGE | Met | Standard marketing complaint and opt-out handling applies |

**Note:** lowest-priority system in the inventory. Included to show that not
every gap analysis needs to surface a critical finding — proportionate
governance means spending the least time here, not finding a problem to
justify the exercise.

---

## NS-AI-006 — Anti-Money-Laundering Transaction Monitoring

| Function | Status | Notes |
|---|---|---|
| GOVERN | Met | Sits within the Financial Crime Compliance governance structure, which has long-standing regulatory accountability independent of AI Act requirements |
| MAP | Met | Purpose and high-risk classification documented |
| MEASURE | Met | Model performance (true/false positive rates) already tracked for existing AML regulatory reporting obligations |
| MANAGE | Met | Investigation and escalation process is mature and pre-existing |

**Note:** this is the best-governed system in the inventory, and the reason
is instructive — it inherited a mature governance structure that already
existed for financial crime regulatory reasons, before the AI Act was ever
a consideration. **Lesson for the program:** wherever possible, AI
governance should plug into existing regulatory governance structures
rather than building parallel ones from scratch. NS-AI-001 (credit scoring)
and NS-AI-004 (recruitment) don't have an equivalent existing structure to
inherit, which is part of why their gaps are larger.

---

## NS-AI-007 — Loan Application Document Extraction

| Function | Status | Notes |
|---|---|---|
| GOVERN | Partial | Owned by Loan Operations; no specific AI governance review since it's correctly out-of-scope for high-risk obligations |
| MAP | Met | Purpose documented; correctly minimal-risk |
| MEASURE | Gap | No documented extraction accuracy testing; errors here would propagate into NS-AI-001's inputs |
| MANAGE | Gap | No defined process for catching or correcting systematic extraction errors before they affect a downstream credit decision |

**Priority gap:** this system's low AI Act risk tier makes it easy to ignore,
but it feeds a high-risk system. An extraction error here (misreading income,
for example) becomes a credit decision error downstream, and the credit
model's own fairness testing would not catch it because the error originates
upstream. **Recommendation:** include this system's accuracy in NS-AI-001's
data governance review (Art. 10), since the two are functionally one
pipeline even though they are classified separately.

---

## NS-AI-008 — Employee Productivity Analytics Dashboard

| Function | Status | Notes |
|---|---|---|
| GOVERN | Gap | Pilot stage; no formal governance review has happened yet, which is appropriate for a pilot but should not be allowed to continue once/if it moves to production |
| MAP | Met | Purpose documented; correctly minimal-risk at current scope |
| MEASURE | N/A | No individual-level outputs to measure for fairness at current scope |
| MANAGE | Gap | No defined trigger for re-classification if scope expands to individual-level scoring (see classification document) |

**Priority gap:** the gap here isn't a current control failure, it's the
absence of a tripwire. **Recommendation:** add a scope-change review gate to
this system's pilot exit criteria before any production sign-off.

---

## NS-AI-009 — Internal IT Helpdesk Ticket Router

| Function | Status | Notes |
|---|---|---|
| GOVERN | Met | Owned by IT Service Management; standard internal tooling governance applies |
| MAP | Met | Purpose documented; correctly minimal-risk |
| MEASURE | Met | Routing accuracy tracked as a standard service-quality metric |
| MANAGE | Met | Misrouted tickets are simply re-routed; no governance escalation needed |

**Note:** no action required. Included for completeness.

---

## NS-AI-010 — Voice Biometric Caller Authentication

| Function | Status | Notes |
|---|---|---|
| GOVERN | Gap | Pilot stage; high-risk obligations under the AI Act are not yet satisfied and no committed date exists for closing this before any production decision |
| MAP | Met | Purpose and high-risk classification documented |
| MEASURE | Gap | No documented accuracy testing across different voice characteristics (accent, age, illness-affected speech) — a known failure mode for voice biometric systems |
| MANAGE | Gap | No fallback process documented for a legitimate customer who is wrongly rejected by the voiceprint match beyond "routes to manual identity verification" — what happens at that point is not specified |

**Priority gap:** this is the most urgent item in the entire inventory. It
combines the highest EU AI Act tier, a pilot status that means none of the
required pre-deployment work is necessarily finished, and a well-documented
class of biometric accuracy failure (lower accuracy for some accents and
speech patterns) that has caused real regulatory and reputational harm to
other organisations. **Recommendation:** this system should not move to
production until Art. 9, 10, 14, and 15 obligations are demonstrably
complete — pilot status should not be treated as a reason to defer this
work, it is the reason this is the right time to do it.

---

## Cross-cutting gaps (apply across multiple systems)

1. **No central AI governance committee with sign-off authority.**
   Several systems (NS-AI-001, NS-AI-003, NS-AI-004) show partial or
   missing GOVERN coverage specifically because there is no single body
   reviewing AI systems as a category, distinct from the business unit that
   happens to own each one. Financial crime (NS-AI-006) is the exception
   because it inherited a pre-existing structure.

2. **Vendor-built systems carry an assumption gap.** NS-AI-003, NS-AI-004,
   NS-AI-007, and NS-AI-010 are all vendor-built, and in each case the
   organisation's own MEASURE evidence is weaker than for internally-built
   systems — there's a recurring pattern of assuming the vendor has tested
   for bias/accuracy rather than confirming it contractually.

3. **Pipeline risk is invisible to per-system classification.** NS-AI-007
   feeds NS-AI-001. A system's own risk tier doesn't capture the risk it
   introduces into a downstream high-risk system. This needs to be tracked
   as a relationship, not just a list of independent systems — a natural
   extension for a future version of this inventory.

4. **Pilot status is being treated informally as a governance grace
   period** (NS-AI-008, NS-AI-010), when the opposite should be true for any
   system whose final scope would land in a high-risk tier.
