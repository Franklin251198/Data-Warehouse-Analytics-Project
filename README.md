# Yelp-Data-Warehouse-Analytics-Project

Welcome to the Yelp Data Warehouse and Analytics Project repository! 🚀

This project demonstrates a comprehensive end-to-end data warehousing and analytics solution for the Yelp Academic Dataset, covering the full journey from raw JSON ingestion to interactive Power BI dashboards.

Designed as a hands-on portfolio project, it highlights industry best practices in data engineering and analytics, including star schema design, data quality management, chunked ETL processing, and advanced SQL-based analytical reporting with 50+ queries.


# Building the Data Warehouse (Data Engineering)
Objective
Develop a modern data warehouse using SQLite to consolidate Yelp data, enabling analytical reporting and informed decision-making for business performance, customer behavior, and review trends.

Specifications

Component	Details
**Data Sources**	            Import 5 JSON files (business, review, user, tip, checkin)
**Chunking Strategy**	        Process data in 10K-row chunks for memory efficiency
**Data Quality**	            Cleanse duplicates, validate nulls, resolve FK integrity issues
**Integration**	              Combine all sources into star schema (3 dimensions + 1 fact table)
**Scope**	                    Focus on complete dataset with referential integrity
**Documentation**	            Provide clear data model documentation and 50 SQL analytical queries
