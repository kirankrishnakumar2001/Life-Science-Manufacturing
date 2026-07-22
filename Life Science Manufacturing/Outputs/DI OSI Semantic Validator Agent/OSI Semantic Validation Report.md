# Overall Status

| Overall Validation Score | Overall Status |
|--------------------------|----------------|
| 96.67% | PASS WITH WARNINGS |

# Completeness Assessment

| Validation Area | Status | Details |
| --- | --- | --- |
| Table Coverage | PASS | All 8 source tables are represented as entities in the OSI Semantic Model. |
| Entity Coverage | PASS | All expected business entities from the data dictionary and glossary are present: 7 dimensions and 1 fact entity. |
| Attribute Coverage | PASS | All 61 source columns are represented as semantic attributes with aligned technical columns and data types. |
| Relationship Coverage | PASS | All 7 source foreign key relationships are represented in the semantic model. |
| Primary Key Coverage | PASS | All 8 primary keys from the source metadata are represented correctly in the semantic model. |
| Foreign Key Coverage | PASS | All 7 foreign keys from ontology.fact_bookings are represented correctly as semantic foreign key attributes and relationships. |
| Measure Coverage | PASS | All 6 business measures documented in the glossary are represented in the semantic model measures section. |
| Business Domain Coverage | PASS | All entities are assigned to appropriate domains, including Contract, Customer, Time, Geographic, Partner, Product, Sales, and Revenue Analytics. |
| Business Glossary Coverage | PASS WITH WARNINGS | All semantic entities and attributes map to glossary terms, but shared key terms are consolidated in glossary mappings for both PK and FK usage rather than always distinguished by role. |

## Completeness Issues

| Severity | Issue | Impact |
| --- | --- | --- |
| Low | Shared glossary terms such as Customer Key, Product Key, Partner Key, Geography Key, and Sales Representative Key are reused across both dimension primary keys and fact foreign keys. | Slightly reduces role-level semantic specificity for downstream consumers expecting separate PK and FK glossary terms. |

# Accuracy Assessment

| Validation Area | Status | Details |
| --- | --- | --- |
| Entity Consistency | PASS | Entity names, technical table mappings, and descriptions are consistent with the supplied data dictionary and glossary. |
| Relationship Consistency | PASS | All semantic relationships align with documented PK-FK relationships and one-to-many cardinality from the source metadata. |
| Business Terminology Consistency | PASS WITH WARNINGS | Terminology is largely aligned to the glossary, with minor variation between shared key names and role-qualified names such as Date Key versus Booking Date Key. |
| Attribute Mapping | PASS | Attribute-to-column mappings are accurate across all 61 columns with no unmapped or mismapped columns detected. |
| Domain Assignment | PASS | Domain assignments are accurate and consistent with the business glossary domain structure. |
| Duplicate Entities | PASS | No duplicate entities were identified in the semantic model. |
| Duplicate Relationships | PASS | No duplicate relationships were identified in the semantic model. |
| Circular Relationships | PASS | No circular relationships were identified; the model follows a clean star-schema semantic pattern. |
| Invalid Mappings | PASS WITH WARNINGS | Mappings are structurally valid, but Discount Percentage is modeled as a percentage while profiling evidence indicates decimal fraction storage. |
| Broken References | PASS | No broken entity, attribute, relationship, or glossary references were detected. |

## Accuracy Issues

| Severity | Area | Issue | Evidence |
| --- | --- | --- | --- |
| Medium | Invalid Mappings | Discount Percentage naming suggests percentage-point semantics, but the profiled values indicate decimal fraction storage. | profiling for ontology.fact_bookings.discount_pct shows values from 0.11 to 0.28; glossary notes it appears stored as decimal fraction. |
| Low | Business Terminology Consistency | The semantic model uses both Date Key and Booking Date Key for the same technical join concept across dimension and fact contexts. | ontology.dim_date.date_key is modeled as Date Key, while ontology.fact_bookings.date_key is modeled as Booking Date Key. |
| Low | Business Terminology Consistency | Shared key business terms are used across dimension PKs and fact FKs without a universal role-qualification convention. | Customer Key, Product Key, Partner Key, Geography Key, Contract Key, and Sales Representative Key appear in both PK and FK contexts. |

# Efficiency Assessment

| Validation Area | Status | Details |
| --- | --- | --- |
| Redundant Entities | PASS | No redundant entities were found; each entity maps uniquely to a source table. |
| Redundant Relationships | PASS | No unnecessary or repeated relationships were detected. |
| Duplicate Glossary Mapping | PASS WITH WARNINGS | Glossary reuse is intentional and supports semantic reuse, but several shared key mappings combine multiple technical contexts under one business term. |
| Model Simplicity | PASS | The semantic model is concise and reflects a straightforward star schema with 8 entities and 7 relationships. |
| Relationship Optimization | PASS | Relationships are optimized around a central fact entity with direct dimension joins and no unnecessary hops. |
| Domain Organization | PASS | Domain segmentation is clear and supports maintainability and subject-area navigation. |
| Semantic Reuse | PASS | Reuse of core business terms across PK and FK contexts improves consistency, though it slightly reduces role precision. |
| Maintainability | PASS | The model is highly maintainable due to complete coverage, consistent structure, and absence of duplicates or broken references. |

## Efficiency Issues

| Severity | Area | Issue | Impact |
| --- | --- | --- | --- |
| Low | Duplicate Glossary Mapping | Consolidated glossary mappings for shared keys trade precision for reuse. | May require downstream semantic consumers to infer whether a reused key term is functioning as a primary key or foreign key in a specific context. |

# Recommendations

## Completeness Recommendations

| Priority | Recommendation | Reason |
| --- | --- | --- |
| Medium | Add role-specific glossary variants for reused shared keys where needed, such as Customer Key (Dimension) and Customer Key (Fact FK), while retaining common preferred terms. | Improves semantic specificity without reducing glossary coverage. |
| Low | Add explicit semantic-role metadata for each attribute, such as Primary Key, Foreign Key, Descriptor, Indicator, or Measure. | Helps downstream knowledge engineering processes consume the model with less inference. |

## Accuracy Recommendations

| Priority | Recommendation | Reason |
| --- | --- | --- |
| High | Clarify whether discount_pct is stored as a decimal fraction or true percentage and align the business term or definition accordingly. | Prevents incorrect analytical interpretation and display logic. |
| Medium | Standardize naming policy for shared join keys, especially Date Key versus Booking Date Key. | Improves terminology consistency across entities and attributes. |
| Low | Define a formal naming convention for when shared key terms should be role-qualified in fact versus dimension contexts. | Reduces ambiguity in semantic mappings and glossary governance. |

## Efficiency Recommendations

| Priority | Recommendation | Reason |
| --- | --- | --- |
| Medium | Preserve semantic reuse for shared keys but enrich mappings with role metadata instead of duplicating glossary terms unnecessarily. | Maintains model simplicity while improving downstream interpretability. |
| Low | Document aggregation and display semantics for rate-style measures such as Discount Percentage separately from additive monetary measures. | Improves maintainability and metric consumption efficiency in downstream semantic applications. |