# Profiling Report: ontology.dim_customer

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Schema | ontology |
| Table Name | dim_customer |
| Full Table Name | ontology.dim_customer |
| Row Count | 8 |
| Column Count | 8 |
| Primary Key Duplicate Count | 0 |

## Column Profile Summary

| Column Name | Data Type | Nullable | Distinct Count | NULL Count | NULL % |
| --- | --- | --- | ---: | ---: | ---: |
| customer_key | integer | NO | 8 | 0 | 0.00% |
| customer_id | character varying | NO | 8 | 0 | 0.00% |
| customer_name | character varying | YES | 8 | 0 | 0.00% |
| segment | character varying | YES | 3 | 0 | 0.00% |
| industry | character varying | YES | 3 | 0 | 0.00% |
| account_tier | character varying | YES | 2 | 0 | 0.00% |
| hq_country | character varying | YES | 5 | 0 | 0.00% |
| hq_region | character varying | YES | 3 | 0 | 0.00% |

## Column Data Types

| Data Type | Columns |
| --- | --- |
| integer | customer_key |
| character varying | customer_id, customer_name, segment, industry, account_tier, hq_country, hq_region |

## Text Statistics

| Column | Min Length | Max Length | Avg Length |
| --- | ---: | ---: | ---: |
| customer_id | 9 | 9 | 9.00 |
| customer_name | 3 | 26 | 11.25 |
| segment | 10 | 16 | 14.88 |
| industry | 10 | 18 | 17.00 |
| account_tier | 6 | 9 | 7.50 |
| hq_country | 5 | 14 | 10.38 |
| hq_region | 4 | 8 | 6.00 |

## Value Distribution Summary

### segment

| Value | Frequency |
| --- | ---: |
| Service Provider | 6 |
| Enterprise | 1 |
| Public Sector | 1 |

### industry

| Value | Frequency |
| --- | ---: |
| Telecommunications | 6 |
| Financial Services | 1 |
| Government | 1 |

### account_tier

| Value | Frequency |
| --- | ---: |
| Growth | 4 |
| Strategic | 4 |

### hq_country

| Value | Frequency |
| --- | ---: |
| United States | 4 |
| Germany | 1 |
| India | 1 |
| Japan | 1 |
| United Kingdom | 1 |

### hq_region

| Value | Frequency |
| --- | ---: |
| Americas | 4 |
| APJC | 2 |
| EMEA | 2 |

## NULL Statistics

| Column | NULL Count | NULL % |
| --- | ---: | ---: |
| customer_key | 0 | 0.00% |
| customer_id | 0 | 0.00% |
| customer_name | 0 | 0.00% |
| segment | 0 | 0.00% |
| industry | 0 | 0.00% |
| account_tier | 0 | 0.00% |
| hq_country | 0 | 0.00% |
| hq_region | 0 | 0.00% |

## Distinct Value Statistics

| Column | Distinct Count |
| --- | ---: |
| customer_key | 8 |
| customer_id | 8 |
| customer_name | 8 |
| segment | 3 |
| industry | 3 |
| account_tier | 2 |
| hq_country | 5 |
| hq_region | 3 |

## Duplicate Statistics

| Check | Result |
| --- | ---: |
| Duplicate customer_key values | 0 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with any NULLs | 0 |
| Total NULL cells | 0 |
| Completeness Status | Complete |

## Data Quality Summary

| Indicator | Observation |
| --- | --- |
| Primary key uniqueness | customer_key is fully unique |
| Business key uniqueness | customer_id is fully unique |
| Mandatory field completeness | No missing values detected |
| Distribution note | Dataset is concentrated in Service Provider / Telecommunications |
| Quality assessment | Complete customer dimension with strong key integrity and skewed business distribution |
