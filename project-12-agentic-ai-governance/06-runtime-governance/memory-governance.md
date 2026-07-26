## Memory Governance

*Agents that remember create a governance surface almost no framework in wide use today addresses directly.*

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer.

---

### Why Memory Is Different From Data Governance

Standard data governance assumes data sits in a system of record with a known schema. Agent memory — conversation history, vector-store embeddings, long-term summarised state — is unstructured, often embedded rather than stored as plain text, and frequently invisible to standard data-loss-prevention tooling. A right-to-erasure request against a relational database is a solved problem; the same request against a vector database, where the original text has been transformed into embeddings that may still encode identifiable information, is not.

### Memory Types and Controls

| Memory Type | Present in `ORG-AI-011`? | Retention | Deletion Mechanism | Key Risk |
|---|---|---|---|---|
| Session/conversation memory | Yes — Intake and Policy-Compliance agents, session-only | Cleared at session end | Automatic on session close | Low — no persistence |
| Long-term memory (persisted across sessions) | Not currently — flagged as a design constraint, not an oversight | N/A | N/A | Would require its own approval under Charter §4 before enabling |
| Vector store / RAG context | N/A for this system | — | — | Embedding-level right-to-forget is an unsolved problem industry-wide; do not persist PII into a vector store without a tested deletion path |
| Shared/cross-agent memory | Explicitly not permitted — see Agent Identity Governance | — | — | Basis for one compromised agent influencing another's behaviour |

### Required Controls Before Any Persistent Memory Is Approved

1. **Classification at write time.** Content is classified (PII / PHI / financial / none) before being written to persistent memory, not after — after-the-fact classification of unstructured memory is unreliable.
2. **Encryption at rest**, matching the classification level of the most sensitive content it may contain.
3. **A tested deletion path**, proven to actually remove the content from any derived representation (embeddings, summaries, caches) — not only the primary store.
4. **Poisoning detection.** Since agents that learn from their own interaction history can be manipulated by an adversary feeding it false "memories" over repeated sessions, any persistent memory system requires periodic review for content that shouldn't have entered memory in the first place.
5. **No cross-agent sharing** without an explicit, Direct-decision-level Charter approval, since shared memory is one of the more direct paths to the inter-agent-manipulation risk in the OWASP multi-agent taxonomy.

### Current Status for `ORG-AI-011`

All three agents operate on session-only or no memory. This is a design decision, not a gap — the case study deliberately shows a system where memory governance was resolved by *not* introducing persistent memory until the controls above could be built, rather than deploying with memory first and governing it later.

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
