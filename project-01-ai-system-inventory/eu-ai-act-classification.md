# EU AI Act Classification Rationale

**Organisation:** NorthStar Financial Services (fictional)
**Scope:** All 10 AI systems identified in `ai-system-inventory.csv`
**Framework applied:** EU AI Act — Article 5 (prohibited practices), Article 6
and Annex III (high-risk classification), Article 50 (transparency
obligations for limited-risk systems)
**Classified by:** AI Governance Lead
**Date:** 2026-06-23

## Purpose of this document

A risk tier on its own is not defensible to a regulator or an internal audit
committee. What is defensible is the *reasoning* that produced the tier — the
specific article or annex relied on, the facts of the system that triggered
it, and what that tier then obligates the organisation to do next. This
document records that reasoning for every system in the inventory, in the
order they appear in the CSV.

---

## NS-AI-001 — Retail Credit Scoring Model

**Tier: HIGH-RISK**

**Basis:** Annex III(5)(b) — AI systems intended to be used to evaluate the
creditworthiness of natural persons or establish their credit score, with the
exception of systems used for the purpose of detecting financial fraud.

**Rationale:** This system's stated purpose is exactly the activity Annex III
names. It determines access to credit for a named individual and is fully
automated, with override available only at the appeal stage rather than at
the point of decision. Under Article 6(2), this places the system squarely
in the high-risk category regardless of how accurate or well-tested the
model is — the obligation attaches to the *use case*, not the performance.

**Obligations triggered:** risk management system (Art. 9), data governance
and bias testing on training/validation data (Art. 10), technical
documentation (Art. 11), human oversight design (Art. 14), accuracy and
robustness testing (Art. 15), and registration in the EU database for
high-risk systems before placing on the market (Art. 49).

---

## NS-AI-002 — Real-Time Fraud Detection Engine

**Tier: MINIMAL RISK (with a documented borderline call)**

**Basis:** Annex III(5)(b), exclusion clause — the same Annex III entry that
classifies credit scoring as high-risk explicitly **excludes** systems used
for the purpose of detecting financial fraud.

**Rationale — and why this one needed care:** On a first pass it is easy to
mis-tier this system. It is fully automated, it affects a named individual,
and it can hold or decline that person's transaction — every signal that
normally points to high-risk. But the Annex III(5)(b) exclusion is specific
and deliberate: fraud detection is carved out because the legislative intent
is to regulate decisions *about a person's general creditworthiness or
financial standing*, not real-time security controls designed to protect
that same person's account. The distinguishing fact is the system's stated
*purpose* field — "scores transactions... suspected of fraud" — not its
autonomy level or its impact.

**This is the system most worth defending in an interview.** The honest
answer is not "I have a rule that says fraud = high-risk." It's "I checked
the exclusion clause specifically because this system looked like it should
be high-risk, and the purpose — fraud detection, not creditworthiness — is
what moved it out." A reviewer who can articulate *why* an exclusion applies,
not just that one exists, is demonstrating the actual skill the EU AI Act
requires: reading the system's purpose against the precise wording of the
annex, not pattern-matching on surface features like "affects a financial
decision."

**Obligations triggered:** none under the EU AI Act's high-risk regime.
However, this system remains in scope for GDPR Article 22 (automated
individual decision-making) given it can produce a decision with legal or
similarly significant effects (declining a payment), and that obligation is
tracked separately — see `nist-rmf-mapping.md`.

---

## NS-AI-003 — Customer Service Virtual Assistant

**Tier: LIMITED RISK**

**Basis:** Article 50(1) — providers of AI systems intended to interact
directly with natural persons must ensure individuals are informed they are
interacting with an AI system, unless this is obvious from the
circumstances.

**Rationale:** The assistant interacts directly with customers in a chat
interface and does not make a high-stakes decision about their credit,
employment, or legal standing — it answers product and account questions
and escalates to a human when uncertain. This keeps it out of Annex III. It
sits squarely in the transparency-obligation tier instead: the customer must
be told, clearly and at the start of the interaction, that they are talking
to an AI system.

**Obligations triggered:** clear AI-disclosure notice at the start of every
chat session; this is a vendor-provided system, so the disclosure obligation
and the underlying model's behaviour both need confirming in the vendor
contract, not assumed from the vendor's marketing material.

---

## NS-AI-004 — Recruitment CV Screening Tool

**Tier: HIGH-RISK**

**Basis:** Annex III(4)(a) — AI systems intended to be used for the
recruitment or selection of natural persons, in particular to place targeted
job advertisements, analyse and filter job applications, and evaluate
candidates.

**Rationale:** This is a direct, unambiguous match to the annex text —
screening and ranking CVs is the example given in the regulation itself.
The fact that a human recruiter makes the final decision does **not** remove
the high-risk classification: Article 6 classifies the system based on its
intended purpose, and a system that filters which candidates a human ever
sees is already shaping the outcome before any human reviews anything.
"Human makes the final call" is a required safeguard *within* the high-risk
regime (Art. 14), not a reason to exit it.

**Obligations triggered:** full Annex III high-risk obligations as above,
plus heightened attention to Art. 10 bias testing given documented
discrimination risk in CV-screening tools specifically, and to the fact this
is vendor-built — the deployer (NorthStar) still carries obligations under
Art. 26 even though it did not build the model.

---

## NS-AI-005 — Marketing Offer Personalisation Engine

**Tier: MINIMAL RISK**

**Basis:** No Annex III category applies; no direct natural-person
interaction in the sense Article 50 targets (the system selects content, it
does not present itself as an interlocutor).

**Rationale:** Personalised marketing is not named anywhere in Annex III,
and selecting which offer a customer sees does not establish creditworthiness,
employment outcomes, or any of the other enumerated harms. This is the
correct outcome, but it is also the category most worth re-checking
periodically: if this engine were ever extended to set differential pricing
based on inferred financial vulnerability, that would raise separate
consumer-protection and potentially unfair commercial practice concerns
outside the AI Act entirely. Flagged for awareness, not reclassification.

**Obligations triggered:** none under the AI Act. Standard data protection
and marketing consent rules apply as they would regardless of AI involvement.

---

## NS-AI-006 — Anti-Money-Laundering Transaction Monitoring

**Tier: HIGH-RISK**

**Basis:** Annex III(6)(g) covers law-enforcement-adjacent risk-assessment
use; more directly, this system's outputs feed regulatory obligations under
EU AML directives, and several member states' implementing guidance treats
AML-decisioning AI as high-risk by virtue of its role in a regulated
compliance process with significant effect on the customer (potential
account restriction, suspicious activity reporting, or relationship exit).

**Rationale:** Every flag is reviewed by a human investigator before any
action is taken, which is a genuine and important mitigating control — but
exactly as with NS-AI-004, a human-in-the-loop step is a safeguard *within*
the tier, not an exit from it. The system shapes which customers get
investigated at all, which is itself consequential.

**Obligations triggered:** full high-risk obligations. Note the overlap with
existing AML regulatory requirements — this is a case where AI Act
compliance and financial-crime regulatory compliance should be run as one
coordinated control set, not two parallel ones, to avoid duplicated and
inconsistent documentation.

---

## NS-AI-007 — Loan Application Document Extraction

**Tier: MINIMAL RISK**

**Basis:** No Annex III category applies — the system performs data
extraction (OCR) and makes no determination about the applicant.

**Rationale:** This is the cleanest minimal-risk classification in the
inventory and is included specifically to show the boundary: it touches
the same loan application process as NS-AI-001, processes the same kind of
sensitive personal and financial data, and feeds directly into a high-risk
system downstream — but it does not itself decide, score, or evaluate
anything. The AI Act classifies by what a system *does*, not by which
business process it sits inside. If this OCR tool were ever extended to
also flag documents as "likely fraudulent" or "incomplete in a way that
disadvantages the applicant," that judgement function would need
re-classification.

**Obligations triggered:** none under the AI Act. Standard data protection
controls apply given the sensitivity of the documents it processes.

---

## NS-AI-008 — Employee Productivity Analytics Dashboard

**Tier: MINIMAL RISK**

**Basis:** No Annex III category applies — outputs are team-level aggregates,
not decisions about a named individual.

**Rationale:** This is currently correctly minimal-risk, but it is the
system in this inventory most likely to *drift* into a higher tier without
anyone noticing, because the change would happen through informal scope
creep rather than a deliberate redesign. If a manager ever requests
individual-level scoring ("show me which employees are underperforming") the
system's purpose changes from aggregate analytics to individual employee
evaluation — which would put it in Annex III(4)(b), monitoring and
evaluation of performance and conduct of persons in a work-related context.
**Recommendation:** any request to add individual-level views to this
dashboard should trigger a mandatory re-classification review before
development starts, not after launch.

**Obligations triggered:** none currently. Monitoring requirement
recommended as above.

---

## NS-AI-009 — Internal IT Helpdesk Ticket Router

**Tier: MINIMAL RISK**

**Basis:** No Annex III category applies; the system has no bearing on any
individual's legal standing, financial access, employment, or safety.

**Rationale:** Included as a deliberate, uncontroversial minimal-risk
example — every inventory needs at least one system that is genuinely
low-stakes, both for completeness and to demonstrate the classifier isn't
biased toward over-flagging everything as a way of looking thorough.
Over-classifying is its own governance failure: it dilutes attention away
from the systems that actually need it.

**Obligations triggered:** none.

---

## NS-AI-010 — Voice Biometric Caller Authentication

**Tier: HIGH-RISK**

**Basis:** Annex III(1)(a) — AI systems intended to be used for biometric
identification of natural persons, where this is not merely incidental to
another commercial service.

**Rationale:** Voiceprint matching is biometric identification by
definition. The fact that it is currently in **pilot**, not production, does
not delay the classification — the obligations under Article 9
(risk management) and Article 10 (data governance) are meant to be
satisfied *before* a high-risk system reaches production, which makes the
pilot stage the correct and only point at which this review should happen.
A system entering full production with these obligations still outstanding
would represent a governance program failure, not a future task.

**Obligations triggered:** full high-risk obligations, with explicit urgency
flagged given the pilot-to-production timeline. Additionally, biometric data
is a special category of personal data under GDPR Article 9, which requires
explicit consent or another Article 9(2) condition independent of the AI Act
analysis — both regimes apply simultaneously and neither substitutes for the
other.

---

## Summary table

| System | Tier | Key Annex/Article |
|---|---|---|
| NS-AI-001 Credit Scoring | HIGH | Annex III(5)(b) |
| NS-AI-002 Fraud Detection | MINIMAL | Annex III(5)(b) exclusion |
| NS-AI-003 Virtual Assistant | LIMITED | Art. 50(1) |
| NS-AI-004 CV Screening | HIGH | Annex III(4)(a) |
| NS-AI-005 Marketing Personalisation | MINIMAL | — |
| NS-AI-006 AML Monitoring | HIGH | Annex III(6)(g) + AML overlap |
| NS-AI-007 Document Extraction | MINIMAL | — |
| NS-AI-008 Productivity Analytics | MINIMAL (monitor for drift) | Annex III(4)(b) if scope changes |
| NS-AI-009 IT Ticket Router | MINIMAL | — |
| NS-AI-010 Voice Biometric Auth | HIGH | Annex III(1)(a) |

**4 high-risk, 1 limited-risk, 5 minimal-risk.** The single most important
judgement call in this set is NS-AI-002, because it is the one system where
the "obvious" classification (high-risk, by surface features) is wrong, and
the correct classification depends on reading the exclusion clause rather
than the general rule.
