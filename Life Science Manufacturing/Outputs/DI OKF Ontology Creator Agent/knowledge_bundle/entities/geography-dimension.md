---
title: Geography Dimension
type: entity
entity_id: ENT004
domain: Geographic Management
technical_mapping: ontology.dim_geography
business_keys:
  - geography_key
measures:
  - Booking Amount (USD)
  - Quantity Sold
relationships:
  - Geography Dimension to Booking Transaction Fact
related_concepts:
  - Sales Region
  - Sales Theater
  - Country
---

# Geography Dimension

## Business Definition
Reference entity containing regional, theater, and country attributes used to group bookings geographically.

## Technical Mapping
`ontology.dim_geography`

## Attributes
| Business Attribute | Technical Column | Data Type | Nullable | Key Type | Description |
| --- | --- | --- | --- | --- | --- |
| Geography Key | geography_key | integer | No | Primary Key | Surrogate key uniquely identifying a geography dimension record. |
| Sales Region | region | character varying(20) | Yes | Attribute | Top-level geographic sales region, such as Americas, APJC, or EMEA. |
| Sales Theater | theater | character varying(30) | Yes | Attribute | Intermediate geographic grouping or theater within a region. |
| Country | country | character varying(40) | Yes | Attribute | Country associated with the geography record. |

## Keys
- Primary / Business Key: `geography_key`

## Measures
- [Booking Amount (USD)](../measures/booking-amount-usd.md)
- [Quantity Sold](../measures/quantity-sold.md)

## Relationships
- [Geography Dimension to Booking Transaction Fact](../relationships/geography-dimension-to-booking-transaction-fact.md)

## Related Concepts
- [Geographic Management](../domains/geographic-management.md)
- [Geography Key](../glossary/geography-key.md)
- [Sales Region](../glossary/sales-region.md)
- [Sales Theater](../glossary/sales-theater.md)
- [Country](../glossary/country.md)

## Cross-Links
- [Entities Index](index.md)
- [Bundle Index](../index.md)