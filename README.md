# Gett: Insights from Failed Orders (Root Cause Analysis)

## Overview
Gett (formerly GetTaxi) is a corporate Ground Transportation Management platform. This project analyzes system and user metrics to diagnose the root causes of "failed orders"—rides where the client clicked "Order" but ultimately did not get a car due to a user cancellation or a system rejection.

## Tech Stack
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Visualization:** Matplotlib

## Methodology
1. **Data Merging & Cleaning:** Merged order logs (`data_orders.csv`) with driver offer logs (`data_offers.csv`), standardizing categorical variables and extracting time-series elements.
2. **Behavioral Analysis:** Mapped cancellation distributions across the 24-hour cycle to identify peak failure hours and categorized them by "Driver Assigned" vs. "No Driver Assigned".
3. **Wait Time Tolerance Analysis:** Calculated the exact seconds elapsed before a user cancels, segmenting by system status to quantify human patience thresholds.

## Key Insights
* **The "2.5x" Patience Threshold:** Identified distinct user churn patterns, revealing that customers tolerate a **2.5x longer wait time** (averaging 276 seconds vs. 115 seconds) before cancelling *if* a driver has already been assigned. 
* **Rush Hour Bottlenecks:** System rejections and cancellations peak sharply at **8:00 AM**, indicating a massive supply-demand imbalance during morning commutes.
* **ETA Correlation:** Proved a direct relationship between high Estimated Times of Arrival (ETAs) and instant pre-assignment cancellations.

## How to Run
1. Clone the repository.
2. Ensure `data_offers.csv` and `data_orders.csv` are located in the root directory
3. Run the Jupyter Notebook to view the analysis 
