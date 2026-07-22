# Profiling Report: ontology.dim_geography

## Table Information

| Metric | Value |
| --- | --- |
| Database Name | ontology |
| Table Name | ontology.dim_geography |
| Row Count | 8 |
| Column Count | 4 |
| Primary Key Duplicate Count | 0 |
| Missing Data Columns | 0 of 4 |
| Database Type | PostgreSQL |

## Column Summary

| Column Name | Data Type | Nullable | Distinct Count | Null Count | Null % | Min | Max | Average |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| geography_key | integer | NO | 8 | 0 | 0.00 | 1 | 8 | 4.50 |
| region | character varying | YES | 3 | 0 | 0.00 |  |  |  |
| theater | character varying | YES | 8 | 0 | 0.00 |  |  |  |
| country | character varying | YES | 8 | 0 | 0.00 |  |  |  |

## Column Data Types

| Data Type | Column Count |
| --- | --- |
| integer | 1 |
| character varying | 3 |

## NULL Statistics

| Column Name | Non-Null Count | Null Count | Null % |
| --- | --- | --- | --- |
| geography_key | 8 | 0 | 0.00 |
| region | 8 | 0 | 0.00 |
| theater | 8 | 0 | 0.00 |
| country | 8 | 0 | 0.00 |

## Distinct Value Statistics

| Column Name | Distinct Count | Duplicate Value Count* |
| --- | --- | --- |
| geography_key | 8 | 0 |
| region | 3 | 5 |
| theater | 8 | 0 |
| country | 8 | 0 |

*Duplicate Value Count = Row Count - Distinct Count.

## Value Distribution Summary

### region

| Value | Frequency |
| --- | --- |
| APJC | 3 |
| EMEA | 3 |
| Americas | 2 |

### theater

| Value | Frequency |
| --- | --- |
| ANZ | 1 |
| Canada | 1 |
| Central Europe | 1 |
| India | 1 |
| Japan | 1 |

### country

| Value | Frequency |
| --- | --- |
| Australia | 1 |
| Canada | 1 |
| Germany | 1 |
| India | 1 |
| Japan | 1 |

## Numeric Statistics

| Column Name | Min | Max | Average | Distinct Count |
| --- | --- | --- | --- | --- |
| geography_key | 1 | 8 | 4.50 | 8 |

## Date Statistics

No date columns in this table.

## Text Statistics

| Column Name | Min Length | Max Length | Avg Length |
| --- | --- | --- | --- |
| region | 4 | 8 | 5.00 |
| theater | 3 | 15 | 9.00 |
| country | 5 | 20 | 9.88 |

## Missing Data Statistics

| Metric | Value |
| --- | --- |
| Columns with Nulls | 0 |
| Fully Populated Columns | 4 |
| Table Completeness % | 100.00 |

## Data Quality Summary

| Check | Result |
| --- | --- |
| Table Exists | Pass |
| Primary Key Duplicates | Pass |
| Null Primary Key | Pass |
| Any Missing Data | Pass |
| Region Coverage | 3 regions represented |
| Country Uniqueness | All listed countries are unique |

## Observations

| Observation Type | Details |
| --- | --- |
| Grain | Appears to be one row per geography mapping |
| Key Quality | geography_key is unique and complete |
| Regional Pattern | APJC and EMEA are tied for the highest representation |
| Country Pattern | No country duplication observed |
| Theater Pattern | Each theater appears once, indicating a reference dimension |
