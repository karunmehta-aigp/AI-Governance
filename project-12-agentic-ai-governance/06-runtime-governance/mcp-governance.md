## MCP Governance

*Governing the Model Context Protocol layer: how agents discover and call tools.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why MCP Needs Its Own Governance Layer

The Model Context Protocol (and equivalent tool-calling standards) sits between an agent and everything it can actually do. Governing the agent's prompt and governing its identity (Agent Identity Governance) both matter, but neither controls what happens if the *tool registry itself* is compromised, misconfigured, or expanded without review — an agent with perfectly scoped credentials is still exposed if it can be pointed at a malicious or unapproved MCP server presenting itself as a legitimate one.

### Governance Requirements

| Area | Requirement |
|---|---|
| Server approval | Every MCP server an agent can connect to is explicitly allow-listed; there is no default-allow posture |
| Tool registry | A single source of truth listing every tool exposed to every agent, cross-checked against the Agent Inventory Register's "Tools/APIs Accessible" field — divergence is a finding under `AI-CNTRL-A02` |
| Tool signing / integrity | Where the platform supports it, tools are cryptographically signed so an agent can verify a tool definition hasn't been altered since approval |
| Trust boundary | The MCP client (agent side) and MCP server (tool side) are treated as separate trust domains; a compromised server should not be able to escalate into agent-side credentials, and a compromised agent should not be able to silently modify server-side tool behaviour |
| Authentication & authorization | Every MCP connection authenticates independently — an agent's identity (Agent Identity Governance) does not implicitly grant trust to every server it can technically reach |
| Blocked servers list | Maintained alongside the approved list; explicit denial is documented, not just absence from the allow-list, so a future reviewer can see *why* a server was excluded |
| Logging | Every tool call via MCP is logged with the same rigor as Agent Policy §4's action traceability requirement — tool name, parameters, calling agent, timestamp, result |
| Versioning | Tool definitions are versioned; an agent tested and approved against tool version N is not automatically approved against version N+1 if the tool's capability scope changed |

### `ORG-AI-011` Approved Tool Registry (Illustrative)

| Tool | Approved For | Server Trust Level | Signed |
|---|---|---|---|
| Claims-queue-read | Intake Agent | Internal, high trust | Yes |
| Expense-policy-lookup | Policy-Compliance Agent | Internal, high trust | Yes |
| Payment-instruction-write (capped) | Disbursement Agent only | Internal, high trust, additional value-cap enforcement at gateway | Yes |

No external or vendor-hosted MCP servers are currently approved for this system — a deliberate scope decision documented here so a future expansion request has a clear baseline to be evaluated against.

### Why This Matters More in 2026 Than It Did in 2024

Tool-calling standards matured faster than the governance practices around them. An organisation can have excellent policy-level agent governance and still have no answer to "which MCP servers can our agents reach, and who approved that list" — which is exactly the kind of gap an auditor or a security review will find first, because it's an infrastructure question, not a policy one.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
