---
title: Partner Dimension
type: entity
entity_id: ENT005
domain: Partner Management
technical_mapping: ontology.dim_partner
business_keys:
  - partner_key
  - partner_id
measures:
  - Booking Amount (USD)
  - Discount Percentage
relationships:
  - Partner Dimension to Booking Transaction Fact
related_concepts:
  - Partner Name
  - Partner Type
  - Partner Tier
  - Route to Market
---

# Partner Dimension

## Business Definition
Reference entity containing partner master data used to analyze indirect and direct sales channels.

## Technical Mapping
`ontology.dim_partner`

## Attributes
| Business Attribute | Technical Column | Data Type | Nullable | Key Type | Description |
| --- | --- | --- | --- | --- | --- |
| Partner Key | partner_key | integer | No | Primary Key | Surrogate key uniquely identifying a partner dimension record. |
| Partner ID | partner_id | character varying(20) | No | Business Key | Business identifier assigned to a partner account. |
| Partner Name | partner_name | character varying(60) | Yes | Attribute | Official name of the partner organization involved in the sale. |
| Partner Type | partner_type | character varying(30) | Yes | Attribute | Classification of the partner, such as distributor, value-added reseller, systems integrator, or direct. |
| Partner Tier | partner_tier | character varying(30) | Yes | Attribute | Program tier or commercial ranking assigned to the partner. |
| Route to Market | route_to_market | character varying(20) | Yes | Attribute | Sales channel path used to fulfill the sale, such as Direct, Reseller, or Two-Tier. |

## Keys
- Primary Key: `partner_key`
- Business Key: `partner_id`

## Measures
- [Booking Amount (USD)](../measures/booking-amount-usd.md)
- [Discount Percentage](../measures/discount-percentage.md)

## Relationships
- [Partner Dimension to Booking Transaction Fact](../relationships/partner-dimension-to-booking-transaction-fact.md)

## Related Concepts
- [Partner Management](../domains/partner-management.md)
- [Partner Key](../glossary/partner-key.md)
- [Partner ID](../glossary/partner-id.md)
- [Partner Name](../glossary/partner-name.md)
- [Partner Type](../glossary/partner-type.md)
- [Partner Tier](../glossary/partner-tier.md)
- [Route to Market](../glossary/route-to-market.md)

## Cross-Links
- [Entities Index](index.md)
- [Bundle Index](../index.md)