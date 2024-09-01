
# Pedalytics: Bike Share Data Analysis Dashboard
![pedalytics](https://github.com/user-attachments/assets/e78bf303-557c-43ed-9f97-3a5034758062)

## Overview

**Pedalytics** is a comprehensive data analysis project focused on analyzing bike-sharing data across different periods and demographics. The dashboard is built using Power BI and SQL Server Management Studio, providing insights into revenue, profit margins, rider demographics, and seasonal trends.

## Key Features

- **Yearly Revenue and Profit Analysis**: The dashboard highlights the total revenue of **$15.19M** and a profit of **$10.45M** for the selected year.
- **Profit Margin**: The project reports a profit margin of **0.45**, giving insights into the profitability of the bike share service.
- **Rider Analysis**: The data reveals that there were **3M riders**, with **81.17%** being registered users and **18.83%** casual riders.
- **KPI Over Time**: A detailed visualization tracks the sum of riders, average revenue, and average profit over time.
- **Hourly Sales Data**: The analysis shows peak earnings during midday and early evening, particularly between **10:00 AM and 3:00 PM**, with Wednesdays and Fridays being the most profitable days.
- **Revenue by Season**: The project breaks down revenue by season, showcasing the differences in profitability across different times of the year.

## Data Sources

The data used for this analysis is sourced from two primary datasets:

1. `bike_share_yr_0.csv`
2. `bike_share_yr_1.csv`

Additionally, a `cost_table.csv` file was used to calculate COGS and other financial metrics.

## SQL Data Manipulation

Data was merged and manipulated using SQL Server Management Studio. Key SQL operations included:

- **Merging Datasets**: The `bike_share_yr_0` and `bike_share_yr_1` datasets were combined using a UNION operation.
- **Data Calculation**: Revenue and profit were calculated using SQL queries by multiplying the number of riders by the price and subtracting COGS.

Example SQL Query:

```sql
WITH cte AS (
    SELECT * FROM bike_share_yr_0 
    UNION ALL
    SELECT * FROM bike_share_yr_1
)
SELECT 
    dteday,
    season,
    a.yr,
    weekday,
    hr,
    rider_type,
    riders,
    price,
    COGS,
    riders * price AS revenue,
    riders * price - COGS AS profit
FROM cte a
LEFT JOIN cost_table b ON a.yr = b.yr;
