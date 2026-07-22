---
title: Customer Dimension
type: entity
entity_id: ENT002
domain: Customer Management
technical_mapping: ontology.dim_customer
business_keys:
  - customer_key
  - customer_id
measures:
  - Booking Amount (USD)
  - Quantity Sold
relationships:
  - Customer Dimension to Booking Transaction Fact
related_concepts:
  - Customer Segment
  - Customer Industry
  - Account Tier
  - Headquarters Country
  - Headquarters Region
---

# Customer Dimension

## Business Definition
Reference entity containing customer master data used to analyze bookings by account, segment, industry, and headquarters geography.

## Technical Mapping
`ontology.dim_customer`

## Attributes
| Business Attribute | Technical Column | Data Type | Nullable | Key Type | Description |
| --- | --- | --- | --- | --- | --- |
| Customer Key | customer_key | integer | No | Primary Key | Surrogate key uniquely identifying a customer dimension record. |
| Customer ID | customer_id | character varying(20) | No | Business Key | Business identifier assigned to a customer account. |
| Customer Name | customer_name | character varying(80) | Yes | Attribute | Official name of the customer account. |
| Customer Segment | segment | character varying(30) | Yes | Attribute | Market segment to which the customer belongs, such as Service Provider, Enterprise, or Public Sector. |
| Customer Industry | industry | character varying(40) | Yes | Attribute | Industry classification of the customer account. |
| Account Tier | account_tier | character varying(20) | Yes | Attribute | Strategic ranking or coverage tier assigned to the customer account. |
| Headquarters Country | hq_country | character varying(40) | Yes | Attribute | Country where the customer’s headquarters is located. |
| Headquarters Region | hq_region | character varying(20) | Yes | Attribute | Broad geographic region where the customer’s headquarters is located. |

## Keys
- Primary Key: `customer_key`
- Business Key: `customer_id`

## Measures
- [Booking Amount (USD)](../measures/booking-amount-usd.md)
- [Quantity Sold](../measures/quantity-sold.md)

## Relationships
- [Customer Dimension to Booking Transaction Fact](../relationships/customer-dimension-to-booking-transaction-fact.md)

## Related Concepts
- [Customer Management](../domains/customer-management.md)
- [Customer Key](../glossary/customer-key.md)
- [Customer ID](../glossary/customer-id.md)
- [Customer Name](../glossary/customer-name.md)
- [Customer Segment](../glossary/customer-segment.md)
- [Customer Industry](../glossary/customer-industry.md)
- [Account Tier](../glossary/account-tier.md)
- [Headquarters Country](../glossary/headquarters-country.md)
- [Headquarters Region](../glossary/headquarters-region.md)

## Cross-Links
- [Entities Index](index.md)
- [Bundle Index](../index.md)