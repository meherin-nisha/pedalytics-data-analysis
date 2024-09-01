# Pedalytics: Bike Share Data Analysis Dashboard

![pedalytics](https://github.com/user-attachments/assets/e78bf303-557c-43ed-9f97-3a5034758062)

## Overview

**Pedalytics** is a comprehensive data analysis project focused on analyzing bike-sharing data across different periods and demographics. The dashboard is built using Power BI and SQL Server Management Studio, providing deep insights into key performance indicators such as revenue, profit margins, rider demographics, and seasonal trends. This project showcases how data can be leveraged to make informed decisions in the bike-sharing industry.

## Key Features

- **Yearly Revenue and Profit Analysis**: The dashboard highlights the total revenue of **$15.19M** and a profit of **$10.45M** for the selected year, offering a clear view of the financial performance of the bike share service.
- **Profit Margin**: A profit margin of **0.45** is reported, reflecting the service's profitability and aiding in financial analysis.
- **Rider Analysis**: The data reveals that there were **3M riders**, with **81.17%** being registered users and **18.83%** casual riders, providing valuable insights into user behavior and demographics.
- **KPI Over Time**: The dashboard includes a detailed visualization tracking the sum of riders, average revenue, and average profit over time, enabling trend analysis.
- **Hourly Sales Data**: The analysis shows peak earnings during midday and early evening, particularly between **10:00 AM and 3:00 PM**, with Wednesdays and Fridays emerging as the most profitable days of the week.
- **Revenue by Season**: The project breaks down revenue by season, showcasing how profitability varies throughout the year, helping to identify seasonal trends.

## Data Sources

The analysis is based on data from three primary sources:

1. **`bike_share_yr_0.csv`**: Contains bike-sharing data for the first year.
2. **`bike_share_yr_1.csv`**: Contains bike-sharing data for the second year.
3. **`cost_table.csv`**: Provides cost of goods sold (COGS) and other financial metrics necessary for calculating revenue and profit.

## SQL Data Manipulation

Data from these sources were merged and manipulated using SQL Server Management Studio (SSMS). Key SQL operations performed include:

- **Merging Datasets**: The `bike_share_yr_0` and `bike_share_yr_1` datasets were combined using a `UNION` operation to create a comprehensive dataset covering both years.
- **Data Calculation**: Revenue and profit were calculated by multiplying the number of riders by the price and subtracting the cost of goods sold (COGS) from the resulting revenue.

## Dashboard Visualization

The data was visualized in Power BI to create an interactive dashboard that allows users to explore various metrics and trends in the bike-sharing data. The dashboard includes:

- **Yearly and Seasonal Revenue/Profit Analysis**
- **Rider Demographics and Behavior**
- **Hourly Sales and Profit Trends**
- **Seasonal Revenue Analysis**

These visualizations help stakeholders make data-driven decisions to optimize operations, improve user experience, and maximize profitability.

## Conclusion

**Pedalytics** provides a detailed and actionable analysis of bike-sharing data, offering valuable insights into financial performance, user behavior, and seasonal trends. This project demonstrates the power of combining SQL data manipulation with advanced visualization tools like Power BI to drive business insights and decision-making.

## How to Use

1. **Data Preparation**: Ensure that the datasets (`bike_share_yr_0.csv`, `bike_share_yr_1.csv`, and `cost_table.csv`) are loaded into your SQL Server.
2. **Run SQL Queries**: Use the provided SQL queries to merge and calculate necessary metrics.
3. **Load Data into Power BI**: Import the resulting data into Power BI for visualization.
4. **Explore the Dashboard**: Interact with the dashboard to explore various metrics and gain insights into the bike-sharing service.

