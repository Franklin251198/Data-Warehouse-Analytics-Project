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
| SQL Queries Written | 50 |
| DAX Measures | 15+ |
| Power BI Dashboards | 4 |

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
┌─────────────────────────────────────────────────────────────────────────────────────┐
│                                    DATA PIPELINE                                     │
└─────────────────────────────────────────────────────────────────────────────────────┘

┌──────────────┐     ┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│   RAW JSON   │────▶│   CHUNKING   │────▶│    DATA      │────▶│   BUILDING   │
│    FILES     │     │  (10K rows)  │     │ PREPARATION  │     │ DATA WAREHOUSE│
│              │     │              │     │              │     │ (Star Schema) │
└──────────────┘     └──────────────┘     └──────────────┘     └──────────────┘
       │                    │                    │                    │
       ▼                    ▼                    ▼                    ▼
  business.json        Memory-efficient      Duplicate Checks      dim_business
  review.json          batch processing      Null Validation       dim_user
  user.json                                   FK Integrity          dim_date
  tip.json                                    Date Conversion       fact_reviews
  checkin.json            
                                                                         │
                                                                         ▼
┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│   POWER BI   │◀────│    ODBC      │◀────│     SQL      │
│  DASHBOARDS  │     │   DRIVER     │     │  DATABASE    │
│              │     │              │     │  (SQLite)    │
└──────────────┘     └──────────────┘     └──────────────┘
       │                    │                    │
       ▼                    ▼                    ▼
  Overview              Connection           yelp.db
  Customer Analysis    Configuration         (Warehouse
  Business Performance                        Tables)
  Geographic & Time





  
