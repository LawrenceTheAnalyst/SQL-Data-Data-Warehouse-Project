# Naming Conventions

This document defines the naming conventions used for schemas, tables, views, columns, stored procedures, and other database objects in the data warehouse.

---

# Table of Contents
- General Principles
- Table Naming Conventions
  - Bronze Rules
  - Silver Rules
  - Gold Rules
- Column Naming Conventions
  - Surrogate Keys
  - Technical Columns
- Stored Procedures

---

# General Principles

**Naming Style**  
All database object names must use **snake_case**, written in lowercase with underscores (`_`) separating words.

**Language**  
All names must be written in **English**.

**Reserved Words**  
Avoid using **SQL reserved keywords** as object names.

---

# Table Naming Conventions

## Bronze Rules

Tables in the **Bronze layer** must start with the **source system name**, and the table name must match the original source table name without modification.

**Pattern**

<sourcesystem>_<entity>


**Definitions**

- `<sourcesystem>` : Name of the source system (e.g., `crm`, `erp`)
- `<entity>` : Exact table name from the source system

**Example**

crm_customer_info


Represents customer information extracted from the CRM system.

---

## Silver Rules

Tables in the **Silver layer** follow the same naming structure as the Bronze layer to maintain traceability to the original source tables.

**Pattern**

<sourcesystem>_<entity>


**Definitions**

- `<sourcesystem>` : Name of the source system (e.g., `crm`, `erp`)
- `<entity>` : Exact table name from the source system

**Example**

crm_customer_info


Represents cleansed and transformed customer information originating from the CRM system.

---

## Gold Rules

Tables in the **Gold layer** use **business-friendly names** aligned with analytical and reporting requirements.

**Pattern**

<category>_<entity>


**Definitions**

- `<category>` : Describes the role of the table (e.g., `dim`, `fact`)
- `<entity>` : Business-related entity name (e.g., customers, products, sales)

**Examples**

dim_customers
fact_sales


- `dim_customers` → Dimension table containing customer attributes  
- `fact_sales` → Fact table storing sales transactions

---

# Glossary of Category Patterns

| Pattern | Meaning | Example |
|--------|--------|--------|
| dim_ | Dimension table | dim_customer, dim_product |
| fact_ | Fact table | fact_sales |
| agg_ | Aggregated table | agg_customers, agg_sales_monthly |

---

# Column Naming Conventions

## Surrogate Keys

All **primary keys in dimension tables** must use the suffix `_key`.

**Pattern**

<table_name>_key

**Definitions**

- `<table_name>` : Name of the entity or table
- `_key` : Indicates the column is a surrogate key

**Example**

customer_key

Represents the surrogate key in the `dim_customers` table.

---

## Technical Columns

Technical metadata columns must start with the prefix `dwh_`.

**Pattern**

dwh_<column_name>

Stores the timestamp when the record was loaded into the data warehouse.

---

# Stored Procedures

Stored procedures used for loading data into the warehouse must follow the pattern below.

**Pattern**
load_<layer>


**Definitions**

- `<layer>` : Data warehouse layer being loaded (`bronze`, `silver`, or `gold`)

**Examples**


load_bronze
load_silver


- `load_bronze` → Loads raw data into the Bronze layer  
- `load_silver` → Loads cleansed and transformed data into the Silver layer
