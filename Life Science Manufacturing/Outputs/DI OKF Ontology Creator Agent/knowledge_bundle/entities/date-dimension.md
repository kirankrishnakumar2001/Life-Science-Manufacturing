---
title: Date Dimension
type: entity
entity_id: ENT003
domain: Time Management
technical_mapping: ontology.dim_date
business_keys:
  - date_key
measures:
  - Booking Amount (USD)
  - Annual Contract Value (USD)
  - Total Contract Value (USD)
relationships:
  - Date Dimension to Booking Transaction Fact
related_concepts:
  - Full Date
  - Month Name
  - Calendar Year
  - Fiscal Year
  - Fiscal Quarter
  - Fiscal Period Sequence
---

# Date Dimension

## Business Definition
Reference entity containing calendar and fiscal attributes used to analyze bookings across reporting dates, fiscal years, quarters, and periods.

## Technical Mapping
`ontology.dim_date`

## Attributes
| Business Attribute | Technical Column | Data Type | Nullable | Key Type | Description |
| --- | --- | --- | --- | --- | --- |
| Date Key | date_key | integer | No | Primary Key | Surrogate or smart key representing the reporting date in YYYYMMDD-style numeric format. |
| Full Date | full_date | date | No | Attribute | Calendar date represented by the date dimension record. |
| Month Name | month_name | character varying(12) | Yes | Attribute | Name of the calendar month associated with the date. |
| Calendar Year | calendar_year | integer | Yes | Attribute | Four-digit calendar year associated with the reporting date. |
| Fiscal Year | fiscal_year | character varying(6) | Yes | Attribute | Fiscal year label used for internal business reporting, such as FY24. |
| Fiscal Quarter | fiscal_quarter | character varying(10) | Yes | Attribute | Fiscal quarter label associated with the date, such as FY24 Q1. |
| Fiscal Period Sequence | fiscal_period_seq | integer | Yes | Attribute | Ordered sequence number of the fiscal reporting period within the profiled range. |

## Keys
- Primary / Business Key: `date_key`

## Measures
- [Booking Amount (USD)](../measures/booking-amount-usd.md)
- [Annual Contract Value (USD)](../measures/annual-contract-value-usd.md)
- [Total Contract Value (USD)](../measures/total-contract-value-usd.md)

## Relationships
- [Date Dimension to Booking Transaction Fact](../relationships/date-dimension-to-booking-transaction-fact.md)

## Related Concepts
- [Time Management](../domains/time-management.md)
- [Date Key](../glossary/date-key.md)
- [Full Date](../glossary/full-date.md)
- [Month Name](../glossary/month-name.md)
- [Calendar Year](../glossary/calendar-year.md)
- [Fiscal Year](../glossary/fiscal-year.md)
- [Fiscal Quarter](../glossary/fiscal-quarter.md)
- [Fiscal Period Sequence](../glossary/fiscal-period-sequence.md)

## Cross-Links
- [Entities Index](index.md)
- [Bundle Index](../index.md)