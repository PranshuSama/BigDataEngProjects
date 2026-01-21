**Olist E-commerce ETL Pipeline & Analytics**
=============================================

**Project Overview**
--------------------

This project builds an end-to-end **Data Lakehouse** using the Olist E-commerce dataset from Kaggle. The goal was to engineer a scalable ETL pipeline that ingests disparate data from **MySQL (Relational)**, **MongoDB (NoSQL)**, and raw storage to produce high-value business insights via a refined **Medallion Architecture**.

**Technical Architecture**
--------------------------

The project follows a modular pipeline designed for scalability and data governance:

*   **Ingestion (Bronze):** Raw data is ingested from multiple sources, including a MySQL relational database for transactional records and MongoDB for document-based product categories.
    
*   **Transformation (Silver):** Data is cleaned, de-duplicated, and joined using **PySpark**. Schema enforcement and data quality checks are applied during the transition from Bronze to Silver layers.
    
*   **Analytics (Gold):** Final business-ready tables are created, featuring enriched metrics like **Customer Lifetime Value (CLV)**, delivery performance ratios, and RFM-based segmentation.
    
*   **Governance:** All data assets are managed within **Unity Catalog** on Azure Databricks to ensure secure access and lineage.
    

**Tech Stack**
--------------

*   **Processing Engine:** Apache Spark (PySpark & Spark SQL).
    
*   **Environment:** Azure Databricks.
    
*   **Databases:** MySQL (RDS), MongoDB.
    
*   **Storage:** Delta Lake (Parquet format).
    
*   **Visualization:** Tableau.
    

**Key Engineering Features**
----------------------------

### **1\. Multi-Source Enrichment**

Unlike standard CSV-only projects, this pipeline integrates relational and non-relational data:

*   **MySQL:** Handled transactional data ingestion using mysql-connector-python.
    
*   **MongoDB:** Ingested product category mappings and metadata to demonstrate handling of semi-structured data formats.
    

### **2\. Spark Performance Optimization**

To handle high-cardinality joins across millions of records, the following optimizations were implemented:

*   **Broadcast Joins:** Utilized for smaller dimension tables to avoid expensive shuffle operations.
    
*   **Adaptive Query Execution (AQE):** Configured Spark to dynamically optimize query plans and coalesce partitions for balanced workloads.
    
*   **Memory Management:** Tuned shuffle partitions and memory allocation to reduce processing latency.
    

### **3\. Data Quality & Cleaning**

*   Implemented automated checks for **null handling** and duplicate removal across the customer and order datasets.
    
*   Standardized date-time formats and handled outliers in delivery timestamps to ensure accurate logistics reporting.
    

**Analytics & Insights**
------------------------

The Gold layer provides deep visibility into Olist's operations:

*   **Delivery Performance:** Calculating the variance between estimated and actual delivery dates to identify logistics bottlenecks.
    
*   **Revenue Distribution:** Segmenting revenue by product category and geographic region to identify high-growth markets.
    
*   **Customer Segmentation:** Flagging customers based on purchase frequency and average order value.
    

**Future Improvements**
--------------------------

To transition this project into a production-grade enterprise platform, the following enhancements are planned:

*   **Real-time Streaming with Kafka:** Transition from batch processing to real-time ingestion using **Apache Kafka** to capture order updates and customer events instantly.
    
*   **Automated Orchestration with Airflow:** Replace manual execution with **Apache Airflow** to manage complex DAGs, implement retry logic, and provide centralized pipeline monitoring.
    
*   **CI/CD Integration:** Implement **GitHub Actions** to automate the testing and deployment of Databricks notebooks and infrastructure changes.
    
*   **Machine Learning Integration:** Build predictive models for **Churn Prediction** and **Estimated Time of Arrival (ETA)** forecasting directly on the Gold layer data.
    
*   **Advanced Monitoring:** Implement **Great Expectations** for rigorous data quality testing and **Grafana/Prometheus** for real-time cluster health monitoring.
    

**How to Run**
--------------

1.  **Azure Setup:** Ensure an Azure Databricks workspace is active with Unity Catalog enabled.
    
2.  **Ingestion:** Run the DataIngestionToSQL&DB.ipynb notebook to populate the Bronze layer from MySQL and MongoDB.
    
3.  **Pipeline:** Execute Project 2 - Real World Data.ipynb to trigger the transformation logic from Bronze to Gold.
