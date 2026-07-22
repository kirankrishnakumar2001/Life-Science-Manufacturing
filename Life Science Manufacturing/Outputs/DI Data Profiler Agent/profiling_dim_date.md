# Profiling Report: ontology.dim_date

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Table Name | ontology.dim_date |
| Row Count | 12 |
| Column Count | 7 |
| Primary Key Duplicate Count | 0 |
| Missing Data Columns | 0 of 7 |
| Database Type | PostgreSQL |

## Column Summary

| Column Name | Data Type | Nullable | Distinct Count | Null Count | Null % | Min | Max | Average |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| date_key | integer | NO | 12 | 0 | 0.00 | 20230915 | 20260615 | 20245765.00 |
| full_date | date | NO | 12 | 0 | 0.00 | 2023-09-15 | 2026-06-15 |  |
| month_name | character varying | YES | 4 | 0 | 0.00 |  |  |  |
| calendar_year | integer | YES | 4 | 0 | 0.00 | 2023 | 2026 | 2024.50 |
| fiscal_year | character varying | YES | 3 | 0 | 0.00 |  |  |  |
| fiscal_quarter | character varying | YES | 12 | 0 | 0.00 |  |  |  |
| fiscal_period_seq | integer | YES | 12 | 0 | 0.00 | 1 | 12 | 6.50 |

## Column Data Types

| Data Type | Column Count |
| --- | --- |
| integer | 3 |
| date | 1 |
| character varying | 3 |

## NULL Statistics

| Column Name | Non-Null Count | Null Count | Null % |
| --- | --- | --- | --- |
| date_key | 12 | 0 | 0.00 |
| full_date | 12 | 0 | 0.00 |
| month_name | 12 | 0 | 0.00 |
| calendar_year | 12 | 0 | 0.00 |
| fiscal_year | 12 | 0 | 0.00 |
| fiscal_quarter | 12 | 0 | 0.00 |
| fiscal_period_seq | 12 | 0 | 0.00 |

## Distinct Value Statistics

| Column Name | Distinct Count | Duplicate Value Count* |
| --- | --- | --- |
| date_key | 12 | 0 |
| full_date | 12 | 0 |
| month_name | 4 | 8 |
| calendar_year | 4 | 8 |
| fiscal_year | 3 | 9 |
| fiscal_quarter | 12 | 0 |
| fiscal_period_seq | 12 | 0 |

*Duplicate Value Count = Row Count - Distinct Count.

## Value Distribution Summary

### month_name

| Value | Frequency |
| --- | --- |
| December | 3 |
| June | 3 |
| March | 3 |
| September | 3 |

### fiscal_year

| Value | Frequency |
| --- | --- |
| FY24 | 4 |
| FY25 | 4 |
| FY26 | 4 |

### fiscal_quarter

| Value | Frequency |
| --- | --- |
| FY24 Q1 | 1 |
| FY24 Q2 | 1 |
| FY24 Q3 | 1 |
| FY24 Q4 | 1 |
| FY25 Q1 | 1 |

## Numeric Statistics

| Column Name | Min | Max | Average | Distinct Count |
| --- | --- | --- | --- | --- |
| date_key | 20230915 | 20260615 | 20245765.00 | 12 |
| calendar_year | 2023 | 2026 | 2024.50 | 4 |
| fiscal_period_seq | 1 | 12 | 6.50 | 12 |

## Date Statistics

| Column Name | Min Date | Max Date | Distinct Count |
| --- | --- | --- | --- |
| full_date | 2023-09-15 | 2026-06-15 | 12 |

## Text Statistics

| Column Name | Min Length | Max Length | Avg Length |
| --- | --- | --- | --- |
| month_name | 4 | 9 | 6.50 |
| fiscal_year | 4 | 4 | 4.00 |
| fiscal_quarter | 7 | 7 | 7.00 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with Nulls | 0 |
| Fully Populated Columns | 7 |
| Table Completeness % | 100.00 |

## Data Quality Summary

| Check | Result |
| --- | --- |
| Table Exists | Pass |
| Primary Key Duplicates | Pass |
| Null Primary Key | Pass |
| Any Missing Data | Pass |
| Date Coverage | 2023-09-15 through 2026-06-15 |
| Fiscal Coverage | FY24 to FY26 |

## Observations

| Observation Type | Details |
| --- | --- |
| Grain | Appears to be one row per fiscal quarter-end style date point |
| Key Quality | date_key is unique and complete |
| Temporal Pattern | 12 rows span 4 calendar years |
| Fiscal Pattern | 3 fiscal years with 4 periods each |
| Distribution | Month distribution is perfectly balanced across March, June, September, and December |
