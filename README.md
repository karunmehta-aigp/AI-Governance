# Project 4: AI Incident Response & Regulatory Escalation Scenario

> **⚠️ Disclaimer:** This project is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed in this material.

## Scenario

**Organisation:** The organisation (as established in Project 1)
**Incident:** The Credit Decisioning System (ORG-AI-001) is found to produce systematically lower creditworthiness scores for loan applicants residing in postcodes that correlate with concentrations of ethnic minority and lower-income residents.

The incident is detected in May 2026 — several weeks after the organisation's AI governance programme structures from Project 3 were formally stood up, but for a model that had been quietly running in production since 2021, long before any of that structure existed. This is deliberate: it demonstrates that a governance programme's first real test is rarely a brand-new system going through Enhanced Review. It is almost always an old system, built before governance existed, whose problems the new structure has to confront retroactively. How an organisation responds to that kind of failure — how fast it is contained, how thoroughly it is investigated, how honestly it is disclosed — is as much a test of governance maturity as the policy documents in Project 3 ever were.

## What This Project Demonstrates

- Understanding of AI governance as **an ongoing discipline carried out in real time under pressure**, not a point-in-time compliance exercise completed once and then filed away.
- Knowledge of how to structure a complete **AI incident response**: detection, triage and severity classification, containment, investigation, regulatory engagement, customer remediation, and formal closure — each with defined owners and timelines, not an undifferentiated "we looked into it and fixed it."
- Awareness of the specific **regulatory escalation obligations** that attach to an AI system once a serious fairness incident is confirmed, spanning the EU AI Act, financial conduct regulation, data protection law, and equal treatment law simultaneously — and the judgement required to manage four parallel regulatory conversations rather than treating them as one undifferentiated "compliance issue."
- Practical, applied understanding of the **NIST AI RMF Manage function**: not an abstract category, but the actual operational discipline of containing harm, coordinating a cross-functional response, and feeding what is learned back into the governance programme that Project 3 established.
- Ability to apply a **structured root cause analysis methodology** (5 Whys plus contributing factors) to an AI system specifically, distinguishing a technical root cause from the organisational and governance conditions that allowed it to persist undetected for years — and the related discipline of identifying contributing factors that, individually, would not have caused the incident, but that compounded the harm or delayed its detection.

## Artefacts

| File | Description |
|---|---|
| `incident-scenario.md` | Full incident description: how the bias was discovered, its mechanism, its scope, and its initial severity classification |
| `incident-response-timeline.md` | A week-by-week incident response timeline from detection through formal closure, with regulatory notifications, containment decisions, and remediation milestones |
| `root-cause-analysis.md` | A structured 5 Whys root cause analysis, contributing factors assessment, corrective action plan, and lessons learned, formally approved by the AI Governance Committee established in Project 3 |

## Why This Project Matters

AI incidents of this kind are not hypothetical. Discriminatory credit scoring, biased recruitment screening, and opaque automated decision-making have already produced regulatory enforcement action, litigation, and significant reputational harm at real organisations across multiple jurisdictions. An AIGP-credentialed governance professional needs to be able to operate not only in the calm, structured world of policy design (Project 3) but in the compressed, high-stakes environment of an active incident, where decisions about containment, disclosure, and remediation have to be made with incomplete information and under genuine time pressure.

The EU AI Act does not regulate AI only at the point of deployment. It establishes obligations across the entire operational lifecycle, several of which are directly engaged by this incident:

- **Article 9** — risk management as a continuous process, not a one-time pre-deployment exercise
- **Article 12** — logging and traceability, which determines how quickly an investigation can establish scope and causation
- **Article 17** — post-market monitoring, the absence of which is precisely what allowed this incident to run undetected for years
- **Article 73** — the obligation to report serious incidents to national authorities, and the judgement required to determine whether a given incident meets that threshold

This project simulates what a well-prepared organisation does once an AI system is confirmed to be causing harm. The quality of that response — measured in days to containment, the thoroughness of the scope assessment, and the honesty of the regulatory and customer disclosure — is what determines whether an incident becomes a contained, well-managed problem or an escalating regulatory and reputational crisis.

## Corporate and Regulatory Context Worth Noting

A few points of broader industry context that an AIGP-credentialed professional should be able to speak to, illustrated by this incident:

**Postcode and similar geographic variables are a recurring, well-documented proxy discrimination risk in credit modelling**, not a novel or obscure failure mode. Financial regulators across multiple jurisdictions have published guidance specifically flagging geographic and historically-correlated variables as carrying elevated fairness risk, precisely because of the link between historical residential patterns (including the lasting effects of historical discriminatory lending and housing practices) and present-day postcode-level demographic concentration. A governance professional encountering this incident in practice should recognise it as a known risk pattern, not treat it as an unprecedented surprise.

**The gap between "no fairness audit was legally required" and "no fairness audit should have been done" is itself a governance maturity signal.** At the time this system was built, no specific legal obligation mandated a pre-deployment bias audit for it. This incident's root cause analysis makes a deliberate point of treating that fact as an aggravating insight rather than a mitigating defence — proactive governance that exceeds the regulatory floor is what actually prevents harm; waiting for law to mandate a control is a reactive posture that, as this case shows, allows preventable harm to accumulate for years before it is caught.

**Detection method matters as much as detection speed.** This incident was caught by an internal bias audit conducted as part of the very governance programme stood up in Project 3 — not by a regulator, a journalist, or a customer complaint. This is the single clearest demonstration in the whole portfolio of why Projects 1 through 3 were worth building before Project 4's incident ever needed to happen: the governance infrastructure is what converts a years-long latent harm into a controlled, internally-detected, properly-managed incident instead of an external scandal.

## Frameworks Applied

- **NIST AI RMF** — the Manage function in full: anticipating, monitoring for, responding to, and recovering from AI-related harms, and feeding the results of that response back into the broader governance programme established in Project 3
- **EU AI Act** — Article 9 (ongoing risk management), Article 12 (logging and traceability), Article 17 (post-market monitoring), Article 73 (reporting of serious incidents to national authorities)
- **ISO/IEC 27035** — incident management principles (detection, triage, response, lessons learned), adapted from information security practice to the specific context of an AI fairness incident
- **Sector conduct regulation principles** — the general financial conduct obligations to act in customers' best interests and to deal openly and cooperatively with regulators, both of which are directly engaged by an incident of this kind regardless of which specific AI regulation also applies

---

*Author: Anju Karun · AIGP (AI Governance Professional)*
