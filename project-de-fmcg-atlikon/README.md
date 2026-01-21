# 📦 FMCG Data Engineering Pipeline – AtliKon

## 📌 Project Overview
This project implements an **end-to-end data engineering pipeline** for an **FMCG (Fast-Moving Consumer Goods)** business use case.  
The pipeline integrates data from **parent and child companies**, processes both **full and incremental loads**, and produces **analytics-ready tables** for dashboarding.

The solution is designed using **real-world data engineering best practices** such as layered architecture, incremental ingestion, and modular notebook-based processing on **Databricks**.

---

## 🎯 Business Problem
AtliKon, an FMCG organization, receives sales, customer, product, and pricing data from multiple operational sources:

- **Parent Company**: Provides dimension and fact data
- **Child Company**: Sends daily incremental order data

Challenges addressed:
- Handling **high-volume daily transactional data**
- Supporting **incremental fact loads**
- Maintaining **clean, analytics-ready dimensions**
- Enabling **business dashboards** for decision-making

---

## 🏗️ Architecture Overview
The pipeline follows a **Bronze → Silver → Gold** layered design:

- **Bronze (Raw)**  
  - Full load and incremental CSV data from parent & child companies
- **Silver (Cleaned & Standardized)**  
  - Validated dimensions and fact tables
- **Gold (Analytics Layer)**  
  - Denormalized tables for dashboarding and reporting

Architecture and design diagrams are available in the `resources/` folder.

---

## 📂 Project Structure
```text
project-de-fmcg-atlikon
├── 0_data/                  # Raw data (ignored from Git)
├── 1_codes/
│   ├── 1_setup/              # Catalog setup, utilities, date dimension
│   ├── 2_dimension_data_processing/
│   │   ├── customers
│   │   ├── products
│   │   └── pricing
│   └── 3_fact_data_processing/
│       ├── full_load
│       └── incremental_load
├── 2_dashboarding/
│   ├── denormalise_table_query_fmcg.txt
│   └── fmcg_dashboard.pdf
├── resources/
│   ├── project_architecture.png
│   └── databricks_project.excalidraw
├── test/
│   └── test_data.py
└── .gitignore
```
---

## 🗂️ Raw Data (Bronze Layer)

The Bronze layer contains **raw, unprocessed CSV data** received from upstream source systems.  
These datasets are **intentionally excluded from version control** and documented here to reflect **enterprise data engineering best practices**.

Raw data is organized by **source company** and **load type (full vs incremental)**.

---

## 📌 Data Sources & Load Types

| Source Company | Dataset Type | Load Type |
|---------------|-------------|-----------|
| Parent Company | Dimensions & Facts | Full Load |
| Child Company  | Orders | Incremental Load |

---

## 👤 Customers (Raw)

**Source:** Parent & Child Company  
**Load Type:** Full Load  
**Description:** Master data representing customer details.

| Column Name | Description |
|------------|-------------|
| customer_id | Unique customer identifier |
| customer_name | Customer name |
| region | Sales region |
| channel | Sales channel |

---

## 📦 Products (Raw)

**Source:** Parent & Child Company  
**Load Type:** Full Load  
**Description:** Product master data used for sales analysis.

| Column Name | Description |
|------------|-------------|
| product_id | Unique product identifier |
| product_name | Product name |
| category | Product category |
| brand | Brand name |

---

## 💰 Pricing (Raw)

**Source:** Parent Company  
**Load Type:** Full Load  
**Description:** Product pricing reference data.

| Column Name | Description |
|------------|-------------|
| product_id | Product reference |
| gross_price | Listed price |
| effective_dt | Price effective date |

---

## 🧾 Orders (Raw)

**Source:**  
- Parent Company – Full Load (historical)  
- Child Company – Incremental Load (daily)

**File Naming Convention (Incremental):**
```text
orders_YYYY_MM_DD.csv
```
---------------------------
### 📄 Sample Raw Order Data

| order_id | customer_id | product_id | order_date  | quantity | gross_price |
|---------:|-------------|------------|-------------|---------:|------------:|
| 10001    | C101        | P501       | 2025-09-01  | 2        | 120.50      |
| 10002    | C104        | P203       | 2025-09-01  | 1        | 75.00       |
| 10003    | C110        | P509       | 2025-09-01  | 4        | 210.00      |

> Sample shown for illustration only. Actual datasets contain significantly higher volumes.
---------------------------

**🔄 Data Processing Flow**
---------------------------

### **1️⃣ Setup Layer**

*   Catalog and schema initialization
    
*   Utility functions
    
*   Date dimension creation
    

### **2️⃣ Dimension Processing**

*   Customer dimension
    
*   Product dimension
    
*   Pricing dimension
    
*   Data standardization and validation
    

### **3️⃣ Fact Processing**

*   **Full Load**: Historical fact ingestion
    
*   **Incremental Load**: Daily order data ingestion
    
*   Handles late-arriving data and updates
    

### **4️⃣ Analytics & Dashboarding**

*   Denormalized fact table creation
    
*   Business KPIs and metrics
    
*   Dashboard-ready datasets
    

**🧪 Data Validation & Testing**
--------------------------------

Basic data quality checks are implemented, including:

*   Null checks
    
*   Schema validation
    
*   Record count validation
    
*   Incremental load consistency
    

Tests are available in the test/ directory.

**📊 Dashboard Output**
-----------------------

The final dashboard provides insights such as:

*   Daily and monthly sales trends
    
*   Product-wise revenue
    
*   Customer-level performance
    
*   Price impact analysis
    

A sample dashboard output is included in 2\_dashboarding/fmcg\_dashboard.pdf.

**🛠️ Tech Stack**
------------------

*   **Platform**: Databricks
    
*   **Language**: Python, SQL
    
*   **Storage Format**: CSV (raw), Delta (processed)
    
*   **Processing**: Spark
    
*   **Visualization**: SQL-based dashboards
    
*   **Version Control**: Git & GitHub
    

**⚠️ Notes on Data**
--------------------

*   Raw data files are **intentionally excluded** from version control
    
*   .gitignore is used to prevent committing large datasets
    
*   The repository focuses on **pipeline logic and architecture**
    

**🚀 Key Learnings**
--------------------

*   Designing scalable data pipelines
    
*   Handling incremental fact loads
    
*   Applying real-world data engineering best practices
    
*   Structuring Databricks projects professionally
    

**📌 Future Enhancements**
--------------------------

*   Automate pipelines using Databricks Workflows
    
*   Add advanced data quality checks (Great Expectations)
    
*   Implement Slowly Changing Dimensions (SCD)
    
*   Real-time ingestion using Kafka
