# SQL-Data-Data-Warehouse-Project
Welcome to the Data Warehouse and Analytics Project repository! 🚀
This repository presents an end-to-end data warehousing and analytics solution, demonstrating the process of designing, building, and analyzing a modern data warehouse to transform raw data into meaningful and actionable business insights.

---

## 📖 Project Overview

Welcome to the **Data Warehouse and Analytics Project** repository! 🚀  
This project demonstrates the development of a modern **data warehousing and analytics solution** using **Microsoft SQL Server**, covering the complete data lifecycle from data ingestion to analytics-ready datasets.

### 🏗️ Data Architecture
Designing a modern **Data Warehouse using the Medallion Architecture**, which includes:
- **Bronze Layer** – Raw data ingestion from source systems.
- **Silver Layer** – Data cleansing, transformation, and standardization.
- **Gold Layer** – Curated, business-ready data optimized for analytics and reporting.

### 🔄 ETL Pipelines
Building efficient **ETL (Extract, Transform, Load) pipelines** to move data from source systems into the data warehouse while ensuring data quality, consistency, and reliability.

### 📊 Data Modeling
Developing optimized **fact and dimension tables** using dimensional modeling techniques to support high-performance analytical queries.

### 📈 Analytics & Reporting
Creating **SQL-based reports and analytical queries** that transform processed data into **actionable insights** to support data-driven decision-making.

---

## 🚀 Project Requirements

### 🏗️ Building the Data Warehouse (Data Engineering)

#### Objective
Develop a modern **data warehouse using Microsoft SQL Server** to consolidate sales data from multiple systems, enabling **analytical reporting and data-driven decision-making**.

#### Specifications

**📂 Data Sources**
- Import data from two source systems:
  - **ERP system**
  - **CRM system**
- Data is provided as **CSV files**.

**🧹 Data Quality**
- Perform data cleansing to handle missing values, inconsistencies, and other **data quality issues** before loading the data into the warehouse.

**🔗 Data Integration**
- Integrate data from both systems into a **single, user-friendly data model** optimized for analytical queries and reporting.

**📅 Scope**
- Focus on processing and analyzing the **latest available dataset only**.
- **Historical tracking (data historization)** is not required for this project.

**📝 Documentation**
- Provide clear and structured **data model documentation** to support both **business stakeholders** and **analytics teams**.

---

### 📊 BI: Analytics & Reporting (Data Analysis)

#### Objective
Develop **SQL-based analytical queries and reports** to generate actionable insights into key business areas, including:

- **Customer Behavior**
- **Product Performance**
- **Sales Trends**

---

## 🏗️ Data Architecture

The data architecture for this project follows the **Medallion Architecture**, consisting of **Bronze, Silver, and Gold layers** to ensure a scalable and structured data processing workflow.

### 🥉 Bronze Layer – Raw Data
The **Bronze layer** stores raw data exactly as received from the source systems.  
Data from the **ERP and CRM systems** is ingested from **CSV files** and loaded into a **SQL Server database** without transformation. This layer serves as the foundation for further processing and ensures the original data is preserved.

### 🥈 Silver Layer – Cleaned & Standardized Data
The **Silver layer** focuses on improving data quality and preparing the data for analytical use. This includes:
- Data cleansing
- Standardization of formats
- Handling missing or inconsistent values
- Data normalization and transformation

This step ensures the data is **structured, reliable, and ready for modeling**.

### 🥇 Gold Layer – Business-Ready Data
The **Gold layer** contains **business-ready datasets** optimized for analytics and reporting.  
In this layer, the data is modeled using a **Star Schema**, which includes:
- **Fact tables** for measurable business events (e.g., sales)
- **Dimension tables** for descriptive attributes (e.g., customers, products)

This structure enables **fast and efficient analytical queries**.

---

## 🔗 Data Integration

To understand how data flows and integrates across different layers and tables, the following **data integration architecture diagram** illustrates the relationships and movement of data throughout the system.

![Data Integration Architecture](docs/data_integration.png)

---

## 📊 Data Modeling

After loading raw data into the **Bronze layer** and transforming it within the **Silver layer**, the **Gold layer** implements a **dimensional data model** using a **Star Schema**.

The model consists of:
- A central **Fact Table** containing transactional sales data
- Multiple **Dimension Tables** such as customers, products, and dates

This model is designed to support **high-performance analytical queries and business intelligence reporting**.

![Data Model](docs/data_model.png)

---

## 🔄 Data Flow

The following diagram illustrates the **end-to-end data flow**, from raw data ingestion to the final analytics-ready datasets.

