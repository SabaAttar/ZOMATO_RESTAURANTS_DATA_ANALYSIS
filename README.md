# 📊 Zomato Restaurant Data Analysis

---

## 🔎 Project Overview

This project analyzes **9500+ restaurants** from the Zomato dataset to uncover business insights related to restaurant growth, pricing trends, rating distribution, and online delivery adoption.

The objective was to transform raw data into meaningful business insights using SQL, Excel, Power BI, and Tableau.

---

## 🛠 Tools & Technologies Used

- SQL (Data extraction & aggregation)
- Microsoft Excel (Data cleaning & preprocessing)
- Power BI (Dashboard development & DAX modeling)
- Tableau (Visual analytics & storytelling)

---

## 📂 Dataset Description

The dataset includes:

- Restaurant Name
- Country
- City
- Rating
- Votes
- Currency
- Average Cost for Two
- Online Delivery Availability
- Opening Date

Total Records: 9500+

---

## 🧹 Data Cleaning Process (Excel)

- Removed duplicate records
- Handled missing/null values
- Standardized date formats
- Converted multiple currencies into USD
- Created structured calendar columns (Year, Quarter, Month)

---

## 🗃 SQL Analysis Performed

Key queries performed:

- Restaurant count by Year, Quarter, Month
- Country-wise restaurant distribution
- Average rating by country
- Online delivery trend analysis
- Aggregation using GROUP BY and JOIN

### Sample SQL Query

```sql
SELECT 
    cal.Year,
    cal.Quarter,
    cal.MonthFullName AS Month_Name,
    COUNT(*) AS Number_of_Restaurants
FROM main m
JOIN calendar cal
    ON cal.Datekey_Opening = m.Datekey
GROUP BY cal.Year, cal.Quarter, cal.MonthFullName
ORDER BY cal.Year, cal.Quarter;
```

---

## 🧩 Data Model

The data model was structured using:

- Fact Table: Restaurant Data
- Dimension Tables:
  - Calendar Table
  - Country Table 

Relationships:
- Datekey → Calendar Table (One-to-Many)
- Country ID → Country Dimension

This structure enabled efficient time-based and country-level analysis.

---

## 📊 DAX Measures Used

Some important DAX calculations:

### Total Restaurants
```DAX
Total Restaurants = COUNT('Restaurants'[RestaurantID])
```

### Average Rating
```DAX
Average Rating = AVERAGE('Restaurants'[Rating])
```

### Online Delivery Count
```DAX
Online Delivery Count = 
CALCULATE(
    COUNT('Restaurants'[RestaurantID]),
    'Restaurants'[Has_Online_Delivery] = "Yes"
)
```

### Year-over-Year Growth
```DAX
YoY Growth = 
CALCULATE(
    [Total Restaurants],
    SAMEPERIODLASTYEAR('Calendar'[Date])
)
```

---

## 📊 Power BI Dashboard Features

- KPI Cards (Total Restaurants, Avg Rating)
- Year-wise Restaurant Growth
- Country-wise Distribution Map
- Rating Distribution Analysis
- Online Delivery Comparison
- Interactive Filters & Slicers

---

## 📈 Tableau Dashboard Features

- Dynamic country and city filters
- Time-series growth analysis
- Rating heatmap visualization
- Cross-country price comparison
- Interactive drill-down functionality

---

## 📷 Dashboard Preview

### 🔵 Power BI Dashboard


### 🟠 Tableau Dashboard


---

## 📈 Key Business Insights

- India has the highest restaurant concentration.
- Most restaurants have ratings between 3.5 – 4.2.
- Online delivery adoption increased significantly after 2015.
- Currency normalization enabled fair cross-country comparison.
- Urban cities show higher restaurant density and rating averages.

---

## ⚠ Challenges Faced

- Handling inconsistent currency formats.
- Managing missing rating values.
- Creating accurate time-based analysis due to date inconsistencies.
- Ensuring correct relationships in data modeling.
- Optimizing DAX measures for performance.

---

## 🚀 Future Improvements

- Implement rolling average analysis.
- Add customer sentiment analysis.
- Build predictive model for rating trends.
- Deploy dashboard to Power BI Service.
- Automate data refresh using scheduled pipelines.

---

## 🎯 Skills Demonstrated

- Data Cleaning & Transformation
- SQL Joins & Aggregations
- Data Modeling
- DAX Calculations
- Tableau Visualization
- Business Insight Generation
- Dashboard Design
- Data Storytelling

---

## 📌 Business Impact

This project helps stakeholders:

- Understand market expansion trends
- Compare country-level performance
- Analyze pricing patterns
- Evaluate online delivery penetration
- Identify high-performing regions

---

## 👩‍💻 Author

Saba Attar  
Aspiring Data Analyst | SQL | Power BI | Tableau | Excel

---
