# Combined Examples

## Example 1: Flight redemption
User: "Find me the best way to book SFO to Tokyo business class next month using points."

Expected flow:
1. Search cash prices.
2. Search award availability.
3. Pull transferable balances if relevant.
4. Compute effective point cost.
5. Recommend the best booking path.

## Example 2: Cash vs points
User: "Compare cash vs points for JFK to London in March."

Expected flow:
1. Find cash options.
2. Find award options.
3. Convert award cost into effective points.
4. Compare value and recommend the better option.

## Example 3: Transfer partner optimization
User: "I have Chase UR and Amex MR. Which should I use for this award?"

Expected flow:
1. Map the award program to available transfer partners.
2. Calculate effective points for each currency.
3. Rank by effective cost.
4. State the winner and why.
