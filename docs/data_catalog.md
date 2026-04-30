# Data Catalog for Gold Layer

## Overview

The Gold Layer is the business-level data representation, structured to support analytical and reporting use cases. It consists of dimension tables and fact tables for business metrics and reporting.

---

# 1. gold.dim_customers

## Purpose
Stores customer details enriched with demographic and geographic data.

## Columns

| Column Name | Data Type | Description |
|---|---|---|
| customer_key | INT | Surrogate key uniquely identifying each customer record in the dimension table. |
| customer_id | INT | Unique numerical identifier assigned to each customer. |
| customer_number | NVARCHAR(50) | Alphanumeric identifier representing the customer. |
| first_name | NVARCHAR(50) | Customer's first name. |
| last_name | NVARCHAR(50) | Customer's last name or family name. |
| country | NVARCHAR(50) | Country of residence of the customer. |
| marital_status | NVARCHAR(50) | Marital status of the customer. |
| gender | NVARCHAR(50) | Gender of the customer. |
| birthdate | DATE | Customer birth date in YYYY-MM-DD format. |
| create_date | DATE | Date when the customer record was created. |

---

# 2. gold.dim_products

## Purpose
Provides product-related information and attributes.

## Columns

| Column Name | Data Type | Description |
|---|---|---|
| product_key | INT | Surrogate key uniquely identifying each product record. |
| product_id | INT | Unique identifier assigned to the product. |
| product_number | NVARCHAR(50) | Alphanumeric product code. |
| product_name | NVARCHAR(50) | Descriptive name of the product. |
| category_id | NVARCHAR(50) | Identifier for the product category. |
| category | NVARCHAR(50) | High-level classification of the product. |
| subcategory | NVARCHAR(50) | Detailed product classification. |
| maintenance_required | NVARCHAR(50) | Indicates whether maintenance is required. |
| cost | INT | Product base price or cost. |
| product_line | NVARCHAR(50) | Product line or series. |
| start_date | DATE | Date product became available. |

---

# 3. gold.fact_sales

## Purpose
Stores transactional sales data for analytics and reporting.

## Columns

| Column Name | Data Type | Description |
|---|---|---|
| order_number | NVARCHAR(50) | Unique identifier for each sales order. |
| product_key | INT | Foreign key linking to product dimension. |
| customer_key | INT | Foreign key linking to customer dimension. |
| order_date | DATE | Date order was placed. |
| shipping_date | DATE | Date order was shipped. |
| due_date | DATE | Payment due date. |
| sales_amount | INT | Total sales amount. |
| quantity | INT | Number of units sold. |
| price | INT | Price per product unit. |

---
