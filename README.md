# Retail analytics with Microsoft Fabric

This project takes 10,000 retail order records through three OneLake lakehouses and into a Power BI report. The report covers sales, product performance, customers and payment methods.

## Data flow

| Layer | Lakehouse | Processing |
| --- | --- | --- |
| Bronze | `lh_retail_bronze` | Stores the incoming order data. |
| Silver | `lh_retail_silver` | Removes duplicate records and validates quantity, unit price, discount and line amount. |
| Gold | `lh_retail_gold` | Organizes the cleaned data into four tables for reporting. |

## Reporting tables

| Gold table | Rows in the project run |
| --- | ---: |
| `gold_sales_summary` | 616 |
| `gold_product_performance` | 100 |
| `gold_customer_analytics` | 2,000 |
| `gold_payment_analysis` | 20 |

## Power BI report

The **RETAIL** report has three pages. **Sales Overview** summarizes sales, **Orders & Products** covers orders and product performance, and **Customer & Payment Analytics** breaks down customer and payment activity.

The implementation uses Fabric Data Pipelines, Dataflow Gen2, PySpark, Delta tables and a semantic model. The ingestion pipeline is named `pl_retail_ingestion`, and the Silver dataflow is named `Run_Retail_Silver_Dataflow`.
