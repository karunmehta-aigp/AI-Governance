# Root Cause Analysis — AI-INC-2026-001

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**Incident:** Credit Decisioning System Postcode Bias
**RCA Status:** Final
**Prepared by:** AI Governance Programme Office + ML Engineering
**Review Date:** 24 July 2026
**Approved by:** AI Governance Committee

---

## 1. Incident Summary

The Credit Decisioning System assigned systematically lower creditworthiness scores to applicants from postcodes correlating with ethnic minority and lower-income populations, constituting indirect discrimination. The bias was present from the model's original go-live in 2021 and remained active for approximately four years before detection.

---

## 2. Root Cause Analysis Method

This RCA uses the **5 Whys** method to trace the incident to its root cause, followed by a structured contributing factors analysis to capture the systemic conditions that compounded or prolonged the harm. The objective is not to assign individual blame, but to identify the conditions that allowed the failure to occur, to go undetected, and to persist for as long as it did — and to ensure the corrective actions address those conditions, not only the immediate symptom.

A methodological note worth recording explicitly: the 5 Whys method is well suited to tracing a single causal chain to a root cause, but it can understate the role of factors that did not *cause* the incident on their own yet meaningfully shaped its scale or duration. This RCA therefore pairs the 5 Whys chain with a separate contributing factors section rather than trying to force every relevant factor into a single linear chain — a discipline that is itself a governance maturity signal, since a root cause analysis that artificially compresses multiple independent contributing conditions into one neat causal line tends to produce a single, narrow corrective action where several are actually needed.

---

## 3. Five Whys Analysis

**Problem statement:** The Credit Decisioning System produced discriminatory credit scores for applicants from specific postcodes, resulting in higher rejection rates and inflated interest rates for affected protected groups.

---

**Why 1: Why did the model produce discriminatory scores?**

Because postcode was included as a feature and acted as a statistically significant proxy for protected characteristics, depressing scores for applicants in areas with historically concentrated ethnic minority and lower-income populations.

---

**Why 2: Why was postcode included as a feature without recognising its discriminatory potential?**

Because the model development team conducted no formal proxy analysis of the features used. Postcode was treated as a legitimate geographic risk variable, assumed to reflect local economic conditions, without any analysis of whether it also encoded protected characteristics.

---

**Why 3: Why was no proxy analysis conducted?**

Because there was no requirement to conduct one. At the time of the model's development, the organisation had no formal AI governance process, no fairness evaluation requirement, and no defined standard for pre-deployment bias assessment of any kind. The data science team followed standard credit risk modelling practice as it existed at the time, which did not yet routinely include systematic fairness auditing as a standard step.

---

**Why 4: Why was there no fairness evaluation requirement?**

Because the organisation had no Responsible AI Policy and no AI governance programme at the time. The model was developed and deployed entirely outside any structured governance framework. No mechanism existed to identify that a fairness assessment was needed, let alone to require one before go-live.

---

**Why 5: Why did the absence of a governance framework go unaddressed for four years?**

Because AI governance was not treated as an organisational priority until external regulatory pressure created urgency. Before the governance programme established in Project 3, AI risk across the organisation was managed informally within individual business units, without cross-functional oversight, a defined escalation path, or named executive accountability. There was no central system inventory, no structured review process, and no post-deployment monitoring framework that would have had any chance of detecting an ongoing bias of this kind.

**Root cause:** The absence of an enterprise AI governance programme. The discriminatory model feature was the proximate symptom; the root cause was the absence of the structures, processes, and accountability mechanisms that would have prevented the feature's inclusion in the first place, required its testing before go-live, and detected its effects once in production.

---

## 4. Contributing Factors

### CF-1: Training Data Encoding Historical Discrimination

The model was trained on the organisation's own historical lending data, spanning several years prior to the model's build. That data reflected lending decisions made by human underwriters before any AI system existed — and those earlier human decisions may themselves have been shaped by the same geographic and demographic biases present in traditional, pre-AI credit assessment practice generally. Training a model on historically uneven outcomes risks teaching the model to reproduce that unevenness with mathematical precision, even where no one involved in building the model intended any discriminatory outcome.

**Implication:** Historical datasets are not a neutral starting point. Governance frameworks must require an explicit assessment of whether training data encodes historical patterns that would be unacceptable if designed into a model intentionally and explicitly — the fact that a pattern arrived "naturally" via historical data does not make it more acceptable than if someone had written it into the model's logic directly.

---

### CF-2: Postcode as a Proxy — A Known Industry Pattern, Not Locally Recognised

The risk of geographic variables functioning as proxies for protected characteristics in credit modelling is a well-documented industry-wide concern, discussed extensively in financial regulatory guidance, academic fairness-in-ML literature, and consumer advocacy reporting across multiple jurisdictions over several years. The organisation's data science team, at the time of the model's build, was not specifically aware of this body of guidance and had not received training oriented toward identifying this class of risk in their own work.

**Implication:** Technical AI practitioners need governance-oriented training that covers fairness concepts directly and concretely — not only general data science skills — because the people best positioned to notice a proxy variable at the point of model design are the people actually choosing which features to include, not a governance function reviewing the model only after the fact, if at all.

---

### CF-3: No Post-Deployment Monitoring for Fairness

Once deployed, the Credit Decisioning System's performance was monitored for predictive accuracy (default prediction accuracy and standard discrimination-power statistics in the technical, not fairness, sense of the term) but not for fairness metrics specifically. Demographic parity, equalised odds, and disparate impact measures were never tracked in production. The bias was therefore structurally invisible to the operational monitoring regime that did exist — the monitoring was working exactly as designed, and what it was designed to monitor for simply did not include this category of harm.

**Implication:** A monitoring framework for any AI system that affects individuals must include fairness metrics as a first-class, defined category alongside accuracy and performance metrics from the point of initial deployment — not added retroactively once a fairness problem happens to be discovered through some other means.

---

### CF-4: No Accessible Mechanism for Affected Individuals to Surface Concerns

Over the four years the bias was active, some rejected applicants may plausibly have suspected unfair treatment. However, no accessible mechanism existed for an applicant to raise a concern specifically about an AI-assisted decision as distinct from a general service complaint, and no clear disclosure informed applicants that an automated system was material to their assessment in the first place. Any such concerns that were in fact raised would have entered the organisation's general complaints process without being flagged, routed, or recognised as a potential AI fairness issue requiring specialist attention.

**Implication:** Customer-facing AI systems that materially affect individuals need a specific, accessible mechanism for those individuals to challenge an AI-assisted decision, and a defined internal process for routing that specific category of challenge to people equipped to assess it as a potential systemic issue — not merely as one customer's individual complaint to be resolved and closed.

---

### CF-5: Delayed Governance Programme Establishment

The organisation's formal AI governance programme was established only in early 2026, substantially triggered by the EU AI Act's phased entry into application for high-risk systems, rather than by proactive internal initiative. Had an equivalent governance programme — including even a basic periodic fairness audit requirement — been established two to three years earlier, in response to the broader industry and regulatory signals that were already visible well before the AI Act's deadlines forced the issue, the bias audit that ultimately detected this incident would very plausibly have occurred years sooner, materially reducing the number of applicants affected.

**Implication:** Proactive governance — established ahead of legal compulsion, in response to industry-wide risk signals rather than only to one's own organisation's specific legal deadlines — consistently produces materially better outcomes than governance that is established reactively, purely in response to an approaching regulatory deadline. Waiting for a law to require a control is observably not equivalent to actually managing the underlying risk that the law is responding to.

---

### CF-6: A Single, Narrow Monitoring Lens Created a False Sense of Adequate Oversight

A subtler systemic factor, worth naming explicitly because it is easy to overlook in a root cause analysis that focuses primarily on the absence of governance: the *presence* of conventional model performance monitoring (accuracy, default-prediction power) may have created a misleading sense within the organisation that the model was being adequately overseen at all. A model that is visibly and routinely monitored for some dimension of its behaviour can give an organisation false confidence about its overall governance maturity, when in fact the specific dimension that matters most for a given harm category was never in scope of that monitoring at all.

**Implication:** Governance maturity assessments — including the RMF-style maturity scoring used throughout this portfolio — must distinguish explicitly between the *existence* of monitoring and the *adequacy of its scope*. A system rated as having "monitoring in place" on a governance checklist can still harbour a severe, multi-year undetected harm if the checklist itself does not interrogate what is actually being measured.

---

## 5. Corrective Action Plan

| Action | Root Cause / Contributing Factor Addressed | Owner | Due Date | Status |
|---|---|---|---|---|
| Remove the postcode feature and retrain the Credit Decisioning System | Direct remediation | ML Engineering | 25 June 2026 | Complete |
| Mandate pre-deployment proxy analysis for all geographic and demographic-adjacent features in future model builds | CF-1, CF-2 | ML Engineering + AGPO | 31 August 2026 | In progress |
| Implement fairness metrics (demographic parity, disparate impact) in all credit model monitoring dashboards, alongside existing accuracy metrics | CF-3, CF-6 | ML Engineering | 31 August 2026 | In progress |
| Develop and deliver AI fairness training for all ML Engineering and data science staff, covering proxy discrimination specifically | CF-2 | AGPO + HR | 30 September 2026 | Not started |
| Implement a customer-facing AI disclosure and challenge mechanism for all credit decisions, distinct from the general complaints channel | CF-4 | Legal + Product + Customer Operations | 31 October 2026 | Not started |
| Update the AUCR template and Enhanced Review criteria (Project 3) to mandate proxy analysis for any feature that could plausibly encode a protected characteristic | Root cause | AGPO | 31 August 2026 | In progress |
| Conduct a retrospective proxy analysis on every other production model in the AI System Inventory, prioritising the Voice Biometric Authentication System and AML Transaction Monitoring System given their own outstanding maturity gaps from Project 1 | CF-1, CF-3 | ML Engineering | 31 October 2026 | Not started |
| Include fairness monitoring requirements explicitly in standard vendor AI contract terms going forward | CF-3 | Legal + Procurement | 30 September 2026 | Not started |
| Define an explicit "monitoring adequacy" criterion in the governance maturity rubric, distinguishing the presence of monitoring from its scope of coverage | CF-6 | AGPO | 30 September 2026 | Not started |

---

## 6. Lessons Learned

**For the AI governance programme:**

1. **Governance programmes must cover existing, already-deployed systems, not only new ones going forward.** The governance programme established in Project 3 was initially designed with new use case submissions as its primary focus. This incident demonstrates that the most significant governance exposure in most organisations sits in systems that predate any formal governance structure entirely. A standing retrospective audit programme — working backward through the existing AI system inventory, prioritised by risk tier — should be treated as a core, permanent element of the governance programme, not a one-time catch-up exercise to be completed and then set aside.

2. **Monitoring frameworks must include fairness metrics from the point of initial deployment, not added after a problem is found through some other route.** Accuracy alone is structurally incapable of surfacing this category of harm; a model can be highly accurate at predicting default risk overall while still being systematically unfair to a specific subgroup. Every AI system that affects individuals should have defined fairness metrics tracked alongside performance metrics, designed in from the start rather than retrofitted.

3. **Proxy discrimination is not obvious by inspection, and an organisation should not expect it to be caught informally.** Postcode reads, on its face, as an entirely legitimate variable, and the discriminatory effect it produced was invisible to the team that originally built the model, despite their not having any discriminatory intent. Governance frameworks need to build in explicit, structured prompts to look specifically for proxy effects in any feature that touches geography, language, or other characteristics correlated with protected groups — it is not sufficient to simply prohibit the use of protected characteristics directly, since the harm here arose entirely through a facially neutral variable.

4. **Speed of detection is the single largest determinant of the eventual scale of harm.** This particular bias was active for roughly four years before being caught. A governance programme established even two years earlier, or a periodic fairness monitoring requirement introduced at any point during that window, would very likely have caught it sooner and proportionally reduced the number of people affected. The corrective action plan therefore deliberately prioritises detection capability — fairness monitoring, retrospective audits — ahead of process documentation improvements, because detection capability is what bounds the scale of the next incident of this kind, whereas documentation alone does not.

5. **Regulatory compliance and genuinely good governance are not the same thing, and treating them as equivalent is itself a risk.** No specific legal obligation required a fairness audit of this model at the time it was built. A proactive governance posture, oriented toward managing real risk to real people rather than toward meeting only the prevailing legal minimum, would have identified the need for that audit anyway, well ahead of any regulatory deadline. An AI governance programme that calibrates its own ambition level purely to "what the law currently requires" will, by construction, always be reactive to the previous generation of harms rather than anticipating the next one.

6. **A root cause analysis is itself a governance artefact, and its quality should be held to the same standard as any other control.** The decision in this RCA to separate the 5 Whys causal chain from a broader contributing factors analysis — rather than forcing every relevant factor into one linear narrative — is a deliberate methodological choice or this exact RCA process. An organisation that consistently produces RCAs collapsing multiple independent contributing conditions into a single tidy root cause is at risk of consistently under-resourcing its corrective action plans, because a narrow RCA tends to produce a narrow, single-item response when several parallel fixes are actually required.

---

*RCA approved by the AI Governance Committee — 24 July 2026*
*Distribution: AI Governance Committee · Board Risk & Audit Committee · relevant national regulator (summary version) · Internal Audit*
