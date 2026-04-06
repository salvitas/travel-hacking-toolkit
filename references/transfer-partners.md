# Transfer Partners

Use this reference to translate award costs into the user's transferable point currencies.

## Rules
- Map award program -> transfer program using local JSON data.
- Compute effective cost as: `award_miles / transfer_ratio`.
- If there is no direct transfer path, say so.
- Prefer the currency that minimizes opportunity cost, not just nominal points.

## Typical flow
1. Identify the award program and miles cost.
2. Look up transfer ratios in the local data file.
3. Calculate points needed per currency.
4. Compare against balances and point valuations.
5. Recommend the cheapest viable path.

## Recommendation rules
- Rank by effective point cost.
- Note transfer bonuses if they materially change the result.
- If the user lacks balance, say which currency is closest and whether a transfer would help.
