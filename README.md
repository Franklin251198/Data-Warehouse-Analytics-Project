# Data Warehouse and Analytics Project - Yelp

Welcome to the **Yelp Data Warehouse and Analytics Project** repository! 🚀

This project demonstrates a comprehensive end-to-end data warehousing and analytics solution for the Yelp Academic Dataset, covering the full journey from raw JSON ingestion to interactive Power BI dashboards.

Designed as a hands-on portfolio project, it highlights industry best practices in data engineering and analytics, including **star schema design**, **data quality management**, **chunked ETL processing**, and **advanced SQL-based analytical reporting** with 50+ queries.

---

## 📊 Project Stats

| Metric | Value |
|--------|-------|
| Total Rows Processed | 8.9M+ |
| Businesses | 150K+ |
| Users | 1.9M |
| Reviews | 6M+ |
| Tips | 900K+ |
| Query Performance Gain | ~50% |
| DAX Measures | 15+ |

---

## 🚀 Project Requirements

### Building the Data Warehouse (Data Engineering)

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

### Star Schema Visual
<img width="636" height="545" alt="image" src="https://github.com/user-attachments/assets/552ff74a-27be-491a-8e80-95f064c03713" />



This design ensures high query performance and intuitive reporting, achieving **~50% faster query execution**.

---

## 🧪 Data Quality & Transformation

The following data processing steps are applied:

| Step | Description |
|------|-------------|
| **Duplicate Removal** | Checked all tables using `duplicated().sum()` – no duplicates found |
| **Data Type Standardization** | Converted all columns to string during ingestion, then typed appropriately |
| **Null Value Handling** | Identified and documented columns with missing values |
| **Foreign Key Integrity** | Validated business_id and user_id references; removed 40 invalid review rows |
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

## 🧪 Data Quality & Transformation

The following data processing steps are applied:

| Step | Description |
|------|-------------|
| **Duplicate Removal** | Checked all tables using `duplicated().sum()` – no duplicates found |
| **Data Type Standardization** | Converted all columns to string during ingestion, then typed appropriately |
| **Null Value Handling** | Identified and documented columns with missing values |
| **Foreign Key Integrity** | Validated business_id and user_id references; removed 40 invalid review rows |
| **Date Transformation** | Converted date strings to datetime objects; created date dimension |
| **Chunked Processing** | Processed 6M+ review rows in 10K chunks for memory efficiency |

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


## 📁 Repository Structure

yelp-data-warehouse/
│
├── data/
│   ├── business.json          # Raw source data (not committed - too large)
│   ├── review.json            # Raw source data (not committed - too large)
│   ├── user.json              # Raw source data (not committed - too large)
│   ├── tip.json               # Raw source data (not committed - too large)
│   ├── checkin.json           # Raw source data (not committed - too large)
│   └── yelp.db                # SQLite database (not committed - too large)
│
├── notebooks/
│   ├── Ingest.ipynb           # Step 1-2: Raw ingestion + chunking
│   ├── Transform.ipynb        # Step 3: Data preparation & quality
│   └── Load_data_to_sqldatabase.ipynb  # Step 4-5: Warehouse + SQL analysis
│
├── docs/
│   ├── Yelp Star Schema 50 Sql Queries.pdf  # Complete SQL documentation
│   └── Datawarehouse+ analytics yelprject.docx  # Project documentation
│
├── powerbi/
│   └── yelp_dashboard.pbix     # Power BI dashboard file
│
├── .gitignore
└── README.md




  
