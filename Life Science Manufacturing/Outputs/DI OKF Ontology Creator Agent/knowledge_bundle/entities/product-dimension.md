---
title: Product Dimension
type: entity
entity_id: ENT006
domain: Product Management
technical_mapping: ontology.dim_product
business_keys:
  - product_key
  - product_id
measures:
  - Quantity Sold
  - Unit List Price (USD)
  - Booking Amount (USD)
relationships:
  - Product Dimension to Booking Transaction Fact
related_concepts:
  - Product Name
  - Product Family
  - Technology Domain
  - Offer Type
  - Business Entity
---

# Product Dimension

## Business Definition
Reference entity containing product and offer attributes used to analyze bookings across portfolios, technology areas, and offer types.

## Technical Mapping
`ontology.dim_product`

## Attributes
| Business Attribute | Technical Column | Data Type | Nullable | Key Type | Description |
| --- | --- | --- | --- | --- | --- |
| Product Key | product_key | integer | No | Primary Key | Surrogate key uniquely identifying a product dimension record. |
| Product ID | product_id | character varying(30) | No | Business Key | Business identifier or SKU-like reference assigned to a product or offering. |
| Product Name | product_name | character varying(80) | Yes | Attribute | Descriptive name of the Cisco product or offering. |
| Product Family | product_family | character varying(30) | Yes | Attribute | Higher-level family grouping for related products. |
| Technology Domain | technology_domain | character varying(40) | Yes | Attribute | Technology area or solution domain to which the product belongs. |
| Offer Type | offer_type | character varying(30) | Yes | Attribute | Commercial form of the offering, such as Hardware, SaaS Subscription, or Software Subscription. |
| Business Entity | business_entity | character varying(30) | Yes | Attribute | Cisco business unit or portfolio grouping associated with the product. |

## Keys
- Primary Key: `product_key`
- Business Key: `product_id`

## Measures
- [Quantity Sold](../measures/quantity-sold.md)
- [Unit List Price (USD)](../measures/unit-list-price-usd.md)
- [Booking Amount (USD)](../measures/booking-amount-usd.md)

## Relationships
- [Product Dimension to Booking Transaction Fact](../relationships/product-dimension-to-booking-transaction-fact.md)

## Related Concepts
- [Product Management](../domains/product-management.md)
- [Product Key](../glossary/product-key.md)
- [Product ID](../glossary/product-id.md)
- [Product Name](../glossary/product-name.md)
- [Product Family](../glossary/product-family.md)
- [Technology Domain](../glossary/technology-domain.md)
- [Offer Type](../glossary/offer-type.md)
- [Business Entity](../glossary/business-entity.md)

## Cross-Links
- [Entities Index](index.md)
- [Bundle Index](../index.md)