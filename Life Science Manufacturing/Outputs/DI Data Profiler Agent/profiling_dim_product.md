# Profiling Report: ontology.dim_product

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Schema | ontology |
| Table Name | dim_product |
| Full Table Name | ontology.dim_product |
| Row Count | 10 |
| Column Count | 7 |
| Primary Key Duplicate Count | 0 |

## Column Profile Summary

| Column Name | Data Type | Nullable | Distinct Count | NULL Count | NULL % |
| --- | --- | --- | ---: | ---: | ---: |
| product_key | integer | NO | 10 | 0 | 0.00% |
| product_id | character varying | NO | 10 | 0 | 0.00% |
| product_name | character varying | YES | 10 | 0 | 0.00% |
| product_family | character varying | YES | 7 | 0 | 0.00% |
| technology_domain | character varying | YES | 7 | 0 | 0.00% |
| offer_type | character varying | YES | 3 | 0 | 0.00% |
| business_entity | character varying | YES | 5 | 0 | 0.00% |

## Column Data Types

| Data Type | Columns |
| --- | --- |
| integer | product_key |
| character varying | product_id, product_name, product_family, technology_domain, offer_type, business_entity |

## Numeric Statistics

| Column | Min | Max | Avg |
| --- | ---: | ---: | ---: |
| product_key | 1 | 10 | 5.50 |

## Text Statistics

| Column | Min Length | Max Length | Avg Length |
| --- | ---: | ---: | ---: |
| product_id | 8 | 11 | 9.40 |
| product_name | 10 | 32 | 20.50 |
| product_family | 3 | 9 | 6.70 |
| technology_domain | 13 | 26 | 20.40 |
| offer_type | 8 | 21 | 12.90 |
| business_entity | 6 | 13 | 8.80 |

## Value Distribution Summary

### product_family

| Value | Frequency |
| --- | ---: |
| Catalyst | 2 |
| Firepower | 2 |
| Meraki | 2 |
| Duo | 1 |
| Nexus | 1 |
| Umbrella | 1 |
| Webex | 1 |

### technology_domain

| Value | Frequency |
| --- | ---: |
| Networking - Cloud Managed | 2 |
| Networking - Switching | 2 |
| Security - Network | 2 |
| Collaboration | 1 |
| Networking - Data Center | 1 |
| Security - SSE | 1 |
| Security - Zero Trust | 1 |

### offer_type

| Value | Frequency |
| --- | ---: |
| Hardware | 5 |
| SaaS Subscription | 4 |
| Software Subscription | 1 |

### business_entity

| Value | Frequency |
| --- | ---: |
| Security | 4 |
| Meraki | 2 |
| Networking | 2 |
| Collaboration | 1 |
| Data Center | 1 |

## NULL Statistics

| Column | NULL Count | NULL % |
| --- | ---: | ---: |
| product_key | 0 | 0.00% |
| product_id | 0 | 0.00% |
| product_name | 0 | 0.00% |
| product_family | 0 | 0.00% |
| technology_domain | 0 | 0.00% |
| offer_type | 0 | 0.00% |
| business_entity | 0 | 0.00% |

## Distinct Value Statistics

| Column | Distinct Count |
| --- | ---: |
| product_key | 10 |
| product_id | 10 |
| product_name | 10 |
| product_family | 7 |
| technology_domain | 7 |
| offer_type | 3 |
| business_entity | 5 |

## Duplicate Statistics

| Check | Result |
| --- | ---: |
| Duplicate product_key values | 0 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with any NULLs | 0 |
| Total NULL cells | 0 |
| Completeness Status | Complete |

## Data Quality Summary

| Indicator | Observation |
| --- | --- |
| Primary key uniqueness | product_key is fully unique |
| Business key uniqueness | product_id is fully unique |
| Completeness | No missing values detected |
| Distribution note | Hardware and Security-oriented products are most common |
| Quality assessment | Clean product dimension with strong identifiers and balanced categorical diversity |
