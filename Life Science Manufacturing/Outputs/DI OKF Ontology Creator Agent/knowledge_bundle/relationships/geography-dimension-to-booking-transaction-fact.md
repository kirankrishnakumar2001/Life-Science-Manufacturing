---
title: Geography Dimension to Booking Transaction Fact
type: relationship
relationship_id: REL004
source_entity: Geography Dimension
target_entity: Booking Transaction Fact
relationship_type: Referential
cardinality: One-to-Many
source_attribute: Geography Key
target_attribute: Geography Key
confidence_score: 1.00
---

# Geography Dimension to Booking Transaction Fact

## Source Entity
- [Geography Dimension](../entities/geography-dimension.md)

## Target Entity
- [Booking Transaction Fact](../entities/booking-transaction-fact.md)

## Relationship Type
Referential

## Cardinality
One-to-Many

## Business Description
Each geography dimension record can be related to many booking transactions. This supports geographic rollup and comparative analysis by region, theater, and country.

## Attribute Mapping
- Parent Attribute: `Geography Key`
- Child Attribute: `Geography Key`

## Cross-Links
- [Relationships Index](index.md)
- [Bundle Index](../index.md)