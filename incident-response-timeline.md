# Incident Response Timeline — AI-INC-2026-001

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**Incident:** Credit Decisioning System Postcode Bias
**Timeline Period:** May 2026 — August 2026

---

## Week 1 (4–8 May 2026): Detection and Immediate Response

### Day 1 — Monday 4 May
**Event:** Detection

- The data scientist seconded to the AI Governance Programme Office identifies an anomalous, statistically significant postcode-correlated score disparity while conducting the system's first formal bias audit
- The finding is documented immediately and shared with the AI Governance Lead
- Informal escalation to the Director of Credit Risk begins the same afternoon

**Status:** Detection phase.

---

### Day 2 — Tuesday 5 May
**Event:** Escalation and Initial Triage

- The Director of Credit Risk convenes an emergency call with the AI Governance Lead and the data scientist who made the finding
- Preliminary analysis confirms the finding: the disparity is statistically significant and consistent across several postcode clusters, not a single anomalous data point
- The AI Governance Programme Office formally classifies the matter as a Severity 1 incident (AI-INC-2026-001) and initiates the incident response procedure established under Project 3's governance operating model

**Notifications issued:**
- Chief Risk Officer notified (Day 2, within the 24-hour requirement) ✓
- Legal and Compliance notified ✓
- Data Protection Officer notified ✓

**Immediate containment decision:**
The AI Governance Programme Office and the Director of Credit Risk jointly recommend immediate suspension of automated decision-making for applications from the affected postcode clusters, pending further investigation. Applications from those postcodes are to be routed to manual underwriting review in the interim.

The Chief Risk Officer approves the containment measure.

---

### Day 3 — Wednesday 6 May
**Event:** Containment Implemented; Board Notification

- The Credit Decisioning System's output for applications from the affected postcode clusters is suspended as the sole decisioning input
- Applications from the affected postcodes (approximately 18–22 per day) are routed to a manual underwriting queue
- Manual underwriting capacity is confirmed adequate for the interim volume, with a contingency plan prepared in case volume exceeds initial estimates
- The Board Risk & Audit Committee Chair is notified by the Chief Risk Officer, within the 48-hour requirement ✓
- An extraordinary AI Governance Committee session is scheduled for 8 May

**Legal and Compliance begin a parallel regulatory disclosure assessment, addressing four distinct questions simultaneously:**
- Does this meet the EU AI Act Article 73 threshold for a "serious incident"?
- Does this trigger a notification obligation to the financial conduct authority?
- Were affected applicants adequately informed of automated decision-making, satisfying applicable data protection law?
- Does the pattern constitute indirect discrimination in access to goods and services under applicable equal treatment law?

---

### Day 4–5 — Thursday–Friday 7–8 May
**Event:** AI Governance Committee Extraordinary Session

**Agenda:**
1. Incident briefing and confirmed scope to date
2. Containment status
3. Regulatory disclosure recommendation
4. Investigation plan approval
5. Customer communication approach

**Decisions made:**
1. Containment measure approved as ongoing, pending completion of the model investigation
2. Legal and Compliance instructed to prepare a regulatory disclosure recommendation for Chief Risk Officer approval by 15 May
3. An independent external fairness consultancy is commissioned to conduct a forensic analysis of the model, engaged by 11 May
4. A retrospective review programme is initiated: every application from the affected postcodes over the past 48 months is to be pulled and reviewed
5. Customer communication strategy: no proactive outreach to affected applicants until the scope of harm is properly quantified — target date for an outreach plan: 22 May
6. Internal staff briefing: Credit Risk, Customer Operations, and Compliance staff to receive a briefing on the incident by 12 May, framed around what they should and should not say if contacted by an affected customer in the interim

---

## Week 2 (11–15 May 2026): Investigation

### Actions

- External forensic analysis of the Credit Decisioning System model begins
- An internal data pull covers every application from the affected postcodes since the model's original go-live (2021–2026)
- A full feature importance analysis is commissioned to identify every input contributing materially to the disparity, not only the postcode feature already suspected
- The Data Protection Officer reviews whether automated-decision disclosure was made correctly for past decisions, consistent with applicable data protection law
- Legal begins drafting the regulatory notification letters in parallel, so they are ready to issue immediately once the Chief Risk Officer's disclosure decision is confirmed
- The AI Governance Programme Office checks whether any other system in the organisation's inventory operates in the same affected geography and could exhibit a similar pattern — the CV Screening & Ranking System (ORG-AI-002) is specifically checked, given that it also processes applicants across the same postcodes, and a separate, precautionary bias review of that system is opened as a result

**Emerging findings (preliminary):**
- The postcode feature contributes approximately 9% to the overall model score in the affected clusters — a material, not marginal, contribution
- The disparity has been present since the model's original go-live; it was not introduced by any subsequent update, meaning the affected period is the full operational life of the system
- Approximately four years of applications are within scope for the retrospective review
- The precautionary review of the CV Screening & Ranking System finds no equivalent geographic feature in that model, narrowing the immediate concern back to the credit system alone, though the review itself is logged as a useful precedent for how the organisation now checks laterally across its inventory when an incident is confirmed

---

## Week 3 (18–22 May 2026): Scope Confirmation and Regulatory Engagement

### External Forensic Analysis — Preliminary Findings (19 May)

**Key findings:**
1. The postcode feature acts as a statistically significant proxy for a protected characteristic across a defined set of postcode clusters
2. The average score depression for affected applicants is 41 points (range: 28–63 points across the affected clusters)
3. At the organisation's credit policy thresholds, a 41-point depression translates into an increased rejection rate of approximately 11 percentage points for applicants near the approval borderline
4. The disparity cannot be explained by genuine underlying creditworthiness differences — the model is introducing bias, not detecting a real risk differential that happens to correlate with geography
5. Root cause (preliminary): postcode was included as a geographic feature at the model's original build with no proxy-discrimination analysis performed. The historical training data reflected lending patterns in those areas that themselves likely reflected past discriminatory practices, meaning the model risked learning to replicate historical unfairness rather than to predict genuine risk

**Scope confirmed:**
- 3,940 applications from the affected postcodes reviewed since the model's original go-live
- 812 rejections identified as potentially influenced by the bias
- 1,740 approvals identified as potentially issued at inflated interest rates or reduced limits

**Regulatory disclosure decision (22 May):**
The Chief Risk Officer approves regulatory notifications on Legal and Compliance's recommendation:
- Financial conduct authority formal notification submitted: 22 May 2026
- EU AI Act national competent authority notified: 22 May 2026
- Data protection authority notified, regarding the potential automated-decision disclosure gap: 22 May 2026

---

## Week 4 (25–29 May 2026): Customer Impact Assessment and Communication Plan

### Customer Impact Quantification

Finance and Credit Risk jointly complete a financial impact model:
- Total estimated excess interest charged to affected approved applicants: approximately €2.1 million
- Estimated number of applicants who were rejected but would likely have been approved under a fair model: 218, based on a re-scoring exercise that removes the postcode feature and reruns the model against the same applications

### Customer Communication Plan Approved (28 May)

**Decision:** Proactive outreach to every affected customer, rather than a passive disclosure-on-request approach.

Communication approach:
1. **Affected applicants who were rejected** — a personal letter acknowledging that their application may have been unfairly assessed, offering a fresh review at no cost, with the new decision made by a human underwriter rather than the system
2. **Affected applicants who were approved at higher rates** — a personal letter acknowledging potential overcharging, confirming they will receive a calculation of any excess interest paid, with a refund to follow
3. **General public notice** — published prominently on the organisation's customer-facing website: a plain-language acknowledgement that a bias issue was identified and is being actively remediated, without disclosing internal investigative detail that is not yet finalised

Legal approves the communications as drafted. The Data Protection Officer confirms the approach is compliant with applicable data protection requirements.

**Customer outreach begins: 2 June 2026**

---

## Week 5–6 (1–12 June 2026): Remediation

### Model Remediation Plan (approved 1 June)

**Short-term (immediate):**
- Remove postcode as a feature from the Credit Decisioning System model entirely
- Retrain the model on an adjusted dataset with postcode excluded
- Validate the retrained model against defined fairness criteria before any redeployment is considered

**Medium-term (60 days):**
- Commission a full independent fairness audit of the retrained model, separate from the forensic analysis already conducted on the original model
- Implement ongoing demographic parity monitoring directly in production, not as a periodic manual exercise
- Establish automated alerting for any emerging score disparity, so a future drift of this kind would be caught in weeks rather than years

**Model retraining timeline:**
- Postcode removal and retraining: 1–25 June
- Internal validation: 26 June – 9 July
- External fairness audit: 10–26 July
- Redeployment, with enhanced monitoring in place: 1 August 2026

**During the remediation period:** all credit decisions continue to be made via manual underwriting, with the temporary capacity increase maintained throughout.

### Retrospective Review Programme

- All 812 rejected applications under review by an internal underwriting panel constructed specifically to exclude any staff member who had any role in the original model's development, to avoid a conflict of interest in re-assessing decisions the model itself produced
- Target completion: 26 June 2026
- Applicants whose original rejection is reversed on review are contacted with a new, current offer rather than a backdated one, given that underlying financial circumstances may have changed in the intervening period

---

## Week 9–11 (July 2026): Root Cause Analysis and Lessons Learned

- The formal root cause analysis is completed (see `root-cause-analysis.md`)
- The AI Governance Committee reviews the RCA and approves the full corrective action plan on 24 July
- The retrained model completes independent validation
- The external fairness audit is completed and confirms the retrained model no longer exhibits the postcode-correlated disparity within the audit's defined tolerance thresholds

**Model redeployment approved: 30 July 2026**, conditional on the enhanced monitoring controls being fully operational and tested at the point of go-live, not merely scheduled to be implemented shortly afterward.

---

## Week 13 (10–14 August 2026): Incident Closure

**Closure conditions:**
- [x] All affected customers contacted
- [x] Retrospective review of rejected applications complete
- [x] Refunds calculated and issued
- [x] Retrained model independently validated
- [x] Fairness audit completed
- [x] Regulators updated with a closure report
- [x] Root cause analysis and corrective actions documented and formally approved
- [x] Lessons learned shared with the broader AI governance programme, including the precautionary lateral check applied to the CV Screening & Ranking System
- [x] Board formally notified of closure

**Incident closed: 13 August 2026**

---

## Incident Summary — Key Metrics

| Metric | Value |
|---|---|
| Detection to containment | 2 days |
| Detection to regulatory notification | 18 days |
| Affected applications reviewed | 3,940 |
| Rejections under retrospective review | 812 |
| Offers issued to previously rejected applicants | 218 |
| Excess interest refunded | approximately €2.1 million |
| Days to model redeployment | 88 |
| Total incident duration | 101 days |

---

*This timeline is a simulation of a well-managed AI incident response. In practice, real timelines vary significantly based on investigation complexity, the number of regulators involved, the organisation's existing operational capacity, and the specific facts of the case.*
