# Pharmaceutical Sales Analysis
![isaac-quesada-6P3OpQDbL3Y-unsplash](https://github.com/Koketso00/MarysPharmacyAnalysis/assets/99824427/4e918f1a-0d83-4a1e-81cf-c77daf357d8b)
This repository showcases a comprehensive analysis of sales data from a Pharmaceutical company.Through this project, I applied my skills in data transformation, data modeling, and visualization using **Power BI** and **Power Query**, focusing on the ETL process to derive meaningful business insights.

## 📋 Table of Contents

- [Introduction](#introduction)
- [Problem Statement](#problem-statement)
- [Data Sourcing](#data-sourcing)
- [Data Transformation (ETL Process)](#data-transformation-etl-process)
- [Data Model Design](#data-model-design)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Tools Used](#tools-used)
- [Dashboard Visualizations](#dashboard-visualizations)
- [Dashboard File](#dashboard-file)
- [Conclusion and Insights](#conclusion-and-insights)
- [Next Steps](#next-steps)


# Introduction

When I came across the dataset for Pharmaceutical Sales Data, I was instantly intrigued by its extensive and intricate nature. As an individual keen on honing my expertise in data cleaning, analysis, and visualization, this dataset presents a perfect opportunity for me to immerse myself and enhance my abilities.

# Problem Statement

- Which pharmaceutical drugs consistently sell the most and the least over the past six years?
- How does the sales performance of the pharmacy evolve over time? Are there any noticeable trends or patterns?
- What is the distribution of sales across different drug categories? Which category contributes the highest share of sales?
- Are there specific months or seasons when the pharmacy experiences significant increases or decreases in sales?
- Is there a correlation between the sales of specific drugs and external factors such as advertising campaigns, promotions, or seasonal events?

# Data Sourcing

The dataset consists of pharmaceutical transactional data collected over a period of 6 years (2014-2019). It includes information on the date, time, pharmaceutical drug brand name, and quantity sold. The dataset comprises 57 drugs classified into different therapeutic categories based on the Anatomical Therapeutic Chemical (ATC) Classification System.

This dataset was sourced from the Point-of-Sale system used by the pharmacy, providing a rich source of information for analysis. The goal is to analyze the sales data of these pharmaceutical drugs and gain insights that can help improve business performance and drive growth for the Pharmacy.

##  Data Transformation (ETL Process)

The data transformation process focused on ensuring high data quality before analysis. Using **Power Query**, I performed the following ETL tasks:

### Extract
- Loaded raw transactional data directly from the pharmacy's Point-of-Sale system into Power BI.

### Transform
- **Data Cleaning**:
  - Removed records with missing or null values in critical fields (e.g., date, drug name).
  - Corrected data types for accurate analysis (e.g., date, text, integer).
  - Standardized drug brand names for consistency.
- **Feature Engineering**:
  - Extracted key date components (year, month, day) to enable trend analysis.
  - Created new calculated columns such as `TotalSalesRevenue` and `TimeOfDay` for more granular analysis.
- **Categorization**:
  - Mapped drugs into their respective ATC therapeutic categories for enhanced analysis.

### Load
- Loaded the cleaned and transformed dataset into Power BI for visualization and further analysis.

## Data Model Design

### Overview

The data model for this project is based on a **Star Schema**, which is a common design pattern in data warehousing that simplifies querying and analysis. The model consists of a **Fact Table** and several **Dimension Tables** that provide context to the transactional data. Below is a brief description of the tables and their relationships:

### Tables

- **Fact Table**: 
  - This table contains the main transactional data, specifically sales information. 
  - It includes fields such as:
    - `QuantitySold`: The amount of drugs sold in each transaction.
    - `TotalSalesRevenue`: The total revenue generated from the sale.
    - `DrugID`: The unique identifier for each drug.
    - `RealDate`: The date the transaction occurred.
    - `Hour`: The specific hour the transaction took place.

- **Dimension Tables**:
  - **Drug Table**: 
    - This table contains detailed information about each drug, including:
      - `DrugID`: Unique identifier for the drug.
      - `DrugCategory`: The category the drug belongs to (e.g., painkillers, antibiotics).
      - `DrugDescription`: A description of the drug.
  - **Time Table**: 
    - Contains time-related data, such as:
      - `Hour`: The specific hour the sale occurred.
      - `TimeOfDay`: This helps to categorize sales by time.
  - **Real Date Table**: 
    - Contains detailed date-related information to facilitate time-based analysis:
      - `Day`: The day of the transaction.
      - `Month`: The month in which the sale occurred.
      - `Year`: The year of the sale.
      - `Season`: The season in which the sale took place.

### Key Relationships

- **Drug Table ↔ Fact Table**: 
  - The two tables are linked by `DrugID` in a **One-to-Many** relationship. This allows the Fact Table to reference detailed information about each drug from the Drug Table.
  
- **Fact Table ↔ Real Date Table**: 
  - The Fact Table and Real Date Table are connected by `RealDate` in a **One-to-One** relationship. Each record in the Fact Table refers to a specific date in the Real Date Table.

- **Fact Table ↔ Time Table**: 
  - The Fact Table and Time Table are connected by `Hour` in a **One-to-Many** relationship. Each sale is associated with a specific time slot of the day from the Time Table.

### Benefits of This Data Model

This design allows for efficient querying and analysis of the sales data. By leveraging these relationships, you can easily analyze the data by:
- Drug categories and descriptions
- Sales over different times of the day
- Trends across various time periods (day, month, year)
- Seasonal and time-based patterns

The Star Schema design is optimized for reporting and analytics in tools like Power BI, enabling deep insights into Mary's Pharmacy sales data.

### 📸 Data Model Snapshot:
![Power BI Data Model](images/images/Data_Model.png)

##  Exploratory Data Analysis (EDA)

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

##  Dashboard File

You can download the Power BI dashboard file (.pbix) using the link below:

[Download Pharmaceutical Sales Dashboard (.pbix)](PBI/Pharmaceutical_Sales_Dashboard.pbix)


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


