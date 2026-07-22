---
title: Sales Representative Dimension to Booking Transaction Fact
type: relationship
relationship_id: REL007
source_entity: Sales Representative Dimension
target_entity: Booking Transaction Fact
relationship_type: Referential
cardinality: One-to-Many
source_attribute: Sales Representative Key
target_attribute: Sales Representative Key
confidence_score: 1.00
---

# Sales Representative Dimension to Booking Transaction Fact

## Source Entity
- [Sales Representative Dimension](../entities/sales-representative-dimension.md)

## Target Entity
- [Booking Transaction Fact](../entities/booking-transaction-fact.md)

## Relationship Type
Referential

## Cardinality
One-to-Many

## Business Description
Each sales representative dimension record can be associated with many booking transactions. This relationship supports seller performance analysis by representative, role, team, and covered segment.

## Attribute Mapping
- Parent Attribute: `Sales Representative Key`
- Child Attribute: `Sales Representative Key`

## Cross-Links
- [Relationships Index](index.md)
- [Bundle Index](../index.md)