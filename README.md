
## 2) `customer-data-warehouse-historical-tracking`

```markdown
# Customer Data Warehouse with Historical Tracking

A customer analytics warehouse project that supports incremental loading, historical tracking, and downstream reporting for churn, active subscriptions, and revenue analysis.

## Project Overview

This project focuses on warehouse modeling for customer and subscription data with an emphasis on preserving historical changes over time.

The project demonstrates how to build a warehouse that does more than store the latest customer state. It captures changes in customer or subscription attributes and makes those changes available for analytics through historical tables and reporting marts.

## Business Problem

Customer and subscription data changes frequently. If analytics systems only store the latest state, teams lose important historical context needed for:
- churn analysis
- subscription lifecycle tracking
- customer plan changes
- retention analysis
- revenue trend reporting

This project addresses that by building a warehouse with incremental loading and historical tracking logic.

## What This Project Demonstrates

- Incremental data loading
- Historical warehouse modeling
- SCD Type 2 design patterns
- Source-to-target reconciliation
- Customer and subscription analytics marts
- Data quality validation for warehouse reliability

## Architecture

Operational Source Tables -> Incremental Extraction -> Warehouse Load -> Historical Modeling -> Analytics Marts -> Reporting

## Tech Stack

- Python
- SQL
- PostgreSQL
- Apache Airflow
- dbt
- Great Expectations or Soda
- Docker
- Git / GitHub

## Core Use Cases

- Track customer attribute changes over time
- Track subscription status and plan history
- Preserve business history for downstream reporting
- Support churn and retention analytics
- Build revenue and active-subscription marts

## Key Features

- Incremental load logic for customer and subscription data
- Historical tracking using SCD Type 2 patterns
- dbt-based transformation workflow
- Source-to-target validation checks
- Reporting-ready marts for churn, revenue, and subscription status

## Example Data Model

Core tables may include:
- `stg_customers`
- `stg_subscriptions`
- `stg_payments`
- `dim_customers_hist`
- `dim_subscriptions_hist`
- `fct_payments`
- `mart_active_subscriptions`
- `mart_churn_analysis`
- `mart_revenue_trends`

## Repository Structure

```text
customer-data-warehouse-historical-tracking/
├── airflow/
│   └── dags/
├── dbt/
│   ├── models/
│   │   ├── staging/
│   │   ├── snapshots/
│   │   └── marts/
│   └── tests/
├── ingestion/
│   ├── extract/
│   ├── transform/
│   └── load/
├── data/
│   ├── source/
│   └── warehouse/
├── docs/
├── docker-compose.yml
└── README.md
