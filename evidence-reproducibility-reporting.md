---
name: evidence-reproducibility-reporting
domain: result-reporting
tags: [evidence-map, headline-numbers, reproducibility-boundary, data-manifest, interpretation-guardrails, honest-reporting, archive-checks, source-provenance, complexity-budget]
when-to-apply: documenting or reviewing a quant result; recording a quant finding in the brain; writing up a backtest or audit
applies-to: [any]
source: "private quantitative-research repositories — evidence-map, reproducibility-boundary, and interpretation-guardrail reporting discipline"
imported: 2026-07-02
---

# Lens — evidence & reproducibility reporting

Report a quant result as an audit archive, not a pitch. The result should be self-limiting and
traceable, so a skeptical reader reaches the same conclusion you did.

- **Evidence Map.** For each claim / layer, name the object, the exact evidence files that support it,
  and the role that evidence plays. Every number traces to a file — and stronger: publish every
  intermediate of the causal chain so a skeptic can *reconstruct* the claim from the disclosed
  columns, not merely trace its endpoints; if any link fails to reconstruct, the claim falls.
- **Observable contract.** Use a structural/theoretical term only when it maps to a named, measured
  column, and attach each proof stage to a named artifact family. Declare signal provenance — what
  generated the numbers (e.g. deterministic equations vs trained/AI components).
- **Headline numbers are descriptors, not promises.** State results as archive/diagnostic descriptors
  ("gross Sharpe X.XX, base-cost net X.XX, stress-cost net X.XX"), explicitly *not* forward return
  claims, and state the role the performance rows play — falsification and executability tests of the
  construct, not the construct itself. Always show the full gross → base-cost net → stress-cost net
  ladder. For intermittent strategies report both active-day and calendar-time denominators — never
  quote an active-days-only figure as calendar performance.
- **Canonical vs exploratory.** Label which experiments are the load-bearing proof and which are
  boundary/behavior probes, so side experiments cannot be read as extra confirmations.
- **Complexity earns its keep.** Keep the low-complexity benchmark in every comparison; justify a
  more complex object with an explicit complexity-value budget — what it adds beyond raw return.
- **Reproducibility boundary.** State what can be inspected directly (the derived-data layer) vs what
  needs a fresh environment to rebuild (raw reconstruction): the protocol transfers, the numbers do
  not — external environments rebuild under the same frozen protocol. Name what is *not* archived
  (private pipelines, credentials, vendor entitlements), and ship a sanitized public rerun path that
  takes explicit inputs (no hidden loaders) and reads secrets only from the environment — enforce
  the boundary in the artifact's shape, don't just state it.
- **Provenance over polish.** Archive artifacts as submitted; document environment/path quirks as
  part of the source boundary instead of silently rewriting them — fixes live in a separate working
  copy, so the archived script stays the one that produced the tables.
- **Verification before citation.** Ship machine-runnable checks (row counts, date-range assertions,
  expected headline keys in the summary artifact) a reader runs to confirm the archive is the one
  the claims describe before citing it.
- **Interpretation guardrails.** Put the do-not list next to the result — anticipate the misreading and
  forbid it in text (e.g. "do not treat a same-date structural diagnostic as executable"; "do not reduce
  a multi-state object to a raw return comparison against the simple benchmark"; "do not collapse
  same-date structural rows and causal costed rows into one trading claim"; "do not read state labels
  as macro stories"; "do not treat the archived universe/environment as externally universal").
- **Data manifest.** Map every archived artifact — code, data, results — to its layer/role, with
  checkable descriptors (row counts, date coverage) so the manifest doubles as a verification surface.

**Within your role:** any role writing up a finding — a **diagnostic's** work-order, an **orchestrator's**
brain page, an **implementer's** notes — reports in this shape, so the record is auditable and
self-limiting rather than a narrated claim. This mirrors gitos's own evidence-first, forward-positive
brain discipline; the lens carries it into quant write-ups specifically. A lens shapes how this role
thinks — it grants no new authority or scope; the role's boundary stands.
