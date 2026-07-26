## Example: Completed Vendor Assessment — Foundation Model Provider

> Part of the Project 12 Agentic AI Governance portfolio — fictional example for educational purposes. See root README for the full disclaimer. Completed instance of [`templates/vendor-assessment-form.md`](../08-templates/vendor-assessment-form.md).

---

**Vendor name:** Vendor A (fictional foundation model provider) **Product/service:** Foundation model API underlying `ORG-AI-011`'s three agents **Assessed by:** Legal + Privacy **Date:** 2026-05-10

| Dimension | Score (1-5) | Weight | Evidence / Notes |
|---|---|---|---|
| Security (SOC 2 / ISO 27001) | 5 | High | Current SOC 2 Type II report reviewed, no material findings |
| Privacy & data residency | 4 | High | Regional data residency confirmed contractually; one subprocessor location pending disclosure update |
| Model transparency | 3 | Medium | Model card provided; upgrade notice period is 30 days, shorter than preferred but workable given Model Governance's version-pinning control |
| Retraining rights on our data | 5 | High | Contract explicitly excludes customer data from training or fine-tuning |
| Subprocessor disclosure | 3 | Medium | List provided but not on a committed update cadence — flagged for contract renewal |
| Incident response commitment | 4 | Medium | Defined SLA, joint incident bridge available |
| Right to audit | 4 | Medium | Contractual audit rights, annual cap on frequency |
| Kill-switch independence | 5 | High | API key revocation confirmed independent of vendor uptime — tested during onboarding |

**Any High-weight dimension scoring below threshold?** N — all High-weight dimensions score 4 or above.

**Overall recommendation:** Approve with conditions

**Conditions:**
1. Subprocessor disclosure cadence to be formalised at contract renewal (next cycle: 2027-05)
2. 30-day model upgrade notice tracked explicitly against Model Governance's regression-testing lead time to confirm it's sufficient

**Next review date:** 2027-05-10 (annual, aligned to contract renewal)

---

**Author:** Karun Mehta · AIGP (AI Governance Professional)
