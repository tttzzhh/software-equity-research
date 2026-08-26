# Software Metrics and Definitions

Use company definitions first. A label is comparable only after its cohort, timing, currency, acquisition treatment, and calculation method are aligned.

## Recurring revenue and retention

| Metric | Working definition | Main use | Common traps |
|---|---|---|---|
| ARR | Annualized value of recurring contracts or subscriptions active at period end | Forward recurring-revenue scale | Not GAAP; may include usage estimates, acquired ARR, or services; do not assume `ARR = quarterly revenue × 4` |
| MRR | Monthly recurring revenue active at period end | Shorter-cycle recurring base | Seasonality and variable usage can make annualization misleading |
| NRR / NDR / DBNER | Ending recurring revenue from the starting customer cohort, including expansion and excluding new customers, divided by beginning cohort revenue | Expansion after churn and contraction | Cohort, period, FX, acquisitions, and metric type differ; NDR and NRR are often similar labels but not universally identical |
| GRR | Ending recurring revenue from the starting cohort before expansion, divided by beginning cohort revenue | Retention floor | Can hide customer-count churn or concentration |
| Logo retention | Retained customers divided by starting customers | Customer durability | A small-customer churn problem can coexist with strong NRR |

Canonical NRR bridge:

`NRR = (starting recurring revenue + expansion - contraction - churn) / starting recurring revenue`

Do not reconstruct NRR unless the cohort components are disclosed or the estimate is explicitly labeled.

## Growth pipeline and visibility

| Metric | Interpretation | Checks |
|---|---|---|
| Bookings / ACV / TCV | Contracted commercial activity | Term length, renewals, cancellation clauses, and whether renewals are included |
| Billings | Often revenue plus change in deferred revenue | Contract timing and multiyear prepayments can dominate quarterly changes |
| RPO | Contracted revenue not yet recognized | Includes current and long-dated obligations; may exclude cancellable or usage-based spend |
| cRPO | RPO expected to be recognized within 12 months | Useful near-term visibility measure | Company definition and FX treatment |
| Deferred revenue | Cash billed before revenue recognition | Cash timing, not demand by itself | Billing schedule and acquisitions |

Treat bookings, billings, RPO, and deferred revenue as different stages of the commercial cycle. Never substitute one for another without a reconciliation.

## Growth efficiency and profitability

### Rule of 40

State the variant explicitly:

`revenue growth rate + profitability margin`

Preferred dashboard variants:

- GAAP operating margin;
- free-cash-flow margin;
- adjusted operating margin, shown only with a GAAP reconciliation.

Use the same period for both components, normally trailing twelve months or a fiscal-year outlook. A quarterly annualized margin can be distorted by seasonality. Never compare companies using different margin variants in one unlabeled ranking.

### Other core measures

- Gross margin by subscription, support, services, and usage infrastructure where disclosed.
- GAAP and non-GAAP operating margins with stock-based compensation, restructuring, and acquisition charges reconciled.
- Free-cash-flow margin: free cash flow divided by revenue. State the company's FCF definition and material working-capital effects.
- Stock-based compensation as a percentage of revenue and operating cash flow.
- Diluted share-count growth and net dilution after repurchases.
- Sales and marketing efficiency, preferably with new ARR or gross-profit-adjusted growth when disclosed.
- CAC payback and LTV/CAC only when customer acquisition cost, gross margin, churn, and cohort definitions are credible.

## Usage and transaction businesses

Track the activity unit that creates revenue: data processed, compute consumed, messages, API calls, payment volume, ad spend, seats actively used, or verified outcomes. Separate:

- customer growth;
- activity per customer;
- price or take-rate change;
- mix and tier migration;
- contracted minimums versus variable consumption.

For transaction platforms:

`revenue ≈ gross transaction volume × take rate + fixed or subscription fees`

For consumption platforms:

`revenue ≈ active customers × usage per customer × realized price per unit`

These equations organize analysis; they are not accounting identities unless management confirms the definitions.

## Comparable KPI table

Use columns such as:

| Company | Period | Revenue growth | Organic / constant-currency growth | ARR growth | NRR | cRPO growth | Gross margin | GAAP op. margin | FCF margin | SBC / revenue | Diluted shares YoY | Rule of 40 variant |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|

For every field, preserve one of these statuses: **reported**, **company-defined**, **derived**, **consensus**, **estimate**, or **not disclosed**. Add footnotes for definition changes and avoid filling unavailable cells with zero.

## Quality checks

- Reconcile fiscal periods and trailing-twelve-month calculations.
- Show organic and acquisition contribution separately when material.
- Identify foreign-exchange impact and constant-currency claims.
- Separate remaining performance obligations from non-cancellable backlog.
- Explain changes in disclosed KPI definitions or reporting frequency.
- Compare cash flow with deferred revenue, capitalized commissions, restructuring payments, and one-time working-capital movements.
