---
name: quant-validation-discipline
domain: model-validation
tags: [overfitting, out-of-fold, purged-embargo, stationarity, bootstrap, exposure-controls, reproducibility-boundary, future-lock, parameter-integration, null-hierarchy, complexity-value, data-integrity]
when-to-apply: evaluating whether a signal / backtest / model result is trustworthy; designing or reviewing a validation protocol before a result is believed
applies-to: [diagnostic, orchestrator]
source: "private quantitative-research repositories — reproducibility, future-lock, parameter-integration, null-hierarchy, and exposure-preserving control discipline"
imported: 2026-07-02
---

# Lens — quant validation discipline

A quant result is not trustworthy because its Sharpe is high — it is trustworthy when it survives a
stack of falsification tests. Treat a skipped rung of this ladder as an unproven result, not a passing one.

- **Stationarity first.** A spread or residual you trade on must pass the declared ADF/KPSS stationarity
  rule on the *causal* centering window actually used — centering that peeks ahead voids the test. A
  non-stationary object has no stable relation to trade.
- **Construct point-in-time; lag the position.** Leakage is controlled at construction and execution, not
  only inside CV folds: signal from information available at decision time, entry-frozen / lagged
  positions. Compute the unlagged same-day twin as a look-ahead check — then exclude it from admissible performance.
- **Separate the upper bound from leakage-controlled evidence.** A same-date detector is an *upper-bound
  diagnostic*, never a tradeable result; trust is **purged + embargoed** out-of-fold evidence. Do not
  collapse the two into one number — quantify the same-date → causal → stress-net conversion budget instead.
- **Subtract the trivial explanation.** A high Sharpe means nothing until its passive-exposure twin is
  subtracted: same-exposure, randomized-timing, cost, event, bootstrap, parameter-grid, sign-flip, and
  permuted-regime controls, plus mechanism-free classical comparators (SMA, dual-momentum, risk-parity,
  vol-target); report control means for separation, not to optimize the headline.
- **Significance by permutation, not by story.** Use block-permutation p-values and an AUC sanity audit
  that isolates leakage-controlled performance from the upper bound; on rare events, report AUC alongside
  the event base rate and average precision — high AUC at a low base rate is the weaker claim.
- **Cost by graded schedule.** Report every book gross → base-cost net → stress-cost net, with execution,
  borrow, funding, slippage, and turnover itemized — a single "net of costs" number is not the discipline.
- **Charge complexity against the simplest benchmark.** Every added layer pays an explicit complexity-value
  budget vs the low-complexity baseline, and non-return value (risk control, transition warning) is named,
  not implied by returns — e.g. entropy reduction of the future-state distribution as an information metric.
- **Integrate parameters instead of selecting them.** When one cell is not justified ex ante, pre-specify
  the grid and deploy its costed average / consensus rather than the argmax; perturbation shows the default
  sits in a stable region — not at the grid maximum.
- **Lock parameters before new data.** Validate the frozen rule on non-overlapping time blocks plus a
  holdout; new universes enter only as external validation under the same frozen protocol and cost
  schedules, never to reselect parameters after observation; report a weak recent block as a capacity test.
- **One null per layer.** State the test stack as explicit per-layer nulls — object non-stationary, state
  adds no information, book fails costs, risk budgeting cannot repair fragility — each with a named object,
  diagnostic, and decision rule, so a failed deployment test is not misread as refuting the structural object.
- **Admissible tests, integrity gates.** A test enters the battery only if it touches a declared model
  object; gate warm-up neutrality (no signal before windows fill), coverage-period and spot-date alignment,
  and every reported figure traceable to an exported column.
- **Validate switching signals event-by-event.** Split eligibility from consequence — non-firing in a
  stress window is informative, and forward tests follow each causal entry/exit before full-sample
  aggregation — and cover distinct stress shapes: the fast shock and the slow erosion, not one average.
- **State what you did not test.** Every result carries a three-level reproducibility boundary — direct
  archive inspection, public-code re-run on your own inputs, full raw reconstruction — and every
  intermediate object and stated identity in the claim chain must reconstruct: audit the chain, not files.

**Within your role:** a **diagnostic** applies this to judge whether a finding is *real* and reports the
verdict with its evidence — it does not fix. An **orchestrator** applies it when scoping a work-order, to
require the right validation *before* a result is trusted or deployed. A lens shapes how this role
thinks — it grants no new authority or scope; the role's boundary stands.
