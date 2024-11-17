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

## 🔎 Exploratory Data Analysis (EDA)

The analysis phase involved exploring the cleaned dataset to gain insights into sales patterns. Key questions explored include:

- **Top-Selling and Least-Selling Drugs**: Identified the best and worst-performing drugs over the six-year period.
- **Sales Trends Over Time**: Analyzed sales performance by year, month, and season.
- **Category Sales Distribution**: Evaluated the contribution of each drug category to total sales.
- **Peak Sales Periods**: Determined peak sales hours and days of the week.

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

   ![Average Sales Per Day of the Week](images/images/linechart.png)


5. **Percentage Change in Sales Revenue by Year**:
   - This line chart highlights **year-over-year sales growth**, showing trends from 2014 to 2019.
   - **Key Insight**: There's a noticeable **decline from 2014 to 2015**, followed by a recovery in 2018, and a decrease in 2019. Identifying the causes behind these changes is key for future planning.

   ![Percentage Change in Sales Revenue by Year](images/images/area_chart.png)


