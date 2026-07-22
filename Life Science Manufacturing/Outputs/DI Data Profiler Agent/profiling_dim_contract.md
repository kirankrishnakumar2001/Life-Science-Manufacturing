# Profiling Report: ontology.dim_contract

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Table Name | ontology.dim_contract |
| Row Count | 6 |
| Column Count | 5 |
| Primary Key Duplicate Count | 0 |
| Missing Data Columns | 0 of 5 |
| Database Type | PostgreSQL |

## Column Summary

| Column Name | Data Type | Nullable | Distinct Count | Null Count | Null % | Min | Max | Average |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| contract_key | integer | NO | 6 | 0 | 0.00 | 1 | 6 | 3.50 |
| contract_type | character varying | YES | 6 | 0 | 0.00 |  |  |  |
| term_months | integer | YES | 3 | 0 | 0.00 | 0 | 36 | 18.00 |
| auto_renew_flag | character | YES | 2 | 0 | 0.00 |  |  |  |
| coverage_level | character varying | YES | 6 | 0 | 0.00 |  |  |  |

## Column Data Types

| Data Type | Column Count |
| --- | --- |
| integer | 2 |
| character varying | 2 |
| character | 1 |

## NULL Statistics

| Column Name | Non-Null Count | Null Count | Null % |
| --- | --- | --- | --- |
| contract_key | 6 | 0 | 0.00 |
| contract_type | 6 | 0 | 0.00 |
| term_months | 6 | 0 | 0.00 |
| auto_renew_flag | 6 | 0 | 0.00 |
| coverage_level | 6 | 0 | 0.00 |

## Distinct Value Statistics

| Column Name | Distinct Count | Duplicate Value Count* |
| --- | --- | --- |
| contract_key | 6 | 0 |
| contract_type | 6 | 0 |
| term_months | 3 | 3 |
| auto_renew_flag | 2 | 4 |
| coverage_level | 6 | 0 |

*Duplicate Value Count = Row Count - Distinct Count.

## Value Distribution Summary

### contract_type

| Value | Frequency |
| --- | --- |
| Enterprise Agreement | 1 |
| Perpetual (no support) | 1 |
| SaaS Subscription | 1 |
| SmartNet Total Care | 1 |
| Solution Support | 1 |

### auto_renew_flag

| Value | Frequency |
| --- | --- |
| Y | 4 |
| N | 2 |

### coverage_level

| Value | Frequency |
| --- | --- |
| 24x7 | 1 |
| 24x7x4 | 1 |
| EA | 1 |
| Expert | 1 |
| None | 1 |

## Numeric Statistics

| Column Name | Min | Max | Average | Distinct Count |
| --- | --- | --- | --- | --- |
| contract_key | 1 | 6 | 3.50 | 6 |
| term_months | 0 | 36 | 18.00 | 3 |

## Date Statistics

No date columns in this table.

## Text Statistics

| Column Name | Min Length | Max Length | Avg Length |
| --- | --- | --- | --- |
| contract_type | 16 | 22 | 18.33 |
| coverage_level | 2 | 8 | 5.00 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with Nulls | 0 |
| Fully Populated Columns | 5 |
| Table Completeness % | 100.00 |

## Data Quality Summary

| Check | Result |
| --- | --- |
| Table Exists | Pass |
| Primary Key Duplicates | Pass |
| Null Primary Key | Pass |
| Any Missing Data | Pass |
| Low Cardinality Flag Columns Present | Yes - auto_renew_flag |
| Numeric Range Review | term_months ranges from 0 to 36 |

## Observations

| Observation Type | Details |
| --- | --- |
| Grain | Appears to be one row per contract definition |
| Key Quality | contract_key is unique and complete |
| Business Pattern | auto_renew_flag is skewed toward Y (4 of 6) |
| Coverage Pattern | coverage_level values are highly diverse with no dominant category in top 5 |
