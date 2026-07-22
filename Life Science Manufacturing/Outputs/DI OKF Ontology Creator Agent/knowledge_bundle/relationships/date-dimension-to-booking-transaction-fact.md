---
title: Date Dimension to Booking Transaction Fact
type: relationship
relationship_id: REL003
source_entity: Date Dimension
target_entity: Booking Transaction Fact
relationship_type: Referential
cardinality: One-to-Many
source_attribute: Date Key
target_attribute: Booking Date Key
confidence_score: 1.00
---

# Date Dimension to Booking Transaction Fact

## Source Entity
- [Date Dimension](../entities/date-dimension.md)

## Target Entity
- [Booking Transaction Fact](../entities/booking-transaction-fact.md)

## Relationship Type
Referential

## Cardinality
One-to-Many

## Business Description
Each date dimension record can be associated with many booking transactions through the booking date key. This relationship enables calendar and fiscal reporting for bookings and revenue analysis.

## Attribute Mapping
- Parent Attribute: `Date Key`
- Child Attribute: `Booking Date Key`

## Cross-Links
- [Relationships Index](index.md)
- [Bundle Index](../index.md)