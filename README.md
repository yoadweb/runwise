# Runwise

Runwise is an interactive biotech risk screener. It ranks biotech stocks by how likely they are to last, using cash runway, pipeline strength, and industry outlook.

Live site: https://runwiseequities.netlify.app/ 

## Why it exists

Small biotech companies rarely turn a profit, so common tools like P/E ratio don't work well. Runwise asks three simpler questions. How long will the cash last? How strong is the pipeline? Where is the industry heading?

## What it does

* Scores each company from 0 to 100 on financial health, pipeline and product maturity, and industry outlook
* Estimates cash runway in months from cash on hand and quarterly burn
* Lets you change the weight of each factor with sliders and watch the ranking update
* Lets you search and pick which companies to compare
* Lets you add any company by ticker, with a live lookup that fills in cash, burn, and capex from the latest SEC filing
* Includes a capex section and a deep dive for each built in company: cash, next milestones, and key risks
* Explains how research clinics and investors judge the same biotech differently

Built in companies: Nautilus Biotechnology, Quantum-Si, Recursion, and Beam Therapeutics, using Q2 2026 SEC filings.

## How the score works

* Financial health: runway in months divided by 36, capped at 100
* Pipeline and product maturity: lead stage (50%), number of programs (20%), team and platform rating (30%)
* Industry outlook: a 1 to 10 judgment, times 10

The final score is a weighted average. Higher means lower risk. Stage, program count, team rating, and industry outlook are judgment calls, not reported facts.

## Live lookup

The lookup runs as a Netlify function in `netlify/functions/lookup.js`. It pulls filing data from SEC EDGAR and a delayed price from Stooq.


## Limits

* Runway ignores new fundraising, partner payments, and dilution
* Filings label cash and investments differently, so some lookups will miss a line and need manual entry
* Prices are delayed and come from a free source that can go down
* Only four companies are built in

## About

Built by Alsadig Bashir, Purdue University.

X: https://x.com/alsabbbb
Substack: https://substack.com/@alsab

Runwise is a student research project, not investment advice.
