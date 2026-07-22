# Profiling Report: ontology.dim_sales_rep

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Table Name | ontology.dim_sales_rep |
| Row Count | 6 |
| Column Count | 6 |
| Primary Key Duplicate Count | 0 |
| Missing Data Columns | 0 of 6 |
| Database Type | PostgreSQL |

## Column Summary

| Column Name | Data Type | Nullable | Distinct Count | Null Count | Null % | Min | Max | Average |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| sales_rep_key | integer | NO | 6 | 0 | 0.00 | 1 | 6 | 3.50 |
| rep_id | character varying | NO | 6 | 0 | 0.00 |  |  |  |
| rep_name | character varying | YES | 6 | 0 | 0.00 |  |  |  |
| sales_role | character varying | YES | 3 | 0 | 0.00 |  |  |  |
| sales_team | character varying | YES | 6 | 0 | 0.00 |  |  |  |
| segment_covered | character varying | YES | 3 | 0 | 0.00 |  |  |  |

## Column Data Types

| Data Type | Column Count |
| --- | --- |
| integer | 1 |
| character varying | 5 |

## NULL Statistics

| Column Name | Non-Null Count | Null Count | Null % |
| --- | --- | --- | --- |
| sales_rep_key | 6 | 0 | 0.00 |
| rep_id | 6 | 0 | 0.00 |
| rep_name | 6 | 0 | 0.00 |
| sales_role | 6 | 0 | 0.00 |
| sales_team | 6 | 0 | 0.00 |
| segment_covered | 6 | 0 | 0.00 |

## Distinct Value Statistics

| Column Name | Distinct Count | Duplicate Value Count* |
| --- | --- | --- |
| sales_rep_key | 6 | 0 |
| rep_id | 6 | 0 |
| rep_name | 6 | 0 |
| sales_role | 3 | 3 |
| sales_team | 6 | 0 |
| segment_covered | 3 | 3 |

*Duplicate Value Count = Row Count - Distinct Count.

## Value Distribution Summary

### sales_role

| Value | Frequency |
| --- | --- |
| Account Executive | 4 |
| Enterprise Account Manager | 1 |
| Public Sector Account Manager | 1 |

### sales_team

| Value | Frequency |
| --- | --- |
| APJC SP | 1 |
| EMEA SP | 1 |
| Enterprise FSI | 1 |
| Federal | 1 |
| SP East | 1 |

### segment_covered

| Value | Frequency |
| --- | --- |
| Service Provider | 4 |
| Enterprise | 1 |
| Public Sector | 1 |

## Numeric Statistics

| Column Name | Min | Max | Average | Distinct Count |
| --- | --- | --- | --- | --- |
| sales_rep_key | 1 | 6 | 3.50 | 6 |

## Date Statistics

No date columns in this table.

## Text Statistics

| Column Name | Min Length | Max Length | Avg Length |
| --- | --- | --- | --- |
| rep_id | 6 | 6 | 6.00 |
| rep_name | 10 | 14 | 12.00 |
| sales_role | 17 | 29 | 20.50 |
| sales_team | 7 | 14 | 8.17 |
| segment_covered | 10 | 16 | 14.50 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with Nulls | 0 |
| Fully Populated Columns | 6 |
| Table Completeness % | 100.00 |

## Data Quality Summary

| Check | Result |
| --- | --- |
| Table Exists | Pass |
| Primary Key Duplicates | Pass |
| Null Primary Key | Pass |
| Any Missing Data | Pass |
| Dominant Role | Account Executive (66.67%) |
| Dominant Coverage Segment | Service Provider (66.67%) |

## Observations

| Observation Type | Details |
| --- | --- |
| Grain | Appears to be one row per sales representative |
| Key Quality | sales_rep_key and rep_id are unique and complete |
| Role Pattern | Account Executive is the primary role |
| Coverage Pattern | Service Provider coverage dominates the team mix |
| Team Diversity | sales_team values are unique across all rows |
