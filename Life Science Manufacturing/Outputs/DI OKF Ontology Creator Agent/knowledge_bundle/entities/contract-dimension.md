---
title: Contract Dimension
type: entity
entity_id: ENT001
domain: Contract Management
technical_mapping: ontology.dim_contract
business_keys:
  - contract_key
measures:
  - Annual Contract Value (USD)
  - Total Contract Value (USD)
relationships:
  - Contract Dimension to Booking Transaction Fact
related_concepts:
  - Contract Type
  - Contract Term in Months
  - Auto-Renew Indicator
  - Coverage Level
---

# Contract Dimension

## Business Definition
Reference entity containing contract attributes used to classify bookings by commercial agreement structure, term, renewal behavior, and support coverage.

## Technical Mapping
`ontology.dim_contract`

## Attributes
| Business Attribute | Technical Column | Data Type | Nullable | Key Type | Description |
| --- | --- | --- | --- | --- | --- |
| Contract Key | contract_key | integer | No | Primary Key | Surrogate key uniquely identifying a contract dimension record. |
| Contract Type | contract_type | character varying(40) | Yes | Attribute | Type of commercial agreement associated with a booking, such as Enterprise Agreement, SaaS Subscription, SmartNet, or Solution Support. |
| Contract Term in Months | term_months | integer | Yes | Attribute | Number of months covered by the contract or agreement. |
| Auto-Renew Indicator | auto_renew_flag | character(1) | Yes | Attribute | Flag indicating whether the contract is configured to renew automatically at the end of its term. |
| Coverage Level | coverage_level | character varying(20) | Yes | Attribute | Service or support coverage tier associated with the contract. |

## Keys
- Primary / Business Key: `contract_key`

## Measures
- [Annual Contract Value (USD)](../measures/annual-contract-value-usd.md)
- [Total Contract Value (USD)](../measures/total-contract-value-usd.md)

## Relationships
- [Contract Dimension to Booking Transaction Fact](../relationships/contract-dimension-to-booking-transaction-fact.md)

## Related Concepts
- [Contract Management](../domains/contract-management.md)
- [Contract Key](../glossary/contract-key.md)
- [Contract Type](../glossary/contract-type.md)
- [Contract Term in Months](../glossary/contract-term-in-months.md)
- [Auto-Renew Indicator](../glossary/auto-renew-indicator.md)
- [Coverage Level](../glossary/coverage-level.md)

## Cross-Links
- [Entities Index](index.md)
- [Bundle Index](../index.md)