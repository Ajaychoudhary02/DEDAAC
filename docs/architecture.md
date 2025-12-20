# Enterprise Sales & User Analytics Platform – Architecture

## Overview
This project implements an end-to-end data platform to support both
sales analytics and user behavior analytics for an e-commerce business.
The platform processes batch and event-based data using a cloud-native
lakehouse architecture.

## Technology Stack
- Databricks (PySpark, Delta Lake)
- Snowflake (Cloud Data Warehouse)
- Airflow (Orchestration)
- Tableau / Power BI (BI)
- GitHub (Version Control)

## Data Sources

### Sales Data
- Orders (CSV / JSON)
- Customers (CSV)
- Products (CSV)

### User Behavior Events
- LOGIN
- ADD_TO_CART
- PURCHASE
- CART_ABANDONED

User behavior data is captured at event level to enable funnel and
conversion analysis.

## Architecture Flow

Data flows through the following layers:

1. Bronze Layer (Raw)
   - Raw sales and user event data ingested into Delta tables
   - No transformations applied

2. Silver Layer (Cleaned)
   - Data cleansing and validation using PySpark
   - Duplicate removal, null handling, data type casting
   - Revenue calculation for sales

3. Gold Layer (Business)
   - Fact and dimension tables created
   - Aggregated and analytics-ready datasets

4. Snowflake
   - Curated tables loaded for BI and ad-hoc analytics

## Data Model

### Fact Tables
- FACT_SALES
- FACT_USER_EVENTS

### Dimension Tables
- DIM_CUSTOMER
- DIM_PRODUCT
- DIM_DATE
- DIM_REGION

## Data Quality Strategy

- Mandatory field checks (order_id, user_id)
- Business rule validation (quantity > 0, price > 0)
- Duplicate detection and removal
- Event validation for user behavior data

## Analytics Use Cases

### Sales Analytics
- Daily and monthly revenue
- Top selling products
- Revenue by region

### User Analytics
- Daily active users
- Add-to-cart rate
- Purchase conversion rate
- Cart abandonment analysis
