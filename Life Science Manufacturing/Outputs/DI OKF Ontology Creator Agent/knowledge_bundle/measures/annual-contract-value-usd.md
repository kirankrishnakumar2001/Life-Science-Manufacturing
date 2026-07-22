---
title: Annual Contract Value (USD)
type: measure
measure_id: MEAS005
entity: Booking Transaction Fact
technical_column: acv_usd
aggregation_type: Sum
related_entities:
  - Booking Transaction Fact
related_domains:
  - Revenue Analytics
  - Contract Management
---

# Annual Contract Value (USD)

## Business Definition
Annualized value of the booked contract or subscription in U.S. dollars.

## Aggregation Type
Sum

## Related Entities
- [Booking Transaction Fact](../entities/booking-transaction-fact.md)

## Related Domains
- [Revenue Analytics](../domains/revenue-analytics.md)
- [Contract Management](../domains/contract-management.md)

## Technical Mapping
`ontology.fact_bookings.acv_usd`

## Cross-Links
- [Measures Index](index.md)
- [Bundle Index](../index.md)