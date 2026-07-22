# Profiling Report: ontology.dim_customer

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Table Name | ontology.dim_customer |
| Row Count | 8 |
| Column Count | 8 |
| Primary Key Duplicate Count | 0 |
| Missing Data Columns | 0 of 8 |
| Database Type | PostgreSQL |

## Column Summary

| Column Name | Data Type | Nullable | Distinct Count | Null Count | Null % | Min | Max | Average |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| customer_key | integer | NO | 8 | 0 | 0.00 | 1 | 8 | 4.50 |
| customer_id | character varying | NO | 8 | 0 | 0.00 |  |  |  |
| customer_name | character varying | YES | 8 | 0 | 0.00 |  |  |  |
| segment | character varying | YES | 3 | 0 | 0.00 |  |  |  |
| industry | character varying | YES | 3 | 0 | 0.00 |  |  |  |
| account_tier | character varying | YES | 2 | 0 | 0.00 |  |  |  |
| hq_country | character varying | YES | 5 | 0 | 0.00 |  |  |  |
| hq_region | character varying | YES | 3 | 0 | 0.00 |  |  |  |

## Column Data Types

| Data Type | Column Count |
| --- | --- |
| integer | 1 |
| character varying | 7 |

## NULL Statistics

| Column Name | Non-Null Count | Null Count | Null % |
| --- | --- | --- | --- |
| customer_key | 8 | 0 | 0.00 |
| customer_id | 8 | 0 | 0.00 |
| customer_name | 8 | 0 | 0.00 |
| segment | 8 | 0 | 0.00 |
| industry | 8 | 0 | 0.00 |
| account_tier | 8 | 0 | 0.00 |
| hq_country | 8 | 0 | 0.00 |
| hq_region | 8 | 0 | 0.00 |

## Distinct Value Statistics

| Column Name | Distinct Count | Duplicate Value Count* |
| --- | --- | --- |
| customer_key | 8 | 0 |
| customer_id | 8 | 0 |
| customer_name | 8 | 0 |
| segment | 3 | 5 |
| industry | 3 | 5 |
| account_tier | 2 | 6 |
| hq_country | 5 | 3 |
| hq_region | 3 | 5 |

*Duplicate Value Count = Row Count - Distinct Count.

## Value Distribution Summary

### segment

| Value | Frequency |
| --- | --- |
| Service Provider | 6 |
| Enterprise | 1 |
| Public Sector | 1 |

### industry

| Value | Frequency |
| --- | --- |
| Telecommunications | 6 |
| Financial Services | 1 |
| Government | 1 |

### account_tier

| Value | Frequency |
| --- | --- |
| Growth | 4 |
| Strategic | 4 |

### hq_country

| Value | Frequency |
| --- | --- |
| United States | 4 |
| Germany | 1 |
| India | 1 |
| Japan | 1 |
| United Kingdom | 1 |

### hq_region

| Value | Frequency |
| --- | --- |
| Americas | 4 |
| APJC | 2 |
| EMEA | 2 |

## Numeric Statistics

| Column Name | Min | Max | Average | Distinct Count |
| --- | --- | --- | --- | --- |
| customer_key | 1 | 8 | 4.50 | 8 |

## Date Statistics

No date columns in this table.

## Text Statistics

| Column Name | Min Length | Max Length | Avg Length |
| --- | --- | --- | --- |
| customer_id | 9 | 9 | 9.00 |
| customer_name | 3 | 26 | 11.25 |
| segment | 10 | 16 | 14.88 |
| industry | 10 | 18 | 17.00 |
| account_tier | 6 | 9 | 7.50 |
| hq_country | 5 | 14 | 10.38 |
| hq_region | 4 | 8 | 6.00 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with Nulls | 0 |
| Fully Populated Columns | 8 |
| Table Completeness % | 100.00 |

## Data Quality Summary

| Check | Result |
| --- | --- |
| Table Exists | Pass |
| Primary Key Duplicates | Pass |
| Null Primary Key | Pass |
| Any Missing Data | Pass |
| Dominant Segment | Service Provider (75.00%) |
| Geographic Spread | 5 countries across 3 regions |

## Observations

| Observation Type | Details |
| --- | --- |
| Grain | Appears to be one row per customer |
| Key Quality | customer_key and customer_id are unique and complete |
| Segment Skew | Service Provider dominates the customer base |
| Industry Pattern | Telecommunications dominates and aligns with segment skew |
| Regional Mix | Americas leads, with APJC and EMEA balanced at lower volume |
