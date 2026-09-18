# Example 1 — Executive market brief

## Audit context

- Target: a leadership briefing dated 15 February 2026.
- Decision use: capacity planning for the next two quarters.
- Supplied evidence: an industry outlook published in November 2025.

## Target text

> The regional market is worth USD 8.2 billion in 2026 and is growing 14% annually. Demand from mid-sized manufacturers is the main driver.

## Supplied evidence

> We forecast the regional market could reach USD 8.2 billion by the end of 2026, representing 14% growth over our 2025 estimate. Survey respondents from 42 large manufacturers reported increased purchase intentions. The outlook did not sample mid-sized manufacturers.

## Expected EvidenceGuard reasoning

1. **“The regional market is worth USD 8.2 billion in 2026”** is `partially_supported`. The source provides a forecast for the end of 2026, not an observed current value. Report `citation_role_mismatch` and recommend changing the claim to an attributed forecast with its endpoint.
2. **“[The market] is growing 14% annually”** is `partially_supported`. The evidence describes growth from a 2025 estimate to an end-2026 forecast; it does not establish a recurring annual growth rate. Report `partial_support` and clarify the comparison period and estimated basis.
3. **“Demand from mid-sized manufacturers is the main driver”** is `unsupported`. The evidence covers purchase intentions among large manufacturers and explicitly excludes mid-sized firms. Report `unsupported_factual_claim` and `unclear_population_or_timeframe`; request evidence about mid-sized manufacturers and comparative driver importance.

## Boundary

Do not search for a newer market report or decide whether the forecast is commercially reliable unless separately requested.

