# Academics-FRA-1: Does "high risk" really behave like high risk?

**Live dashboard:** https://thepanchanandgupta.github.io/Academics-FRA-1/

Financial Risk Analytics, Group Project 1. PGDM-2, Group 7.

An interactive risk dashboard that takes 20 NSE stocks, splits them into a high-volatility Portfolio A and a low-volatility Portfolio B (10 stocks each, ₹15 lakh each, amount editable), and asks two questions across three market eras (COVID crisis, a calm bull run, and the latest year):

1. **Test 1, the risk label.** Did "high risk" behave like high risk, and did "low risk" hold up? Measured with historical VaR, Expected Shortfall, Monte Carlo VaR, Kupiec backtests, drawdowns, correlations and stress tests.
2. **Test 2, the allocation.** If the efficient frontier is rebuilt from each era's data, aiming for the same return equal weight earns today, would the optimiser still pick 10% per stock?

## Why it matters

Risk labels such as "safe" and "aggressive" are usually set from today's data. This project checks whether a label survives a crash and whether an "optimal" mix is stable or just a product of one year's numbers. It shows why VaR alone is not enough (Expected Shortfall, drawdown and backtests), and why optimiser weights should be treated with caution (estimation error).

## Headline findings

- On bad days A lost more than B in every era (1-day Expected Shortfall at 97.5%: crisis 7.5% vs 5.5%, calm 2.9% vs 1.0%, today 3.6% vs 2.1%).
- In the COVID crash A fell 48%, the Nifty 50 38% and B 26%. Low risk meant less risky, not safe.
- Today is the exception: B's drawdown (19.3%) was deeper than A's (17.3%), and B lost money while A gained.
- An optimiser would not keep equal weights, and its picks change a lot from era to era.

## Bring your own data

Click **Upload your prices** (or drop a file anywhere on the page). The whole dashboard re-computes in your browser; nothing is uploaded.

- **Prices sheet (first sheet):** dates in column A, one stock per column, the index in any column (it is detected, or choose it).
- **Optional `Portfolios` sheet:** columns `Ticker`, `Portfolio` (A or B), `Sector`. Without it, the most volatile stocks form A and the least volatile form B.
- Formats: `.xlsx` or `.csv`. Samples are in `data/`.
- Eras, rankings, VaR, Expected Shortfall, backtests, correlations, stress tests, efficient frontiers and every worked calculation update for the new portfolios and prices.

## Features

- Locked top navigation and control bar: focus (A or B), regime (crisis, calm, today), VaR level, weight limits, amount
- Ticker tape, watchlist, Plain English mode, notes pad, text-size control
- Hover values on every chart; light and dark theme; responsive for phone, tablet and laptop
- Adjustable confidence level, investment amount and weight cap
- Calculations section with formulas, derivations and live worked numbers
- QR code that links to the deployed site (it reads the page address, so no editing is needed)

## Repository layout

| File | Purpose |
| --- | --- |
| `index.html` | The whole dashboard (single self-contained page) |
| `data/all_prices_v3.xlsx` | Daily adjusted closes, 20 stocks plus Nifty 50, Jan 2017 to Oct 2026 |
| `data/sample_with_portfolios.xlsx` | Same prices plus a `Portfolios` sheet, to show the upload format |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## Run locally

Open `index.html` in a browser. The QR code appears once the page is served over http(s), for example with `python -m http.server`.

## Team

| Roll No. | Name |
| --- | --- |
| P2511008 | Alan John Wilson |
| P2511026 | Devraj Chaudhary |
| P2511046 | Nityam Abichandani |
| P2511048 | Panchanand Gupta |
| P2512026 | Febin Francis Kavalakatt |

Educational project, not investment advice.
