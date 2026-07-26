## Agentic AI Inventory Register

*The CMDB for agents — extends Project 1's system inventory with fields specific to agentic systems.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why This Is a Separate Register, Not Just Extra Columns on Project 1's Inventory

Project 1's inventory answers "what AI systems exist and how are they classified." An agent inventory has to answer a harder question: "what can this thing actually *do*, on its own, right now" — which requires fields a standard model inventory doesn't carry: autonomy level, credential scope, tool access, and kill-switch status. Bolting these onto the existing inventory would bury agent-specific risk inside fields most rows don't need. This register sits alongside Project 1's inventory and is joined to it by System ID.

### Register Schema

| Field | Description |
|---|---|
| Agent ID | Unique identifier, e.g. `ORG-AI-011-A1` (system + agent sequence) |
| Parent System ID | Links to Project 1 inventory, e.g. `ORG-AI-011` |
| Agent Name | e.g. Intake Agent |
| Owner | Named individual, not a team alias |
| Business Unit | e.g. Finance Operations |
| Purpose | One sentence, plain language |
| Risk Level | Inherited from Risk Classification Addendum, post-autonomy-multiplier |
| Autonomy Level | Assistive / Supervised / Conditional / Full |
| Underlying Model | e.g. vendor + model family (kept current — this field has the shortest shelf life in the register) |
| Tools / APIs Accessible | Explicit list, not "various" |
| Memory Type | None / session-only / persistent — see Memory Governance, backlog |
| External API Calls | Yes/No + which |
| Handles PII | Yes/No |
| Handles PHI | Yes/No |
| Handles Financial Data | Yes/No |
| Approval Date | Date Charter Section 4 requirements were met |
| Last Review Date | Must not exceed annual cadence |
| Kill Switch Tested | Date of last test — an untested kill switch is treated as not having one |
| Runtime Status | Active / Suspended / Retired |

### Example Entries — `ORG-AI-011`

| Agent ID | Agent Name | Autonomy Level | Tools/APIs | Memory | PII | Kill Switch Tested | Status |
|---|---|---|---|---|---|---|---|
| ORG-AI-011-A1 | Intake Agent | Supervised | Claims queue (read), receipt store (read) | Session-only | Yes | 2026-06-01 | Active |
| ORG-AI-011-A2 | Policy-Compliance Agent | Supervised | Expense policy DB (read) | Session-only | No | 2026-06-01 | Active |
| ORG-AI-011-A3 | Disbursement Agent | Conditional | Payment system (write, capped) | None | Yes | 2026-06-01 | Active |

### Governance Rule Attached to This Register

**No agent is permitted a Runtime Status of "Active" without a Kill Switch Tested date within the last 90 days.** This is enforced as a hard gate, not a recommendation — an agent whose kill switch has not been re-verified within that window is automatically flagged for suspension pending re-test. This closes the most common real-world gap: kill switches that were built and tested once at launch and never verified again as the system evolved.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
