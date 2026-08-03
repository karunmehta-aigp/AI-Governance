![AI Governance – Agentic Financial Advisor poster](./org-ai-013-poster.png)

# Enterprise Agentic Wealth Advisory Governance Lifecycle

### From Critical Risk Classification to Controlled Production Monitoring

**System:** `ORG-AI-013` — Agentic Wealth Advisory System (multi-agent, enterprise-orchestrated)
**Author:** Karun Mehta · AIGP (AI Governance Professional)
**Status:** Conditional Go, 1 accepted finding open, first monitoring cycle Amber

*Fictional example for professional learning and portfolio development. Not legal or regulatory advice.*

---

## AI System Context Box

| | |
|---|---|
| **Business domain** | Wealth Management |
| **Risk tier** | Critical |
| **Architecture** | 15 components |
| **Workflow** | 9 phases |
| **AI agents/components** | 13 |
| **Human gate** | 1 (Licensed Advisor) |
| **Deterministic services** | 1 (Books-and-Records) |
| **Runtime status** | Conditional Go |
| **Current state** | Amber monitoring |

---

## Governance Lifecycle Timeline

Business request → Risk classification → Architecture review → Control design → Pre-deployment testing → No-Go/Go decision → Production deployment → Continuous monitoring → Post-deployment validation → Continuous improvement

This one line ties together what Sections 5, 6, 8, 10, and 11 each cover in depth — everything below is the detail behind one of these ten steps.

---

## 1. Enterprise Business Context

`ORG-AI-013` is not one agent handling a request end to end — it's a nine-phase chain of fifteen components, where **not every component is an agent**. Some are deterministic services, and one is a mandatory human gate with no AI equivalent.

| # | Component | Type | Responsibility |
|---|---|---|---|
| 1 | Customer Intake Agent | AI agent | Classify and route requests |
| 2 | Client Profile Agent | AI-assisted retrieval | Assemble validated client context |
| 3 | Market Data Agent | AI-assisted retrieval | Gather approved market data |
| 4 | Portfolio Analysis Agent | AI + analytics tools | Analyze portfolio, propose options |
| 5 | Compliance & Suitability Agent | Hybrid rules + AI | Validate suitability, hard blocks |
| 6 | FA-Assist Agent | Generative AI | Draft advisor recommendation |
| 7 | Supervisory Review Agent | Independent AI review | Catch gaps before the advisor sees it |
| 8 | **Licensed Advisor** | **Human — not an agent** | Approve recommendation and action |
| 9 | Client Communication Agent | Controlled generative AI | Deliver approved content only |
| 10 | Trade Preparation Agent | Controlled agent | Prepare proposed orders |
| 11 | Pre-Trade Compliance Agent | Rules-driven | Final transaction-level check |
| 12 | Portfolio Update/Trading Agent | Restricted execution agent | Execute approved orders — **Critical tier** |
| 13 | **Books-and-Records Service** | **Deterministic service — not an agent** | Update enterprise systems |
| 14 | Governance Reporting & Evidence Agent | AI-assisted reporting | Grounded reports, no invented values |
| 15 | Governance Monitoring Agent | Governance and operational monitoring | Drift, overrides, incidents, kill switch |

**Nine-phase flow:** Intake & client context → Market & portfolio analysis → Compliance & suitability check → Recommendation drafting → **Licensed advisor approval (human gate)** → Client communication & consent → Trade prep & pre-trade check → Trade execution (Critical) → Records, reporting & monitoring.

Although multiple AI agents participate in this workflow, no single component can independently complete an end-to-end financial transaction.

**Full execution state machine** (maps onto the nine phases above, not a separate flow): Client Request → Knowledge Retrieval (Phase 1–2, Sec. 1.6) → Planning (Phase 2–4, Sec. 1.7) → Suitability (Phase 3) → Advisor Approval (Phase 5) → Client Consent (Phase 6) → Trade Preparation (Phase 7) → Pre-Trade Validation (Phase 7) → Execution (Phase 8) → Settlement (Phase 9) → Monitoring (Phase 9) → Continuous Improvement (Sec. 11).

**Trust boundaries**, outermost to innermost — each line below is a boundary an action must cross, never skip:

External data → Enterprise knowledge (Sec. 1.6) → Planning agents (Sec. 1.7) → Human gate (Sec. 1.4) → Execution → Enterprise systems of record

### Why This System Is Classified Critical

- **Financial loss** — the Trading Agent moves real client funds
- **Fiduciary obligations** — SEC/FINRA suitability duty applies to every recommendation the chain produces
- **Customer harm** — an unsuitable or poorly explained action reaches a paying client, not an internal user
- **Regulatory exposure** — Annex III-adjacent, GDPR Art. 22-adjacent, and SEC/FINRA recordkeeping obligations stack on this system simultaneously
- **Autonomous execution** — one component in the chain can act without a human re-confirming that specific action

### 1.1. Autonomy Boundaries

| Tier | Components |
|---|---|
| Read-only | Customer Intake, Client Profile, Market Data, Reporting |
| Draft-and-review | Portfolio Analysis, FA-Assist, Supervisory Review, Client Communication, Trade Preparation |
| Restricted action | Portfolio Update/Trading Agent only |
| **Mandatory human approval** | Client-facing recommendation, suitability exception, material portfolio change, trade submission, limit override, restricted product use |

Autonomy increases only after governance controls, human approvals, and deterministic policy checks are satisfied — never by default and never by inheritance from an upstream agent.

### 1.2. Governed Handoffs: Agent-to-Agent (A2A) and Tool/MCP Governance

Every transition in the nine-phase flow is a **governed handoff** — not every one is agent-to-agent. Machine-to-machine transitions receive A2A-specific controls; the transition into the Licensed Advisor gate and into deterministic services (Books-and-Records, Pre-Trade Compliance's hard rules) require their own approval and integrity controls instead.

| Concern | Applied here |
|---|---|
| A2A handoff checkpoint survival | Each machine-to-machine handoff (e.g., Portfolio Analysis → Compliance & Suitability) must carry the same policy context forward; a checkpoint that only exists at phase 1 is not a checkpoint by phase 8 |
| Confused-deputy risk | Market Data Agent's read-only output must be independently validated before Portfolio Analysis or FA-Assist treat it as ground truth — a low-privilege agent's output should never act as an unreviewed instruction to a high-privilege one |
| Tool/MCP access boundary | Every agent's tool and MCP-server access is allow-listed per AI-CNTRL-A14 — Trading Agent's access to the order management system is never inherited by any upstream drafting agent |
| Agent identity per hop | AI-CNTRL-A01 requires each machine component to operate under its own scoped service identity, so a post-incident review can trace which specific agent in the chain took an action, not just "the system" |

### 1.3. Where AI Judgment Stops and Deterministic Rules Take Over

The Compliance & Suitability Agent is hybrid, and the boundary inside it is explicit, not implied: AI may interpret facts, identify potential suitability concerns, and generate review explanations. **Deterministic rules — not AI judgment — enforce restricted products, eligibility requirements, concentration limits, mandatory disclosures, and other non-discretionary policy blocks.** A generated judgment never overrides a hard compliance rule.

### 1.4. Segregation of Duties

No component may generate, approve, execute, and reconcile the same transaction.

| Duty | Held by |
|---|---|
| Recommendation generation | FA-Assist Agent |
| Approval | Licensed Advisor (human gate) — separate from generation |
| Execution | Portfolio Update/Trading Agent — separate from approval |
| Reconciliation | Books-and-Records Service — separate from execution |
| Compliance overrides | Restricted to authorized human roles only; no agent may approve its own output |

Recommendation generation, human approval, execution, and reconciliation must remain independently attributable — no single component's log entry can stand in for another's.

### 1.5. Client Consent Control

Client consent must be captured through an approved channel, tied to the exact recommendation and trade package presented, timestamped, and **invalidated if the recommendation materially changes before execution**. This closes the gap between recommendation approval (Phase 5) and trade preparation (Phase 7).

### 1.6. Enterprise Knowledge Layer

FA-Assist doesn't generate from unstructured prompt knowledge — it retrieves from a governed enterprise knowledge base via RAG, then generates grounded on what it retrieved.

| Knowledge source | Governance requirement |
|---|---|
| Policy documents | Version-controlled; retrieval must cite the current version |
| Research reports | Approved-source list only, timestamped |
| Product library | Matched against Pre-Trade eligibility checks |
| Regulations | Kept current with jurisdiction (ties to Sec. 9) |
| Historical cases | Used for pattern matching, never as a suitability override |
| Client documents | Access scoped to the specific client record only |

All of the above sit behind a vector database with its own access control — FA-Assist's retrieval scope is allow-listed the same way its tool access is (AI-CNTRL-A14).

### 1.7. Planning vs. Execution Separation

| Planning agents | Can | Cannot |
|---|---|---|
| Portfolio Analysis, FA-Assist, Trade Preparation | Recommend, draft, propose | Execute anything |

| Execution agent | Can execute only after |
|---|---|
| Portfolio Update/Trading Agent | Licensed advisor approval + compliance approval + client consent + deterministic pre-trade validation |

No planning agent holds execution privilege at any point — this is the same segregation-of-duties principle in Sec. 1.4, restated as an architectural boundary rather than a
