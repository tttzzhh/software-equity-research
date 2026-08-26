# Report and Dashboard Output Specification

Use this specification for Markdown reports, HTML dashboards, or both. Stable quality matters more than identical decoration.

## Shared analytical block

Every module includes:

1. a one-sentence conclusion;
2. supporting evidence;
3. counterevidence or a competing explanation;
4. missing data;
5. the next observable condition that would confirm or falsify the conclusion.

Label important values as **reported**, **company-defined**, **derived**, **consensus**, **third-party**, or **analyst estimate**. Attach the period and source.

## Markdown report

A complete report uses this order:

1. title, as-of date, scope, horizon, benchmarks, and peer rule;
2. executive summary with exactly three module conclusions;
3. Part 1 - fund flows and market positioning;
4. Part 2 - industry analysis;
5. Part 3 - company deep dive;
6. sources, methodology, caveats, and missing data;
7. Part 4 - final conclusion and scenario decision, containing the fund-flow conclusion, industry-development position, and a conditional action for every analyzed company.

Part 4 is the final numbered analytical section. It includes bear, base, and bull scenarios, entry conditions, catalysts, falsifiers, and the consolidated monitoring checklist. No new investment conclusion may appear after it.

A single-module report retains the conclusion-evidence-counterevidence-monitoring structure without pretending to be complete.

Do not publish a table without causal interpretation and its main limitation. Do not claim acceleration without a comparable prior period. Include at least one plausible counterinterpretation for every major investment conclusion.

## HTML dashboard

Build the dashboard only after the report's numbers and conclusions are stable.

### Page order

1. **Opening view:** title, date, scope, and conclusion cards for fund flows, industry, and company. Do not fill the opening view with detailed KPIs.
2. **Fund flows:** universe, benchmarks, period controls, relative performance, breadth, verified flow, and positioning conclusion.
3. **Industry:** subsector map, demand and business-model evidence, peer comparison, and conclusion.
4. **Company:** revenue engine, operating KPIs, growth quality, profitability, cash conversion, moat evidence, and risks.
5. **Valuation and scenarios:** assumptions, bear/base/bull outcomes, catalysts, and falsifiers when supported.
6. **Sources and methodology:** primary sources first, calculation notes, missing data, and update date.
7. **Final conclusion:** the last full analytical section, combining separate fund-flow, industry-development, and company conclusions with scenario-based action labels, entry conditions, and thesis-breaking conditions.

The HTML may place compact source links in a footer after Part 4, but no analytical card, scenario, recommendation, or conclusion may follow the final-conclusion section.

For a single-module dashboard, keep the opening conclusion and only the requested sections.

### Visual and interaction rules

- Use one design system for colors, spacing, radii, borders, typography, and charts.
- Default content width: 1180-1320 px.
- Body text: at least 17 px with line height of at least 1.55.
- Secondary labels and source notes: at least 14 px.
- Major KPI values: at least 32 px.
- Each card carries one main conclusion and its evidence.
- Keep a normal screen to roughly four to six primary data points.
- Every chart needs title, period, unit, source, and a one-sentence takeaway.
- Useful interactions are sticky navigation, period switching, benchmark switching, and optional evidence expansion.
- Never hide a core conclusion behind interaction.
- Do not add presentation-mode controls, animated counters, or ornamental motion unless requested.
- Make the Part 4 action label prominent but show the valuation date, scenario hurdle, and risk condition beside it. Never display an unexplained buy badge.

## Report-to-dashboard parity

Before delivery, verify exact agreement on scope, as-of date, universe, benchmarks, module conclusions, KPI value and period, derived assumptions, scenarios, action labels, entry conditions, risks, falsifiers, and sources. The dashboard may compress the report but cannot introduce a new conclusion or different number.

## Final QA

When tools are available:

1. validate HTML structure and links;
2. load the page through its local server after the final edit;
3. confirm zero console errors;
4. inspect the opening view and every section at a normal desktop viewport;
5. check narrow-width stacking when responsiveness is in scope;
6. check clipped text, small labels, overflow, contrast, chart units, and sources;
7. confirm the final analytical section contains fund-flow, industry-development, and company conclusions;
8. reconcile the page against the final Markdown report, including scenario values and action labels.

If visual testing is unavailable, say that the page was structurally checked but not visually verified.
