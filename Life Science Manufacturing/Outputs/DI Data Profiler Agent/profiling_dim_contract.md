# Profiling Report: ontology.dim_contract

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Schema Name | ontology |
| Table Name | dim_contract |
| Row Count | 6 |
| Column Count | 5 |

## Column Summary

| Column Name | Data Type | Nullable |
| --- | --- | --- |
| contract_key | integer | NO |
| contract_type | character varying | YES |
| term_months | integer | YES |
| auto_renew_flag | character | YES |
| coverage_level | character varying | YES |

## Column Profile Summary

| Column | Null Count | Null % | Distinct Count | Duplicate Count | Min | Max | Avg | Min Length | Max Length | Avg Length |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| contract_key | 0 | 0.00 | 6 | 0 | 1 | 6 | 3.50 | - | - | - |
| contract_type | 0 | 0.00 | 6 | 0 | - | - | - | 16 | 22 | 18.33 |
| term_months | 0 | 0.00 | 3 | 3 | 0 | 36 | 18.00 | - | - | - |
| auto_renew_flag | 0 | 0.00 | 2 | 4 | - | - | - | 1 | 1 | 1.00 |
| coverage_level | 0 | 0.00 | 6 | 0 | - | - | - | 2 | 8 | 5.00 |

## Value Distribution Summary

### contract_type

| Value | Frequency |
| --- | --- |
| Enterprise Agreement | 1 |
| Perpetual (no support) | 1 |
| SaaS Subscription | 1 |
| SmartNet Total Care | 1 |
| Solution Support | 1 |
| Success Track L2 | 1 |

### term_months

| Value | Frequency |
| --- | --- |
| 12 | 3 |
| 36 | 2 |
| 0 | 1 |

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
| Standard | 1 |

## Numeric Statistics

| Column | Min | Max | Avg |
| --- | --- | --- | --- |
| contract_key | 1 | 6 | 3.50 |
| term_months | 0 | 36 | 18.00 |

## Text Statistics

| Column | Min Length | Max Length | Avg Length |
| --- | --- | --- | --- |
| contract_type | 16 | 22 | 18.33 |
| auto_renew_flag | 1 | 1 | 1.00 |
| coverage_level | 2 | 8 | 5.00 |

## NULL Statistics

| Column | Null Count | Null % |
| --- | --- | --- |
| contract_key | 0 | 0.00 |
| contract_type | 0 | 0.00 |
| term_months | 0 | 0.00 |
| auto_renew_flag | 0 | 0.00 |
| coverage_level | 0 | 0.00 |

## Distinct Value Statistics

| Column | Distinct Count |
| --- | --- |
| contract_key | 6 |
| contract_type | 6 |
| term_months | 3 |
| auto_renew_flag | 2 |
| coverage_level | 6 |

## Duplicate Statistics

| Column | Duplicate Count |
| --- | --- |
| contract_key | 0 |
| contract_type | 0 |
| term_months | 3 |
| auto_renew_flag | 4 |
| coverage_level | 0 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with Missing Values | 0 |
| Fully Populated Columns | 5 |

## Data Quality Summary

| Indicator | Result |
| --- | --- |
| Primary key candidate uniqueness (contract_key) | Pass |
| Null issue detected | No |
| Duplicate-heavy attribute | auto_renew_flag, term_months |
| Potential business rule observation | term_months includes 0, indicating perpetual/no-term contracts |
| Overall assessment | Good structural quality with expected low-cardinality categorical fields |
