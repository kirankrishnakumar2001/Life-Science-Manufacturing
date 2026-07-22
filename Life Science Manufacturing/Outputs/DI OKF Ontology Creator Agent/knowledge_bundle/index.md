---
title: Life Science Manufacturing OKF Knowledge Bundle
bundle: knowledge_bundle
domains_count: 9
entities_count: 8
relationships_count: 7
measures_count: 6
glossary_terms_count: 61
validation_status: warnings
---

# Life Science Manufacturing OKF Knowledge Bundle

## Overview
This Open Knowledge Format (OKF) knowledge bundle represents the validated semantic content extracted from the OSI Semantic Model for life science manufacturing analytics. The source semantic model describes a bookings and revenue analytics environment spanning contracts, customers, time, geography, partners, products, sales representatives, and booking transactions.

## Validation Summary
- OSI Semantic Model readability: Passed
- Business Process document readability: Warning - source `.docx` file could not be decoded by the reader tool
- Required semantic sections present: Passed
- Duplicate entities detected: None
- Duplicate domains detected: None
- Missing relationships: None for the defined star-schema entities

## Navigation
- [Semantic Summary](semantic_summary.md)
- [Metrics](metrics.md)
- [Domains](domains/index.md)
- [Entities](entities/index.md)
- [Relationships](relationships/index.md)
- [Measures](measures/index.md)
- [Glossary](glossary/index.md)

## Domains
- [Cisco Sales Bookings and Revenue Analytics](domains/cisco-sales-bookings-and-revenue-analytics.md)
- [Contract Management](domains/contract-management.md)
- [Customer Management](domains/customer-management.md)
- [Time Management](domains/time-management.md)
- [Geographic Management](domains/geographic-management.md)
- [Partner Management](domains/partner-management.md)
- [Product Management](domains/product-management.md)
- [Sales Management](domains/sales-management.md)
- [Revenue Analytics](domains/revenue-analytics.md)

## Entities
- [Contract Dimension](entities/contract-dimension.md)
- [Customer Dimension](entities/customer-dimension.md)
- [Date Dimension](entities/date-dimension.md)
- [Geography Dimension](entities/geography-dimension.md)
- [Partner Dimension](entities/partner-dimension.md)
- [Product Dimension](entities/product-dimension.md)
- [Sales Representative Dimension](entities/sales-representative-dimension.md)
- [Booking Transaction Fact](entities/booking-transaction-fact.md)

## Relationships
- [Contract Dimension to Booking Transaction Fact](relationships/contract-dimension-to-booking-transaction-fact.md)
- [Customer Dimension to Booking Transaction Fact](relationships/customer-dimension-to-booking-transaction-fact.md)
- [Date Dimension to Booking Transaction Fact](relationships/date-dimension-to-booking-transaction-fact.md)
- [Geography Dimension to Booking Transaction Fact](relationships/geography-dimension-to-booking-transaction-fact.md)
- [Partner Dimension to Booking Transaction Fact](relationships/partner-dimension-to-booking-transaction-fact.md)
- [Product Dimension to Booking Transaction Fact](relationships/product-dimension-to-booking-transaction-fact.md)
- [Sales Representative Dimension to Booking Transaction Fact](relationships/sales-representative-dimension-to-booking-transaction-fact.md)

## Measures
- [Quantity Sold](measures/quantity-sold.md)
- [Unit List Price (USD)](measures/unit-list-price-usd.md)
- [Discount Percentage](measures/discount-percentage.md)
- [Booking Amount (USD)](measures/booking-amount-usd.md)
- [Annual Contract Value (USD)](measures/annual-contract-value-usd.md)
- [Total Contract Value (USD)](measures/total-contract-value-usd.md)

## Notes
The business process document could not be read in source format, so this bundle preserves the semantic meaning of the OSI Semantic Model without additional process enrichment.