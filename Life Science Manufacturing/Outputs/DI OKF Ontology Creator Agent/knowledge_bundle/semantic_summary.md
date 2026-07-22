---
title: Semantic Summary
type: semantic_summary
source_model: OSI Semantic Model
validation_status: warnings
---

# Semantic Summary

## Source Scope
The semantic model describes a dimensional analytics structure centered on booking transactions. The primary business purpose is to support bookings and revenue analysis across customer, product, partner, geography, contract, sales, and time perspectives.

## Extracted Business Domains
1. Cisco Sales Bookings and Revenue Analytics
2. Contract Management
3. Customer Management
4. Time Management
5. Geographic Management
6. Partner Management
7. Product Management
8. Sales Management
9. Revenue Analytics

## Extracted Business Entities
- Contract Dimension
- Customer Dimension
- Date Dimension
- Geography Dimension
- Partner Dimension
- Product Dimension
- Sales Representative Dimension
- Booking Transaction Fact

## Extracted Relationships
The model follows a star-schema pattern in which the Booking Transaction Fact entity is the child in seven referential one-to-many relationships from the business dimensions.

- Contract Dimension -> Booking Transaction Fact
- Customer Dimension -> Booking Transaction Fact
- Date Dimension -> Booking Transaction Fact
- Geography Dimension -> Booking Transaction Fact
- Partner Dimension -> Booking Transaction Fact
- Product Dimension -> Booking Transaction Fact
- Sales Representative Dimension -> Booking Transaction Fact

## Extracted Measures
All measures are defined on the Booking Transaction Fact entity:
- Quantity Sold
- Unit List Price (USD)
- Discount Percentage
- Booking Amount (USD)
- Annual Contract Value (USD)
- Total Contract Value (USD)

## Business Glossary Coverage
The glossary maps core business concepts to technical tables and columns in the ontology schema. Coverage includes entities, keys, dimensional descriptors, transactional descriptors, and financial measures.

## Validation Warnings
- The Business Process `.docx` source could not be decoded by the file reader tool, so process-based enrichment was not applied.
- No semantic structural defects were found in the OSI Semantic Model.

## Cross-Links
- [Bundle Index](index.md)
- [Metrics](metrics.md)
- [Domains Index](domains/index.md)
- [Entities Index](entities/index.md)
- [Relationships Index](relationships/index.md)
- [Measures Index](measures/index.md)
- [Glossary Index](glossary/index.md)