# Profiling Report: ontology.dim_partner

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Table Name | ontology.dim_partner |
| Row Count | 6 |
| Column Count | 6 |
| Primary Key Duplicate Count | 0 |
| Missing Data Columns | 0 of 6 |
| Database Type | PostgreSQL |

## Column Summary

| Column Name | Data Type | Nullable | Distinct Count | Null Count | Null % | Min | Max | Average |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| partner_key | integer | NO | 6 | 0 | 0.00 | 1 | 6 | 3.50 |
| partner_id | character varying | NO | 6 | 0 | 0.00 |  |  |  |
| partner_name | character varying | YES | 6 | 0 | 0.00 |  |  |  |
| partner_type | character varying | YES | 4 | 0 | 0.00 |  |  |  |
| partner_tier | character varying | YES | 5 | 0 | 0.00 |  |  |  |
| route_to_market | character varying | YES | 3 | 0 | 0.00 |  |  |  |

## Column Data Types

| Data Type | Column Count |
| --- | --- |
| integer | 1 |
| character varying | 5 |

## NULL Statistics

| Column Name | Non-Null Count | Null Count | Null % |
| --- | --- | --- | --- |
| partner_key | 6 | 0 | 0.00 |
| partner_id | 6 | 0 | 0.00 |
| partner_name | 6 | 0 | 0.00 |
| partner_type | 6 | 0 | 0.00 |
| partner_tier | 6 | 0 | 0.00 |
| route_to_market | 6 | 0 | 0.00 |

## Distinct Value Statistics

| Column Name | Distinct Count | Duplicate Value Count* |
| --- | --- | --- |
| partner_key | 6 | 0 |
| partner_id | 6 | 0 |
| partner_name | 6 | 0 |
| partner_type | 4 | 2 |
| partner_tier | 5 | 1 |
| route_to_market | 3 | 3 |

*Duplicate Value Count = Row Count - Distinct Count.

## Value Distribution Summary

### partner_type

| Value | Frequency |
| --- | --- |
| Value-Added Reseller | 3 |
| Direct | 1 |
| Distributor | 1 |
| Systems Integrator | 1 |

### partner_tier

| Value | Frequency |
| --- | --- |
| Gold Integrator | 2 |
| Authorized Distributor | 1 |
| N/A | 1 |
| Premier | 1 |
| Select | 1 |

### route_to_market

| Value | Frequency |
| --- | --- |
| Reseller | 3 |
| Two-Tier | 2 |
| Direct | 1 |

## Numeric Statistics

| Column Name | Min | Max | Average | Distinct Count |
| --- | --- | --- | --- | --- |
| partner_key | 1 | 6 | 3.50 | 6 |

## Date Statistics

No date columns in this table.

## Text Statistics

| Column Name | Min Length | Max Length | Avg Length |
| --- | --- | --- | --- |
| partner_id | 6 | 6 | 6.00 |
| partner_name | 3 | 21 | 10.67 |
| partner_type | 6 | 20 | 15.83 |
| partner_tier | 3 | 22 | 11.33 |
| route_to_market | 6 | 8 | 7.67 |

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
| Dominant Partner Type | Value-Added Reseller (50.00%) |
| Route Coverage | Reseller, Two-Tier, and Direct represented |

## Observations

| Observation Type | Details |
| --- | --- |
| Grain | Appears to be one row per partner |
| Key Quality | partner_key and partner_id are unique and complete |
| Channel Pattern | Reseller-led ecosystem dominates the sample |
| Type Pattern | Value-Added Reseller is the largest partner category |
| Tier Diversity | partner_tier is diverse with only one repeated category |
