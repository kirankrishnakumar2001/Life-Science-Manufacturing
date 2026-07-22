# Overall Profiling Summary

## Repository Output

| File Name | Table Covered |
| --- | --- |
| profiling_dim_contract.md | ontology.dim_contract |
| profiling_dim_customer.md | ontology.dim_customer |
| profiling_dim_date.md | ontology.dim_date |
| profiling_dim_geography.md | ontology.dim_geography |
| profiling_dim_partner.md | ontology.dim_partner |
| profiling_dim_product.md | ontology.dim_product |
| profiling_dim_sales_rep.md | ontology.dim_sales_rep |
| profiling_fact_bookings.md | ontology.fact_bookings |

## Database Summary

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Database Type | PostgreSQL |
| Schema Profiled | ontology |
| Tables Profiled | 8 |
| Total Columns Profiled | 61 |
| Tables Verified Present | 8 |

## Table-Level Overview

| Table Name | Row Count | Column Count | PK Duplicate Count | Columns With Nulls | Completeness % |
| --- | --- | --- | --- | --- | --- |
| ontology.dim_contract | 6 | 5 | 0 | 0 | 100.00 |
| ontology.dim_customer | 8 | 8 | 0 | 0 | 100.00 |
| ontology.dim_date | 12 | 7 | 0 | 0 | 100.00 |
| ontology.dim_geography | 8 | 4 | 0 | 0 | 100.00 |
| ontology.dim_partner | 6 | 6 | 0 | 0 | 100.00 |
| ontology.dim_product | 10 | 7 | 0 | 0 | 100.00 |
| ontology.dim_sales_rep | 6 | 6 | 0 | 0 | 100.00 |
| ontology.fact_bookings | 10 | 18 | 0 | 0 | 100.00 |

## Cross-Table Data Quality Highlights

| Quality Check | Result |
| --- | --- |
| Missing Required GitHub Inputs | Not detected |
| Database Connection | Successful |
| Table Existence Validation | Successful for all 8 requested tables |
| Primary Key Duplicate Check | 0 duplicates across all profiled tables |
| Null Completeness | No nulls detected in any profiled column |
| Referential Model Context | 7 foreign key relationships into fact_bookings |

## Business Pattern Highlights

| Area | Observation |
| --- | --- |
| Customers | Customer base is dominated by Service Provider and Telecommunications segments |
| Products | Hardware and Security-oriented offerings are most represented |
| Partners | Reseller-oriented routes dominate partner distribution |
| Sales | Service Provider coverage dominates the sales team sample |
| Geography | Fact table activity is concentrated in a single geography_key |
| Bookings | New bookings exceed renewals, 60% vs 40% |

## Files Written to GitHub

All profiling reports were written to:

`kirankrishnakumar2001/Life-Science-Manufacturing/main/Life Science Manufacturing/Outputs/DI Data Profiler Agent`
