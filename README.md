# Customer Data Warehouse with Historical Tracking

A customer analytics warehouse project that supports incremental loading, historical tracking, and downstream reporting for churn, active subscriptions, and revenue analysis.

## Project Overview

This project simulates a modern warehouse modeling workflow for customer and subscription data. It ingests operational datasets, loads them into a warehouse-style environment, applies incremental and history-preserving transformations, and publishes reporting-ready marts for downstream analysis.

The goal of this project is to demonstrate practical junior data engineering skills in:
- incremental data loading
- historical warehouse modeling
- SCD Type 2 implementation
- workflow orchestration
- data testing
- analytics-ready warehouse design

## Business Problem

Customer and subscription data changes frequently, but analytics teams often only have access to the latest record state. Without historical tracking, it becomes difficult to analyze customer behavior over time or understand important business events such as plan changes, churn, and retention.

This project solves that problem by building a structured warehouse workflow that:
- ingests customer and subscription datasets
- preserves record history over time
- standardizes and validates source data
- transforms data into clean staging and business-ready marts
- supports downstream churn, retention, and revenue analysis

## What This Project Demonstrates

- Incremental warehouse loading
- Historical data modeling using SCD Type 2 patterns
- Airflow-based orchestration
- dbt modeling with staging, snapshots, and mart layers
- Source-to-target reconciliation
- Data quality validation
- Reproducible local development with Docker

## Architecture

Operational Source Tables -> Python Ingestion -> PostgreSQL -> Airflow Orchestration -> dbt Snapshots and Models -> Historical Warehouse Tables -> Analytics Marts -> Reporting

## Tech Stack

- Python
- SQL
- PostgreSQL
- Apache Airflow
- dbt
- Docker
- Great Expectations or Soda
- Git / GitHub

## Datasets

- Customer dataset: `<dataset-link>`
- Subscription dataset: `<dataset-link>`
- Payment dataset: `<dataset-link>`

## Key Features

- Incremental loading of customer and subscription data
- Historical tracking using SCD Type 2 logic
- dbt snapshots for change preservation
- Source-to-target validation and reconciliation checks
- Analytics-ready marts for churn, revenue, and subscription analysis
- Reproducible local setup for warehouse development

## Data Model

Example marts included in this project:
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
│   ├── dags/
│   └── logs/
├── dbt/
│   ├── models/
│   │   ├── staging/
│   │   ├── intermediate/
│   │   └── marts/
│   ├── snapshots/
│   └── tests/
├── data/
│   ├── source/
│   └── warehouse/
├── ingestion/
│   ├── extract/
│   ├── load/
│   └── utils/
├── docs/
├── docker-compose.yml
└── README.md
