AI Governance in Practice
Enterprise AI Governance – Autonomous Expense & Reimbursement Reviewer
Finance Operations

Author:
Karun Mehta · AIGP (AI Governance Professional)

Business Context

Finance Operations needed faster expense reimbursement — manual review was taking an average of 4 business days per claim due to queue backlog.
Deployed a three-agent pipeline (Intake → Policy-Compliance → Disbursement) that reads expense claims, checks them against policy, and — below a defined value threshold — approves and disburses reimbursement without human review.
Objective: cut turnaround time while keeping an agent that can both decide and move money auditable, reversible, and contained if something goes wrong.

Governance Challenge

Set the right autonomy level for a system that doesn't just recommend — it executes financial transactions directly.
Prevent claimant-supplied text from being treated as policy input by the agent reading it (a cross-agent prompt injection risk).
Maintain a working kill switch and full traceability given the system can disburse funds with no human in the loop below threshold.

Governance Decision

Evaluated the original engineering design against risk scoring and security testing before approving deployment.

Rejected

One shared service credential across all three agents "for simplicity" (a single credential compromise would have exposed the whole pipeline).
The originally proposed full-autonomy design at the initial threshold (the risk score's autonomy multiplier pushed it into Moderate territory, forcing a redesign rather than a straight approval).

Selected

One scoped, least-privilege identity per agent — no shared credentials.
A Direct-decision approval with conditions: a reviewable approval threshold, mandatory 90-day kill-switch testing, and a full re-test requirement before any threshold increase.

Operational Governance Controls

Least-privilege agent identity — one scoped credential per agent, independently revocable.
Structural separation of trusted policy content from untrusted claim content in every prompt.
Kill-switch capability with a defined, tested response time.
Runtime monitoring against defined KPI thresholds, including a fabrication-rate metric.
Model version pinning with a tested rollback path.

AI Validation & Testing

Red-team testing against the OWASP multi-agent taxonomy — found a claimant could embed instructions inside a claim description that the Policy-Compliance Agent partially followed as if it were a policy update; prompt redesigned and re-tested.
Vendor due-diligence assessment on the foundation model provider, completed before deployment — surfaced a contractual 30-day model-upgrade notice period that later proved essential during incident response.
Full test suite and injection-resistance re-verification before sign-off.

Framework & Regulatory Alignment

NIST AI RMF — full Govern • Map • Measure • Manage cycle applied from intake through incident response and framework change control.
Third-party / vendor AI governance — the upgrade-notice terms captured at intake directly enabled fast root-causing when the incident occurred.
Internal AI control library — agent identity governance, runtime drift thresholds, and an evidence library that had already indexed where incident evidence would live before any incident happened.

Key Trade-offs

Full autonomy vs. a bounded, reviewable approval threshold.
Deployment speed vs. mandatory kill-switch testing and re-test requirements before scaling autonomy.
Vendor model flexibility vs. governance visibility into when and how the model changes underneath the agent.

Decision

We accepted a capped approval threshold and mandatory 90-day kill-switch testing — rather than the originally proposed full-autonomy design — to deploy an agent that autonomously approves and disburses money without losing the ability to contain it fast if something went wrong.

Business Outcomes (Illustrative Example)

The system operated within every KPI threshold for ten weeks.
A vendor-side model upgrade — received inside the contractual 30-day notice window flagged at intake — subtly changed model behavior on ambiguous claims; the fabrication-rate KPI caught it after three claims were approved citing a policy clause that didn't exist.
The Disbursement Agent was suspended within 6 minutes of detection; root cause was traced to the model upgrade specifically, not a prompt or credential failure, because the vendor assessment from intake had already flagged the upgrade cadence to watch for.
The model was rolled back to the prior pinned version, the regression suite was expanded, and two permanent framework changes were logged through change control rather than fixed silently: a tightened drift threshold for policy-citation anomalies, and a standing requirement to re-run the full regression suite after any vendor model upgrade, not just a spot-check.

Key Takeaway

Nothing in this incident was caught by a document — it was caught by a KPI threshold that existed because it had been defined in advance, contained by a kill-switch design that existed because identity governance required scoped credentials, root-caused quickly because evidence was already indexed before the incident happened, and closed out through a change-control process that turned it into two permanent improvements rather than a near-miss nobody remembers by year end. This use case shows that governance chain applied to the highest-stakes system in this portfolio's single-pipeline tier — an agent that doesn't just recommend, but autonomously approves and disburses funds.

Disclaimer

This is an illustrative AI Governance use case created for professional learning, portfolio development, and discussion. Any scenarios, metrics, or examples are illustrative and intended to demonstrate governance design concepts rather than represent production results. This material is not legal or regulatory advice. Organizations should consult their legal, compliance, risk, and information security teams when designing or implementing AI governance programs.
