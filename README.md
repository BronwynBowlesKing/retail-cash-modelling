# Retail Cash Cycle Monte Carlo Simulation

## Overview
This Jupyter notebook implements a Monte Carlo simulation to model daily cash flows through tills in large South African supermarkets. It estimates key metrics like cash inflows, cashback withdrawals, change given, net till cash, CIT uplifts, and till floats across Conservative, Moderate, and Optimistic scenarios.

The model uses hybrid statistical methods to account for data uncertainty from sources like SARB, BankservAfrica, and retailer reports, predicting national daily volumes (e.g., R741M cash inflow in the Moderate case). 

## Key Features
- **Scenarios**: Conservative (low volumes), Moderate (baseline), Optimistic (high adoption).
- **Stochastic Simulation**: 10,000 runs with normal distributions for transaction values (mean R212), cash shares (56%), cashback (11%), etc.
- **Outputs**: Summary statistics (mean, SD, percentiles), full simulation DataFrame, CSV export.
- **Validation**: Benchmarked against international retail cash practices and SA payment data.
  
## Model Inputs
| Parameter | Conservative | Moderate | Optimistic | Source |
|-----------|--------------|----------|------------|--------|
| Avg Cash Transaction (ZAR) | 180 | 212 | 250 | SARB/BankservAfrica |
| Cash Share of Transactions | 0.50 | 0.56 | 0.65 | SARB Payments Study |
| Till Float per Lane (ZAR) | 300 | 500 | 800 | International benchmarks |
| CIT Pickup Frequency (per week) | 7 | 3 | 2 | SA retail practices  |
| Cashback Penetration | 0.05 | 0.11 | 0.20 | Standard Bank data  |

## Outputs (Moderate Scenario Example)
| Metric | Mean (ZAR) | Std Dev (ZAR) | 5th-95th Percentile Range (ZAR) |
|--------|------------|---------------|--------------------------------|
| Daily Cash Inflow | 741M | 74M | 619M - 864M  |
| Daily Cashback | 82M | 18M | 53M - 113M  |
| Daily Change Given | 185M | 19M | 155M - 216M  |
| Net Cash in Tills | 474M | 51M | 393M - 559M  |
| CIT Uplift per Pickup | 158M | 17M | 131M - 186M  |
| Till Float per Lane | 500 | 75 | 379 - 623   |

## Background
Analyses the South African retail cash cycle, considering high cash preference (56% transactions), cashback growth, and CIT logistics. Supports cash management strategy for supermarkets like Shoprite (R215B turnover). 

The purpose of this project was to simulate daily cash flow patterns through tills in large South African supermarkets. It is part of a hybrid statistical model created to understand and estimate cash volumes. Limits on data available and uncertainty around those variables are taken into account. Part A estimates the cash cycle, and Part B is a literature review presenting the data considered in the model.

The Python program accommodates three possible scenarios - Conservative, Moderate and Optimistic - each with different input variables. The model covers daily cash inflow, cashback, and change given; till float per lane; net cash in tills; and CIT uplift per pickup. The data is consolidated into an analytical framework covering market structure, payment patterns, cash circulation, demographics, and operational metrics for the South African supermarket sector. National payment patterns, volume proxies, cash access and recycling are taken into account.
