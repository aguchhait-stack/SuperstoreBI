📊 Superstore BI Dashboard

This repository contains a Power BI project built on a star-schema model derived from a global superstore sales dataset. It includes transformed fact and dimension tables, DAX measures, and visualizations focused on regional sales performance, shipping trends, and customer behavior.
![Uploading Screenshot 2025-07-20 at 1.12.43 AM.png…]()


🔗 Live Dashboard (Power BI Service):
Click to View on Power BI Service

🗂️ Data Model

The Power BI data model follows a star schema:

✅ Fact Table

fact_sales.csv
✅ Dimension Tables

dim_customers.csv
dim_products.csv
dim_locations.csv
dim_dates.csv
dim_payments.csv
Each table is cleaned and modeled for optimal DAX and visualization performance.

🛠️ Python ETL Automation

The ETL pipeline is implemented in the Jupyter Notebook PowerBi_automation.ipynb, which automates:

Extraction of CSV files directly from GitHub using pandas.read_csv()
Transformation to clean date formats, remove invalid or missing values, and structure the data
Loading cleaned datasets into a specified local directory (/Users/arijitguchhait/Desktop/Windows 11/Shared)
🔃 Transformations Include:

Order Date, Ship Date: parsed to datetime (%d-%m-%Y)
Returns: replaced #N/A with 0
Quantity: converted to integer after coercing errors
Other tables: stripped whitespace, replaced #N/A with NaN, dropped fully empty rows
✅ You can run this notebook in JupyterLab, VS Code, or Google Colab to automate the full ETL process before loading data into Power BI.
⏰ Automation with Cron (macOS)

To schedule this ETL daily at 8 AM:

Open Terminal:
crontab -e
Add this line:
0 8 * * * /usr/bin/python3 /full/path/to/PowerBi_automation.py
📎 Credits

Created by Arijit Guchhait
Repo: SuperstoreBI
