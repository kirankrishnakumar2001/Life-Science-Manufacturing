# Profiling Report: ontology.dim_partner

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Schema | ontology |
| Table Name | dim_partner |
| Full Table Name | ontology.dim_partner |
| Row Count | 6 |
| Column Count | 6 |
| Primary Key Duplicate Count | 0 |

## Column Profile Summary

| Column Name | Data Type | Nullable | Distinct Count | NULL Count | NULL % |
| --- | --- | --- | ---: | ---: | ---: |
| partner_key | integer | NO | 6 | 0 | 0.00% |
| partner_id | character varying | NO | 6 | 0 | 0.00% |
| partner_name | character varying | YES | 6 | 0 | 0.00% |
| partner_type | character varying | YES | 4 | 0 | 0.00% |
| partner_tier | character varying | YES | 5 | 0 | 0.00% |
| route_to_market | character varying | YES | 3 | 0 | 0.00% |

## Column Data Types

| Data Type | Columns |
| --- | --- |
| integer | partner_key |
| character varying | partner_id, partner_name, partner_type, partner_tier, route_to_market |

## Numeric Statistics

| Column | Min | Max | Avg |
| --- | ---: | ---: | ---: |
| partner_key | 1 | 6 | 3.50 |

## Text Statistics

| Column | Min Length | Max Length | Avg Length |
| --- | ---: | ---: | ---: |
| partner_id | 6 | 6 | 6.00 |
| partner_name | 3 | 21 | 10.67 |
| partner_type | 6 | 20 | 15.83 |
| partner_tier | 3 | 22 | 11.33 |
| route_to_market | 6 | 8 | 7.67 |

## Value Distribution Summary

### partner_type

| Value | Frequency |
| --- | ---: |
| Value-Added Reseller | 3 |
| Direct | 1 |
| Distributor | 1 |
| Systems Integrator | 1 |

### partner_tier

| Value | Frequency |
| --- | ---: |
| Gold Integrator | 2 |
| Authorized Distributor | 1 |
| N/A | 1 |
| Premier | 1 |
| Select | 1 |

### route_to_market

| Value | Frequency |
| --- | ---: |
| Reseller | 3 |
| Two-Tier | 2 |
| Direct | 1 |

## NULL Statistics

| Column | NULL Count | NULL % |
| --- | ---: | ---: |
| partner_key | 0 | 0.00% |
| partner_id | 0 | 0.00% |
| partner_name | 0 | 0.00% |
| partner_type | 0 | 0.00% |
| partner_tier | 0 | 0.00% |
| route_to_market | 0 | 0.00% |

## Distinct Value Statistics

| Column | Distinct Count |
| --- | ---: |
| partner_key | 6 |
| partner_id | 6 |
| partner_name | 6 |
| partner_type | 4 |
| partner_tier | 5 |
| route_to_market | 3 |

## Duplicate Statistics

| Check | Result |
| --- | ---: |
| Duplicate partner_key values | 0 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with any NULLs | 0 |
| Total NULL cells | 0 |
| Completeness Status | Complete |

## Data Quality Summary

| Indicator | Observation |
| --- | --- |
| Primary key uniqueness | partner_key is fully unique |
| Business key uniqueness | partner_id is fully unique |
| Completeness | No missing values detected |
| Distribution note | Value-Added Reseller and Reseller route dominate the table |
| Quality assessment | Complete partner dimension with good key quality and moderate category concentration |
