---
title: Total Contract Value (USD)
type: measure
measure_id: MEAS006
entity: Booking Transaction Fact
technical_column: tcv_usd
aggregation_type: Sum
related_entities:
  - Booking Transaction Fact
related_domains:
  - Revenue Analytics
  - Contract Management
---

# Total Contract Value (USD)

## Business Definition
Total contractual value of the deal across the full contract term in U.S. dollars.

## Aggregation Type
Sum

## Related Entities
- [Booking Transaction Fact](../entities/booking-transaction-fact.md)

## Related Domains
- [Revenue Analytics](../domains/revenue-analytics.md)
- [Contract Management](../domains/contract-management.md)

## Technical Mapping
`ontology.fact_bookings.tcv_usd`

## Cross-Links
- [Measures Index](index.md)
- [Bundle Index](../index.md)