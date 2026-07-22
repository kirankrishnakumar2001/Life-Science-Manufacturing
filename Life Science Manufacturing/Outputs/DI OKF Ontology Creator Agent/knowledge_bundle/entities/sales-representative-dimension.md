---
title: Sales Representative Dimension
type: entity
entity_id: ENT007
domain: Sales Management
technical_mapping: ontology.dim_sales_rep
business_keys:
  - sales_rep_key
  - rep_id
measures:
  - Booking Amount (USD)
  - Quantity Sold
relationships:
  - Sales Representative Dimension to Booking Transaction Fact
related_concepts:
  - Sales Representative Name
  - Sales Role
  - Sales Team
  - Covered Segment
---

# Sales Representative Dimension

## Business Definition
Reference entity containing sales representative attributes used to analyze bookings by seller, team, role, and covered segment.

## Technical Mapping
`ontology.dim_sales_rep`

## Attributes
| Business Attribute | Technical Column | Data Type | Nullable | Key Type | Description |
| --- | --- | --- | --- | --- | --- |
| Sales Representative Key | sales_rep_key | integer | No | Primary Key | Surrogate key uniquely identifying a sales representative dimension record. |
| Sales Representative ID | rep_id | character varying(20) | No | Business Key | Business identifier assigned to a sales representative. |
| Sales Representative Name | rep_name | character varying(60) | Yes | Attribute | Full name of the sales representative. |
| Sales Role | sales_role | character varying(40) | Yes | Attribute | Job role or commercial role performed by the sales representative. |
| Sales Team | sales_team | character varying(40) | Yes | Attribute | Team or organizational unit to which the sales representative belongs. |
| Covered Segment | segment_covered | character varying(30) | Yes | Attribute | Customer market segment primarily covered by the sales representative. |

## Keys
- Primary Key: `sales_rep_key`
- Business Key: `rep_id`

## Measures
- [Booking Amount (USD)](../measures/booking-amount-usd.md)
- [Quantity Sold](../measures/quantity-sold.md)

## Relationships
- [Sales Representative Dimension to Booking Transaction Fact](../relationships/sales-representative-dimension-to-booking-transaction-fact.md)

## Related Concepts
- [Sales Management](../domains/sales-management.md)
- [Sales Representative Key](../glossary/sales-representative-key.md)
- [Sales Representative ID](../glossary/sales-representative-id.md)
- [Sales Representative Name](../glossary/sales-representative-name.md)
- [Sales Role](../glossary/sales-role.md)
- [Sales Team](../glossary/sales-team.md)
- [Covered Segment](../glossary/covered-segment.md)

## Cross-Links
- [Entities Index](index.md)
- [Bundle Index](../index.md)