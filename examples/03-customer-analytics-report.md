# Example 3 — Customer analytics report

## Audit context

- Target: a customer-experience report.
- Supplied evidence: a pilot dashboard and analyst note.

## Target text

> The new onboarding flow reduced churn by 25% across all customers in Q2. Churn fell from 12% to 9%, proving that the redesign caused the improvement.

## Supplied evidence

- Pilot group: 800 newly acquired self-service customers in one country.
- Comparison: pilot group's 90-day churn was 12% in Q1 and 9% in Q2.
- Deployment occurred at the start of Q2.
- No concurrent control group was used; pricing and acquisition channels also changed between quarters.

## Expected EvidenceGuard reasoning

1. **“Reduced churn by 25%”** may be numerically consistent as a relative reduction: `(12% - 9%) / 12% = 25%`. The absolute change is 3 percentage points. Do not report a numeric inconsistency solely because both descriptions differ; recommend stating the basis.
2. **“Across all customers”** is `unsupported`. The evidence covers newly acquired self-service customers in one country. Report `unclear_population_or_timeframe` and `partial_support` or `unsupported_factual_claim`, depending on whether the claim is separated.
3. **“The redesign caused the improvement”** is `unsupported`. A before/after comparison without a control group, alongside other changes, does not isolate causality. Report `causal_overclaim` and recommend descriptive language or an appropriate causal design.
4. **“In Q2”** and the 90-day outcome require clarification because a cohort acquired during Q2 may not have completed 90 days by quarter end. Report `unclear_population_or_timeframe` if the dashboard does not define the cohort window and observation cutoff.

## Boundary

EvidenceGuard identifies the integrity gap; it does not choose or conduct a causal analysis unless separately requested.

