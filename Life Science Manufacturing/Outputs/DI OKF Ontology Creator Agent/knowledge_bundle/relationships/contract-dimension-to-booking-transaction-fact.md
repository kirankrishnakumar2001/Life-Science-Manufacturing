---
title: Contract Dimension to Booking Transaction Fact
type: relationship
relationship_id: REL001
source_entity: Contract Dimension
target_entity: Booking Transaction Fact
relationship_type: Referential
cardinality: One-to-Many
source_attribute: Contract Key
target_attribute: Contract Key
confidence_score: 1.00
---

# Contract Dimension to Booking Transaction Fact

## Source Entity
- [Contract Dimension](../entities/contract-dimension.md)

## Target Entity
- [Booking Transaction Fact](../entities/booking-transaction-fact.md)

## Relationship Type
Referential

## Cardinality
One-to-Many

## Business Description
Each contract dimension record can be associated with many booking transaction records through the contract key. This relationship supports analysis of bookings by contract structure, renewal behavior, and coverage level.

## Attribute Mapping
- Parent Attribute: `Contract Key`
- Child Attribute: `Contract Key`

## Cross-Links
- [Relationships Index](index.md)
- [Bundle Index](../index.md)