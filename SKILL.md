# China Real Estate Quant Forecast Skill

Use this skill to produce concise, evidence-driven forecasts for Chinese residential real estate markets. Keep the analysis centered on housing-market data: price trend, transaction volume, inventory or listings, valuation, credit conditions, policy changes, and district segmentation.

Do not turn the forecast into a broad macroeconomic report, crawler system, or machine-learning system. Economic cycle and population flow are important overlays, but they remain a small adjustment within +/-8 points.

Standard disclaimer for formal outputs: 仅供交流学习娱乐，不提供投资建议，所有解释权归作者所有。

## When to Use

Use this skill when the user asks about:

- Housing price trends in a Chinese city or district
- New-home or second-hand-home market forecasts
- Whether a market is stabilizing, bottoming, or still declining
- Whether now is suitable for self-use purchase or investment
- 3/6/12/24 month probability forecasts
- Risk checks for core areas, suburbs, new districts, or satellite cities

## Fresh Data Retrieval Rule

When the user question includes any of the following, prioritize latest public data retrieval before scoring:

- 最新
- 当前
- 现在
- 今年
- 最近
- 当下
- 未来几个月
- 未来 3 个月
- 未来 6 个月
- 未来 12 个月
- 某城市是否见底
- 现在是否适合买房
- 当前是否适合投资

If the runtime supports web search, perform fresh public data retrieval. Use only publicly accessible sources. Do not bypass paywalls, login restrictions, anti-bot systems, or captchas.

If the runtime does not support web search:

1. State clearly that latest data cannot be fetched automatically.
2. Ask the user to provide data, or continue with a low-confidence framework analysis.
3. Mark the missing items as Data Gap.
4. Do not fabricate current or latest data.

## Traceable Source Requirement

For formal forecasts using fresh data:

- Show source name, data date, and freshness status.
- Prefer traceable official or industry sources.
- Include source links or identifiable publication names if available.
- Do not claim to have used latest data unless the source date is visible.
- If the source cannot be opened and only a snippet is available, treat it as weak evidence.
- If a key data point has unclear source or unclear date, mark it as Data Gap or Stale and lower confidence.

## Fresh Data Retrieval Workflow

1. Define scope:
   - City
   - District
   - New home / second-hand home / both
   - Forecast horizon
   - User purpose: self-use / investment / research / risk check

2. Search latest data:
   - Price data
   - Transaction volume
   - Inventory / listings
   - Mortgage rate / LPR / credit policy
   - Local purchase restrictions, provident fund, subsidies, purchase support, destocking or acquisition policies
   - Population inflow / outflow
   - Income, employment, and economic-cycle data

3. Assign data quality:
   - Use `data_sources.md` A/B/C/D reliability levels.

4. Check freshness:
   - Use `data_sources.md` freshness standards.

5. Resolve conflicts:
   - If sources conflict, explain methodology differences.

6. Mark gaps:
   - If key data is missing, mark Data Gap and apply `scoring_model.md` confidence caps.

7. Score and forecast:
   - Use `scoring_model.md` for core scoring, probability mapping, economic/population adjustment, and horizon adjustment.

8. Cross-check:
   - Use Minimal Multi-Agent Mode and Bear Case Review.

9. Output:
   - Use `output_template.md`.

## Required Data

### Housing Market Data

- New-home and second-hand-home price trend
- Transaction volume and listing volume
- Inventory or months of supply
- Discount rate and price-cut ratio if available
- Rental yield or price-to-income ratio if available
- Mortgage rate, credit availability, and down-payment policy
- Local purchase restrictions, tax policy, provident fund policy, and housing support policy
- District-level split between core areas, mature urban areas, outer suburbs, new districts, and satellite cities

### Economic Cycle Data

- GDP growth or regional GDP growth
- Unemployment rate
- Resident disposable income growth
- Consumer confidence if available
- PMI or local industrial activity if available

### Population Flow Data

- Permanent population change
- Net population inflow or outflow
- Young population share if available
- Household registration change if available
- Employment inflow if available

If data is missing, do not block the forecast. Mark Data Gap and lower confidence according to `scoring_model.md`.

## Economic Cycle and Population Flow Overlay

Economic cycle and population flow correct the final judgment but do not replace the core housing model.

- Economic expansion can improve income expectations, employment stability, and purchase confidence.
- Economic downturn can weaken income expectations, raise employment pressure, and reduce willingness to add leverage.
- Net population inflow supports long-term demand, especially in core districts.
- Net population outflow weakens long-term demand, especially in non-core areas and high-inventory new-home markets.
- Young population inflow matters more than total population inflow.
- Population inflow alone does not imply price growth; it must be checked against income, industry, and inventory.
- Population outflow does not mean every area declines; scarce core locations may still have support.

## New Home Price Distortion Rule

New-home listed prices and official filing prices may not reflect real transaction values.

Check:

- Discount rate
- Free parking space
- Decoration package
- Channel rebate
- Down-payment installment
- Developer financing pressure
- Group-buying discounts
- Promotional payment terms

If new-home sales improve mainly because of heavy discounts, do not treat it as organic recovery.

## Self-Use vs Investment Rule

A property can be acceptable for self-use but unattractive for investment.

Self-use judgment should focus on:

- Affordability
- Commute
- School, hospital, and public services
- Family stability
- Holding period

Investment judgment should focus on:

- Rental yield
- Liquidity
- Population and job inflow
- Supply pressure
- Expected resale demand
- Leverage risk

## Minimal Multi-Agent Mode

For every formal forecast, simulate at least five roles:

1. Trend Agent
2. Supply and Inventory Agent
3. Credit, Policy and Valuation Agent
4. Population and Economic Overlay Agent
5. Bear Case Review Agent

Each role must output:

- Score
- Direction
- Confidence
- Key Reason
- Main Risk

The Bear Case Review Agent must challenge the main conclusion before the final probability table is produced. If it raises a major objection, lower confidence or reduce rise probability.

## Workflow

1. Define scope and user purpose.
2. Trigger Fresh Data Retrieval Rule when the user asks about current or latest conditions.
3. Assign source quality and freshness using `data_sources.md`.
4. Score the original housing model using `scoring_model.md`.
5. Apply Economic and Population Adjustment within +/-8 points.
6. Apply Data Gap Confidence Cap if data is missing or stale.
7. Run Minimal Multi-Agent Mode and Bear Case Review.
8. Produce 3/6/12/24 month rise, sideways, and fall probabilities.
9. Separate self-use recommendation from investment recommendation.
10. Output using `output_template.md`.

## Output Discipline

- Every formal forecast output must include this disclaimer: 仅供交流学习娱乐，不提供投资建议，所有解释权归作者所有。
- Always show data sources, dates, quality, and freshness for formal forecasts.
- Preserve source names, publication dates, or traceable links whenever available.
- Always output the 3/6/12/24 month probability table.
- Every probability row must sum to 100%.
- Separate short-term trend from medium- and long-term fundamentals.
- Explain conflicts between transaction signals, source types, economic cycle, and population flow.
- Use examples only as format references, never as real current data.

## File Integration Map

- Use `data_sources.md` for source reliability, freshness, and conflict handling.
- Use `scoring_model.md` for score calculation, probability mapping, horizon adjustment, and confidence caps.
- Use `output_template.md` for final report format.
- Use `risk_rules.md` to avoid prohibited or overconfident conclusions.
- Use `examples/` only as format references, not as real data.
- Use `tests/` to validate output quality.
