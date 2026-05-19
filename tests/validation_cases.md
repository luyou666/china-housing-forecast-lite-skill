# Validation Cases

All formal forecast outputs should include: 仅供交流学习娱乐，不提供投资建议，所有解释权归作者所有。

## Case 1: Policy Easing Without Volume Recovery

Input: Mortgage rates fall and purchase restrictions ease, but transactions remain weak.

Expected: Do not call a recovery. Credit and policy may receive a mild improvement, but the probability view should remain cautious.

## Case 2: Price Stabilization With Rising Listings

Input: Asking prices stop falling, but second-hand listings and price cuts rise.

Expected: Treat stabilization as fragile and require volume confirmation.

## Case 3: Core Area Stronger Than Outer Suburb

Input: Core district transactions improve while outer suburbs have high inventory.

Expected: Split the forecast by district. Do not use the core-area signal to upgrade the entire city.

## Case 4: High Inventory New-Home Market

Input: New-home promotions increase and months of supply remains high.

Expected: Keep downside or discount pressure visible even if policy improves.

## Case 5: Missing Key Data

Input: Price data is available, but transaction and inventory data are missing.

Expected: Lower confidence and mark Data Gap rather than making a high-confidence call.

## Case 6: Net Population Inflow With Very High Inventory

Input: A city has net population inflow, but new-home inventory is very high and income growth is weak.

Expected: Do not simply judge price growth. At most, mildly raise long-term demand while keeping inventory pressure central.

## Case 7: Downturn, Lower Rates, No Transaction Improvement

Input: The economy is under downward pressure, mortgage rates decline, and transactions do not improve.

Expected: Do not assume rate cuts bring recovery. Lower the judgment of credit-policy effectiveness and purchase demand.

## Case 8: User Asks for Latest Market Trend

Input:
用户问："现在北京二手房是不是见底了？"

Expected:
- Trigger Fresh Data Retrieval Rule.
- Search latest public data if environment supports it.
- Output Data Sources Used.
- If latest transaction or listing data is missing, lower confidence.
- Do not answer from memory alone.

## Case 9: Stale Data Problem

Input:
Only data from 18 months ago is available.

Expected:
- Mark data as Stale.
- Do not present it as current.
- Confidence should be Low or Low-Medium.
- Output Data Gap.

## Case 10: Platform Data Conflict

Input:
Official price index shows slight decline, platform asking prices show stability.

Expected:
- Explain that asking prices are not transaction prices.
- Do not mechanically average them.
- Prefer official or transaction data for price judgment.
- Use platform data only as supplementary sentiment or listing pressure evidence.

## Case 11: Only Policy News Available

Input:
A city announced purchase restrictions were relaxed, but no transaction, listing, or price data is available.

Expected:
- Do not call recovery.
- Mark missing transaction/listing/price data.
- Confidence max Low-Medium.

## Case 12: Score Formula Ambiguity

Input:
A component has score 80 and weight 25.

Expected:
- Weighted score should be 80 × 25 / 100 = 20.
- The model must not calculate 80 × 25 = 2000.

## Case 13: Sentiment Data Without Transaction Confirmation

Input:
Social media discussion and search heat increase, but transaction volume remains weak.

Expected:
- Sentiment score is capped because evidence is C/D level.
- Do not call recovery.
- Require transaction confirmation.

## Case 14: Land Market Improves but Housing Transactions Remain Weak

Input:
Land premium rate improves, but second-hand transactions remain weak and listings rise.

Expected:
- Treat land recovery as developer expectation improvement.
- Do not override weak household demand.
- Explain horizon difference.

## Case 15: Source Date Unclear

Input:
A report says "recent market improved" but has no publication date or data period.

Expected:
- Mark source date as Unclear.
- Do not call it latest data.
- Lower confidence if it supports a key conclusion.
