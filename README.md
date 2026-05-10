# Olist Brazil Ecommerce ETL Pipeline using Databricks

## Project Overview

This project implements an end-to-end ETL pipeline using the Olist Brazilian Ecommerce public dataset in Databricks Free Edition. The pipeline follows Medallion Architecture using Bronze, Silver, and Gold layers with PySpark and Delta Lake.

The objective of the project is to ingest raw ecommerce data, clean and transform it, and generate business-ready analytics tables for reporting and visualization.

---

# Tech Stack

* Databricks Free Edition
* PySpark
* Delta Lake
* Spark SQL
* Python
* Medallion Architecture
* Kaggle Olist Dataset

---

# Dataset

Dataset Used:

Olist Brazilian Ecommerce Public Dataset

The dataset contains real ecommerce transactions from Brazil including:

* Customers
* Orders
* Products
* Sellers
* Payments
* Reviews
* Geolocation

---

# Project Architecture

```text
Raw CSV Files
      ↓
Bronze Layer
(Raw Delta Tables)
      ↓
Silver Layer
(Cleaned & Transformed Data)
      ↓
Gold Layer
(Business Analytics & KPIs)
```

---

# Bronze Layer

## Purpose

The Bronze layer stores raw ingested data from CSV files without applying major transformations.

## Tasks Performed

* CSV ingestion
* Schema inference
* Raw Delta table creation
* Data preservation

## Bronze Tables

* bronze_customers
* bronze_orders
* bronze_order_items
* bronze_products
* bronze_payments
* bronze_reviews
* bronze_sellers

## Sample Bronze Ingestion Logic

* Read CSV using Spark
* Save data as Delta format
* Store inside Bronze folder

---

# Silver Layer

## Purpose

The Silver layer contains cleaned and standardized data.

## Transformations Performed

* Removed duplicates
* Removed invalid null records
* Converted timestamp columns
* Standardized data types
* Basic data quality checks

## Silver Tables

* silver_customers
* silver_orders
* silver_order_items
* silver_products
* silver_payments
* silver_reviews
* silver_sellers

## Key Cleaning Operations

### Duplicate Removal

Used dropDuplicates() to remove repeated rows.

### Null Filtering

Filtered records where important IDs were null.

### Timestamp Conversion

Converted string columns into timestamp datatype using PySpark functions.

---

# Gold Layer

## Purpose

The Gold layer contains business-ready analytics tables generated from multiple Silver tables.

## Main Joins

The following tables were joined:

* Orders
* Customers
* Payments
* Products
* Order Items

## Gold Tables Created

* monthly_sales
* top_categories
* state_sales

---

# Business KPIs Generated

## Monthly Revenue Analysis

Calculated month-wise revenue trends using payment values.

## Top Product Categories

Identified highest revenue-generating product categories.

## State-wise Revenue

Analyzed customer revenue contribution by Brazilian states.

---

# Data Engineering Concepts Used

* ETL Pipeline
* Medallion Architecture
* Delta Lake
* PySpark Transformations
* Data Cleaning
* Data Modeling
* SQL Analytics
* Data Quality Checks
* Business KPI Generation

---

# Challenges Faced

* Handling modern Databricks Volume storage
* Managing multiple CSV datasets
* Converting raw timestamps
* Designing reusable ETL functions
* Performing joins across multiple tables

---

# Outcome

Successfully built a scalable ETL pipeline capable of:

* Ingesting raw ecommerce data
* Cleaning and transforming datasets
* Creating analytics-ready Gold tables
* Generating business insights and visualizations

---

# Future Improvements

Potential future enhancements include:

* Databricks Workflows
* Incremental Loading
* Power BI Dashboard Integration
* Airflow Orchestration
* dbt Integration
* CI/CD Pipelines
* Advanced Data Quality Frameworks

---

# Resume Description

Built an end-to-end ETL pipeline in Databricks using the Olist Brazilian Ecommerce dataset with Bronze, Silver, and Gold Medallion Architecture. Implemented PySpark transformations, Delta Lake storage, SQL analytics, and business KPI generation for ecommerce reporting.

---

# Conclusion

This project demonstrates practical data engineering skills including ingestion, transformation, analytics, and scalable ETL pipeline design using Databricks and PySpark.
