---
name: quant-foundations
domain: mathematical-grounding
tags: [arbitrage-free, stochastic-calculus, greeks, volatility-surface, vol-conventions, garch, factor-models, entropy, assumptions]
when-to-apply: doing a derivation or a pricing / vol / risk computation; sanity-checking a quant method's mathematical footing
applies-to: [implementer, orchestrator]
source: "a private quantitative-trading curriculum — pricing -> stochastic calculus -> Greeks -> volatility surfaces -> local/stochastic vol -> jumps -> econophysics/entropy -> allocation (Markowitz/CAPM/APT/Black-Litterman) -> ARCH-GARCH"
imported: 2026-07-02
---

# Lens — quant foundations (light)

When a task calls for a quant method, ground it: reach for the right tool and know what it assumes. This
is a method-*awareness* map, not a derivation and not a textbook — it points at the foundations so a
computation rests on sound footing rather than a fitted shortcut.

- **Pricing rests on arbitrage-free reasoning** — put-call parity, replication, no-arbitrage forward
  rates. If a price violates no-arbitrage, the model or the data is wrong; fix that before anything else.
- **Dynamics live in stochastic calculus** — Itô, geometric Brownian motion. The **Greeks** are the
  derivatives of price with respect to its parameters (spot, σ, T, r) — sensors, not concepts. Derive
  them analytically and confirm against finite differences (mind the step size `h`): if a Greek is wrong,
  the hedge is wrong, and you take a risk you think you're not taking.
- **Volatility is a surface, not a number** — and its axes depend on the object: in rates the standard
  surface is expiry × tenor (1Y×5Y and 10Y×1Y place uncertainty in entirely different places), with
  strike as a finer slice for the smile; in equity, expiry × strike. Implied → local → stochastic
  (Heston); jumps; sticky-strike vs sticky-delta. A single-σ model on a real smile misprices the wings.
- **A quote is not a parameter** — always ask: vol of *what object*, on which expiry, on which curve
  underlying, in which convention. Black (lognormal, unitless) and Bachelier (normal, rate units) do not
  measure the same quantity — never read them as two writings of one number.
- **Validate a surface in prices and derivatives, never by eye** — decreasing and convex in strike,
  increasing in maturity, Greeks smooth under small bumps. A broken butterfly is a negative probability,
  and everything differentiated from a dirty surface (density, local vol) disintegrates.
- **Variance has memory** — ARCH/GARCH: conditional variance is a state with reactivity (`α`) and
  persistence (`β`). Four checks: `ω > 0` and `α, β ≥ 0`; `α + β < 1` for stationarity; the
  standardized-residual squares lose their autocorrelation; and if residual tails stay heavy under
  normality, switch the innovation law (Student-t) or you underprice tail risk. Use it for sizing / VaR,
  not for direction.
- **Check readability before trusting any signal computed on the market** — entropy asks whether the
  system is readable at all, Hurst whether a shock leaves a persistent trace, Lyapunov how fast a
  perturbation propagates. Risk is the moment the system stops dissipating and starts propagating — and a
  calm surface can hide high entropy, so low movement does not mean low risk.
- **Allocation is geometry + factors** — Markowitz (the return-risk frontier — assumes correlations stay
  exploitable; in stress they lock toward 1 and the diversification margin folds back in; weights that
  swing across estimation windows mean the optimizer is amplifying input error, not the market changing),
  CAPM (priced vs unpriced risk), APT / multi-factor ("alpha" is often just a missing factor),
  Black-Litterman (don't let `μ` say whatever it wants).

The discipline in one line: **name the assumption each method carries, and check it holds before trusting
the output.**

**Within your role:** an **implementer** reaches for the correct grounded method and states its
assumptions; an **orchestrator** sanity-checks that a proposed approach rests on sound footing. The lens
points at the foundations — it does not replace them. A lens shapes how this role thinks — it grants no
new authority or scope; the role's boundary stands.
