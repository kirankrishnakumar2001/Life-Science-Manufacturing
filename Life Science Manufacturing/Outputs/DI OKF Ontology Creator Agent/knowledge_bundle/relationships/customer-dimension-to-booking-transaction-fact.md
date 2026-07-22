---
title: Customer Dimension to Booking Transaction Fact
type: relationship
relationship_id: REL002
source_entity: Customer Dimension
target_entity: Booking Transaction Fact
relationship_type: Referential
cardinality: One-to-Many
source_attribute: Customer Key
target_attribute: Customer Key
confidence_score: 1.00
---

# Customer Dimension to Booking Transaction Fact

## Source Entity
- [Customer Dimension](../entities/customer-dimension.md)

## Target Entity
- [Booking Transaction Fact](../entities/booking-transaction-fact.md)

## Relationship Type
Referential

## Cardinality
One-to-Many

## Business Description
Each customer dimension record can be linked to many booking transaction records. This relationship enables analysis of bookings by account, segment, industry, and strategic customer tier.

## Attribute Mapping
- Parent Attribute: `Customer Key`
- Child Attribute: `Customer Key`

## Cross-Links
- [Relationships Index](index.md)
- [Bundle Index](../index.md)