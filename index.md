# Quant-discipline lenses — registry

A frozen, portable pack of gitos **lenses** distilling the quantitative-research *discipline* of private research
repositories (see `README.md`). Copy any lens `.md` into a gitos repo's `.gitos/agents/` and add its row
to that repo's `.gitos/agents/index.md` — the four roles apply it on demand under the engine-v11
apply-directive, within their boundary. Lenses hold *approach* (how to work a domain), never facts or code.
In the **Applies to** column, `[any]` is a wildcard meaning every role.

| Lens | Domain | When to apply | Applies to |
|------|--------|---------------|------------|
| `quant-validation-discipline` | model-validation | evaluating whether a signal / backtest / model result is trustworthy; designing or reviewing a validation protocol before a result is believed | diagnostic, orchestrator |
| `causal-deployment-ordering` | research-to-deployment | deciding whether / how a research result moves toward deployment; sequencing structural diagnostics vs cost + execution modeling | orchestrator, diagnostic |
| `regime-aware-modeling` | regime-detection | modeling behavior that shifts across market states; assessing hedge effectiveness; building or reviewing a regime / switching signal | orchestrator, implementer |
| `fragility-variance-response` | econophysics-fragility | seeing coupled assets as positive/negative response fields; measuring how an asset responds to variance stress; building a fragility signal on coupled pairs | orchestrator, implementer |
| `evidence-reproducibility-reporting` | result-reporting | documenting or reviewing a quant result; recording a quant finding in the brain; writing up a backtest or audit | [any] |
| `quant-foundations` | mathematical-grounding | doing a derivation or a pricing / vol / risk computation; sanity-checking a quant method's mathematical footing | implementer, orchestrator |
