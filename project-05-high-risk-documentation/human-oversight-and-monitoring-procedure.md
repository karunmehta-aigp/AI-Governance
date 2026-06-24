# Human Oversight and Post-Market Monitoring Procedure — Voice Biometric Authentication System

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**System:** ORG-AI-004 · Voice Biometric Authentication System
**Document Status:** Active operating procedure
**Owner:** Head of Customer Operations
**Prepared by:** AI Governance Programme Office, with Customer Operations and Information Security
**Date:** September 2026

---

## 1. Purpose

This document sets out the operational human oversight procedure for the Voice Biometric Authentication System, and the post-market monitoring plan that keeps the system's conformity status (as assessed in `conformity-assessment.md`) honest on an ongoing basis. A high-risk system's conformity is not a fixed achievement; it is a standing condition that depends on this procedure actually functioning as described, continuously, for the system's entire operational life.

This document is written deliberately to avoid the failure mode named explicitly in Project 3's Responsible AI Policy as **oversight capacity erosion** — a human review step that exists in form but, under volume or time pressure, degrades into a step that no longer meaningfully changes any outcome. Every control below is written with a specific, checkable criterion attached, not a general statement of intent.

---

## 2. Human Oversight Procedure

### 2.1 The Three Authentication Outcomes

| Outcome | Trigger | What Happens |
|---|---|---|
| Pass | Match score above the upper confidence threshold | Caller proceeds with full account access; no human involvement |
| Escalate | Match score between the upper and lower thresholds | Caller is asked a supplementary knowledge-based verification question by the automated system; a second failure routes to a human agent |
| Fail | Match score below the lower confidence threshold, or supplementary verification also fails | Caller is routed directly to a human agent for full manual identity verification |

### 2.2 What "Meaningful" Human Oversight Requires for This System

The human agent receiving an escalated or failed call must have:

- Visibility that the call has been routed to them specifically because of an automated authentication outcome, not just a generic "verify this customer" instruction with no context
- Access to the customer's account-level identity verification options available through other channels (for example, security questions tied to recent account activity that the voice system does not have access to), so the agent has genuine alternative verification tools, not merely the same passphrase the automated system already failed to match
- The explicit authority, and the expectation, to decline to authenticate a customer if they cannot be satisfactorily verified through the available alternative means — an agent must never feel pressure to "pass" a customer through simply because the call has already taken longer than the standard call-handling time target

### 2.3 Specific Override Criteria

A human agent handling an escalated or failed authentication is required to decline manual verification, and refer the case to a fraud-review queue, if any of the following are present:

- The caller cannot answer alternative verification questions consistent with genuine account knowledge
- The caller's stated reason for the original voice mismatch (for example, illness affecting their voice) cannot be corroborated by any other account signal and the request involves a sensitive action (such as a large transfer or a change of registered contact details)
- Multiple recent failed authentication attempts are visible on the account, regardless of the customer's explanation for the current call

These criteria are deliberately specific rather than left to general judgement, because a documented, specific override standard is what makes oversight auditable — an auditor or regulator reviewing this procedure should be able to assess whether agents are actually applying it, not only whether the procedure exists on paper.

---

## 3. Fallback-Path Throughput and Quality Audit

This is the single highest-priority open item carried over from the conformity assessment, and is described here in full operational detail rather than only summarised.

### 3.1 What the Audit Will Measure

- **Volume:** What proportion of total authentication attempts are routed to Escalate or Fail, in aggregate and broken down by available customer demographic proxies (language preference, registered country of residence as a proxy for regional accent, and age band)
- **Agent time per fallback case:** Average and distribution of handling time for escalated and failed authentication calls, to detect whether agents are spending genuinely adequate time on these calls or processing them as quickly as possible under general call-handling time pressure
- **Outcome consistency:** Whether the eventual outcome of a fallback-path call (successfully verified by an agent versus referred to fraud review versus call abandoned by the customer) varies in a way correlated with the same demographic proxies used in the volume measure above

### 3.2 Why This Audit Is Structured This Way

A fallback path that exists, and is even used appropriately by agents in each individual case, can still represent a fairness problem at the aggregate level if customers from a particular group are routed to it at a systematically higher rate than other customers — meaning that group experiences a structurally worse, slower, more friction-laden authentication experience overall, even if no single interaction is mishandled. This audit is designed specifically to detect that aggregate pattern, which a case-by-case quality review alone would not surface.

### 3.3 Timeline and Ownership

- Audit design finalised by Information Security and the AI Governance Programme Office: October 2026
- Data collection period: November 2026
- Findings reported to the AI Governance Committee: no later than 15 December 2026, ahead of the conformity assessment's broader 31 December target, given this item's priority status

---

## 4. Post-Market Monitoring Plan

### 4.1 Ongoing Metrics

Once the fallback-path audit (Section 3) and the independent accuracy validation referenced in the conformity assessment are both complete, the following metrics will be tracked on a continuing basis, not as a one-time exercise:

| Metric | Frequency | Threshold Triggering Review |
|---|---|---|
| Aggregate match rate | Monthly | Any change exceeding 3 percentage points from the prior quarter's baseline |
| Escalate/Fail routing rate, by demographic proxy | Quarterly | Any demographic segment's routing rate exceeding 1.5x the overall average |
| Fallback-path agent handling time | Quarterly | Median handling time falling below the level established as adequate in the Section 3 audit |
| Customer complaints specifically referencing voice authentication difficulty | Monthly | Any month-on-month increase exceeding 25% |

### 4.2 Escalation on Threshold Breach

A breach of any threshold above triggers an automatic notification to the AI Governance Programme Office and the system owner (Head of Customer Operations) within 5 business days of the metric being calculated, and is reported to the AI Governance Committee at its next scheduled session, or immediately via the extraordinary session mechanism established in Project 3's governance operating model if the breach is severe enough to warrant it.

### 4.3 Relationship to the Vendor

The organisation's own monitoring, described above, operates independently of and in addition to the vendor's periodic aggregate match-rate reporting. The two are not treated as substitutes for one another: the vendor's report describes the model's behaviour from the vendor's vantage point; the organisation's own monitoring describes the system's actual effect on the organisation's specific customer base, including the fallback path the vendor's own reporting does not cover at all.

---

## 5. Training Requirements for Staff Exercising Oversight

Consistent with the Responsible AI Policy's training requirements established in Project 3, every Customer Operations agent who may handle an escalated or failed voice authentication call must complete role-specific training covering: the override criteria in Section 2.3, the alternative verification tools available to them, and the explicit expectation that declining to authenticate a customer they cannot adequately verify is the correct and supported outcome, not a failure to resolve the call.

This training will be refreshed if the override criteria are updated, or if the fallback-path audit (Section 3) identifies a need for revised guidance — not only on the standard annual cycle that applies to AI governance training generally.

---

*This procedure is a live operating document. It will be updated upon completion of the fallback-path audit, the independent accuracy validation, and any other remediation item tracked in the companion conformity assessment, and is subject to the same annual review cycle as the organisation's broader AI governance documentation.*
