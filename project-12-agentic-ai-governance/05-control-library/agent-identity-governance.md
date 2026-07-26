## Agent Identity Governance

*Agents are machine identities. This document treats them with the same rigour as privileged human accounts, plus controls humans don't need.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### The Core Distinction From Human IAM

A human credential is used by one accountable person who can be asked "why did you do that." An agent credential is used by a non-deterministic process that can be manipulated (via prompt injection or tool misuse) into using its own legitimate credentials for an illegitimate action. Identity governance for agents therefore has to assume the credential itself may be used correctly by the platform while the *decision* to use it was compromised — which is why scope and revocability matter more than authentication strength alone.

### Identity Requirements

| Requirement | Detail |
|---|---|
| One identity per agent, not per system | `ORG-AI-011` has three agents → three distinct service identities, never a shared one, so any single agent's compromise or misbehaviour can be isolated and revoked without affecting its pipeline peers |
| Authentication | OAuth 2.0 / OIDC client-credentials flow for service-to-service calls; no static long-lived API keys embedded in code or prompts |
| Authorization | RBAC as the floor (role tied to documented action scope in the Inventory Register); ABAC where the platform supports it, to add contextual constraints (e.g., time-of-day, transaction-value limits) on top of role |
| Secrets management | All credentials issued and rotated through a vault, never hardcoded, never logged in plaintext — including in the action logs required by Agent Policy §4 |
| Certificate / mTLS | Required for agent-to-agent and agent-to-internal-API calls where the platform supports it, to prevent a compromised agent from impersonating a peer |
| Credential rotation | Fixed schedule (90 days per Agent Policy §2) plus immediate rotation on: personnel change of the named system owner, any Charter Section 6 escalation trigger, or any finding from a shadow agent discovery scan |
| Revocation / kill switch | Revocation must be independent of the agent's own execution path — an agent must never be able to prevent or delay revocation of its own credentials |

### Identity Register Fields (Extension to Agent Inventory Register)

| Field | Purpose |
|---|---|
| Identity type | OAuth client / OIDC service account / certificate-based |
| Vault reference | Pointer, never the secret itself, in any document |
| Last rotation date | Ties to the 90-day requirement |
| Authorized scopes | Explicit list, cross-checked against Inventory's "Tools/APIs Accessible" field — any mismatch is `AI-CNTRL-A02` |
| Revocation tested | Date of last confirmed independent revocation test |

### Why This Deserves Its Own Document Rather Than a Section

Identity is the control surface every other agentic control ultimately depends on — least-privilege scoping (Agent Policy §2), the kill switch (`AI-CNTRL-A04`), and shadow agent containment all resolve to "can we revoke this identity, and does revoking it actually stop the behaviour." Treating identity as a subsection under policy undersells that it's the load-bearing control, not a supporting one.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
