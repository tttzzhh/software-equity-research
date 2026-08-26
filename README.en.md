# Software Equity Research

**Language: [中文](README.md) | English**

A Codex skill for evidence-based software-equity research across four coordinated modules: fund flows and market positioning, industry analysis, company deep dives, and a final scenario-based investment conclusion.

This version provides a default ETF universe and a stable delivery contract for Markdown research reports and HTML dashboards.

## Use cases

- Complete software-sector or subsector reports
- ETF flows, relative strength, breadth, shorts, options, and crowding
- Cloud and cybersecurity industry research
- Earnings reviews and company deep dives
- Peer comparisons, valuation scenarios, and monitoring frameworks
- Consistent Markdown reports and HTML dashboards

It is not intended for software engineering, product architecture, or code review.

## Research framework

### 1. Fund flows and market positioning

Lock the comparison set before observing results. When the prompt is silent, use SPY and QQQ as benchmarks and IGV and XSW as the broad software pair. Add cloud or cybersecurity proxies only when the subsector is in scope.

The module distinguishes verified ETF creations and redemptions from price-driven AUM changes and trading volume. If reliable flow data are unavailable, the result is labeled a performance and positioning proxy.

### 2. Industry analysis

Select peers by buyer, product mission, revenue model, scale, growth stage, and geography. Compare demand, pricing units, contracts, revenue visibility, margins, expansion mechanisms, platform competition, bundling, self-build, open source, and commoditization.

### 3. Company deep dive

Map the product, buyer, pricing unit, renewal mechanism, and revenue engine. Examine ARR, NRR/NDR, RPO, customer growth, margins, cash conversion, stock-based compensation, dilution, moat evidence, valuation, scenarios, catalysts, and falsifiers.

Unavailable data remain `Missing Data` or `not disclosed`.

### 4. Final conclusion and scenario decision

The final module keeps three conclusions separate before combining them: the fund-flow regime, the industry's development position, and the company's business quality and valuation.

Each company receives bear, base, and bull scenarios plus one conditional research action: `Buy / Accumulate`, `Watchlist / Hold`, `Avoid / Reduce`, `Speculative / High Risk`, or `No Rating`.

Unless the user supplies different thresholds, `Buy / Accumulate` requires at least 20% base-case expected return, no more than 25% bear-case downside, identifiable catalysts, and no active thesis-breaking evidence. Missing current-price or valuation inputs require `No Rating` rather than a forced buy opinion.

## Delivery contract

A complete report contains scope and comparison design, a three-part executive summary, Parts 1 through 3, sources and methodology, and Part 4 as the final numbered analytical section. Part 4 contains scenario decisions, action labels, entry conditions, falsifiers, and the monitoring checklist.

Each module must contain a conclusion, supporting evidence, counterevidence, missing data, and a falsifiable next observation.

The HTML dashboard is a visual layer of the report. Its opening view presents the fund-flow, industry, and company conclusions rather than detailed KPIs. Its final full analytical section is Part 4, followed only by a compact source footer. Reports and dashboards must agree on every repeated number, period, scenario, action label, and conclusion.

## Examples

```text
Use $software-equity-research to produce a complete cybersecurity software report.
Include fund flows, industry analysis, and company deep dives for CRWD, PANW, and ZS.
Lock the period, benchmarks, and peer-selection rule before collecting results.
Deliver a Markdown report and an HTML dashboard.
```

```text
Use $software-equity-research to review this earnings report.
Focus on ARR, NRR, RPO, growth quality, margins, cash flow, stock-based compensation, and guidance changes.
Separate reported, derived, and analyst-estimated values.
```

## Structure

```text
software-equity-research/
├── SKILL.md
├── README.md
├── README.en.md
├── agents/openai.yaml
└── references/
    ├── etf-universe.md
    ├── investment-conclusion.md
    ├── output-spec.md
    ├── market-positioning.md
    ├── metrics.md
    ├── business-models.md
    ├── moat-and-risks.md
    └── subsectors.md
```

Copy the folder into the Codex Skills directory and invoke it with `$software-equity-research`.

This skill provides a conditional research framework, not personalized investment advice.
