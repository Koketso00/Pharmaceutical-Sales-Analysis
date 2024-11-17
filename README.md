# MarysPharmacyAnalysis
![isaac-quesada-6P3OpQDbL3Y-unsplash](https://github.com/Koketso00/MarysPharmacyAnalysis/assets/99824427/4e918f1a-0d83-4a1e-81cf-c77daf357d8b)
This repository presents an in-depth analysis of sales data from Mary's Pharmacy, a small pharmacy located in a busy city center

# Introduction

When I came across the dataset for Mary's Pharmacy, I was instantly intrigued by its extensive and intricate nature. As an individual keen on honing my expertise in data cleaning, analysis, and visualization, this dataset presents a perfect opportunity for me to immerse myself and enhance my abilities.

# Problem Statement

- Which pharmaceutical drugs consistently sell the most and the least over the past six years?
- How does the sales performance of the pharmacy evolve over time? Are there any noticeable trends or patterns?
- What is the distribution of sales across different drug categories? Which category contributes the highest share of sales?
- Are there specific months or seasons when the pharmacy experiences significant increases or decreases in sales?
- Is there a correlation between the sales of specific drugs and external factors such as advertising campaigns, promotions, or seasonal events?

# Data Sourcing

The dataset for Mary's Pharmacy consists of transactional data collected over a period of 6 years (2014-2019). It includes information on the date, time, pharmaceutical drug brand name, and quantity sold. The dataset comprises 57 drugs classified into different therapeutic categories based on the Anatomical Therapeutic Chemical (ATC) Classification System.

This dataset was sourced from the Point-of-Sale system used by the pharmacy, providing a rich source of information for analysis. The goal is to analyze the sales data of these pharmaceutical drugs and gain insights that can help improve business performance and drive growth for Mary's Pharmacy.

## 🧹 Data Cleaning and Transformation

The dataset underwent a thorough data cleaning process using **Power Query** to ensure its quality and usability. The following steps were taken:

1. **Handling Missing Values**: Removed rows with missing or null values in critical fields such as date and drug brand name.
2. **Data Type Corrections**: Ensured that columns were assigned the correct data types (e.g., date, text, integer).
3. **Standardization**: Standardized drug names to maintain consistency across the dataset.
4. **Date Extraction**: Extracted year, month, and day components for trend analysis.
5. **Classification**: Categorized drugs into their respective ATC therapeutic groups.

## 📐 Data Modeling Summary

I designed a **Star Schema** data model with **one-to-one relationships** to optimize the analysis of Mary's Pharmacy sales data. The model includes a **central Fact Table (`SalesFactTable`)** and three Dimension Tables (`DrugTable`, `DateTable`, and `TimeTable`):

- **`SalesFactTable`**: Central table containing detailed sales data, including:
  - `TransactionID`, `DrugID`, `DateID`, `TimeID`, `QuantitySold`, and `TotalSales`.

- **`DrugTable`**: Contains descriptive attributes of each drug:
  - `DrugID`, `DrugName`, `DrugCategory`.

- **`DateTable`**: Includes all date-related attributes for analysis:
  - `DateID`, `FullDate`, `Year`, `Month`, `Day`, `Quarter`, and `WeekNumber`.

- **`TimeTable`**: Contains temporal data for time-based analysis:
  - `TimeID`, `Hour`, `Minute`, and `Second`.

### 💡 Key Relationships:
- **One-to-One relationship** between `SalesFactTable` and `DrugTable` via `DrugID`.
- **One-to-One relationship** between `SalesFactTable` and `DateTable` via `DateID`.
- **One-to-One relationship** between `SalesFactTable` and `TimeTable` via `TimeID`.

### 📸 Data Model Snapshot:
![Power BI Data Model](images/Data_Modelling.png)

## 🔎 Exploratory Data Analysis (EDA)

The analysis phase involved exploring the cleaned dataset to gain insights into sales patterns. Key questions explored include:

- **Top-Selling and Least-Selling Drugs**: Identified the best and worst-performing drugs over the six-year period.
- **Sales Trends Over Time**: Analyzed sales performance by year, month, and season.
- **Category Sales Distribution**: Evaluated the contribution of each drug category to total sales.
- **Peak Sales Periods**: Determined peak sales hours and days of the week.


## Tools Used

- **Power BI**: Used for visualizing and creating interactive dashboards to analyze the sales data.
- **Power Query**: Used for data transformation and cleaning, including merging tables, filtering, and shaping data for analysis.
- **Excel**: Initially used for exploratory analysis and data validation.
- **DAX (Data Analysis Expressions)**: Utilized for creating custom calculations and measures in Power BI, such as Total Sales and Average Sales per Day.
- **Power BI Service**: Published and shared the interactive Power BI report/dashboard.


## Dashboard Visualizations

1. **Revenue Distribution by Drug Category**:
   - This pie chart shows the **revenue share** for each drug category.
   - **Key Insight**: The **N02BE/B** category generates the highest revenue, dominating sales, which should be a focus for stocking and promotions.
   
   ![Revenue Distribution by Drug Category](images/images/pie_chart.png)

2. **Sales by Drug Category**:
   - This column chart illustrates **sales performance** by drug category over time.
   - **Key Insight**: This allows for identifying strong-performing categories and those that may need further attention in marketing and stock management.
   
   ![Sales by Drug Category](images/images/column_chart.png)

3. **Hourly Sales Heatmap**:
   - The heatmap displays **sales data by hour** of the day.
   - **Key Insight**: **Afternoons and evenings** experience the highest traffic, while late hours are quieter. This is important for optimizing staffing and store hours.

   ![Hourly Sales Heatmap](images/images/heat_map.png)

4. **Average Sales Per Day of the Week**:
   - This line chart shows the **average sales per day** for each day of the week.
   - **Key Insight**: Peak sales occur on **Tuesdays, Wednesdays, and Saturdays**, while Mondays see the lowest sales.
   - **Recommendation**: Optimize staffing on peak days and consider promotions on quieter days (Monday and Thursday) to boost sales.

   ![Average Sales Per Day of the Week](images/images/line_chart.png)


5. **Percentage Change in Sales Revenue by Year**:
   - This line chart highlights **year-over-year sales growth**, showing trends from 2014 to 2019.
   - **Key Insight**: There's a noticeable **decline from 2014 to 2015**, followed by a recovery in 2018, and a decrease in 2019. Identifying the causes behind these changes is key for future planning.

   ![Percentage Change in Sales Revenue by Year](images/images/area_chart.png)

## 📊 Dashboard File

You can download the Power BI dashboard file (.pbix) using the link below:

[Download Mary's Pharmacy Sales Dashboard (.pbix)](PBI/Pharmaceutical_Sales_Dashboard.pbix)


  ## Conclusion and Insights

Based on the analysis of the various visualizations, the following insights and recommendations are made:

- **Staffing and Resource Allocation**: Adjust staffing schedules based on peak sales times (afternoons and evenings). Ensure adequate coverage during quieter periods.
- **Targeted Promotions**: Run promotions during quieter hours (late hours and Mondays/Thursdays) to increase traffic and sales.
- **Inventory Management**: Focus on stocking high-demand drugs, particularly those in the **N02BE/B** category, based on revenue and sales performance.
- **Sales Trends**: Continue to track and analyze year-over-year performance to spot further opportunities for growth or areas that need improvement.

The dashboard provides a solid foundation for data-driven decision-making to optimize operations and sales performance at Mary’s Pharmacy.

## Next Steps

1. **Implement Recommendations**: Put into practice the strategies suggested based on the dashboard insights.
2. **Monitor Results**: Continue tracking sales and operational metrics, adjusting strategies as needed.
3. **Ongoing Analysis**: Further explore data for deeper insights into drug-specific performance, seasonal trends, and potential correlations with external events or promotions. 


