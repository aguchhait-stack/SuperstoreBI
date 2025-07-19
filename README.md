# 📊 Super Store Sales Dashboard – Power BI Project

<img width="1154" height="655" alt="Screenshot 2025-07-20 at 1 12 43 AM" src="https://github.com/user-attachments/assets/e7387ee8-a355-4041-a8a0-ea6dbb813695" />


## 📌 Project Overview

This Power BI dashboard visualizes Superstore retail sales across multiple business dimensions. It provides decision-makers with an interactive way to monitor key performance indicators (KPIs), track profitability trends, evaluate shipping and payment behaviors, and analyze customer segments.

The model is built using a **star schema** approach, enabling faster querying, modular design, and scalable reporting.

---

## 🔧 Tools & Technologies

- Power BI Desktop
- DAX (Data Analysis Expressions)
- Power Query (M)
- Star Schema Modeling
- GitHub for versioning

---

## 🧱 Data Model

The model is centered around a single fact table `fact_sales` and multiple dimension tables:

### 🟦 Fact Table:
- **`fact_sales`**  
  Contains transaction-level data including:
  - `Sales`, `Profit`, `Quantity`, `Returns`
  - `Customer ID`, `Product ID`, `Order Date`, `Ship Date`
  - `Payment Mode`, `City`, `Order ID`

### 🟨 Dimension Tables:
- **`dim_customers`** – Customer ID, Name, Segment
- **`dim_products`** – Product ID, Name, Category, Sub-Category
- **`dim_locations`** – City, State, Region, Country
- **`dim_payments`** – Payment Mode
- **`dim_dates`** – Order and Ship Dates for time intelligence

Each relationship is modeled as **one-to-many** (1:*), with **single-directional filtering** from dimensions to the fact table for optimized performance.

---

## 📈 Dashboard Features

The final dashboard provides:

- ✅ **KPI Cards**: Total Sales, Total Quantity
- 📊 **Charts**:
  - Monthly Sales and Profit (YoY line charts)
  - Sales by Product Category and Sub-Category
  - Sales by Payment Mode and Segment (Donut charts)
  - Sales by Ship Mode (Bar chart)
- 🌍 **Geographic View**: US Sales by City using a Filled Map
- 🎯 **Interactive Slicers**: Region selector for dynamic filtering

---

## 📂 Dataset Source

The dataset is adapted from the popular [Sample Superstore Dataset](https://community.tableau.com/s/question/0D54T00000CWeWRSA1/sample-superstore-sales-excelxls) and split into a star-schema format. CSV files are stored on GitHub for dynamic loading via URL or local folder.

Example CSVs:
- [`fact_sales.csv`](https://raw.githubusercontent.com/aguchhait-stack/SuperstoreBI/main/fact_sales.csv)
- [`dim_products.csv`](https://raw.githubusercontent.com/aguchhait-stack/SuperstoreBI/main/dim_products.csv)
- [`dim_customers.csv`](https://raw.githubusercontent.com/aguchhait-stack/SuperstoreBI/main/dim_customers.csv)

---

## 🚀 How to Use

1. Clone this repository:
   ```bash
   git clone https://github.com/aguchhait-stack/SuperstoreBI.git
