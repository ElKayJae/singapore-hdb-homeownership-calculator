# Singapore HDB Homeownership Calculator: Model Notes

**Research snapshot:** 11 October 2026

This guide describes the public-data sources and illustrative defaults used by the calculator. The defaults are a sample scenario, not a representation of any individual: S$100,000 starting cash, S$100,000 starting CPF OA, S$7,999 monthly Ordinary Wages, and the CPF age band above 35 to 45. Change the assumptions in the calculator to explore other cases.

This is a planning model, not an HDB loan assessment, valuation, tax opinion, or investment forecast. Eligibility, financing, CPF use, and grants depend on the applicant and the specific flat. Verify current rules with HDB, CPF Board, and IRAS before making a decision.

## Eligibility context

Eligible single Singapore Citizens aged 35 or above may apply for a 2-room Flexi flat from HDB or buy a resale flat, subject to the applicable scheme conditions. HDB's current monthly household income ceiling for eligible singles purchasing a 99-year 2-room Flexi flat or obtaining an HDB housing loan is S$8,000. The S$7,999 calculator default is a near-ceiling benchmark; it does not establish eligibility. A valid HFE assessment and all other eligibility conditions still apply.

For resale purchases, the calculator includes an assumed Singles Grant for eligible cases. The actual amount and eligibility depend on the applicant's circumstances. Enhanced CPF Housing Grant eligibility has a lower income ceiling for a single applicant, and proximity grants have separate conditions. None of these assumptions is an approval or entitlement.

Official guidance: [HDB singles eligibility](https://www.hdb.gov.sg/buying-a-flat/flat-grant-and-loan-eligibility/singles), [2026 income-ceiling change](https://www.hdb.gov.sg/hdb-pulse/news/2026/increase-in-income-ceilings-and-greater-support-for-families-with-children), [Singles Grant](https://www.hdb.gov.sg/buying-a-flat/flat-grant-and-loan-eligibility/singles/cpf-housing-grant), [EHG for singles](https://www.hdb.gov.sg/buying-a-flat/flat-grant-and-loan-eligibility/singles/enhanced-cpf-housing-grant), and [PHG for singles](https://www.hdb.gov.sg/buying-a-flat/flat-grant-and-loan-eligibility/singles/proximity-housing-grant).

## Public resale data and sample prices

The resale scenarios use rounded 75th-percentile prices from HDB transactions registered between October 2025 and September 2026, filtered to flats with 80 to under 100 years remaining at resale application. These all-town figures are not estimates for a particular MRT station, block, or flat condition.

| Flat type | Transactions in lease band | 25th–75th percentile price | Median price | Sample P75 price |
|---|---:|---:|---:|---:|
| 3-room | 1,519 | S$515,000–695,000 | S$559,000 | S$695,000 |
| 4-room | 4,594 | S$640,000–860,000 | S$708,000 | S$860,000 |
| 5-room | 1,681 | S$770,000–960,000 | S$840,000 | S$960,000 |

Source: [HDB resale flat prices dataset on data.gov.sg](https://data.gov.sg/datasets/d_8b84c4ee58e3cfc0ece0d773c8ca6abc/view), retrieved 11 October 2026. The dataset contains public transaction records and notes that resale prices are indicative because prices depend on many factors. The 2-room BTO price of S$300,000 is an editable illustration, not a quoted or current price for a specific project.

## How the main outputs are modeled

- **Loan and instalment:** the modeled loan is the lower of price times the selected LTV and the loan supported by the income-based monthly payment limit at the assessment rate. Monthly instalments use the standard amortization formula and the selected term and rate. HFE may assess a lower amount.
- **Upfront funds:** purchase price minus modeled loan and assumed grant, plus residential Buyer’s Stamp Duty. Legal fees, valuation shortfall/COV, renovation, furnishing, and moving costs are excluded.
- **Funding sources:** use starting OA above the selected buffer first, then cash. Any remaining amount is shown as a funding gap. This is a simplified source order, not a CPF withdrawal approval or payment schedule.
- **Rent:** tenant count times gross rent per room, reduced by the selected vacancy/upkeep reserve. Rent is not guaranteed and is not counted toward loan eligibility.
- **Cash flow:** the model shows both mortgage less reserve-adjusted rent and cash available after modeled OA mortgage withdrawals. These are separate measures. BTO wait-period housing costs can be entered separately.
- **Home equity:** projected property value less remaining modeled mortgage. It excludes selling costs, renovation, CPF refunds, rent, and other assets or debts. Price growth is a sensitivity, not a forecast.
- **Opportunity cost:** cash investment and monthly cash-flow alternatives are shown separately from property equity. They should not be added as extra losses to home equity.

## CPF OA contribution estimate

The calculator derives its monthly OA contribution estimate from the monthly wage input and selected CPF age band; it is no longer an independent editable amount. The default assumes a Singapore Citizen or a third-year-or-later Singapore Permanent Resident on full contribution rates, with salary treated entirely as Ordinary Wages. The 2026 Ordinary Wage ceiling is S$8,000 per month. Additional Wages, first/second-year PR graduated rates, and other special contribution arrangements are excluded.

The model estimates total CPF contributions using the 2026 age-based rates and allocates the OA share using CPF Board's 2026 allocation ratios. For the sample age band above 35 to 45, the total rate is 37% and the OA allocation ratio is 56.77% of contributions. At S$7,999 monthly Ordinary Wages, the estimated OA contribution is about S$1,680 per month after whole-dollar rounding. This is an estimate; use the official [CPF contribution calculator](https://www.cpf.gov.sg/member/tools-and-services/calculators/cpf-contribution-calculator) for an individual's exact contribution.

Sources: [CPF contribution rates from January 2026](https://www.cpf.gov.sg/content/dam/web/employer/employer-obligations/documents/CPFcontributionratesfrom1Jan2026.pdf), [CPF allocation rates from January 2026](https://www.cpf.gov.sg/content/dam/web/employer/employer-obligations/documents/CPFAllocationRatesfromJanuary2026.pdf), and [Ordinary Wage ceiling](https://www.cpf.gov.sg/service/article/what-is-the-ordinary-wage-ow-ceiling-mbr).

The OA simulation adds the estimated monthly contribution, models mortgage payments from OA above the chosen buffer, and applies the selected base interest monthly. It does not model CPF extra interest, staged BTO payments, changes in wage or age during the horizon, CPF housing-use limits, or exact CPF Board posting and rounding in every case.

## Timing, rental, and resale considerations

Standard resale flats are generally subject to a five-year MOP; Standard BTO flats have an MOP after key collection, and Plus/Prime flats generally have a ten-year MOP. The calculator adds the selected BTO wait to its MOP for an illustrative earliest-sale timeline. Actual sale eligibility depends on the flat classification and prevailing HDB conditions.

Renting bedrooms is subject to HDB eligibility, registration, and occupancy requirements. The model's tenant counts and rents are sensitivities only. Carry the mortgage during vacancies and account for utilities, furnishing, tax, repairs, turnover, and the lifestyle impact of sharing the flat.

HDB resale prices and the Resale Price Index describe past market activity; they do not predict an individual flat's future value. A complete net-worth comparison would align the purchase and sale dates and include cash, CPF balances and refunds, property value, outstanding loans, living costs, transaction costs, and other assets and debts.

Further references: [HDB resale statistics](https://www.hdb.gov.sg/managing-my-home/selling-a-flat/process-for-selling-a-flat/resale-flat-planning/resale-statistics), [HDB sale eligibility](https://www.hdb.gov.sg/managing-my-home/selling-a-flat/eligibility), [HDB bedroom rental eligibility](https://www.hdb.gov.sg/managing-my-home/home-ownership/renting-out-a-flat-or-bedrooms/renting-out-bedrooms/eligibility), and [IRAS guidance on gains from property sales](https://www.iras.gov.sg/taxes/individual-income-tax/basics-of-individual-income-tax/what-is-taxable-what-is-not/gains-from-sale-of-property-shares-and-financial-instruments).
