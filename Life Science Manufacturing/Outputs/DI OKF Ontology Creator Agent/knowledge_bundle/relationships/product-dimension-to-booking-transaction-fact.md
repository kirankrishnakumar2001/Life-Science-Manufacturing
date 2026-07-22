---
title: Product Dimension to Booking Transaction Fact
type: relationship
relationship_id: REL006
source_entity: Product Dimension
target_entity: Booking Transaction Fact
relationship_type: Referential
cardinality: One-to-Many
source_attribute: Product Key
target_attribute: Product Key
confidence_score: 1.00
---

# Product Dimension to Booking Transaction Fact

## Source Entity
- [Product Dimension](../entities/product-dimension.md)

## Target Entity
- [Booking Transaction Fact](../entities/booking-transaction-fact.md)

## Relationship Type
Referential

## Cardinality
One-to-Many

## Business Description
Each product dimension record can be linked to many booking transactions. This supports analysis by product identity, family, technology domain, offer type, and business portfolio.

## Attribute Mapping
- Parent Attribute: `Product Key`
- Child Attribute: `Product Key`

## Cross-Links
- [Relationships Index](index.md)
- [Bundle Index](../index.md)