# Profiling Report: ontology.dim_date

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Schema | ontology |
| Table Name | dim_date |
| Full Table Name | ontology.dim_date |
| Row Count | 12 |
| Column Count | 7 |
| Primary Key Duplicate Count | 0 |
| Min full_date | 2023-09-15 |
| Max full_date | 2026-06-15 |

## Column Profile Summary

| Column Name | Data Type | Nullable | Distinct Count | NULL Count | NULL % |
| --- | --- | --- | ---: | ---: | ---: |
| date_key | integer | NO | 12 | 0 | 0.00% |
| full_date | date | NO | 12 | 0 | 0.00% |
| month_name | character varying | YES | 4 | 0 | 0.00% |
| calendar_year | integer | YES | 4 | 0 | 0.00% |
| fiscal_year | character varying | YES | 3 | 0 | 0.00% |
| fiscal_quarter | character varying | YES | 12 | 0 | 0.00% |
| fiscal_period_seq | integer | YES | 12 | 0 | 0.00% |

## Column Data Types

| Data Type | Columns |
| --- | --- |
| integer | date_key, calendar_year, fiscal_period_seq |
| date | full_date |
| character varying | month_name, fiscal_year, fiscal_quarter |

## Numeric Statistics

| Column | Min | Max | Avg |
| --- | ---: | ---: | ---: |
| date_key | 20230915 | 20260615 | 20245765.00 |
| calendar_year | 2023 | 2026 | 2024.50 |
| fiscal_period_seq | 1 | 12 | 6.50 |

## Date Statistics

| Column | Min Date | Max Date |
| --- | --- | --- |
| full_date | 2023-09-15 | 2026-06-15 |

## Text Statistics

| Column | Min Length | Max Length | Avg Length |
| --- | ---: | ---: | ---: |
| month_name | 4 | 9 | 6.50 |
| fiscal_year | 4 | 4 | 4.00 |
| fiscal_quarter | 7 | 7 | 7.00 |

## Value Distribution Summary

### month_name

| Value | Frequency |
| --- | ---: |
| December | 3 |
| June | 3 |
| March | 3 |
| September | 3 |

### calendar_year

| Value | Frequency |
| --- | ---: |
| 2024 | 4 |
| 2025 | 4 |
| 2023 | 2 |
| 2026 | 2 |

### fiscal_year

| Value | Frequency |
| --- | ---: |
| FY24 | 4 |
| FY25 | 4 |
| FY26 | 4 |

### fiscal_quarter

| Value | Frequency |
| --- | ---: |
| FY24 Q1 | 1 |
| FY24 Q2 | 1 |
| FY24 Q3 | 1 |
| FY24 Q4 | 1 |
| FY25 Q1 | 1 |
| FY25 Q2 | 1 |
| FY25 Q3 | 1 |
| FY25 Q4 | 1 |
| FY26 Q1 | 1 |
| FY26 Q2 | 1 |

## NULL Statistics

| Column | NULL Count | NULL % |
| --- | ---: | ---: |
| date_key | 0 | 0.00% |
| full_date | 0 | 0.00% |
| month_name | 0 | 0.00% |
| calendar_year | 0 | 0.00% |
| fiscal_year | 0 | 0.00% |
| fiscal_quarter | 0 | 0.00% |
| fiscal_period_seq | 0 | 0.00% |

## Distinct Value Statistics

| Column | Distinct Count |
| --- | ---: |
| date_key | 12 |
| full_date | 12 |
| month_name | 4 |
| calendar_year | 4 |
| fiscal_year | 3 |
| fiscal_quarter | 12 |
| fiscal_period_seq | 12 |

## Duplicate Statistics

| Check | Result |
| --- | ---: |
| Duplicate date_key values | 0 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with any NULLs | 0 |
| Total NULL cells | 0 |
| Completeness Status | Complete |

## Data Quality Summary

| Indicator | Observation |
| --- | --- |
| Primary key uniqueness | date_key is fully unique |
| Date completeness | full_date has no missing values |
| Range consistency | Date span covers 2023-09-15 through 2026-06-15 |
| Distribution note | Quarter-level calendar with evenly distributed quarter-month anchors |
| Quality assessment | Clean date dimension with complete fiscal and calendar attributes |
