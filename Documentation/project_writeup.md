# BrightLearn Data Engineering Project 1
## Snowflake Sales Data Engineering & Analytics

## 1. Project Overview

This project demonstrates a complete Snowflake-based data engineering and analytics workflow using customer, product, and order data.

The objective was to load structured CSV datasets into Snowflake, create appropriately typed relational tables, validate the loaded data, combine datasets using SQL joins, calculate revenue, and produce business-focused analytical queries.

The project was completed using Snowflake as the required data platform.

---

## 2. Business Problem

A business has separate datasets containing customer information, product information, and sales transactions.

Although the datasets contain useful information individually, business insights require these datasets to be connected.

This project creates a relational data model that connects customers and products to order transactions. This makes it possible to answer questions such as:

- What products were purchased?
- Which customers generated the most revenue?
- Which product categories generated the most revenue?
- Who are the top five customers by total spending?

The resulting SQL analysis provides a foundation for understanding sales performance and supporting business decision-making.

---

## 3. Data Sources

The project uses three CSV datasets:

### customers.csv

Contains customer information.

| Column | Description |
|---|---|
| customer_id | Unique customer identifier |
| customer_name | Customer name |
| email | Customer email address |
| province | Customer province |
| signup_date | Customer registration date |

Expected records: **50 customers**

---

### products.csv

Contains product information.

| Column | Description |
|---|---|
| product_id | Unique product identifier |
| product_name | Product name |
| category | Product category |
| unit_price | Product selling price |

Expected records: **20 products**

---

### orders.csv

Contains sales transaction information.

| Column | Description |
|---|---|
| order_id | Unique order identifier |
| customer_id | Customer associated with the order |
| product_id | Product associated with the order |
| order_date | Date the order was placed |
| quantity | Quantity purchased |

Expected records: **150 orders**

---

## 4. Snowflake Data Model

The project uses three relational tables:

```text
CUSTOMERS
    |
    | customer_id
    |
    v
ORDERS
    |
    | product_id
    |
    v
PRODUCTS
