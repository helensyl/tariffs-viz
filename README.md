# Liberation Day: Visualizing US Stock Market Reactions to Trade Policy Changes

> An interactive data journalism project exploring how Trump's April 2, 2025 tariff announcement impacted the US stock market, built for INFO 4310 Interactive Information Visualization.

---

## Overview

This project bridges the gap between political news and financial markets by visualizing how Trump's "Liberation Day" tariff announcement affected stock prices across key sectors. Inspired by *The New York Times Upshot*, it presents complex financial information in an accessible, story-driven format for users with limited financial literacy.

---

## Features

- **Scrollable narrative layout** -- structured as a guided story connecting political events to market reactions
- **Interactive timeline** -- vertical timeline of Trump's trade-related policy announcements since inauguration
- **Choropleth world map** -- countries affected by tariffs, shaded by severity (0-50%), with hover tooltips
- **Treemap of trade volume** -- visualizes affected countries by 2024 US trade volume, colored by tariff rate
- **Interactive stock market chart** -- tracks 10 ETFs and indexes by relative change (Mar 26 to Apr 8, 2025), with toggleable stock buttons, vertical date markers, and rich tooltips
- **Stock card animations** -- flip cards revealing the top companies behind each ticker

---

## Stocks Tracked

| Category | Tickers |
|---|---|
| Trade-related ETFs | XLI (Industrials), SOXX (Semiconductors), MOO (Agribusiness), XLB (Materials) |
| Investor-sensitive ETFs | XLK (Technology), XLF (Financials), XLP (Consumer Staples), VCR (Consumer Discretionary) |
| Benchmark Indexes | SPY (S&P 500), DJI (Dow Jones) |

---

## Tech Stack

- **D3.js** -- all interactive visualizations (choropleth, treemap, line chart, timeline)
- **HTML/CSS** -- layout, scroll-based storytelling, animations
- **Excel** (`STOCKHISTORY` function) -- stock data collection and preprocessing

---

## Data Sources

- **Timeline of events** -- compiled from news articles on Trump's 2025 trade policies
- **Tariff rates by country** -- sourced from official White House announcements
- **Stock market data** -- pulled via Excel's `STOCKHISTORY` function (daily closing prices, Mar 26 to Apr 8, 2025)

A full list of reference websites is included in the project webpage footnotes.

---

## Design Decisions

- **Relative change over absolute price** -- stocks had vastly different price scales, so the chart plots normalized change from a baseline of 1.0
- **Consistent visual language** -- Cormorant Garamond font, muted red color palette, and unified tooltip styling across all visualizations
- **Progressive tooltip complexity** -- tooltips grow more informative section by section, easing users into interactivity
- **Vertical scroll structure** -- mirrors journalistic storytelling; each section builds on the last

---

## Intended Audience

This project is designed for users with limited financial literacy, including students, casual investors, and anyone curious about the relationship between government policy and financial markets. It is not intended for professional financial analysts.

---

## Limitations

- **Excel `STOCKHISTORY` constraints** -- the function imposed several limitations on the stock market data:
  - Not all desired tickers were supported; for example, XLY (Consumer Discretionary) was unavailable and had to be substituted with VCR as an alternative representative ETF
  - Only daily closing prices are returned, making a more granular hour-by-hour view of the April 2 announcement impossible
  - Because only daily prices were available, the immediate intraday market reaction on April 2 itself is not fully visible; the chart only reflects end-of-day closes
- **Short time window** -- the data range (Mar 26 to Apr 8, 2025) ends before Trump's tariff pause on April 9, which was an intentional editorial choice but means the visualization does not capture the market recovery that followed
- **Target audience scope** -- the project is intentionally simplified for financial beginners, so it omits nuances like dividend adjustments, trading volume context, and currency effects that a more advanced analysis would include

---

## References

- [Foreign Policy](https://foreignpolicy.com/2025/02/06/trump-global-trade-system-china-reciprocal-tariffs/)
- [Executive Order Summary -- The White House](https://www.whitehouse.gov/fact-sheets/2025/04/report-to-the-president-on-the-america-first-trade-policy-executive-summary/)
- [Reciprocal Tariff Executive Order -- The White House](https://www.whitehouse.gov/presidential-actions/2025/04/regulating-imports-with-a-reciprocal-tariff-to-rectify-trade-practices-that-contribute-to-large-and-persistent-annual-united-states-goods-trade-deficits/)
- [Reciprocal Tariffs by Countries List -- The White House (PDF)](https://www.whitehouse.gov/wp-content/uploads/2025/04/Annex-I.pdf)
- [US Trading Imports & Exports -- Trading Economics](https://tradingeconomics.com/united-states/imports-by-country)
