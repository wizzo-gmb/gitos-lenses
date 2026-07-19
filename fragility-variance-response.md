---
name: fragility-variance-response
domain: econophysics-fragility
tags: [variance-response-beta, fragility, anti-fragility, put-call-parity-gate, signed-density, coupled-pairs, dynamic-beta, asymmetric-exit, exposure-controls]
when-to-apply: seeing coupled assets as positive/negative response fields; measuring how an asset responds to variance stress; building a fragility signal on coupled pairs
applies-to: [orchestrator, implementer]
source: "private fragility-strategy research repository — signed variance-response / coupled-pair method; econophysics reference literature"
imported: 2026-07-02
---

# Lens — fragility & variance response

A distinctive way of seeing coupled assets: treat a pair as a positive/negative response system, and
measure fragility through how excess return responds to variance.

- **The fragility law.** Fit `R_excess = α − β·σ²`. `β > 0` is **fragile** (return penalized as
  volatility rises); `β < 0` is **anti-fragile** (return gains from chaos); `β ≈ 0` is variance-neutral.
  This `β` is the asset's "mass" — its *sensitivity* to variance stress — and is *not* its CAPM beta.
  Resistance to a regime change is a separate quantity: inertia `I = σ²/β`.
- **β is a state, not a label.** Estimate `β(t)` dynamically — an asset can flip response class across
  regimes, so run deliberate state-change checks instead of freezing a fragility classification.
- **The physics analogy is structural, not literal.** Never port the raw cosmological dust rule
  (`ρ ∝ a⁻³` price scaling) as the trading density; the primitive object is the measured signed
  variance-response law.
- **Coupled pairs, signed densities.** Model a pair (a growth leg vs a safe-haven leg) as two coupled
  response fields: sign-rectify the mass fields so each leg contributes only its expected-sign mass, and
  make the coupling *directional* — the growth leg's stress simultaneously suppresses the growth density
  and feeds the refuge pressure density. Monitor the balance `H_plus2 = ρ₊ − ρ₋`; its crossing below
  zero is the crash / rotate-to-refuge signal. Build it strictly backward-looking and execute it with a
  lag — the theory buys you nothing if the signal peeks ahead.
- **Entry and exit are asymmetric.** The density crossing triggers only the rotation to the refuge;
  return-to-growth is a *different* criterion — a causal acceleration (second-derivative) recovery
  condition on the growth leg — never the same crossing run in reverse. A symmetric one-crossing switch
  is a mis-port.
- **Sanity-check both failure modes.** A correctly built density balance registers fast shocks as
  instantaneous shifts *and* slow bears as gradual erosion of the growth density by the pressure
  density; a formulation that captures only one mode is suspect.
- **Validation is exposure-preserving reconstruction.** A density-timed switch is proven only when
  same-exposure, randomized-timing, cost, event, bootstrap, and parameter-grid controls separate timing
  skill from passive refuge allocation — and every layer reconstructs: β signs, densities, the
  `H_plus2` balance, regime recursion, lagged positions, strategy returns.
- **Put-call parity as an independent gate.** `C − P = S − K·e^{−rT}` is a conservation law; a deviation
  is either arbitrage or a data error. Use parity as a cheap, *independent* validation gate on the option
  layer — kept separate from the spot-driven density switch, not blended into it.
- **Know the Black-Scholes blind spot.** Standard BS assumes symmetric, constant volatility; fragile and
  anti-fragile assets respond asymmetrically (a missing `−β·σ²` drift), which is one origin of the
  volatility smile. Distrust a symmetric-vol model on an asset you have measured as fragile.

**Within your role:** an **implementer** builds fragility signals this way; an **orchestrator**
recognizes when a problem *is* a fragility / coupled-pair problem and reaches for this lens. The lens is
the way-of-seeing and its gates — the specific strategy's tickers, betas, and Sharpe numbers are project
facts, not lens content. A lens shapes how this role thinks — it grants no new authority or scope; the
role's boundary stands.
