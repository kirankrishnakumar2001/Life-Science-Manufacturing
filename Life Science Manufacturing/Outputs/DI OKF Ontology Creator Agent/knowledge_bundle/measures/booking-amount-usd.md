---
title: Booking Amount (USD)
type: measure
measure_id: MEAS004
entity: Booking Transaction Fact
technical_column: booking_amount_usd
aggregation_type: Sum
related_entities:
  - Booking Transaction Fact
related_domains:
  - Revenue Analytics
  - Cisco Sales Bookings and Revenue Analytics
---

# Booking Amount (USD)

## Business Definition
Total booked transaction amount in U.S. dollars after pricing and discount considerations.

## Aggregation Type
Sum

## Related Entities
- [Booking Transaction Fact](../entities/booking-transaction-fact.md)

## Related Domains
- [Revenue Analytics](../domains/revenue-analytics.md)
- [Cisco Sales Bookings and Revenue Analytics](../domains/cisco-sales-bookings-and-revenue-analytics.md)

## Technical Mapping
`ontology.fact_bookings.booking_amount_usd`

## Cross-Links
- [Measures Index](index.md)
- [Bundle Index](../index.md)