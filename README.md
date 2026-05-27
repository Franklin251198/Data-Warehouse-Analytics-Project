# Data Warehouse and Analytics Project

[![Python](https://img.shields.io/badge/Python-3.13-blue)](https://python.org)
[![SQLite](https://img.shields.io/badge/SQLite-003B57?logo=sqlite)](https://sqlite.org)
[![PowerBI](https://img.shields.io/badge/Power_BI-F2C811?logo=powerbi)](https://powerbi.microsoft.com)
[![VS Code](https://img.shields.io/badge/VS_Code-007ACC?logo=visualstudiocode)](https://code.visualstudio.com)
[![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter)](https://jupyter.org)
[![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas)](https://pandas.pydata.org)
[![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-FF0000?logo=sqlalchemy)](https://www.sqlalchemy.org)
[![ODBC](https://img.shields.io/badge/ODBC-0066CC?logo=databricks)](https://learn.microsoft.com/en-us/sql/odbc)
[![Git](https://img.shields.io/badge/Git-F05032?logo=git)](https://git-scm.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?logo=github)](https://github.com)

Welcome to the **Yelp Data Warehouse and Analytics Project** repository! 🚀

This project demonstrates a comprehensive end-to-end data warehousing and analytics solution for the Yelp Academic Dataset, covering the full journey from raw JSON ingestion to interactive Power BI dashboards.

Designed as a hands-on portfolio project, it highlights industry best practices in data engineering and analytics, including **star schema design**, **data quality management**, **chunked ETL processing**, and **advanced SQL-based analytical reporting**.

---
## 📊 Dashboard Preview

<img width="884" height="498" alt="Overview" src="https://github.com/user-attachments/assets/e7435deb-deed-4427-a15e-2b934e559ada" />

---
## 📊 Project Stats

| Metric | Value |
|--------|-------|
| Total Rows Processed | 8.9M+ |
| Businesses | 150K+ |
| Users | 1.9M |
| Reviews | 6M+ |
| Tips | 900K+ |
| Query Performance Gain | ~40% |
| DAX Measures | 15+ |

---

## 🚀 Project Requirements

### Building the Data Warehouse 

**Objective**  
Develop a modern data warehouse using SQLite to consolidate Yelp data, enabling analytical reporting and informed decision-making for business performance, customer behavior, and review trends.

**Specifications**

| Component | Details |
|-----------|---------|
| **Data Sources** | Import 5 JSON files (business, review, user, tip, checkin) |
| **Chunking Strategy** | Process data in 10K-row chunks for memory efficiency |
| **Data Quality** | Cleanse duplicates, validate nulls, resolve FK integrity issues |
| **Integration** | Combine all sources into star schema (3 dimensions + 1 fact table) |
| **Scope** | Focus on complete dataset with referential integrity |
| **Documentation** | Provide clear data model documentation and 50 SQL analytical queries |

### 📊 BI: Analytics & Reporting (Data Analytics)

**Objective**  
Develop SQL-based analytics and Power BI dashboards to deliver detailed insights into:

- **Business Performance** – Top businesses, overrated/underrated analysis, category performance
- **Customer Behavior** – Elite vs normal users, activity patterns, engagement metrics
- **Review Trends** – Seasonal patterns, rating distribution, YoY growth

These insights empower stakeholders with key business metrics, enabling data-driven and strategic decision-making.

---

## 🏗️ System Architecture

<img width="486" height="446" alt="image" src="https://github.com/user-attachments/assets/20bda626-2844-4fd1-8a22-9eb9742d55cf" />

---

## 📁 Dataset

The Yelp Academic Dataset includes 5 JSON files:

| File | Rows | Description |
|------|------|-------------|
| business.json | 150K+ | Business attributes (name, location, categories, ratings) |
| review.json | 6M | User reviews with ratings and engagement metrics |
| user.json | 1.9M | User profiles (yelping_since, fans, elite status) |
| tip.json | 900K+ | Short tips left by users |
| checkin.json | 130K+ | Check-in records per business |

---

## 🗄️ Data Warehouse Design

The data warehouse is designed using a **dimensional (star schema)** model optimized for analytical workloads.

### Fact Table

**fact_reviews**
- review_id (Primary Key)
- business_id (Foreign Key)
- user_id (Foreign Key)
- date_key (Foreign Key)
- review_stars
- useful_votes
- funny_votes
- cool_votes

### Dimension Tables

| Table | Attributes |
|-------|------------|
| **dim_business** | business_id, name, city, state, latitude, longitude, categories, business_stars, business_review_count |
| **dim_user** | user_id, name, yelping_since, fans, average_stars, user_review_count, elite |
| **dim_date** | date_key, year, month, day, quarter, day_name, month_name |

This design ensures high query performance and intuitive reporting, achieving **~40% faster query execution**.

---

## 🧪 Data Quality & Transformation

The following data processing steps are applied:

| Step | Description |
|------|-------------|
| **Duplicate Removal** | Checked all tables using `duplicated().sum()` – no duplicates found |
| **Data Type Standardization** | Converted all columns to string during ingestion, then typed appropriately |
| **Null Value Handling** | Identified and documented columns with missing values |
| **Foreign Key Integrity** | Validated business_id and user_id references; removed 32 invalid review rows |
| **Date Transformation** | Converted date strings to datetime objects; created date dimension |
| **Chunked Processing** | Processed 6M+ review rows in 10K chunks for memory efficiency |

---

## 📊 SQL Analytics

### Query Categories

| Category | Techniques | Example Questions |
|----------|------------|-------------------|
| **Aggregation** | COUNT, AVG, SUM, GROUP BY | Total reviews, avg ratings by city |
| **Ranking** | RANK(), DENSE_RANK(), LIMIT | Top 10 businesses, most active users |
| **Window Functions** | OVER(), PARTITION BY, LAG | Running totals, YoY growth |
| **CTEs** | WITH clause | Business engagement categorization |
| **Subqueries** | Correlated & non-correlated | Businesses above city average |
| **CASE Statements** | CASE WHEN | Elite vs normal user segmentation |
| **NTILE** | Quartile segmentation | User activity level grouping |

---

## 🛠️ Tools & Technologies

| Category | Technology |
|----------|------------|
| Database | SQLite |
| Language | Python, SQL |
| Libraries | pandas, SQLAlchemy |
| Data Modeling | Star Schema |
| Source Data | Yelp JSON Dataset |
| Analytics | SQL Queries, Pandas |
| Visualization | Power BI |
| Development Environment | Jupyter Notebook, VS Code |
| Version Control | Git & GitHub |

---

## 📁 Repository Structure

<img width="806" height="295" alt="image" src="https://github.com/user-attachments/assets/e6f5c17d-14ed-4bc1-980a-138f0d8a6f09" />

---

## 🚀 How to Run This Project

1. **Clone the repo**
   ```bash
   git clone https://github.com/yourusername/yelp-data-warehouse.git
   cd yelp-data-warehouse
   
2. **Install dependencies**
   ```bash
   pip install -r requirements.txt


3. **Download Yelp dataset** from https://www.yelp.com/dataset

4. **Update file path** in scripts/Ingest.ipynb (line with folder_path)

5. **Run notebooks in order**: Ingest → Transform → Load_data_to_sqldatabase

6. **Connect Power BI** using ODBC driver to the generated yelp.db

  
