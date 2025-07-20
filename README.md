# 📊 Superstore BI Dashboard

This repository contains a Power BI project built on a star-schema model derived from a global superstore sales dataset. It includes transformed fact and dimension tables, DAX measures, and visualizations focused on regional sales performance, shipping trends, and customer behavior.

<img width="1154" height="655" alt="Screenshot 2025-07-20 at 1 12 43 AM" src="https://github.com/user-attachments/assets/9607eff7-b01f-4061-b094-4a120e20c57e" />


🔗 **Live Dashboard (Power BI Service)**:  
[View on Power BI](https://app.fabric.microsoft.com/links/sw5bBg-hlH?ctid=17dcb00c-6941-4050-b69e-bd7eb8951712&pbi_source=linkShare&bookmarkGuid=22bf2c5b-06eb-4c25-8b90-af21d9346ee5)

---

## 🗂️ Data Model

The Power BI data model follows a star schema structure:

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

The ETL pipeline is implemented in the Jupyter Notebook [`PowerBi_automation.ipynb`](./PowerBi_automation.ipynb), which automates:

- **Extraction** of CSV files directly from GitHub using `pandas.read_csv()`
- **Transformation** to clean date formats, remove invalid or missing values, and structure the data
- **Loading** cleaned datasets into a specified local directory (`/Users/arijitguchhait/Desktop/Windows 11/Shared`)

### 🔃 Transformations Include:
- `Order Date`, `Ship Date`: parsed to datetime (`%d-%m-%Y`)
- `Returns`: replaced `#N/A` with `0`
- `Quantity`: converted to integer after coercing errors
- Other tables: stripped whitespace, replaced `#N/A` with `NaN`, dropped fully empty rows

> ✅ You can run this notebook in JupyterLab, VS Code, or Google Colab to automate the full ETL process before loading data into Power BI.

---

## ⏰ Automation with Cron (macOS)

To schedule this ETL daily at 8 AM:

1. Open Terminal:
   ```bash
   crontab -e


To schedule this ETL daily at 8 AM:

Open Terminal:
crontab -e
Add this line:
0 8 * * * /usr/bin/python3 /full/path/to/PowerBi_automation.py

## 📎 Credits

- **Author**: [Arijit Guchhait](https://github.com/aguchhait-stack)
- **Repository**: [SuperstoreBI](https://github.com/aguchhait-stack/SuperstoreBI)
