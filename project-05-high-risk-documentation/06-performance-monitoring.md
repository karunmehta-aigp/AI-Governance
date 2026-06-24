# Document 06: Performance Monitoring Plan

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**System:** TalentBridge Screener (ORG-AI-011)
**EU AI Act Reference:** Article 15 (Accuracy, Robustness, Cybersecurity) · Article 17 (Post-Market Monitoring)
**Document Type:** Deployer
**Version:** 1.0 — October 2026

---

## 1. Purpose

Article 17 of the EU AI Act requires deployers of high-risk AI systems to implement a post-market monitoring plan that systematically collects and analyses performance data throughout the system's operational life. Article 15 requires that the system achieve and maintain an appropriate level of accuracy, robustness, and cybersecurity.

This plan is built to do more than satisfy that minimum legal bar. It is written so that an external reviewer — a regulator, an auditor, or a prospective employer assessing this portfolio — can see exactly what is measured, why that specific metric was chosen over plausible alternatives, what the response is when a threshold is breached, and how this monitoring plan learns from the rest of this portfolio rather than existing in isolation.

---

## 2. Monitoring Objectives

This plan is organised around four objectives, each mapped to a specific category of failure this portfolio has already documented somewhere in Projects 1 through 4 — monitoring exists to catch the next version of a failure this organisation has already seen at least once, not only theoretical risks:

1. **Performance validation** — is the model still doing the job it was approved to do?
2. **Fairness assurance** — is the model treating comparable candidates comparably, regardless of group membership? (Directly responsive to Project 4's incident, where a fairness failure went undetected for years precisely because no fairness-specific monitoring existed.)
3. **Oversight quality assurance** — is human review still meaningful, or has it quietly degraded into a formality? (Directly responsive to the oversight capacity erosion risk named in Project 3 and tested operationally in Project 2's AML risk assessment.)
4. **Drift and currency detection** — has the world the model operates in changed enough that its original validation no longer reflects current reality?

---

## 3. Performance Metrics

### 3.1 Model Performance Metrics

| Metric | Definition | Why This Metric, Specifically | Target | Frequency | Alert Threshold |
|---|---|---|---|---|---|
| **Shortlist stability rate** | The percentage of candidates appearing in the AI's shortlist who remain in the coordinator's final shortlist, unmodified | Chosen over a simple "acceptance rate" because it captures partial agreement at the candidate level, not just whether the whole shortlist was accepted wholesale — a more granular and more honest signal of how much the AI's judgement and the human's judgement actually converge | Baseline established over the first full quarter of production, then tracked relative to that baseline | Monthly | A change of more than 20 percentage points from the established baseline in either direction |
| **Time-to-shortlist** | Elapsed time from job description finalisation to a coordinator-approved shortlist being ready | A genuine efficiency metric — the entire business case for this system rests on this number improving relative to fully manual screening, and that business case should be measured honestly, not assumed | Established at acceptance testing | Monthly | A sustained reversion toward, or beyond, the pre-AI manual screening baseline, which would indicate the tool is not delivering its intended benefit |
| **Explanation usefulness rating** | Coordinator-submitted rating (on a defined scale) of whether the explanation text for a given candidate was useful in reaching a decision | Distinguishes a model that scores well from a model that scores well *and* explains itself well enough to support genuine oversight — Article 14 requires the latter, not only the former | A defined minimum average rating | Quarterly | Two consecutive quarters below the defined minimum |
| **Special category data filter trigger rate** | Percentage of CVs flagged by the automated special-category-data filter | Primarily informational, but a sudden change can indicate either a shift in the applicant population or a filter malfunction, both worth investigating | Informational baseline | Monthly | A material deviation from the established baseline range |

### 3.2 Fairness Metrics

This section is deliberately the most detailed in this plan, given that the absence of an equivalent section is the single root cause Project 4's analysis traced the organisation's worst incident back to.

| Metric | Definition | Why This Metric | Target | Frequency | Alert Threshold |
|---|---|---|---|---|---|
| **Demographic parity ratio** | The shortlisting rate for a given proxy group, divided by the shortlisting rate for the largest reference group | The standard industry baseline fairness metric; chosen as the first-line metric because it is simple to compute, simple to explain to a non-technical Committee member, and directly comparable across reporting periods | A ratio of at least 0.80 for every measurable proxy group, the same threshold used industry-wide as a conventional fairness screening line | Quarterly | Any group falling below 0.80, or a declining trend across two consecutive quarters even if still above 0.80 |
| **Equal opportunity difference** | The difference in shortlisting rate between groups, calculated only among candidates who are genuinely well-qualified for the role by an independent, model-external criterion | Chosen specifically *in addition to* demographic parity, because parity alone can be satisfied in a misleading way if a system shortlists comparable raw *numbers* from each group while still being systematically less accurate at correctly identifying the strongest candidates *within* one group — this metric is designed to catch that specific failure mode, which a parity ratio alone would miss entirely | No statistically significant difference between groups | Quarterly | A statistically significant gap, assessed at a conventional significance threshold |
| **Override-correction rate by group** | Among candidates the model scored lower, the rate at which human override moved them into the final shortlist, broken out by demographic proxy | This is an original metric specific to this monitoring plan, not a standard industry metric — it exists to answer a question neither demographic parity nor equal opportunity difference can answer on its own: is human oversight *actively correcting* any model-level disparity, or is it passively reproducing the same pattern the model already shows? | No systematic difference in override-correction rate across groups | Quarterly | A pattern where one group is being "rescued" by human override at a meaningfully different rate than another, which would indicate the human layer is itself an uneven safeguard |
| **Score-distribution overlap** | The degree of overlap between the score distributions of different proxy groups, rather than only comparing group means | Comparing means alone can hide a meaningful difference in distribution shape — two groups can have similar average scores while one group's distribution is far more spread out, meaning that group experiences more volatile, less predictable outcomes even at an equal average | High overlap, assessed qualitatively alongside the quantitative metrics above | Quarterly | A visibly diverging distribution shape flagged for qualitative review by the AI Governance Programme Office, even if the mean-based metrics above do not independently trigger |

**A note on proxy data, stated plainly rather than buried in a footnote:** the organisation does not collect protected characteristic data from candidates. Every fairness metric above is therefore computed using imperfect proxy indicators, and every report presenting these metrics states that limitation in the same paragraph as the finding itself — not in a separate caveats section that a reader could skip past.

### 3.3 Oversight Quality Metrics

| Metric | Definition | Why This Metric | Target | Frequency | Alert Threshold |
|---|---|---|---|---|---|
| **Override rate** | Percentage of AI shortlists modified in any way by a coordinator | The headline oversight-health metric: too low suggests passive acceptance; too high suggests the model itself may not be performing adequately, in which case the problem is with the model, not the reviewers | A defined normal operating range, established from the first quarter of production and revisited annually | Monthly | Below the lower bound (possible passive acceptance) or above the upper bound (possible model inadequacy) |
| **Median review time per candidate** | Median time a coordinator spends actively engaged with a candidate's profile before a shortlist decision | A direct, simple proxy for whether review is substantive; chosen deliberately as a *floor* metric, not a ceiling — there is no penalty in this plan for a coordinator spending longer than the floor, only for spending less | A minimum threshold established during acceptance testing | Monthly | Sustained time below the established minimum |
| **Override-reason category distribution** | The relative frequency of each structured override-reason category (Document 04) over time | A sudden shift in which reasons dominate can be an early indicator of an emerging model issue — for example, a sharp rise in "explanation text does not reflect relevant unlisted experience" could indicate the model is increasingly missing a particular kind of relevant experience across many candidates, not just one | No specific target; tracked for trend | Quarterly | Any category's share shifting materially from its established baseline |
| **Candidate challenge rate** | Percentage of rejections that result in a candidate-initiated challenge | A customer-facing signal of whether the process feels fair and explicable from the outside, complementing the internally-facing metrics above | An informational baseline | Quarterly | A rate materially above the established baseline |
| **Training currency** | Percentage of active system users with current, non-expired oversight training | A binary compliance metric with zero tolerance, consistent with the access-gating control described in Document 04 | 100% | Continuous | Any drop below 100% triggers automatic access suspension for the relevant individual, not merely a flag for review |

---

## 4. Why This Plan Goes Beyond the Legal Minimum

Article 17 requires "a" post-market monitoring plan; it does not mandate the specific metrics above. The choice to include four separate fairness metrics, rather than the single demographic parity ratio that would technically satisfy a minimal reading of the obligation, is a deliberate decision consistent with Project 4's central lesson: the predecessor incident occurred in an environment with *no* fairness metric tracked at all, and the broader lesson drawn from that incident was that compliance with the legal floor and genuinely effective governance are not the same thing. A monitoring plan calibrated only to the minimum legal requirement would, by the same logic, be vulnerable to exactly the kind of single-metric blind spot this plan is specifically designed to avoid.

---

## 5. Monitoring Cadence and Responsibilities

| Activity | Frequency | Owner | Output |
|---|---|---|---|
| Automated metric dashboard refresh | Daily | AI Governance Programme Office (automated) | Live dashboard, accessible to the HR Director and AI Governance Programme Office |
| Override and review-time check | Monthly | HR Director | Escalation to the AI Governance Programme Office if any threshold is triggered |
| Full performance and fairness report | Quarterly | AI Governance Programme Office | Presented to the AI Governance Committee |
| Vendor model performance report review | Quarterly (vendor-supplied) | AI Governance Programme Office | Cross-checked against the organisation's own independent metrics, not accepted at face value |
| Annual system review | Annual | AI Governance Programme Office | Full review feeding the system's continuation decision, per the lifecycle requirements in Project 3 |

---

## 6. Drift Detection and Revalidation Triggers

| Trigger | Rationale |
|---|---|
| Demographic parity ratio falls below 0.80 for any group | A direct, threshold-defined fairness concern requiring immediate attention |
| Equal opportunity difference becomes statistically significant | A subtler fairness concern that parity alone would not catch, per Section 3.2 |
| Override-correction rate diverges materially across groups | An indication that human oversight itself may not be functioning evenly, the specific failure mode this plan's original metric (Section 3.2) was designed to surface |
| The organisation's hiring mix shifts materially — for example, expansion into a new function not well represented in the original validation data | The model's original validation may no longer generalise to a meaningfully different applicant population |
| Vendor G releases a new model version | Any material model change requires the organisation's own validation before acceptance into production, per the contractual right secured in Document 02, R5 |
| Any AI incident involving this system | Standard post-incident revalidation, consistent with the closure conditions exercised in Project 4 |
| 24 months since the last full revalidation, absent any other trigger | A scheduled backstop, so the system is never left unrevalidated indefinitely simply because no other trigger happened to fire |

When a trigger is reached, the AI Governance Programme Office initiates a formal revalidation review. The system continues operating during revalidation unless the AI Governance Programme Office determines the specific trigger represents a risk material enough to warrant suspension in the interim — a judgement call documented explicitly each time, rather than a fixed automatic rule, since the right response to "24 months have passed" is materially different from the right response to "a fairness threshold has been breached."

---

## 7. Serious Incident Escalation Pathway

If monitoring detects a pattern serious enough to potentially meet the threshold for a reportable incident, the escalation follows the same structure exercised in Project 4, applied proactively here rather than reconstructed under pressure for the first time:

```
[Detection] Metric alert triggered, or a material candidate
            challenge pattern identified
     |
     v
[AI Governance Programme Office triage] Is this a potential
            serious incident? Assessed within a committed
            short window, not left open-ended
     |
     +---> Not a serious incident: documented; monitoring
     |     frequency increased for the relevant metric
     |
     +---> Potential serious incident: AI Incident Response
           procedure initiated immediately
              |
              v
           AI Governance Committee notified per the timeline
           established in Project 3's governance operating model
              |
              v
           Regulatory reporting obligation assessed under
           Article 73, following the same structured four-part
           question set used in Project 4's incident
              |
              v
           Containment, investigation, and remediation proceed
           per the incident response procedure
```

---

## 8. Annual System Review

At the system's first annual review mark, the AI Governance Programme Office will produce a full review covering: a summary of performance against every metric in this plan; a fairness analysis summary, with particular attention to whether the override-correction rate metric (Section 3.2) has shown any persistent group-level divergence; an incident log review; an oversight quality assessment; a vendor performance assessment, cross-checked against the organisation's own independent data rather than the vendor's report alone; a regulatory change assessment; and a continuation recommendation.

This review is presented to the AI Governance Committee, and the system's continuation in production is conditional on a satisfactory outcome — consistent with every other system in this portfolio being subject to the same standing principle that approval is not a one-time event but a continuously renewed judgement.

---

## 9. Documentation and Retention

All monitoring outputs — dashboards, quarterly reports, annual reviews, incident records, and revalidation findings — are retained for 36 months in the AI Governance Programme Office's documentation archive, and are available for regulatory inspection on request.

---

*This monitoring plan is a living document. Metric thresholds and review frequencies may be refined based on experience in the system's first year of operation, subject to AI Governance Programme Office approval, consistent with the continuous-improvement principle underlying ISO/IEC 42001 and applied throughout this portfolio.*
