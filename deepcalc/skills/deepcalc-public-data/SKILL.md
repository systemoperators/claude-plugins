---
name: deepcalc-public-data
description: "Answer from Deepcalc's public datasets with no sign-in: World Bank indicators, countries, currencies, US states, US sales tax, the US federal income tax brackets and EU VAT rates, each number with its source."
---

# Answer from Deepcalc's public data

Use the public datasets when the person asks for a country's numbers, a currency, a US state's facts, a sales tax rate, an income tax bracket or a VAT rate. They need no sign-in and no workbook of the person's own.

## Find the dataset

search_datasets finds a dataset by topic in the person's words (GDP of Poland, sales tax in Ohio, VAT in Germany). get_entity gives one country, currency or US state with its latest numbers in one call; use it before reading ranges for a single country or state.

The datasets are named like workbooks: worldbank/gdp, worldbank/population, data/us-sales-tax, data/us-sales-tax-thresholds, data/us-federal-income-tax, data/eu-vat-rates, data/vat-registration-rules. read_workbook gives a dataset's worksheets and its README (where the numbers come from, how often they are refreshed and the license); read_range reads the cells you need.

## Say where each number comes from

Give every number with its dataset's address at deepcalc.com and the source the README names (the World Bank, a state's own rate file, the European Commission). Say the year or the date a rate took effect. A sales tax rate depends on the address: a state, county or ZIP rate is where the person can start, and the street address decides. Keep every decimal the source publishes (New Mexico's 8.1875%, never 8.19%).

When a dataset does not hold what was asked, say so and name what it does hold; never fill a gap from memory.

## What this is not

These are reference numbers, not tax advice. Filing, registering and paying are the person's own steps; say so when the question is about what they owe.
