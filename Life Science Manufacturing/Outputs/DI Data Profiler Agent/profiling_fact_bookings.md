# Profiling Report: ontology.fact_bookings

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Table Name | ontology.fact_bookings |
| Row Count | 10 |
| Column Count | 18 |
| Primary Key Duplicate Count | 0 |
| Missing Data Columns | 0 of 18 |
| Database Type | PostgreSQL |

## Column Summary

| Column Name | Data Type | Nullable | Distinct Count | Null Count | Null % | Min | Max | Average |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| booking_id | integer | NO | 10 | 0 | 0.00 | 1 | 10 | 5.50 |
| order_number | character varying | YES | 10 | 0 | 0.00 |  |  |  |
| order_line_number | integer | YES | 1 | 0 | 0.00 | 1 | 1 | 1.00 |
| date_key | integer | YES | 7 | 0 | 0.00 | 20241215 | 20260615 | 20250795.00 |
| customer_key | integer | YES | 2 | 0 | 0.00 | 1 | 2 | 1.30 |
| product_key | integer | YES | 5 | 0 | 0.00 | 1 | 10 | 3.60 |
| partner_key | integer | YES | 3 | 0 | 0.00 | 1 | 4 | 1.60 |
| geography_key | integer | YES | 1 | 0 | 0.00 | 1 | 1 | 1.00 |
| sales_rep_key | integer | YES | 2 | 0 | 0.00 | 1 | 2 | 1.30 |
| contract_key | integer | YES | 2 | 0 | 0.00 | 1 | 5 | 2.20 |
| booking_type | character varying | YES | 2 | 0 | 0.00 |  |  |  |
| is_renewal | integer | YES | 2 | 0 | 0.00 | 0 | 1 | 0.40 |
| quantity | integer | YES | 7 | 0 | 0.00 | 4 | 250 | 98.20 |
| unit_list_price_usd | numeric | YES | 5 | 0 | 0.00 | 8000.00 | 50000.00 | 22400.00 |
| discount_pct | numeric | YES | 7 | 0 | 0.00 | 0.11 | 0.28 | 0.18 |
| booking_amount_usd | numeric | YES | 10 | 0 | 0.00 | 130000.00 | 2670000.00 | 900500.00 |
| acv_usd | numeric | YES | 10 | 0 | 0.00 | 43333.00 | 2670000.00 | 545700.00 |
| tcv_usd | numeric | YES | 10 | 0 | 0.00 | 130000.00 | 2670000.00 | 900500.00 |

## Column Data Types

| Data Type | Column Count |
| --- | --- |
| integer | 9 |
| character varying | 2 |
| numeric | 5 |

## NULL Statistics

| Column Name | Non-Null Count | Null Count | Null % |
| --- | --- | --- | --- |
| booking_id | 10 | 0 | 0.00 |
| order_number | 10 | 0 | 0.00 |
| order_line_number | 10 | 0 | 0.00 |
| date_key | 10 | 0 | 0.00 |
| customer_key | 10 | 0 | 0.00 |
| product_key | 10 | 0 | 0.00 |
| partner_key | 10 | 0 | 0.00 |
| geography_key | 10 | 0 | 0.00 |
| sales_rep_key | 10 | 0 | 0.00 |
| contract_key | 10 | 0 | 0.00 |
| booking_type | 10 | 0 | 0.00 |
| is_renewal | 10 | 0 | 0.00 |
| quantity | 10 | 0 | 0.00 |
| unit_list_price_usd | 10 | 0 | 0.00 |
| discount_pct | 10 | 0 | 0.00 |
| booking_amount_usd | 10 | 0 | 0.00 |
| acv_usd | 10 | 0 | 0.00 |
| tcv_usd | 10 | 0 | 0.00 |

## Distinct Value Statistics

| Column Name | Distinct Count | Duplicate Value Count* |
| --- | --- | --- |
| booking_id | 10 | 0 |
| order_number | 10 | 0 |
| order_line_number | 1 | 9 |
| date_key | 7 | 3 |
| customer_key | 2 | 8 |
| product_key | 5 | 5 |
| partner_key | 3 | 7 |
| geography_key | 1 | 9 |
| sales_rep_key | 2 | 8 |
| contract_key | 2 | 8 |
| booking_type | 2 | 8 |
| is_renewal | 2 | 8 |
| quantity | 7 | 3 |
| unit_list_price_usd | 5 | 5 |
| discount_pct | 7 | 3 |
| booking_amount_usd | 10 | 0 |
| acv_usd | 10 | 0 |
| tcv_usd | 10 | 0 |

*Duplicate Value Count = Row Count - Distinct Count.

## Value Distribution Summary

### booking_type

| Value | Frequency |
| --- | --- |
| New | 6 |
| Renewal | 4 |

## Numeric Statistics

| Column Name | Min | Max | Average | Distinct Count |
| --- | --- | --- | --- | --- |
| booking_id | 1 | 10 | 5.50 | 10 |
| order_line_number | 1 | 1 | 1.00 | 1 |
| date_key | 20241215 | 20260615 | 20250795.00 | 7 |
| customer_key | 1 | 2 | 1.30 | 2 |
| product_key | 1 | 10 | 3.60 | 5 |
| partner_key | 1 | 4 | 1.60 | 3 |
| geography_key | 1 | 1 | 1.00 | 1 |
| sales_rep_key | 1 | 2 | 1.30 | 2 |
| contract_key | 1 | 5 | 2.20 | 2 |
| is_renewal | 0 | 1 | 0.40 | 2 |
| quantity | 4 | 250 | 98.20 | 7 |
| unit_list_price_usd | 8000.00 | 50000.00 | 22400.00 | 5 |
| discount_pct | 0.11 | 0.28 | 0.18 | 7 |
| booking_amount_usd | 130000.00 | 2670000.00 | 900500.00 | 10 |
| acv_usd | 43333.00 | 2670000.00 | 545700.00 | 10 |
| tcv_usd | 130000.00 | 2670000.00 | 900500.00 | 10 |

## Date Statistics

No native date columns in this table. date_key appears to reference ontology.dim_date.

## Text Statistics

| Column Name | Min Length | Max Length | Avg Length |
| --- | --- | --- | --- |
| order_number | 8 | 8 | 8.00 |
| booking_type | 3 | 7 | 4.60 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with Nulls | 0 |
| Fully Populated Columns | 18 |
| Table Completeness % | 100.00 |

## Data Quality Summary

| Check | Result |
| --- | --- |
| Table Exists | Pass |
| Primary Key Duplicates | Pass |
| Null Primary Key | Pass |
| Any Missing Data | Pass |
| Booking Type Mix | New 60.00%, Renewal 40.00% |
| Renewal Indicator Average | 0.40 |
| Geography Concentration | All rows map to geography_key = 1 |

## Observations

| Observation Type | Details |
| --- | --- |
| Grain | Appears to be one row per booking transaction line |
| Key Quality | booking_id is unique and complete |
| Concentration Risk | geography_key has only one distinct value across all 10 rows |
| Customer Mix | Only 2 customers appear in the sample fact table |
| Order Pattern | order_line_number is constant at 1 for all rows |
| Financial Spread | booking_amount_usd ranges from 130000.00 to 2670000.00 |
| Revenue Shape | acv_usd is lower than tcv_usd on average, consistent with annualized contract logic |
