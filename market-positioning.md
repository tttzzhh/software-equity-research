# Market Positioning

Use this reference to analyze whether software-sector price action is broad, flow-supported, short-covering, or crowded. Market positioning is a separate layer from business quality.

## Fix the comparison set first

Read [etf-universe.md](etf-universe.md), then define the universe and benchmark before examining returns. Use its defaults when the prompt is silent and record:

- cap-weighted and, when useful, equal-weighted software baskets;
- relevant subsector proxies and their constituent rules;
- broad-market benchmark such as SPY and growth benchmark such as QQQ;
- analysis windows, normally short, medium, and long rather than one favorable interval;
- price-return or total-return treatment;
- the market-data source, query date, and latest observation date.

ETF examples can help define a basket, but an ETF is not identical to an industry. Review its index methodology, holdings, concentration, rebalance schedule, currency, and use of ADRs before interpreting it as sector evidence.

## Alpha Vantage market-data call

When the Alpha Vantage connector is available, use it as the default market-data source for the locked universe:

- call `TIME_SERIES_DAILY_ADJUSTED` for historical ETF and stock OHLCV, adjusted close, splits, and dividends;
- call `GLOBAL_QUOTE` when a dated latest quote is required;
- call `ETF_PROFILE` for ETF net assets, expense ratio, turnover, sector allocation, and holdings;
- save raw results before calculations and record the request date, last observation date, symbol, and return convention;
- if the required history exceeds the compact response, request the full series rather than silently shortening the window.

Alpha Vantage provides market and fund-profile data, not conclusive daily ETF net-creation data. Use official shares outstanding, NAV, or an explicitly identified flow dataset for creations and redemptions. If those data are unavailable, label the output **performance and positioning proxy** and mark flow `Missing Data`.

## Measurement map

### Returns and relative strength

- Interval return: `end value / start value - 1`.
- Relative return: `sector return - benchmark return`; for longer periods, also show the ratio series `sector index / benchmark index`.
- Drawdown: `value / running peak - 1`; maximum drawdown is the minimum of that series.
- Realized volatility: sample standard deviation of daily returns multiplied by `sqrt(252)` unless a different convention is stated.
- Use several windows such as 20, 60, and 120 trading days. A single hand-picked window is supporting evidence, not a regime conclusion.

When data permits, separate beta exposure from residual performance with a stated estimation window. Do not call simple benchmark outperformance “alpha.”

### Breadth and concentration

Measure the share of constituents:

- above 20-, 50-, and 200-day moving averages;
- making 20- or 52-week highs and lows;
- with positive returns over the chosen window;
- contributing to the basket's total return.

Compare cap-weighted with equal-weighted returns. Cap-weight outperformance alongside weak breadth suggests leadership concentration, not broad sector strength. Keep current and historical index constituents separate when survivorship bias matters.

### Fund flows

Use primary ETF flow or shares-outstanding data where possible. Distinguish:

- net creations or redemptions;
- estimated dollar flow;
- assets under management changed by market performance;
- trading volume, which is turnover and not an inflow;
- fund-level flow from underlying-company capital flow.

Report absolute flow, flow as a percentage of beginning AUM, persistence across several periods, and concentration across funds. Large AUM gains with flat shares outstanding may be price appreciation rather than new money.

### Short positioning

Use exchange-reported short interest and its publication date. Track:

- short interest as a percentage of float;
- days to cover: short interest divided by average daily volume;
- change across reporting periods;
- borrow fee or utilization when a reliable source exists;
- performance on high-volume up days that may indicate covering.

Do not treat daily short-sale volume as outstanding short interest. High short interest may reflect hedging or capital-structure trades rather than a directional view.

### Options and crowding

When available, examine put/call open interest and volume, implied versus realized volatility, skew, term structure, and concentration around strikes or expiries. Options activity is context, not proof of investor direction.

Assess crowding through several independent signals:

- persistent inflows relative to AUM;
- narrow leadership and correlated positioning;
- valuation percentile versus the company's own history and peers;
- ownership concentration and changes in institutional holdings;
- low short interest after a sharp rally or evidence of recent covering;
- elevated call skew or implied volatility where relevant.

Never collapse crowding into a precise score unless inputs, history, normalization, and weights are disclosed.

## Interpretation grid

| Price and relative strength | Breadth | Flow | Plausible reading |
|---|---|---|---|
| Strong | Broad | Positive and persistent | Supported risk-on participation |
| Strong | Narrow | Weak or mixed | Concentrated leadership |
| Strong | Improving | Weak | Possible short covering or fundamental repricing |
| Weak | Deteriorating | Negative | Broad risk reduction |
| Weak | Stable | Positive | Early accumulation or flows lagging price; investigate |

Treat this grid as a hypothesis generator. Confirm with earnings revisions, rates, index changes, and company-specific events.

## Output block

Include:

1. universe, benchmark, horizon, and data dates;
2. return and relative-strength table;
3. breadth and concentration evidence;
4. ETF flow evidence with AUM normalization;
5. short and options positioning with reporting lags;
6. a conclusion labeled **broad participation**, **concentrated leadership**, **de-risking**, or **inconclusive**;
7. missing data and the next observations that would change the conclusion.
