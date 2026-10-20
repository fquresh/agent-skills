---
name: market-positioning-read
description: Turn a market news item, analyst post, or tweet into a sourced positioning read with bull and bear cases for each affected stock. Use when the user shares a headline, article, link, screenshot, or thread about a company, sector, or supply chain and asks for market research, financial analysis, a breakdown, a positioning read, trade ideas, or bull and bear cases. Finds the primary source, separates what it says from how it was framed, and checks recent price action. Then it ranks the names. Do not use for portfolio construction, tax questions, or a single price lookup.
argument-hint: <a link, pasted text, or screenshot of the news item>
---

# Market positioning read

The user shares a news item and wants to know what it means for specific stocks.
The output is a positioning read: what the source says, what the market should take from it, and a bull and bear case for each name.
Write as a sell-side or buy-side analyst writes for a portfolio manager. Be short and specific, and give a view.

## Step 1: Get the primary source

1. Follow every link to its end. Short links (t.co, bit.ly) redirect. Fetch the final URL.
2. Read the original article, filing, or transcript, not only the post about it. A foreign-language source is fine. Translate the facts.
3. Write down the outlet, author, date, and every number, quote, and company named.
4. Write down what the source does NOT say. Missing terms, counterparties, and figures are often the story.
5. If you only get a summary or a paywall teaser, say so. Mark numbers from it as UNVERIFIED.

## Step 2: Compare the framing with the source

Posts compress. Compression changes meaning.
Find each place where the post and the source differ.
The common traps:

| Trap | Example | Check |
|---|---|---|
| Volume vs price | "Shortage eases" can mean buyers get supply while prices still rise | Does the source talk about units, price, or both? |
| Level vs rate of change | "Prices rise slower" is still a rise, but the second derivative turned | Which one does the stock trade on? |
| Cause hidden | "Supply eases" because demand collapsed | Is the relief from supply or from demand destruction? |
| Scope | "Major vendors" signed deals, so smaller ones did not | Who is left out, and who takes the squeeze? |
| Stale forecast | An outlet repeats a forecast that the source has since revised | Find the newest dated version |

## Step 3: Pull the market context

Search for these before you form a view. Use dated sources and note each date.

- Recent price action for each name: the last 2-4 weeks, the drawdown from the high, and the cause.
- Is the news already priced in? A headline that confirms a known story moves less than new information does.
- Recent statements from management that agree with the source or contradict it.
- The newest third-party data: industry trackers, contract prices, shipment data.
- Upcoming catalysts with dates: earnings, data releases, policy decisions.

When sources conflict, do not pick one. Reconcile them, or state the conflict as a key debate.

## Step 4: Find the second-order signal

Answer these in a table of signal and meaning:

- Who gains pricing power, and who absorbs the cost?
- Which revenue mix wins: enterprise or consumer, data center or client, contracted or spot?
- Who is not named but is exposed? Mark this as inference.
- What does the news change about the next 2-4 quarters of estimates?

## Step 5: Write bull and bear cases

Cover each directly affected stock, grouped by role in the chain (supplier, buyer, competitor, second tier).
Give each name a ticker and its listing.
Each case is 2-3 lines and holds the mechanism plus at least one sourced number.
Mark the best-placed and most-exposed names in each group.
Do not give a name a bull case it does not have. "Limited bull case" is a valid answer.

## Step 6: Give the positioning read

1. A table with columns name, read, and one-line reason. Reads: constructive, neutral, relative long, relative short, underweight.
2. Pair ideas only where the mechanism links the two legs.
3. The main risk to the whole view, in 2 sentences or fewer.
4. Catalysts with dates.
5. Limits: what you did not verify, which numbers came from secondary sources, and which points are inference.
6. One line that says this is analysis, not investment advice.

## Output template

Use the blank copy in `references/template.md`.
For a filled example, see `references/example-memory-ltas.md`.

## Rules

1. Every number has a source and a date. Never invent a price, multiple, or estimate.
2. Keep fact, interpretation, and inference apart. Label inference.
3. Do not quote a valuation multiple or live price you did not fetch. Say they were not checked instead.
4. Give a view. A read that lists only "on one hand, on the other hand" fails.
5. Favor the rate of change over the level. Markets price changes in the trend.
6. Be brief. Use tables for comparisons and short bullets for cases.
7. End with a sources list that has a markdown link for each URL used.

## Pitfalls

- Do not analyze the post when the article is one click away.
- Do not treat a headline word ("eases", "surges", "record") as the finding. Find the number behind it.
- Do not skip price action. The same news is bullish after a 30% drawdown and bearish after a 30% rally.
- Do not cover a long list of loosely related tickers. Cover the names the mechanism touches.
