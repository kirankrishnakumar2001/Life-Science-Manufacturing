---
title: Quantity Sold
type: measure
measure_id: MEAS001
entity: Booking Transaction Fact
technical_column: quantity
aggregation_type: Sum
related_entities:
  - Booking Transaction Fact
related_domains:
  - Revenue Analytics
  - Cisco Sales Bookings and Revenue Analytics
---

# Quantity Sold

## Business Definition
Number of units, licenses, or service quantities booked in the transaction line.

## Aggregation Type
Sum

## Related Entities
- [Booking Transaction Fact](../entities/booking-transaction-fact.md)

## Related Domains
- [Revenue Analytics](../domains/revenue-analytics.md)
- [Cisco Sales Bookings and Revenue Analytics](../domains/cisco-sales-bookings-and-revenue-analytics.md)

## Technical Mapping
`ontology.fact_bookings.quantity`

## Cross-Links
- [Measures Index](index.md)
- [Bundle Index](../index.md)