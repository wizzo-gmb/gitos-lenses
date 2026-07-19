---
name: regime-aware-modeling
domain: regime-detection
tags: [regimes, multi-state, cointegration, variance-compression, hedge-effectiveness, causal-lag, transition-risk, hysteresis, complexity-budget, point-in-time-weights, exposure-controls]
when-to-apply: modeling behavior that shifts across market states; assessing hedge effectiveness; building or reviewing a regime / switching signal
applies-to: [orchestrator, implementer]
source: "private quantitative-research repositories — multi-state (four-state) regime support, point-in-time inverse-vol weighting, hysteresis-banded switching, and complexity-value budgeting"
imported: 2026-07-02
---

# Lens — regime-aware modeling

Markets are not one regime, and hedge effectiveness is a measured variance compression, not an assumed
property. When you model state-dependent behavior:

- **Prefer multi-state over binary.** A four-state (Q1–Q4) support carries regime persistence, transition
  warning, entropy/gap information, and a risk-control channel that a two-state view discards. Keep the
  low-complexity baseline as the *benchmark*, but do not reduce the richer state object to a single
  return comparison against it.
- **Charge complexity an explicit value budget.** Each layer above the low-complexity benchmark earns
  retention only through a measured return, regime-support, transition-warning, or risk-control channel
  the benchmark cannot observe — an itemized, auditable ledger, not taste. A conditional diagnostic
  around the benchmark is not a re-optimized trading rule.
- **Build the state object point-in-time.** Weight opposing legs from information available at each date
  only, sized inverse to volatility so no single name's variance dominates the spread — a look-ahead
  weight poisons everything downstream before any validation gate can catch it.
- **Construct a continuous state; reduce late.** Build the signed-response / density state as a
  continuous field and reduce it to a binary crossing only as the last step, so the variable registers
  both violent instantaneous shifts and diffuse prolonged pressure.
- **Treat state labels as statistical coordinates** of the measured object, not macro story labels — do
  not attach narratives to them.
- **Measure hedge effectiveness as variance compression.** Report the level-volatility reduction the
  hedge coordinate achieves, backed by a variance/covariance identity, with correlation and cointegration
  as audited input fields rather than the effectiveness metric. Compression is a measured diagnostic, not
  a pass-fail admission rule: a low-compression state can still earn retention through regime-support,
  transition-warning, or information channels — charge it to the value budget.
- **Switch on confirmed shifts, with an explicit lag and a hysteresis band.** The regime variable is
  adapted to information at the close of the decision day; the executable allocation is lagged —
  `w_minus(t) = G(t-1)`, `w_plus(t) = 1 - G(t-1)`. Confirmation is mechanical: a hysteresis band/margin,
  grid-searched as a first-class design parameter, controls boundary churn — report the switch count as
  a cost driver.
- **Validate switching against exposure-matched controls.** A regime/switching signal is not validated by
  static exposure to the hedge asset: same-exposure, randomized-timing, cost, event, bootstrap, and
  parameter-grid controls must separate passive refuge allocation from timed switching.
- **Keep structural and causal results as separate objects.** Same-date state-readability diagnostics and
  causal costed rows are different objects — never collapse them into one trading claim; carry an
  explicit structural → causal → stress-cost net conversion budget between them.
- **Carry transition risk as a first-class object:** persistence, a transition matrix, entropy reduction.
  Report classifier evidence in two tiers — the upper-bound (potentially leaky) diagnostic labeled as
  such versus purged/embargoed out-of-fold evidence — and keep the out-of-fold transition-risk gate on
  the costed book as a separate risk-overlay object, distinct from the classification test.

**Within your role:** an **implementer** builds regime logic this way (point-in-time, multi-state,
lagged, banded, variance-compression-measured); an **orchestrator** judges whether a proposed model
respects these or silently collapses to binary / contemporaneous / unbudgeted complexity. Keep the
specific model's numbers as the project's facts (its brain), not lens content — the lens is the
*approach*. A lens shapes how this role thinks — it grants no new authority or scope; the role's
boundary stands.
