# Incident Description — Credit Decisioning System Postcode Bias

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**Incident ID:** AI-INC-2026-001
**System:** ORG-AI-001 · Credit Decisioning System
**Incident Type:** AI Fairness / Discriminatory Output
**Severity:** 1 — Critical
**Status:** Under Investigation (as of Week 2)
**Incident Owner:** Director of Credit Risk
**Governance Lead:** AI Governance Programme Office

---

## Incident Summary

The Credit Decisioning System, the organisation's ML-based credit scoring model, has been found to systematically assign lower creditworthiness scores to loan applicants residing in postcodes that correlate with concentrations of ethnic minority and lower-income residents. The effect is statistically significant and cannot be explained by genuine differences in financial history or creditworthiness indicators alone.

The disparity results in affected applicants facing higher rejection rates, higher interest rates, or lower loan limits than comparably creditworthy applicants from other postcodes. This constitutes potential indirect discrimination under equal treatment law and raises serious compliance concerns under the EU AI Act, independent of and in addition to the governance gaps already flagged for this system in Project 1's classification work and Project 1's RMF maturity mapping.

---

## How the Incident Was Detected

**Detection source:** Internal bias audit, conducted by the AI Governance Programme Office as part of the structured review cadence established in Project 3

**Detection narrative:**

In early May 2026, a data scientist seconded part-time to the AI Governance Programme Office was conducting the first formal bias audit of the Credit Decisioning System — the same audit identified as an outstanding priority action in Project 1's NIST RMF mapping for this system. While examining model outputs disaggregated by geography, she identified an anomaly: applicants from a defined cluster of postcodes were receiving creditworthiness scores 30–55 points lower on average than applicants with otherwise comparable financial profiles from other postcodes.

She flagged the finding immediately to the AI Governance Lead, who escalated to the Director of Credit Risk the same day. Initial internal analysis confirmed the finding was statistically robust and not an artefact of sample size or seasonal variation. The affected postcode cluster corresponds closely, according to national demographic statistics, with areas carrying above-average concentrations of ethnic minority and lower-income residents.

A preliminary assessment indicates that postcode was included in the original 2021 model build as a general "geographic risk factor," reflecting a common — but, as this incident demonstrates, risky — practice in credit risk modelling of using location as a proxy for local economic conditions. In this instance, postcode is instead acting as a proxy for protected characteristics, producing indirect discrimination rather than a genuine measure of credit risk.

---

## Scope and Impact Assessment

**Estimated affected population (preliminary):**
- Approximately 2,600 loan applications processed from the affected postcode cluster in the 12 months preceding discovery
- Of those, approximately 740 resulted in a rejection decision
- Approximately 1,250 resulted in approval, but at higher interest rates or lower credit limits than a postcode-agnostic model would have produced

**Financial impact to affected customers (preliminary estimate):**
- Excess interest paid as a result of inflated risk pricing: to be quantified during the investigation
- Credit access denied: 740 applications, an unknown proportion of which would likely have been approved under a fair model

**Regulatory implications:**
- **EU AI Act Article 73** — serious incidents involving AI systems must be reported to the relevant national authority; this incident may meet the definition of a "serious incident," given the apparent significant impairment of affected individuals' right to non-discrimination
- **Financial conduct regulation** — an obligation to report material conduct issues affecting customer outcomes to the relevant financial conduct authority
- **Data protection law** — automated decision-making challenge rights may have been unlawfully impaired if affected applicants were not adequately informed that an automated system was material to their assessment
- **Equal treatment / non-discrimination law governing access to goods and services** — indirect discrimination in access to financial services on the basis of a protected characteristic, even where the discrimination arises via a facially neutral proxy variable rather than direct classification

**Reputational risk:** High. Algorithmic discrimination in consumer financial services is a high-visibility regulatory and media issue across multiple jurisdictions. Proactive, transparent handling of this incident — rather than a defensive or minimising posture — is essential to limiting reputational harm and to demonstrating the credibility of the broader governance programme to regulators and the public alike.

---

## Immediate Context

**Why was postcode included in the model?**
Postcode was included as a geographic risk variable on the assumption that it reflected local economic conditions — local unemployment rates, property values, and general area-level economic health. This is a commonly used variable category in credit risk modelling generally. In this organisation's operating context, however, postcode also encodes historical patterns of residential concentration correlated with ethnicity and income, meaning it functions in practice as a proxy for protected characteristics rather than a clean measure of economic context.

**Was the risk known?**
The informal risk review conducted at the model's original build in 2021 — predating any formal AI governance programme — did not include a structured proxy-discrimination analysis of geographic variables. The inclusion of postcode was not specifically questioned at the time, because no process existed that would have required it to be questioned. This is precisely the kind of structural gap that Project 1's classification exercise and RMF mapping flagged for this system, and that this incident now demonstrates was not a theoretical concern.

**Is this ongoing?**
Yes. The Credit Decisioning System processes applications in real time, continuously. Every application processed during the incident period, and every application that would be processed going forward absent intervention, may be affected. Immediate containment is required as a first step, independent of and prior to the full investigation.

---

## Incident Severity Classification

| Dimension | Assessment |
|---|---|
| Harm to individuals | High — potential financial harm and discriminatory treatment affecting multiple protected groups |
| Regulatory exposure | Critical — multiple, simultaneous potential reporting obligations across different regulatory regimes |
| Reputational risk | High |
| Operational impact | Medium — model suspension for affected postcodes requires a temporary shift to manual underwriting capacity |
| Reversibility | Medium — past decisions can be reviewed and remediated retrospectively; the model itself can be retrained, but the time already affected individuals have lived with an adverse outcome cannot be fully undone |

**Overall severity: 1 — Critical**

Severity 1 incidents require, per the incident response procedure established alongside Project 3's governance operating model:
- Immediate notification to the AI Governance Committee, within 24 hours of confirmation
- Chief Risk Officer notification within 24 hours
- Board Risk & Audit Committee notification within 48 hours
- Immediate involvement of Legal and Compliance
- Formal consideration of regulatory disclosure obligations as a first-week priority, not a downstream afterthought

---

*This incident document was prepared by the AI Governance Programme Office on the day the finding was confirmed. It is a living document, updated as the investigation progresses, consistent with the structure set out in the accompanying incident response timeline.*
