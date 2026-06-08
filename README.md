# SQL-Bookstore-Analysis
# 📚 Online Bookstore Database Project

## Overview
This project focuses on building a relational database for an online bookstore using SQL. The goal is to take raw data from 3 CSV files (`Books`, `Customers`, and `Orders`), structure them into connected database tables, and run queries to analyze sales and inventory.

---

## Tech Stack & Tools
* **Database Engine:** MySQL
* **Development Environment:** MySQL Workbench

### Core SQL Concepts Applied
* Creating tables and defining relationships (DDL)
* Importing data from CSV files
* Basic data retrieval and multi-table `JOIN` operations
* Grouping and Data Aggregations (`COUNT`, `SUM`, `AVG`)

---

## Database Schema (ERD)

This repository structures 3 core CSV data files into a connected relational model using Primary Keys (PK) and Foreign Keys (FK).

```mermaid
erDiagram
    BOOKS {
        int Book_ID PK
        string Title
        string Author
        float Price
        string Genre
        int Stock_Quantity
    }
    CUSTOMERS {
        int Customer_ID PK
        string Name
        string Email
        string Phone
    }
    ORDERS {
        int Order_ID PK
        int Customer_ID FK
        int Book_ID FK
        int Quantity
        date Order_Date
    }

    CUSTOMERS ||--o{ ORDERS : places
    BOOKS ||--o{ ORDERS : contains
```

---

## Database Source Code
The complete, ready-to-run SQL scripts for this project are organized into separate files for easy navigation:
* **Table Creation & Schema Setup:** [`01_schema_setup.sql`](./scripts/01_schema_setup.sql)
* **Data Analysis & Business Queries:** [`02_eda_queries.sql`](./scripts/02_eda_queries.sql)

---

##  Key Business Questions Addressed

By executing the queries in this repository, the following business objectives are accomplished:

1. **Data Integrity Audit:** Checking for missing or null values in critical fields across all tables.
2. **Inventory Management:** Assessing the overall stock distribution and tracking available inventory by book genre.
3. **Sales Performance:** Calculating total order volumes, tracking individual customer purchases, and monitoring total gross revenue.
4.


