---
title: Discount Percentage
type: measure
measure_id: MEAS003
entity: Booking Transaction Fact
technical_column: discount_pct
aggregation_type: Average
related_entities:
  - Booking Transaction Fact
related_domains:
  - Revenue Analytics
  - Partner Management
---

# Discount Percentage

## Business Definition
Discount rate applied to the list price for the booked transaction.

## Aggregation Type
Average

## Related Entities
- [Booking Transaction Fact](../entities/booking-transaction-fact.md)

## Related Domains
- [Revenue Analytics](../domains/revenue-analytics.md)
- [Partner Management](../domains/partner-management.md)

## Technical Mapping
`ontology.fact_bookings.discount_pct`

## Cross-Links
- [Measures Index](index.md)
- [Bundle Index](../index.md)