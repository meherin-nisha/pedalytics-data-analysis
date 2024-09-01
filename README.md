
# Pedalytics: Bike Share Data Analysis Dashboard
![pedalytics](https://github.com/user-attachments/assets/e78bf303-557c-43ed-9f97-3a5034758062)


Overview

Pedalytics is a comprehensive data analysis project focused on analyzing bike-sharing data across different periods and demographics. The dashboard is built using Power BI and SQL Server Management Studio, and it provides insights into revenue, profit margins, rider demographics, and seasonal trends.

Key Features

Yearly Revenue and Profit Analysis: The dashboard highlights the total revenue of $15.19M and a profit of $10.45M for the selected year.
Profit Margin: The project reports a profit margin of 0.45, giving insights into the profitability of the bike share service.
Rider Analysis: The data reveals that there were 3M riders, with 81.17% being registered users and 18.83% casual riders.
KPI Over Time: A detailed visualization tracks the sum of riders, average revenue, and average profit over time.
Hourly Sales Data: The analysis shows peak earnings during midday and early evening, particularly between 10:00 AM and 3:00 PM, with Wednesdays and Fridays being the most profitable days.
Revenue by Season: The project breaks down revenue by season, showcasing the differences in profitability across different times of the year.
Data Sources

The data used for this analysis is sourced from two primary datasets:

bike_share_yr_0.csv
bike_share_yr_1.csv
Additionally, a cost_table.csv file was used to calculate COGS and other financial metrics.

SQL Data Manipulation

Data was merged and manipulated using SQL Server Management Studio. Key SQL operations included:

Merging Datasets: The bike_share_yr_0 and bike_share_yr_1 datasets were combined using a UNION operation.
Data Calculation: Revenue and profit were calculated using SQL queries by multiplying the number of riders by the price and subtracting COGS.
Example SQL Query:

sql
Copy code
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
Tools Used

SQL Server Management Studio: For data manipulation and calculations.
Power BI: For creating the dashboard and visualizations.
Python/Excel: For additional data processing (if applicable).
How to Use

Clone the Repository:
bash
Copy code
git clone https://github.com/yourusername/Pedalytics.git
Open the Power BI File:
Open Rider_Data_Analysis.pbix in Power BI Desktop to explore the dashboard.
Run SQL Queries:
Use the provided SQL queries to manipulate and explore the data in SQL Server Management Studio.
Conclusion

The Pedalytics project provides deep insights into bike-sharing trends, highlighting key metrics such as revenue, profit, and rider demographics. The analysis reveals significant patterns, such as peak riding hours and the profitability of different days of the week, which can be leveraged for strategic decision-making.
