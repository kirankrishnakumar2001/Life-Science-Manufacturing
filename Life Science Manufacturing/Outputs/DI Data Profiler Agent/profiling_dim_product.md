# Profiling Report: ontology.dim_product

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Table Name | ontology.dim_product |
| Row Count | 10 |
| Column Count | 7 |
| Primary Key Duplicate Count | 0 |
| Missing Data Columns | 0 of 7 |
| Database Type | PostgreSQL |

## Column Summary

| Column Name | Data Type | Nullable | Distinct Count | Null Count | Null % | Min | Max | Average |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| product_key | integer | NO | 10 | 0 | 0.00 | 1 | 10 | 5.50 |
| product_id | character varying | NO | 10 | 0 | 0.00 |  |  |  |
| product_name | character varying | YES | 10 | 0 | 0.00 |  |  |  |
| product_family | character varying | YES | 7 | 0 | 0.00 |  |  |  |
| technology_domain | character varying | YES | 7 | 0 | 0.00 |  |  |  |
| offer_type | character varying | YES | 3 | 0 | 0.00 |  |  |  |
| business_entity | character varying | YES | 5 | 0 | 0.00 |  |  |  |

## Column Data Types

| Data Type | Column Count |
| --- | --- |
| integer | 1 |
| character varying | 6 |

## NULL Statistics

| Column Name | Non-Null Count | Null Count | Null % |
| --- | --- | --- | --- |
| product_key | 10 | 0 | 0.00 |
| product_id | 10 | 0 | 0.00 |
| product_name | 10 | 0 | 0.00 |
| product_family | 10 | 0 | 0.00 |
| technology_domain | 10 | 0 | 0.00 |
| offer_type | 10 | 0 | 0.00 |
| business_entity | 10 | 0 | 0.00 |

## Distinct Value Statistics

| Column Name | Distinct Count | Duplicate Value Count* |
| --- | --- | --- |
| product_key | 10 | 0 |
| product_id | 10 | 0 |
| product_name | 10 | 0 |
| product_family | 7 | 3 |
| technology_domain | 7 | 3 |
| offer_type | 3 | 7 |
| business_entity | 5 | 5 |

*Duplicate Value Count = Row Count - Distinct Count.

## Value Distribution Summary

### product_family

| Value | Frequency |
| --- | --- |
| Catalyst | 2 |
| Firepower | 2 |
| Meraki | 2 |
| Duo | 1 |
| Nexus | 1 |

### technology_domain

| Value | Frequency |
| --- | --- |
| Networking - Cloud Managed | 2 |
| Networking - Switching | 2 |
| Security - Network | 2 |
| Collaboration | 1 |
| Networking - Data Center | 1 |

### offer_type

| Value | Frequency |
| --- | --- |
| Hardware | 5 |
| SaaS Subscription | 4 |
| Software Subscription | 1 |

### business_entity

| Value | Frequency |
| --- | --- |
| Security | 4 |
| Meraki | 2 |
| Networking | 2 |
| Collaboration | 1 |
| Data Center | 1 |

## Numeric Statistics

| Column Name | Min | Max | Average | Distinct Count |
| --- | --- | --- | --- | --- |
| product_key | 1 | 10 | 5.50 | 10 |

## Date Statistics

No date columns in this table.

## Text Statistics

| Column Name | Min Length | Max Length | Avg Length |
| --- | --- | --- | --- |
| product_id | 8 | 11 | 9.40 |
| product_name | 10 | 32 | 20.50 |
| product_family | 3 | 9 | 6.70 |
| technology_domain | 13 | 26 | 20.40 |
| offer_type | 8 | 21 | 12.90 |
| business_entity | 6 | 13 | 8.80 |

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
| Dominant Offer Type | Hardware (50.00%) |
| Largest Business Entity | Security (40.00%) |

## Observations

| Observation Type | Details |
| --- | --- |
| Grain | Appears to be one row per product |
| Key Quality | product_key and product_id are unique and complete |
| Portfolio Mix | Hardware slightly exceeds subscription-based offerings |
| Entity Pattern | Security has the strongest representation |
| Family Diversity | Product family and technology domain are moderately diverse with a few repeated clusters |
