# Profiling Report: ontology.dim_contract

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Schema | ontology |
| Table Name | dim_contract |
| Full Table Name | ontology.dim_contract |
| Row Count | 6 |
| Column Count | 5 |
| Primary Key Duplicate Count | 0 |

## Column Profile Summary

| Column Name | Data Type | Nullable | Distinct Count | NULL Count | NULL % |
| --- | --- | --- | ---: | ---: | ---: |
| contract_key | integer | NO | 6 | 0 | 0.00% |
| contract_type | character varying | YES | 6 | 0 | 0.00% |
| term_months | integer | YES | 3 | 0 | 0.00% |
| auto_renew_flag | character | YES | 2 | 0 | 0.00% |
| coverage_level | character varying | YES | 6 | 0 | 0.00% |

## Column Data Types

| Data Type | Columns |
| --- | --- |
| integer | contract_key, term_months |
| character varying | contract_type, coverage_level |
| character | auto_renew_flag |

## Numeric Statistics

| Column | Min | Max | Avg |
| --- | ---: | ---: | ---: |
| contract_key | 1 | 6 | 3.50 |
| term_months | 0 | 36 | 18.00 |

## Text Statistics

| Column | Min Length | Max Length | Avg Length |
| --- | ---: | ---: | ---: |
| contract_type | 16 | 22 | 18.33 |
| auto_renew_flag | 1 | 1 | 1.00 |
| coverage_level | 2 | 8 | 5.00 |

## Value Distribution Summary

### contract_type

| Value | Frequency |
| --- | ---: |
| Enterprise Agreement | 1 |
| Perpetual (no support) | 1 |
| SaaS Subscription | 1 |
| SmartNet Total Care | 1 |
| Solution Support | 1 |
| Success Track L2 | 1 |

### auto_renew_flag

| Value | Frequency |
| --- | ---: |
| Y | 4 |
| N | 2 |

### coverage_level

| Value | Frequency |
| --- | ---: |
| 24x7 | 1 |
| 24x7x4 | 1 |
| EA | 1 |
| Expert | 1 |
| None | 1 |
| Standard | 1 |

## NULL Statistics

| Column | NULL Count | NULL % |
| --- | ---: | ---: |
| contract_key | 0 | 0.00% |
| contract_type | 0 | 0.00% |
| term_months | 0 | 0.00% |
| auto_renew_flag | 0 | 0.00% |
| coverage_level | 0 | 0.00% |

## Distinct Value Statistics

| Column | Distinct Count |
| --- | ---: |
| contract_key | 6 |
| contract_type | 6 |
| term_months | 3 |
| auto_renew_flag | 2 |
| coverage_level | 6 |

## Duplicate Statistics

| Check | Result |
| --- | ---: |
| Duplicate contract_key values | 0 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with any NULLs | 0 |
| Total NULL cells | 0 |
| Completeness Status | Complete |

## Data Quality Summary

| Indicator | Observation |
| --- | --- |
| Primary key uniqueness | contract_key is fully unique |
| Mandatory field completeness | No missing values detected |
| Categorical consistency | auto_renew_flag contains 2 values (Y/N) |
| Distribution note | contract_type and coverage_level are fully unique across 6 rows |
| Quality assessment | Small, complete, high-quality dimension table |
