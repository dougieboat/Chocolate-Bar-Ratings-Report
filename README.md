# Chocolate Bar Ratings Analysis Dashboard

![Chocolate Home Page Banner](INSERT_SCREENSHOT_PAGE1_HERE)

## 🚀 Introduction

Chocolate is one of the world’s most beloved treats, consumed in massive quantities across the globe. However, not all chocolate bars deliver the same experience. Using expert-rated data, this report explores what distinguishes a high-quality chocolate bar from an average or unpleasant one. It provides a data-driven analysis of ratings, origins, cocoa content, and manufacturing companies.

---

## 🛠️ Skills Demonstrated

✔️ **Power Query transformations**  
✔️ **Data modeling using Star Schema**  
✔️ **Power BI dashboard creation**  
✔️ **DAX measures and KPIs**  
✔️ **Time-based trend analysis**  
✔️ **Interactive slicers and decomposition tree visuals**  
✔️ **Data storytelling and business recommendations**

---

## 📚 Table of Contents

[Problem Statement](#problem-statement)  
[Data Sourcing](#data-sourcing)  
[Data Transformation/Cleaning](#data-transformationcleaning)  
[Data Modeling](#data-modeling)  
[Analysis and Visualization](#analysis-and-visualization)  
[Conclusion & Recommendations](#conclusion-and-recommendations)

---

## Problem Statement

Key questions explored:

🍫 Which countries produce the highest-rated chocolate bars?  
🌱 How does cocoa content affect chocolate ratings?  
🏭 Which companies consistently produce Premium or Elite chocolates?  
📈 Is there a trend in chocolate ratings over time?  
🫘 What are the most common bean types used, and how are they rated?  

---

## Data Sourcing

- **Source:** [Kaggle – Flavors of Cacao: Chocolate Bar Ratings](https://www.kaggle.com/datasets/rtatman/chocolate-bar-ratings)
- **Dimensions:** 1,796 rows × 9 columns

**Columns Included:**
- Company (Maker-if known)
- Specific Bean Origin or Bar Name
- REF
- ReviewDate
- CocoaPercent
- CompanyLocation
- Rating
- BeanType
- Broad Bean Origin

---

## Data Transformation/Cleaning

All transformations were performed in Power BI using Power Query. Steps taken:

- Promoted headers for clarity
- Changed column types appropriately (dates, text, numbers)
- Renamed ambiguous columns (e.g., “Specific Bean Origin or Bar Name” to “Bar_Name”)
- Added prefixes to avoid confusion (e.g., “REF” to “REF_1462”)
- Trimmed and cleaned whitespace in text fields
- Replaced inconsistent values (e.g., unknown spellings)
- Reordered columns for intuitive display
- Removed duplicates and irrelevant columns

These transformations ensured clean, accurate data suitable for modeling and analysis.

---

## Data Modeling

The model follows a **star schema architecture** with a central fact table and two dimension tables.

- **Fact Table:** ChocolateRating
- **Dimensions:**
    - RatingDim (Rating label: Elite, Premium, etc.)
    - DateTable (linked by Review Year)

**Key Relationships:**

- ChocolateRating[Rating] → RatingDim[Rating]
- ChocolateRating[Review_Year] → DateTable[Review_Year]

![Power BI Model View](INSERT_SCREENSHOT_MODEL_VIEW_HERE)

---

## Analysis and Visualization

### Page 1: Global Chocolate Quality Overview

**KPIs:**
- **Total Unique Bars Reviewed:** 1,038
- **Average Rating:** 3.19 / 5

**Insights:**
- **Top countries by average rating:**  
    - Italy (3.33), Canada (3.32), France (3.25), United States (3.15), UK (3.05)
- **Gradual improvement in ratings** from 2008 (2.99) to 2017 (3.31)
- **Most common rating label:** Satisfactory (773 bars)
- **Elite chocolates are extremely rare:** Only 2 bars

![Country vs Average Rating and Rating Trend](INSERT_CHART_PAGE1_HERE)

---

### Page 2: Company and Bean Insights

**KPI:**
- **Average Cocoa Content:** 72%

**Insights:**
- **Most common cocoa content:** 70% (dark chocolate)
- **Optimal cocoa range for higher ratings:** 68%–74%
- **After 75%, ratings tend to decline**
- **Top 5 companies by bar count:**  
    - Soma (Canada), Bonnat (France), Fresco (USA), Pralus (France), A. Morin (France)
- **Best average-rated companies:**  
    - Soma (3.59), Arete (3.53), Domori (3.48)

**Bean Type Analysis:**
- **Criollo and Trinitario beans** from Ecuador, Venezuela, Peru have highest ratings (some above 4.0)
- **Forastero beans** score lower on average

![Cocoa vs Rating, Bean Type vs Rating, Top Companies](INSERT_CHART_PAGE2_HERE)

---

### Page 3: Star Rating Analysis

**KPIs:**
- **Total Bars:** 1,795
- **Average Rating:** 3.19

**Rating Label Distribution:**
- Satisfactory: 773
- Disappointing: 288
- Premium: 87
- Elite: 2
- Unpleasant: 17

**Company Location Insights (Sample):**

| Company Location | Rating Label  | Bar Count |
|------------------|--------------|-----------|
| Amsterdam        | Satisfactory | 4         |
| Netherlands      | Satisfactory | 4         |
| Iceland          | Satisfactory | 3         |
| Chile            | Satisfactory | 2         |
| Philippines      | Satisfactory | 1         |

**Decomposition Tree Insights:**
- Highest-rated bars use **Criollo and Trinitario** beans
- Sourced mainly from **Venezuela, Peru, and Ecuador**
- Top-performing companies: Soma, Bonnat, Valrhona, Amedei

![Decomposition Tree and Bar Chart Visuals](INSERT_CHART_PAGE3_HERE)

---

## Conclusion and Recommendations

### 🎯 **Conclusion**

- **Elite and Premium quality chocolates are very rare**, with the majority falling into the Satisfactory category.
- **Italy, Canada, and France** consistently produce higher-rated chocolates.
- The **optimal cocoa content range** is 68%–74%.
- **Criollo and Trinitario beans**, especially from Ecuador and Venezuela, correlate with higher quality.
- **Quality has gradually improved over time**, indicating better practices or bean sourcing.

---

### 💡 **Recommendations**

#### For Chocolate Makers:
- Prioritize sourcing **Criollo beans** from high-performing origins
- Aim for **cocoa content between 68%–74%**
- Study top companies like **Soma** and **Domori** for best practices

#### For Consumers:
- Consider premium brands such as **Soma, Bonnat, or Arete** for the best experience
- Avoid bars with excessively high cocoa percentages unless flavor-balanced

#### For Analysts:
- Track rating consistency across years
- Use decomposition tools to explore bean-country-company interactions more deeply

---

## 📎 Quick Links

- [Dataset on Kaggle](https://www.kaggle.com/datasets/rtatman/chocolate-bar-ratings)

---

> _Ready to explore the the three-page report? Download the [Power BI file]() and visuals for deeper insights!_

---

*© 2025 Douglas Boateng | [GitHub](https://github.com/dougieboat)*
