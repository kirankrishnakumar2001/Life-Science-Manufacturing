# Profiling Report: ontology.fact_bookings

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Schema | ontology |
| Table Name | fact_bookings |
| Full Table Name | ontology.fact_bookings |
| Row Count | 10 |
| Column Count | 18 |
| Primary Key Duplicate Count | 0 |

## Column Profile Summary

| Column Name | Data Type | Nullable | Distinct Count | NULL Count | NULL % |
| --- | --- | --- | ---: | ---: | ---: |
| booking_id | integer | NO | 10 | 0 | 0.00% |
| order_number | character varying | YES | 10 | 0 | 0.00% |
| order_line_number | integer | YES | 1 | 0 | 0.00% |
| date_key | integer | YES | 7 | 0 | 0.00% |
| customer_key | integer | YES | 2 | 0 | 0.00% |
| product_key | integer | YES | 5 | 0 | 0.00% |
| partner_key | integer | YES | 3 | 0 | 0.00% |
| geography_key | integer | YES | 1 | 0 | 0.00% |
| sales_rep_key | integer | YES | 2 | 0 | 0.00% |
| contract_key | integer | YES | 2 | 0 | 0.00% |
| booking_type | character varying | YES | 2 | 0 | 0.00% |
| is_renewal | integer | YES | 2 | 0 | 0.00% |
| quantity | integer | YES | 7 | 0 | 0.00% |
| unit_list_price_usd | numeric | YES | 5 | 0 | 0.00% |
| discount_pct | numeric | YES | 7 | 0 | 0.00% |
| booking_amount_usd | numeric | YES | 10 | 0 | 0.00% |
| acv_usd | numeric | YES | 10 | 0 | 0.00% |
| tcv_usd | numeric | YES | 10 | 0 | 0.00% |

## Column Data Types

| Data Type | Columns |
| --- | --- |
| integer | booking_id, order_line_number, date_key, customer_key, product_key, partner_key, geography_key, sales_rep_key, contract_key, is_renewal, quantity |
| character varying | order_number, booking_type |
| numeric | unit_list_price_usd, discount_pct, booking_amount_usd, acv_usd, tcv_usd |

## Numeric Statistics

| Column | Min | Max | Avg |
| --- | ---: | ---: | ---: |
| booking_id | 1 | 10 | 5.50 |
| order_line_number | 1 | 1 | 1.00 |
| date_key | 20241215 | 20260615 | 20250795.00 |
| customer_key | 1 | 2 | 1.30 |
| product_key | 1 | 10 | 3.60 |
| partner_key | 1 | 4 | 1.60 |
| geography_key | 1 | 1 | 1.00 |
| sales_rep_key | 1 | 2 | 1.30 |
| contract_key | 1 | 5 | 2.20 |
| is_renewal | 0 | 1 | 0.40 |
| quantity | 4 | 250 | 98.20 |
| unit_list_price_usd | 8000.00 | 50000.00 | 22400.00 |
| discount_pct | 0.11 | 0.28 | 0.18 |
| booking_amount_usd | 130000.00 | 2670000.00 | 900500.00 |
| acv_usd | 43333.00 | 2670000.00 | 545700.00 |
| tcv_usd | 130000.00 | 2670000.00 | 900500.00 |

## Text Statistics

| Column | Min Length | Max Length | Avg Length |
| --- | ---: | ---: | ---: |
| order_number | 8 | 8 | 8.00 |
| booking_type | 3 | 7 | 4.60 |

## Value Distribution Summary

### booking_type

| Value | Frequency |
| --- | ---: |
| New | 6 |
| Renewal | 4 |

### is_renewal

| Value | Frequency |
| --- | ---: |
| 0 | 6 |
| 1 | 4 |

## NULL Statistics

| Column | NULL Count | NULL % |
| --- | ---: | ---: |
| booking_id | 0 | 0.00% |
| order_number | 0 | 0.00% |
| order_line_number | 0 | 0.00% |
| date_key | 0 | 0.00% |
| customer_key | 0 | 0.00% |
| product_key | 0 | 0.00% |
| partner_key | 0 | 0.00% |
| geography_key | 0 | 0.00% |
| sales_rep_key | 0 | 0.00% |
| contract_key | 0 | 0.00% |
| booking_type | 0 | 0.00% |
| is_renewal | 0 | 0.00% |
| quantity | 0 | 0.00% |
| unit_list_price_usd | 0 | 0.00% |
| discount_pct | 0 | 0.00% |
| booking_amount_usd | 0 | 0.00% |
| acv_usd | 0 | 0.00% |
| tcv_usd | 0 | 0.00% |

## Distinct Value Statistics

| Column | Distinct Count |
| --- | ---: |
| booking_id | 10 |
| order_number | 10 |
| order_line_number | 1 |
| date_key | 7 |
| customer_key | 2 |
| product_key | 5 |
| partner_key | 3 |
| geography_key | 1 |
| sales_rep_key | 2 |
| contract_key | 2 |
| booking_type | 2 |
| is_renewal | 2 |
| quantity | 7 |
| unit_list_price_usd | 5 |
| discount_pct | 7 |
| booking_amount_usd | 10 |
| acv_usd | 10 |
| tcv_usd | 10 |

## Duplicate Statistics

| Check | Result |
| --- | ---: |
| Duplicate booking_id values | 0 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with any NULLs | 0 |
| Total NULL cells | 0 |
| Completeness Status | Complete |

## Data Quality Summary

| Indicator | Observation |
| --- | --- |
| Primary key uniqueness | booking_id is fully unique |
| Completeness | No missing values detected across 18 columns |
| Renewal consistency | booking_type and is_renewal distributions align at 6 new vs 4 renewal |
| Distribution note | geography_key is constant at 1; customer_key and sales_rep_key have low cardinality |
| Financial range | booking_amount_usd ranges from 130,000 to 2,670,000 |
| Quality assessment | Complete fact table with unique booking identifiers and concentrated dimensional usage |
