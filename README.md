# Retail Data Analytics

This project analyzes Retail Weekly-Sales using Microsoft Excel. It features interactive dashboard, Weekly-Sales Trend Analysis, performance of Stores & Departments and critic score evaluations. Data was cleaned and visualized using Pivot Tables, Charts, Slicers, and Conditional Formatting with custom hyperlinks for easy navigation.

![image alt](https://github.com/Aashriya11/Retail-Data-Analytics/blob/01e5bcbfc1757bd93940f2a578b02211323aa7df/Dashboard.PNG)

---

## 1. Introduction

This project showcases a Microsoft Excel-created Retail Weekly Sales dashboard that is both interactive and visually appealing. The dataset contains historical sales data for 45 stores located in different regions - each store contains a number of departments.

The core objective of this project is to analyze and interpret sales patterns from 2010 to 2012, offering a comprehensive view of how store performance, seasonality, holidays, and economic indicators (like fuel price and temperature) impact weekly retail sales. In addition to showcasing the Weekly Sales Trend Analysis, the dashboard makes navigation easy and intuitive by letting users interact with data using slicers, filters, and hyperlinks.

This project is a perfect example of how Excel—when used skillfully—can serve as a full-fledged analytics platform for business intelligence, even without the need for advanced tools or coding. To add functionality and depth, advanced Excel features like power query, pivot tables, dynamic charts and conditional formatting are used. These tools allow users to examine various scenarios and obtain useful insights.

---

## 2. Source of Dataset

The datasets was sourced from:
[https://www.kaggle.com/datasets/manjeetsingh/retaildataset/code](https://www.kaggle.com/datasets/manjeetsingh/retaildataset/data)

---

## 3. Data Pre-Processing Process

The data preparation phase was crucial to ensure accuracy, consistency, and usability of the dataset for analytical insights. All transformations were performed using Power Query Editor in Microsoft Excel, which allowed for robust data cleaning and automation.

### 1. Power Query Steps and Transformations:

#### - Importing Data from Folder

* Used Power Query to extract datasets from a folder containing CSV/Excel files.
* Ensured dynamic loading of data to allow updates whenever the source files are changed.

#### - Changing Data Types Using Locale

* Changed the Date column data type from Text to Date using the Locale function, selecting English (United Kingdom) to ensure correct date formatting.
* Converted Weekly\_Sales column to Currency format for financial accuracy.

#### - Feature Engineering with Add Column

Inserted new columns to support time-based analysis:

* Month Name (e.g., January, February)
* Year (extracted from date)
* Week of Month (to group weekly data within a month)

#### - Categorical Labeling

Transformed the binary IsHoliday column:

* Replaced TRUE with "Holiday"
* Replaced FALSE with "Regular Day"

#### - Data Cleaning: Removing Irrelevant Columns

* Removed markdown or metadata columns not relevant to the analysis (e.g., placeholder or unused columns), ensuring a clean feature set.

### 2. Custom Queries Created

To organize the analysis effectively, the following three query tables were created:

* **Weekly Sales Summary**: Aggregates weekly sales at the store and department level to analyze trends over time.
* **Correlation Table 1**: Prepared for examining the relationship between Average Weekly\_Sales and external factors like CPI, and Unemployment.
* **Correlation Table 2**: A secondary correlation table for segmented comparison Average Fuel Price and Temperature.

---

## 4. Analysis on Data

### 1. Weekly Sales-Trend Analysis

**Introduction**: The objective is to track how retail sales fluctuate over time.

**Tools & Functions Used**:

* Pivot Table: To group and summarize weekly sales data by Month
* Slicer: To filter by Year, Store, Department, IsHoliday, Date Timeline
* Charts: Line Chart to track the sales trend across all three years (2010, 2011 & 2012)

**Results**:

| Year | Highest Month               | Lowest Month                 |
| ---- | --------------------------- | ---------------------------- |
| 2010 | December - \$288,760,532.72 | September - \$177,267,896.37 |
| 2011 | December - \$288,078,102.48 | January - \$163,703,966.83   |
| 2012 | June - \$240,610,329.29     | January - \$168,894,471.66   |

* December consistently emerged as the peak month for sales in 2010 and 2011, likely due to the holiday season.
* January showed the lowest sales in 2011 and 2012, indicating a post-holiday slump in consumer spending.

| Year | Holiday (Highest / Lowest Month) | Regular Day (Highest / Lowest Month) |
| ---- | -------------------------------- | ------------------------------------ |
| 2010 | November / December              | December / September                 |
| 2011 | November / December              | December / February                  |
| 2012 | February / September             | June / September                     |

* Holiday Sales Peaks often occurred in November, signaling strong performance during Thanksgiving and early holiday shopping.
* Regular Days performed best in December, showing consistent year-end consumer activity.
* September frequently recorded the lowest sales across both holiday and regular periods.

---

### 2. Top-Performing Stores & Departments

**Introduction**: Rank stores/departments based on weekly sales performance across different years and store sizes.

**Tools & Functions Used**:

* Pivot Table: To total Weekly Sales grouped by Store and Department
* Slicer: To filter by Store Size, Store Type and Year
* Charts: Bar Charts were created to visualize:

  * Top 5 Performing Stores
  * Top 5 Performing Departments
  * Bottom 5 Performing Departments

**Results**:

**Overall Top & Bottom Performers**

* Top 5 performing Stores: 20, 4, 14, 13, 2
* Top 5 performing Departments: 92, 95, 38, 72, 65
* Bottom 5 performing Departments: 47, 43, 78, 39, 51

**Performance Breakdown by Year**

| Year | Top Stores       | Top Departments    | Bottom Departments |
| ---- | ---------------- | ------------------ | ------------------ |
| 2010 | 14, 20, 2, 4, 10 | 92, 95, 38, 72, 65 | 47, 43, 99, 39, 77 |
| 2011 | 4, 20, 14, 13, 2 | 92, 95, 38, 72, 90 | 47, 39, 43, 78, 51 |
| 2012 | 4, 20, 13, 2, 14 | 92, 95, 38, 65, 90 | 43, 51, 78, 47, 39 |

* Store #20 consistently leads as the top-performing store, showing strong sales across all three years.
* Department #92 ranks highest in overall sales performance, indicating a high-value category.
* Departments #47 & #43 have shown consistently poor performance and need critical business attention.
  Notably, Department #47 had a negative weekly sales value of \$7.68, an alarming issue despite partial recovery in 2012.

**Performance by Store Size**

| Size | Top Stores         | Top Departments    | Bottom Departments |
| ---- | ------------------ | ------------------ | ------------------ |
| A    | 20, 4, 14, 13, 2   | 92, 95, 90, 38, 72 | 43, 47, 78, 39, 45 |
| B    | 10, 23, 18, 22, 12 | 38, 72, 2, 40, 95  | 47, 43, 78, 51, 45 |
| C    | 43, 42, 37, 30, 38 | 92, 38, 95, 90, 94 | 71, 19, 44, 55, 33 |

* Store Size A (large-sized stores) dominates with Store #20 and Department #92 as top contributors.
* Store Size C (small stores) shows good departmental performance from Dept #92 and #38 despite lower overall sales volume.

---

### 3. Total Weekly\_Sales by Week of Month

**Introduction**: The objective of this analysis is to track how retail sales fluctuate within the weeks of each month.

**Tools & Functions Used**:

* Pivot Table: Grouped and summarized Weekly\_Sales by Week of Month across different years
* Slicer: To filter by Year
* Charts:

  * Line Chart (Left): Shows overall trend of sales across Weeks 1 to 5, combining all years.
  * Clustered Column Chart (Right): Compares weekly sales side-by-side for 2010, 2011, and 2012.

**Results**:

**Line Chart Insights (All Years Combined)**

* Week 2 and Week 4 recorded the highest total weekly sales, peaking around \$1.5–1.6 billion.
* A significant drop in sales is observed in Week 5, indicating a shorter or less active retail period (likely due to fewer months containing 5 full weeks).

**Clustered Column Chart Insights (Year-Wise Breakdown)**

* 2011 consistently leads in sales across most weeks, indicating a possible growth year or more promotional events.
* Week 5 shows the weakest performance in all three years — a possible indicator of low consumer engagement or calendar month-end effects.

---

### 4. Correlation between Average Weekly Sales & External Factors

**Introduction**: The objective of this analysis is to examine the relationship between Average Weekly\_Sales and key external economic/environmental factors, including:

* CPI (Consumer Price Index)
* Unemployment Rate
* Fuel Prices
* Temperature

**Method Used**:

* CORREL Function in Excel: Applied to calculate Pearson correlation coefficients between Average Weekly\_Sales and each external variable.

**Results**:

| External Factor | Correlation | Nature of Relationship         |
| --------------- | ----------- | ------------------------------ |
| CPI             | -0.0226     | Very Weak Negative Correlation |
| Unemployment    | 0.0454      | Very Weak Positive Correlation |
| Fuel Prices     | -0.0916     | Weak Negative Correlation      |
| Temperature     | -0.1309     | Moderate Negative Correlation  |

* Temperature and fuel prices show a negative correlation with average weekly sales, indicating they may slightly reduce consumer activity.
* CPI and unemployment rate exhibit minimal to very weak correlations, suggesting inflation and job market conditions had little impact on retail sales.

---

## 5. Conclusion

The Retail Data Analytics project successfully demonstrates how Microsoft Excel can be used as a powerful tool for uncovering meaningful business insights from historical retail data. By analyzing weekly sales across different stores, departments, time periods, and external conditions, several actionable conclusions were drawn:

* Seasonal trends are clearly evident, with December leading in sales and January/September lagging behind.
* Top-performing stores and departments such as Store #20 and Department #92 consistently drive a significant portion of total revenue.
* Underperforming departments, like Department #47, signal areas where business strategies may need revision or intervention.
* Week-wise analysis reveals that Week 2 and Week 4 are peak periods for customer activity, while Week 5 is typically weaker.
* External factors such as fuel price and temperature exhibit mild to moderate negative influence on sales, though CPI and unemployment rates had negligible effects.

Ultimately, this project lays the groundwork for more advanced retail analytics and sets the stage for forecasting, segmentation, and real-time dashboarding in future iterations.

---

## 6. Future Scope

* Forecasting future weekly sales using time series models
* Migrating dashboards to Power BI or Tableau
* Analyzing the impact of promotions and events
* Adding location-based insights using geographic data
* Expanding to product-level (SKU) sales analysis
* Integrating machine learning for clustering and predictions
* Automating dashboard refresh and report generation
* Enabling real-time data streaming and live dashboards


