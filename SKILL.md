---
name: software-equity-research
description: "Produce evidence-based software-equity research with a locked ETF universe, industry analysis, company deep dives, Markdown reports, and consistent HTML dashboards. Use for software-sector fund flows, subsector research, earnings reviews, peer comparisons, investment theses, and monitoring frameworks; do not use for software engineering or product architecture reviews."
---

# Software Equity Research

Produce software-equity research that separates market positioning, industry structure, company fundamentals, and valuation. Lock comparison sets before observing outcomes, preserve metric definitions, and keep the Markdown report and HTML dashboard consistent.

## Choose the mode

- **Complete report:** Run fund flows, industry analysis, company deep dive, and final conclusion in that order.
- **Single module:** Run only the module the user requests.
- **Document-led earnings review:** When the user supplies one company's filing, release, transcript, or presentation, default to the company deep dive followed by a fundamental conclusion. Do not issue a buy rating without current price and valuation inputs. State that current fund-flow and industry modules were not run unless requested.
- **Mixed scope:** Run the requested modules in report order and identify what was omitted.

## Lock the research design

Before collecting results, state the as-of date, horizon, company or subsector, geography, benchmark, peer-selection rule, return convention, and whether the task is monitoring, earnings review, comparative research, or an investment thesis.

Choose peers by buyer, product mission, revenue model, scale, growth stage, and geography. Do not alter peers or ETFs because their subsequent results support a preferred conclusion.

## Read only the relevant references

- **Fund flows:** Read [references/etf-universe.md](references/etf-universe.md) and [references/market-positioning.md](references/market-positioning.md).
- **Industry analysis:** Read [references/subsectors.md](references/subsectors.md), the relevant parts of [references/business-models.md](references/business-models.md), and [references/metrics.md](references/metrics.md) when building peer tables.
- **Company deep dive:** Read [references/metrics.md](references/metrics.md), [references/business-models.md](references/business-models.md), [references/moat-and-risks.md](references/moat-and-risks.md), and the relevant subsector section in [references/subsectors.md](references/subsectors.md).
- **Final conclusion or buy/hold/avoid question:** Read [references/investment-conclusion.md](references/investment-conclusion.md).
- **Markdown or HTML deliverable:** Read [references/output-spec.md](references/output-spec.md).

## Research workflow

### Part 1 - Fund flows and market positioning

1. Lock the universe before observing performance. If the prompt is silent, use SPY and QQQ as benchmarks and IGV and XSW as the broad software pair; add only relevant subsector proxies.
2. Call Alpha Vantage first for market data when the connector is available: use `TIME_SERIES_DAILY_ADJUSTED` for historical ETF and stock OHLCV, adjusted close, splits, and dividends; `GLOBAL_QUOTE` for the dated latest quote; and `ETF_PROFILE` for fund metadata and holdings. Save the raw responses and query dates.
3. Use Alpha Vantage price data to calculate returns, drawdowns, realized volatility, relative strength, and price-based breadth. State whether the analysis uses adjusted close, raw close, price return, or total return.
4. Measure verified creations or redemptions, flow relative to beginning AUM, persistence, and concentration. Alpha Vantage prices, volume, and ETF profiles do not by themselves prove net creations or redemptions. Never call trading volume or price-driven AUM growth an inflow.
5. Compare absolute and relative returns, cap-weighted and equal-weighted performance, breadth, and leadership concentration.
6. Add short interest, borrow, options, and crowding evidence when reliable data exist, preserving reporting lags.
7. Conclude **broad participation**, **concentrated leadership**, **de-risking**, **short covering**, or **inconclusive**, and state what would change the conclusion.

### Part 2 - Industry analysis

1. Define the subsector and peer universe before comparing results.
2. Map customer budgets, adoption cycles, regulation, infrastructure shifts, and technology transitions.
3. Compare pricing units, contract structures, revenue visibility, margin intensity, and expansion mechanisms.
4. Build a normalized peer dashboard using comparable definitions and periods.
5. Assess platform vendors, specialists, bundling, self-build, open source, distribution, and commoditization.
6. Separate acceleration, deceleration, and mix shift, then define the monitoring indicators.

### Part 3 - Company deep dive

1. Map product, economic buyer, pricing unit, contract duration, renewal mechanism, expansion driver, and revenue-recognition lag.
2. Build an operating dashboard that distinguishes reported, company-defined, derived, consensus, third-party, and analyst-estimated values.
3. Test growth quality across new customers, expansion, price, usage, acquisitions, and foreign exchange when disclosed. Pair growth with margins, cash conversion, stock-based compensation, and dilution.
4. Evaluate workflow depth, switching costs, data, integrations, distribution, and ecosystem evidence. Treat feature breadth and AI branding as claims rather than moats.
5. Match valuation methods to the company's revenue model and maturity, using dated market inputs.
6. Form bear, base, and bull scenarios with explicit assumptions, catalysts, and falsifiers.

### Part 4 - Final conclusion and scenario decision

1. Synthesize three separate conclusions: fund-flow regime, industry development position, and company quality and valuation.
2. Preserve disagreement between the three layers. Strong fundamentals do not erase weak positioning or an excessive valuation.
3. Present bear, base, and bull scenarios with dated operating assumptions, valuation method, implied value or return, catalysts, and falsifiers.
4. For every analyzed company, give one conditional research action: **Buy / Accumulate**, **Watchlist / Hold**, **Avoid / Reduce**, **Speculative / High Risk**, or **No Rating**.
5. State the price or valuation condition that would change the action, the required margin of safety, the time horizon, and the thesis-breaking evidence.
6. Use the user's decision thresholds when supplied. Otherwise apply and disclose the default thresholds in [references/investment-conclusion.md](references/investment-conclusion.md).

## Evidence rules

- Prefer regulatory filings, investor-relations material, earnings calls, official fund data, and exchange data.
- Attach source, period, publication date, currency, and GAAP or non-GAAP status.
- Never silently equate ARR with revenue, bookings with billings, RPO with backlog, or NRR with customer retention.
- Mark unavailable metrics `not disclosed` or `Missing Data`; do not guess.
- Show formulas and assumptions for derived or estimated values.
- Reconcile fiscal and calendar periods, quarterly and trailing values, acquisitions, divestitures, and constant-currency adjustments.
- Treat stock-based compensation and diluted share growth as economic costs.
- Present conclusions as conditional research, not certainty or personalized investment advice.

## Delivery contract

A complete report has exactly four main analytical parts: fund flows, industry analysis, company deep dive, and final conclusion. Part 4 is the final numbered analytical section in both Markdown and HTML. Sources and methodology may appear as an appendix or footer, but no new analytical conclusion may follow Part 4.

Before delivery:

1. Put the conclusion before detail in every section.
2. Pair each material conclusion with evidence, counterevidence, missing data, and a falsifiable next observation.
3. Keep price action, positioning, business quality, and valuation separate.
4. Reconcile every repeated number and conclusion across Markdown and HTML.
5. Apply [references/output-spec.md](references/output-spec.md) for structure, readability, interactions, and QA.
6. Verify that Part 4 contains a separate conclusion for fund flows, industry development, and every analyzed company.
7. When browser testing is available, do not deliver HTML before checking console errors, overflow, legibility, and report-to-dashboard parity.
