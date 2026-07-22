---
title: Partner Dimension to Booking Transaction Fact
type: relationship
relationship_id: REL005
source_entity: Partner Dimension
target_entity: Booking Transaction Fact
relationship_type: Referential
cardinality: One-to-Many
source_attribute: Partner Key
target_attribute: Partner Key
confidence_score: 1.00
---

# Partner Dimension to Booking Transaction Fact

## Source Entity
- [Partner Dimension](../entities/partner-dimension.md)

## Target Entity
- [Booking Transaction Fact](../entities/booking-transaction-fact.md)

## Relationship Type
Referential

## Cardinality
One-to-Many

## Business Description
Each partner dimension record can be associated with many booking transaction records. This relationship enables analysis by partner organization, partner type, partner tier, and route to market.

## Attribute Mapping
- Parent Attribute: `Partner Key`
- Child Attribute: `Partner Key`

## Cross-Links
- [Relationships Index](index.md)
- [Bundle Index](../index.md)