---
name: travel-hacking-toolkit
description: Travel hacking workflow for points, miles, award flights, and redemption optimization. Use when the user asks to compare cash vs points, find award availability, check transfer partners, estimate cents-per-point value, plan travel using loyalty programs, or choose the best booking path.
---

# Travel Hacking Toolkit

Use this skill for award flights, cash-vs-points decisions, transfer-partner optimization, and travel deal comparisons.

## Core flow

1. Clarify the trip and cabin constraints.
2. Search cash prices and award availability with the right tools.
3. Check loyalty balances and transferable currencies if points are involved.
4. Compare the real cost in points and cash-equivalent value.
5. Recommend the best booking path, not just the cheapest number.

## Decision rubric

When ranking options, prefer the option with the best mix of:
- lowest effective point cost
- best cash-equivalent value
- realistic availability
- acceptable routing/time
- lowest friction to book

If two options are close, prefer the one that is easier to book and more likely to remain available.

## Default search order for flights

For any flight search, prefer this order when available:
- Duffel
- Ignav
- Google Flights / browser search
- Skiplagged
- Kiwi
- Seats.aero for awards
- Southwest skill if Southwest serves the route

## Award math

Use this math for transfer-partner comparisons:
- `effective_points = award_miles / transfer_ratio`
- `opportunity_cost = effective_points × point_value_cpp / 100`

If there is no direct transfer path, say so clearly.

## Transfer partner logic

When points matter, use the local `transfer-partners` data to map transferable currencies to airline programs and compute the effective point cost. Treat the lowest effective cost as the best path, but consider award availability and transfer ratio.

## Use these prompt patterns

### Flight search prompt
- "Find the best flight options for [route] on [dates]. Include cash prices, stops, cabin, and your top recommendation."
- "Search all relevant flight sources for [route], then rank the best options by price and practicality."

### Award search prompt
- "Find award availability for [route] in [cabin] on [dates] and tell me the best mileage play."
- "Compare award options across programs and tell me which redemption is best value."

### Transfer-partner prompt
- "I have [currency balances]. For this award price, which currency gives the cheapest effective cost?"
- "Map the award program to my transferable points and show the math."

### Cash-vs-points prompt
- "Compare cash vs points for this trip and tell me whether I should pay cash or redeem points."
- "Show the effective cents-per-point value and recommend the better option."

## Local workflow

1. Get the route, dates, cabin, travelers, and flexibility.
2. Search cash and award options.
3. Pull balances and transfer paths if relevant.
4. Compute effective cost in each usable currency.
5. Compare against cash price and point valuations.
6. Recommend the best booking path with a brief explanation.

## When to load references

- `references/transfer-partners.md` — transfer ratios, effective-cost math, and award optimization
- `references/workflow.md` — concise booking workflow and recommendation format
- `references/examples.md` — copy-paste prompts for common travel tasks
- `references/combined-examples.md` — end-to-end travel-hacking examples
- `references/cheatsheet.md` — one-page summary of the whole workflow

## Output style

- Be opinionated.
- Show the math.
- Use markdown tables for comparisons.
- State the best option clearly.
- Keep hotel search out unless explicitly requested.
