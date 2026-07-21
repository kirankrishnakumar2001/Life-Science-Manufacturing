# Profiling Report: ontology.dim_sales_rep

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Schema | ontology |
| Table Name | dim_sales_rep |
| Full Table Name | ontology.dim_sales_rep |
| Row Count | 6 |
| Column Count | 6 |
| Primary Key Duplicate Count | 0 |

## Column Profile Summary

| Column Name | Data Type | Nullable | Distinct Count | NULL Count | NULL % |
| --- | --- | --- | ---: | ---: | ---: |
| sales_rep_key | integer | NO | 6 | 0 | 0.00% |
| rep_id | character varying | NO | 6 | 0 | 0.00% |
| rep_name | character varying | YES | 6 | 0 | 0.00% |
| sales_role | character varying | YES | 3 | 0 | 0.00% |
| sales_team | character varying | YES | 6 | 0 | 0.00% |
| segment_covered | character varying | YES | 3 | 0 | 0.00% |

## Column Data Types

| Data Type | Columns |
| --- | --- |
| integer | sales_rep_key |
| character varying | rep_id, rep_name, sales_role, sales_team, segment_covered |

## Numeric Statistics

| Column | Min | Max | Avg |
| --- | ---: | ---: | ---: |
| sales_rep_key | 1 | 6 | 3.50 |

## Text Statistics

| Column | Min Length | Max Length | Avg Length |
| --- | ---: | ---: | ---: |
| rep_id | 6 | 6 | 6.00 |
| rep_name | 10 | 14 | 12.00 |
| sales_role | 17 | 29 | 20.50 |
| sales_team | 7 | 14 | 8.17 |
| segment_covered | 10 | 16 | 14.50 |

## Value Distribution Summary

### sales_role

| Value | Frequency |
| --- | ---: |
| Account Executive | 4 |
| Enterprise Account Manager | 1 |
| Public Sector Account Manager | 1 |

### sales_team

| Value | Frequency |
| --- | ---: |
| APJC SP | 1 |
| EMEA SP | 1 |
| Enterprise FSI | 1 |
| Federal | 1 |
| SP East | 1 |
| SP West | 1 |

### segment_covered

| Value | Frequency |
| --- | ---: |
| Service Provider | 4 |
| Enterprise | 1 |
| Public Sector | 1 |

## NULL Statistics

| Column | NULL Count | NULL % |
| --- | ---: | ---: |
| sales_rep_key | 0 | 0.00% |
| rep_id | 0 | 0.00% |
| rep_name | 0 | 0.00% |
| sales_role | 0 | 0.00% |
| sales_team | 0 | 0.00% |
| segment_covered | 0 | 0.00% |

## Distinct Value Statistics

| Column | Distinct Count |
| --- | ---: |
| sales_rep_key | 6 |
| rep_id | 6 |
| rep_name | 6 |
| sales_role | 3 |
| sales_team | 6 |
| segment_covered | 3 |

## Duplicate Statistics

| Check | Result |
| --- | ---: |
| Duplicate sales_rep_key values | 0 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with any NULLs | 0 |
| Total NULL cells | 0 |
| Completeness Status | Complete |

## Data Quality Summary

| Indicator | Observation |
| --- | --- |
| Primary key uniqueness | sales_rep_key is fully unique |
| Business key uniqueness | rep_id is fully unique |
| Completeness | No missing values detected |
| Distribution note | Service Provider coverage and Account Executive role dominate |
| Quality assessment | Clean sales representative dimension with strong identifiers and no completeness issues |
