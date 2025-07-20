
# 📊 Superstore BI Dashboard

This repository contains a Power BI project built on a star-schema model derived from a global superstore sales dataset. It includes transformed fact and dimension tables, DAX measures, and visualizations focused on regional sales performance, shipping trends, and customer behavior.

![Dashboard Screenshot](./Screenshot%202025-07-20%20at%201.12.43%E2%80%AFAM.png)

---

## 🗂️ Data Model

The Power BI data model follows a star schema:

### ✅ Fact Table
- `fact_sales.csv`

### ✅ Dimension Tables
- `dim_customers.csv`
- `dim_products.csv`
- `dim_locations.csv`
- `dim_dates.csv`
- `dim_payments.csv`

Each table is cleaned and modeled for optimal DAX and visualization performance.

---

## 🛠️ Python ETL Automation

A custom ETL pipeline is included via the script [`etl_superstore.py`](./etl_superstore.py), which automates:

- **Extraction** of CSVs from GitHub (via raw links)
- **Transformation** of inconsistent or missing data
- **Loading** cleaned data to a local directory

### 🔃 Transformations Include:
- `Order Date`, `Ship Date`: converted to datetime (`%Y-%m-%d`)
- `Returns`: cleaned and filled with 0
- `Quantity`: cast to integer
- All other dimension tables are stripped, `#N/A` handled, and blank rows dropped

### 📥 CSV Files Processed:
- `fact_sales.csv`
- `dim_customers.csv`
- `dim_products.csv`
- `dim_locations.csv`
- `dim_dates.csv`
- `dim_payments.csv`

### 📍 Output Path:
By default:
```
/Users/arijitguchhait/Desktop/Windows 11/Shared
```

---

## ⏰ Automation with Cron (macOS)

To schedule this ETL daily at 8 AM:

1. Open Terminal:
```bash
crontab -e
```

2. Add this line:
```bash
0 8 * * * /usr/bin/python3 /full/path/to/etl_superstore.py
```

---

## 📎 Credits

Created by [Arijit Guchhait](https://github.com/aguchhait-stack)  
Repo: [SuperstoreBI](https://github.com/aguchhait-stack/SuperstoreBI)
