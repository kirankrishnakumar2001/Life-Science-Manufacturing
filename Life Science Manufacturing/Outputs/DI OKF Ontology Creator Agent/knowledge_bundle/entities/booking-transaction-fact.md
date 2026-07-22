---
title: Booking Transaction Fact
type: entity
entity_id: ENT008
domain: Revenue Analytics
technical_mapping: ontology.fact_bookings
business_keys:
  - booking_id
  - order_number
  - order_line_number
measures:
  - Quantity Sold
  - Unit List Price (USD)
  - Discount Percentage
  - Booking Amount (USD)
  - Annual Contract Value (USD)
  - Total Contract Value (USD)
relationships:
  - Contract Dimension to Booking Transaction Fact
  - Customer Dimension to Booking Transaction Fact
  - Date Dimension to Booking Transaction Fact
  - Geography Dimension to Booking Transaction Fact
  - Partner Dimension to Booking Transaction Fact
  - Product Dimension to Booking Transaction Fact
  - Sales Representative Dimension to Booking Transaction Fact
related_concepts:
  - Booking Type
  - Renewal Indicator
---

# Booking Transaction Fact

## Business Definition
Central transactional entity capturing individual booking transaction lines and associated financial measures linked to all core business dimensions.

## Technical Mapping
`ontology.fact_bookings`

## Attributes
| Business Attribute | Technical Column | Data Type | Nullable | Key Type | Description |
| --- | --- | --- | --- | --- | --- |
| Booking ID | booking_id | integer | No | Primary Key | Unique identifier for an individual booking transaction line. |
| Order Number | order_number | character varying(20) | Yes | Business Key | Business order reference associated with the booking transaction. |
| Order Line Number | order_line_number | integer | Yes | Business Key | Line number within the order identifying the booked line item. |
| Booking Date Key | date_key | integer | Yes | Foreign Key | Foreign key linking the booking to the date dimension. |
| Customer Key | customer_key | integer | Yes | Foreign Key | Foreign key linking the booking to the customer dimension. |
| Product Key | product_key | integer | Yes | Foreign Key | Foreign key linking the booking to the product dimension. |
| Partner Key | partner_key | integer | Yes | Foreign Key | Foreign key linking the booking to the partner dimension. |
| Geography Key | geography_key | integer | Yes | Foreign Key | Foreign key linking the booking to the geography dimension. |
| Sales Representative Key | sales_rep_key | integer | Yes | Foreign Key | Foreign key linking the booking to the sales representative dimension. |
| Contract Key | contract_key | integer | Yes | Foreign Key | Foreign key linking the booking to the contract dimension. |
| Booking Type | booking_type | character varying(15) | Yes | Attribute | Classification of the booking event, such as New or Renewal. |
| Renewal Indicator | is_renewal | integer | Yes | Attribute | Numeric flag indicating whether the booking represents a renewal transaction. |
| Quantity Sold | quantity | integer | Yes | Measure | Number of units, licenses, or service quantities booked in the transaction line. |
| Unit List Price (USD) | unit_list_price_usd | numeric(12,2) | Yes | Measure | Standard list price per unit in U.S. dollars before discounts. |
| Discount Percentage | discount_pct | numeric(5,2) | Yes | Measure | Discount rate applied to the list price for the booked transaction. |
| Booking Amount (USD) | booking_amount_usd | numeric(14,2) | Yes | Measure | Total booked transaction amount in U.S. dollars after pricing and discount considerations. |
| Annual Contract Value (USD) | acv_usd | numeric(14,2) | Yes | Measure | Annualized value of the booked contract or subscription in U.S. dollars. |
| Total Contract Value (USD) | tcv_usd | numeric(14,2) | Yes | Measure | Total contractual value of the deal across the full contract term in U.S. dollars. |

## Keys
- Primary Key: `booking_id`
- Business Keys: `order_number`, `order_line_number`
- Foreign Keys: `date_key`, `customer_key`, `product_key`, `partner_key`, `geography_key`, `sales_rep_key`, `contract_key`

## Measures
- [Quantity Sold](../measures/quantity-sold.md)
- [Unit List Price (USD)](../measures/unit-list-price-usd.md)
- [Discount Percentage](../measures/discount-percentage.md)
- [Booking Amount (USD)](../measures/booking-amount-usd.md)
- [Annual Contract Value (USD)](../measures/annual-contract-value-usd.md)
- [Total Contract Value (USD)](../measures/total-contract-value-usd.md)

## Relationships
- [Contract Dimension to Booking Transaction Fact](../relationships/contract-dimension-to-booking-transaction-fact.md)
- [Customer Dimension to Booking Transaction Fact](../relationships/customer-dimension-to-booking-transaction-fact.md)
- [Date Dimension to Booking Transaction Fact](../relationships/date-dimension-to-booking-transaction-fact.md)
- [Geography Dimension to Booking Transaction Fact](../relationships/geography-dimension-to-booking-transaction-fact.md)
- [Partner Dimension to Booking Transaction Fact](../relationships/partner-dimension-to-booking-transaction-fact.md)
- [Product Dimension to Booking Transaction Fact](../relationships/product-dimension-to-booking-transaction-fact.md)
- [Sales Representative Dimension to Booking Transaction Fact](../relationships/sales-representative-dimension-to-booking-transaction-fact.md)

## Related Concepts
- [Revenue Analytics](../domains/revenue-analytics.md)
- [Cisco Sales Bookings and Revenue Analytics](../domains/cisco-sales-bookings-and-revenue-analytics.md)
- [Booking ID](../glossary/booking-id.md)
- [Order Number](../glossary/order-number.md)
- [Order Line Number](../glossary/order-line-number.md)
- [Booking Date Key](../glossary/booking-date-key.md)
- [Booking Type](../glossary/booking-type.md)
- [Renewal Indicator](../glossary/renewal-indicator.md)

## Cross-Links
- [Entities Index](index.md)
- [Bundle Index](../index.md)