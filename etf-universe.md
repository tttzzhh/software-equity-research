# Software ETF Universe

Lock this universe before observing returns. It is a research registry, not a claim that every fund is a pure representation of its label.

## Precedence

1. Preserve a user-supplied universe and disclose unusable securities.
2. If the prompt is silent, apply the default core.
3. Add subsector proxies only when that subsector is in scope.
4. Verify official objectives, index methodology, holdings, weighting, rebalance schedule, listing status, and data availability.
5. Never change the universe because subsequent performance supports a preferred conclusion.

## Default core

| Role | Ticker | Status | Interpretation |
|---|---|---|---|
| Broad market benchmark | SPY | Required | U.S. large-cap market context |
| Growth benchmark | QQQ | Required | Growth and large-cap technology context |
| Broad software, cap weighted | IGV | Required | Software leadership; inspect current methodology and non-software inclusions |
| Broad software, modified equal weighted | XSW | Required | Software breadth; compare with IGV rather than combining their flows |

Use RSP only when equal-weight market breadth is relevant. It is a benchmark, not a software ETF.

## Subsector registry

| Subsector | Primary | Cross-check | Rule |
|---|---|---|---|
| Cloud software and computing | WCLD, SKYY | CLOU | Add for SaaS, cloud adoption, or cloud infrastructure research |
| Cybersecurity | CIBR, HACK | BUG, IHAK | Add for network, endpoint, identity, data, or platform security |
| Semiconductor context | SOXX | None | Use only for AI infrastructure or technology risk appetite; never label it software flow |

Do not run every thematic ETF in every report. Overlapping holdings can make duplicated exposure look like independent confirmation.

## Selection and data rules

- A complete software-sector report uses SPY, QQQ, IGV, and XSW at minimum.
- A subsector report adds two primary proxies when both remain listed and have adequate data.
- Use a cross-check when primary funds disagree, index purity is questionable, or one fund is highly concentrated.
- Record exclusions as out of scope, stale data, short history, delisted, changed mandate, or unavailable holdings.
- Save a universe manifest with ticker, fund name, role, index, weighting, holdings date, return convention, and inclusion reason.
- When the Alpha Vantage connector is available, call `TIME_SERIES_DAILY_ADJUSTED` for every locked ETF and benchmark, `GLOBAL_QUOTE` for the current dated quote, and `ETF_PROFILE` for fund metadata and holdings. Preserve the raw response, query date, symbol, and output-size setting.
- Use Alpha Vantage adjusted close for comparable return, drawdown, volatility, and relative-strength calculations unless the research design explicitly requires raw price return. Do not mix adjusted and unadjusted series in one comparison.
- When the user supplies an interval, report it. Unless the user requests only that interval, add 20-, 60-, and 120-trading-day context using a common end date.
- Prefer official shares outstanding, NAV, AUM, and creation or redemption data.
- Treat Alpha Vantage ETF profiles as fund-description and holdings evidence, not as proof of daily creations or redemptions. Obtain flow from official fund shares-outstanding/NAV data or another explicitly sourced flow dataset.
- Do not infer flow from price return, trading volume, or AUM change alone.
- If only price data exist, label the section **performance and positioning proxy**, not **fund flow**.
- Do not sum overlapping ETF flows without a disclosed overlap method.

Fund mandates can change. Verify this registry against current official materials for current-market work and mark unresolved items `Missing Data`.
