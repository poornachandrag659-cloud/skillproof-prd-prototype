# Metrics Plan

No product analytics are implemented in this frontend-only prototype. The metrics below are definitions for a future validated product.

| Metric | Definition | Why it matters |
|---|---|---|
| First-skill activation | Users who create ≥1 skill card / users who start onboarding | Measures initial value |
| Evidence attachment rate | Skill cards with ≥1 evidence reference / all skill cards | Measures whether claims are supported |
| Evidence-backed profile completion | Profiles with ≥3 cards and evidence on each / activated profiles | Candidate north-star candidate |
| Task success | Participants who add a skill and evidence without help / participants tested | Measures usability |
| Time to first evidence | Median elapsed time to first evidence reference | Measures friction |
| Reviewer find time | Median time to locate a relevant evidence item | Tests reviewer value |
| Verification comprehension | Participants who correctly identify evidence as user-submitted / participants tested | Trust guardrail |

## Instrumentation principles
- Collect only what is needed.
- Do not infer candidate quality from activity.
- Clearly disclose analytics in a production product.
- Establish consent, retention, and deletion policies before collecting user-level data.
