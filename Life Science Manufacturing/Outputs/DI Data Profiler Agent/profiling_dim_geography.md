# Profiling Report: ontology.dim_geography

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Schema | ontology |
| Table Name | dim_geography |
| Full Table Name | ontology.dim_geography |
| Row Count | 8 |
| Column Count | 4 |
| Primary Key Duplicate Count | 0 |

## Column Profile Summary

| Column Name | Data Type | Nullable | Distinct Count | NULL Count | NULL % |
| --- | --- | --- | ---: | ---: | ---: |
| geography_key | integer | NO | 8 | 0 | 0.00% |
| region | character varying | YES | 3 | 0 | 0.00% |
| theater | character varying | YES | 8 | 0 | 0.00% |
| country | character varying | YES | 8 | 0 | 0.00% |

## Column Data Types

| Data Type | Columns |
| --- | --- |
| integer | geography_key |
| character varying | region, theater, country |

## Numeric Statistics

| Column | Min | Max | Avg |
| --- | ---: | ---: | ---: |
| geography_key | 1 | 8 | 4.50 |

## Text Statistics

| Column | Min Length | Max Length | Avg Length |
| --- | ---: | ---: | ---: |
| region | 4 | 8 | 5.00 |
| theater | 3 | 15 | 9.00 |
| country | 5 | 20 | 9.88 |

## Value Distribution Summary

### region

| Value | Frequency |
| --- | ---: |
| APJC | 3 |
| EMEA | 3 |
| Americas | 2 |

### theater

| Value | Frequency |
| --- | ---: |
| ANZ | 1 |
| Canada | 1 |
| Central Europe | 1 |
| India | 1 |
| Japan | 1 |
| Middle East | 1 |
| Northern Europe | 1 |
| US Commercial | 1 |

### country

| Value | Frequency |
| --- | ---: |
| Australia | 1 |
| Canada | 1 |
| Germany | 1 |
| India | 1 |
| Japan | 1 |
| United Arab Emirates | 1 |
| United Kingdom | 1 |
| United States | 1 |

## NULL Statistics

| Column | NULL Count | NULL % |
| --- | ---: | ---: |
| geography_key | 0 | 0.00% |
| region | 0 | 0.00% |
| theater | 0 | 0.00% |
| country | 0 | 0.00% |

## Distinct Value Statistics

| Column | Distinct Count |
| --- | ---: |
| geography_key | 8 |
| region | 3 |
| theater | 8 |
| country | 8 |

## Duplicate Statistics

| Check | Result |
| --- | ---: |
| Duplicate geography_key values | 0 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with any NULLs | 0 |
| Total NULL cells | 0 |
| Completeness Status | Complete |

## Data Quality Summary

| Indicator | Observation |
| --- | --- |
| Primary key uniqueness | geography_key is fully unique |
| Completeness | No missing values detected |
| Regional coverage | 3 regions across 8 countries |
| Distribution note | geography_key is unique; theater and country are also unique in this sample |
| Quality assessment | Clean, complete geography dimension with broad regional spread |
