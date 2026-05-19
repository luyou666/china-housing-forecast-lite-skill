# Scoring Model

Use a 0 to 100 composite score. Higher scores imply stronger probability of stabilization or upward pressure; lower scores imply higher downside risk.

## Core Components

| Component | Suggested Weight | Focus |
|---|---:|---|
| Price and transaction trend | 25 | Price direction, transaction volume, listing pressure, price cuts |
| Inventory and supply pressure | 20 | Months of supply, new-home backlog, second-hand listings |
| Valuation and affordability | 15 | Price-to-income, rental yield, payment burden |
| Credit and policy effectiveness | 15 | Mortgage rates, down payment, purchase restrictions, actual take-up |
| City and district segmentation | 15 | Core area resilience, suburban weakness, product split |
| Sentiment and confidence | 10 | Buyer expectations, developer confidence, negotiation power |

## Original Composite Score

Original Composite Score =
sum(Core Component Score × Core Component Weight / 100)

The core model should remain focused on trend, transaction, inventory, valuation, credit, policy, and segmentation.

Rules:

- Each component score ranges from 0 to 100.
- Each component weight is expressed as a percentage.
- The final Original Composite Score should remain within 0 to 100.
- Do not multiply raw scores by whole-number weights without dividing by 100.

## Economic and Population Adjustment

Economic and Population Adjustment =
Economic Cycle Adjustment
+ Population Flow Adjustment

Where:

- Economic Cycle Adjustment range: -4 to +4
- Population Flow Adjustment range: -4 to +4
- Total adjustment range: -8 to +8

Adjustment guidance:

| Level | Score |
|---|---:|
| Strong positive adjustment | +5 to +8 |
| Mild positive adjustment | +2 to +4 |
| Neutral | 0 |
| Mild negative adjustment | -2 to -4 |
| Strong negative adjustment | -5 to -8 |

Positive conditions include improving economic growth, stable employment, better resident income growth, net population inflow, young population inflow, high-income industries, and rising core-area job density.

Negative conditions include clear economic downward pressure, rising employment pressure, slowing income growth, weak consumer confidence, net population outflow, shrinking young population, weak new-district population import, and industrial hollowing-out.

Rules:

- The adjustment can affect the final score by at most +/-8 points.
- If the adjustment exceeds +/-5 points, explain the reason.
- If data is insufficient, use only a light adjustment from 0 to +/-3.
- Do not make a large adjustment based only on subjective judgment.

## Final Adjusted Score

Final Adjusted Score =
Original Composite Score
+ Economic and Population Adjustment

Economic cycle and population flow are correction factors only. Do not allow this module to override core variables such as trend, inventory, valuation, and credit.

## Minimum Scoring Thresholds

Use these thresholds to reduce subjective scoring. If local context requires a different score, explain the reason and keep the change small.

### Transaction Volume YoY

- > +30%: 85-95
- +10% to +30%: 70-85
- -10% to +10%: 45-65
- -30% to -10%: 25-45
- < -30%: 10-25

### Price Momentum MoM

- > +0.5%: 85-95
- 0% to +0.5%: 70-85
- -0.5% to 0%: 50-65
- -1.0% to -0.5%: 30-50
- < -1.0%: 10-30

### Months of Supply

- < 12 months: 80-90
- 12-18 months: 60-75
- 18-24 months: 40-55
- > 24 months: 10-35

### Listing Pressure

- Listings falling clearly: 75-90
- Listings stable: 50-65
- Listings rising moderately: 30-50
- Listings rising sharply: 10-30

### Rental Yield

- > 3.5%: 80-90
- 2.5%-3.5%: 60-75
- 1.5%-2.5%: 35-55
- < 1.5%: 10-30

## Sentiment Score Cap

Rules:

- If sentiment evidence is based mainly on A/B level data, such as verified transaction behavior, official confidence indicators, or industry research, the sentiment score may use the standard 0-100 range.
- If sentiment evidence is based mainly on C level data, such as search index, platform heat, social media discussion, or broker feedback, the sentiment score must not exceed 60.
- If sentiment evidence is based mainly on D level data, such as self-media opinions, forum posts, or unverified screenshots, the sentiment score must not exceed 40.
- C/D level sentiment data cannot independently support a recovery conclusion.
- Sentiment improvement without transaction confirmation should only raise confidence slightly, not change the main market direction.
- If sentiment and transaction data conflict, prioritize transaction data.

## Probability Mapping

Use Final Adjusted Score to generate the 3/6/12/24 month probability table. Keep each row within the matching score range, then adjust slightly by horizon, Bear Case Review, and data gaps.

Final Adjusted Score >= 80:
- Rise: 55%-70%
- Sideways: 20%-35%
- Fall: 5%-15%

65 <= Score < 80:
- Rise: 35%-50%
- Sideways: 35%-45%
- Fall: 10%-25%

50 <= Score < 65:
- Rise: 20%-35%
- Sideways: 40%-55%
- Fall: 20%-35%

35 <= Score < 50:
- Rise: 10%-25%
- Sideways: 35%-50%
- Fall: 30%-50%

Score < 35:
- Rise: 5%-15%
- Sideways: 20%-40%
- Fall: 45%-70%

Rules:

- Probabilities must sum to 100%.
- Bear Case Review may reduce rise probability.
- Strong volume confirmation may raise rise probability within the allowed range.
- Missing key data lowers confidence and narrows aggressive conclusions.
- If 24-month fundamentals conflict with 3-month transaction signals, explain the horizon difference.

## Data Gap Confidence Cap

- Missing transaction volume: confidence max Medium.
- Missing inventory or listings: confidence max Medium.
- Missing valuation data: investment recommendation must be conservative.
- Missing population data: medium-long-term confidence max Medium.
- Missing latest policy: policy-impact judgment max Medium.
- Only policy data available: confidence max Low-Medium.
- Only C/D level, anecdotal, or social media data available: confidence max Low.

## Horizon Adjustment Rules

### 3-month forecast

- Give more weight to price MoM, transaction volume, listing volume, and short-term policy shocks.
- Population and long-term industry signals should only make weak adjustments.
- Do not give high confidence without recent transaction or listing data.

### 6-month forecast

- Price, transaction volume, inventory, and credit conditions jointly determine the result.
- If transactions have not improved continuously, do not sharply raise rise probability.

### 12-month forecast

- Increase the impact of inventory, credit effectiveness, income, and economic cycle.
- If policy is loose but medium- and long-term household loans and transactions do not improve, remain cautious.

### 24-month forecast

- Increase the impact of population flow, industry income, city tier, and long-term supply pressure.
- If long-term population outflow or weak industry is clear, do not give a high-confidence rise judgment even if short-term policy support exists.

## Fresh Data Scoring Rule

- If latest data is available and source quality is A/B, scoring can use standard confidence.
- If latest data is available but only C level, scoring must lower confidence.
- If latest data is not available, use older data only with a stale warning.
- If data is stale and key to the conclusion, confidence must be capped.
- Do not use outdated data as if it were current.

## Use Disclaimer

仅供交流学习娱乐，不提供投资建议，所有解释权归作者所有。
