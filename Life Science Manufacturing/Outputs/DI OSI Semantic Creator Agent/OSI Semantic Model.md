## Domains

| Domain ID | Domain Name | Description |
| --- | --- | --- |
| DOM001 | Cisco Sales Bookings and Revenue Analytics | Business domain representing Cisco sales booking operations for enterprise networking, security, collaboration, observability, and software subscription products, supporting analysis of bookings across customers, products, partners, geographies, sales representatives, contracts, and fiscal periods. |
| DOM002 | Contract Management | Business domain for contract classification, term, renewal behavior, and coverage attributes used in booking analysis. |
| DOM003 | Customer Management | Business domain for customer master data used for account, segment, industry, and headquarters analysis. |
| DOM004 | Time Management | Business domain for calendar and fiscal reporting periods used in booking and revenue analysis. |
| DOM005 | Geographic Management | Business domain for regional, theater, and country structures used in geographic performance analysis. |
| DOM006 | Partner Management | Business domain for partner master data supporting channel, route-to-market, and partner segmentation analysis. |
| DOM007 | Product Management | Business domain for product, portfolio, technology, and offer attributes used in product performance analysis. |
| DOM008 | Sales Management | Business domain for sales representative, role, team, and coverage attributes used in sales performance analysis. |
| DOM009 | Revenue Analytics | Business domain for booking transaction measures, pricing, discounting, and contract value analysis. |

## Entities

| Entity ID | Domain ID | Business Name | Technical Table Name | Description | Business Keys |
| --- | --- | --- | --- | --- | --- |
| ENT001 | DOM002 | Contract Dimension | ontology.dim_contract | Reference entity containing contract attributes used to classify bookings by commercial agreement structure, term, renewal behavior, and support coverage. | contract_key |
| ENT002 | DOM003 | Customer Dimension | ontology.dim_customer | Reference entity containing customer master data used to analyze bookings by account, segment, industry, and headquarters geography. | customer_key; customer_id |
| ENT003 | DOM004 | Date Dimension | ontology.dim_date | Reference entity containing calendar and fiscal attributes used to analyze bookings across reporting dates, fiscal years, quarters, and periods. | date_key |
| ENT004 | DOM005 | Geography Dimension | ontology.dim_geography | Reference entity containing regional, theater, and country attributes used to group bookings geographically. | geography_key |
| ENT005 | DOM006 | Partner Dimension | ontology.dim_partner | Reference entity containing partner master data used to analyze indirect and direct sales channels. | partner_key; partner_id |
| ENT006 | DOM007 | Product Dimension | ontology.dim_product | Reference entity containing product and offer attributes used to analyze bookings across portfolios, technology areas, and offer types. | product_key; product_id |
| ENT007 | DOM008 | Sales Representative Dimension | ontology.dim_sales_rep | Reference entity containing sales representative attributes used to analyze bookings by seller, team, role, and covered segment. | sales_rep_key; rep_id |
| ENT008 | DOM009 | Booking Transaction Fact | ontology.fact_bookings | Central transactional entity capturing individual booking transaction lines and associated financial measures linked to all core business dimensions. | booking_id; order_number; order_line_number |

## Attributes

| Attribute ID | Entity ID | Business Attribute | Technical Column | Data Type | Nullable | Primary Key | Foreign Key | Description |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ATTR001 | ENT001 | Contract Key | contract_key | integer | No | Yes | No | Surrogate key uniquely identifying a contract dimension record. |
| ATTR002 | ENT001 | Contract Type | contract_type | character varying(40) | Yes | No | No | Type of commercial agreement associated with a booking, such as Enterprise Agreement, SaaS Subscription, SmartNet, or Solution Support. |
| ATTR003 | ENT001 | Contract Term in Months | term_months | integer | Yes | No | No | Number of months covered by the contract or agreement. |
| ATTR004 | ENT001 | Auto-Renew Indicator | auto_renew_flag | character(1) | Yes | No | No | Flag indicating whether the contract is configured to renew automatically at the end of its term. |
| ATTR005 | ENT001 | Coverage Level | coverage_level | character varying(20) | Yes | No | No | Service or support coverage tier associated with the contract. |
| ATTR006 | ENT002 | Customer Key | customer_key | integer | No | Yes | No | Surrogate key uniquely identifying a customer dimension record. |
| ATTR007 | ENT002 | Customer ID | customer_id | character varying(20) | No | No | No | Business identifier assigned to a customer account. |
| ATTR008 | ENT002 | Customer Name | customer_name | character varying(80) | Yes | No | No | Official name of the customer account. |
| ATTR009 | ENT002 | Customer Segment | segment | character varying(30) | Yes | No | No | Market segment to which the customer belongs, such as Service Provider, Enterprise, or Public Sector. |
| ATTR010 | ENT002 | Customer Industry | industry | character varying(40) | Yes | No | No | Industry classification of the customer account. |
| ATTR011 | ENT002 | Account Tier | account_tier | character varying(20) | Yes | No | No | Strategic ranking or coverage tier assigned to the customer account. |
| ATTR012 | ENT002 | Headquarters Country | hq_country | character varying(40) | Yes | No | No | Country where the customer’s headquarters is located. |
| ATTR013 | ENT002 | Headquarters Region | hq_region | character varying(20) | Yes | No | No | Broad geographic region where the customer’s headquarters is located. |
| ATTR014 | ENT003 | Date Key | date_key | integer | No | Yes | No | Surrogate or smart key representing the reporting date in YYYYMMDD-style numeric format. |
| ATTR015 | ENT003 | Full Date | full_date | date | No | No | No | Calendar date represented by the date dimension record. |
| ATTR016 | ENT003 | Month Name | month_name | character varying(12) | Yes | No | No | Name of the calendar month associated with the date. |
| ATTR017 | ENT003 | Calendar Year | calendar_year | integer | Yes | No | No | Four-digit calendar year associated with the reporting date. |
| ATTR018 | ENT003 | Fiscal Year | fiscal_year | character varying(6) | Yes | No | No | Fiscal year label used for internal business reporting, such as FY24. |
| ATTR019 | ENT003 | Fiscal Quarter | fiscal_quarter | character varying(10) | Yes | No | No | Fiscal quarter label associated with the date, such as FY24 Q1. |
| ATTR020 | ENT003 | Fiscal Period Sequence | fiscal_period_seq | integer | Yes | No | No | Ordered sequence number of the fiscal reporting period within the profiled range. |
| ATTR021 | ENT004 | Geography Key | geography_key | integer | No | Yes | No | Surrogate key uniquely identifying a geography dimension record. |
| ATTR022 | ENT004 | Sales Region | region | character varying(20) | Yes | No | No | Top-level geographic sales region, such as Americas, APJC, or EMEA. |
| ATTR023 | ENT004 | Sales Theater | theater | character varying(30) | Yes | No | No | Intermediate geographic grouping or theater within a region. |
| ATTR024 | ENT004 | Country | country | character varying(40) | Yes | No | No | Country associated with the geography record. |
| ATTR025 | ENT005 | Partner Key | partner_key | integer | No | Yes | No | Surrogate key uniquely identifying a partner dimension record. |
| ATTR026 | ENT005 | Partner ID | partner_id | character varying(20) | No | No | No | Business identifier assigned to a partner account. |
| ATTR027 | ENT005 | Partner Name | partner_name | character varying(60) | Yes | No | No | Official name of the partner organization involved in the sale. |
| ATTR028 | ENT005 | Partner Type | partner_type | character varying(30) | Yes | No | No | Classification of the partner, such as distributor, value-added reseller, systems integrator, or direct. |
| ATTR029 | ENT005 | Partner Tier | partner_tier | character varying(30) | Yes | No | No | Program tier or commercial ranking assigned to the partner. |
| ATTR030 | ENT005 | Route to Market | route_to_market | character varying(20) | Yes | No | No | Sales channel path used to fulfill the sale, such as Direct, Reseller, or Two-Tier. |
| ATTR031 | ENT006 | Product Key | product_key | integer | No | Yes | No | Surrogate key uniquely identifying a product dimension record. |
| ATTR032 | ENT006 | Product ID | product_id | character varying(30) | No | No | No | Business identifier or SKU-like reference assigned to a product or offering. |
| ATTR033 | ENT006 | Product Name | product_name | character varying(80) | Yes | No | No | Descriptive name of the Cisco product or offering. |
| ATTR034 | ENT006 | Product Family | product_family | character varying(30) | Yes | No | No | Higher-level family grouping for related products. |
| ATTR035 | ENT006 | Technology Domain | technology_domain | character varying(40) | Yes | No | No | Technology area or solution domain to which the product belongs. |
| ATTR036 | ENT006 | Offer Type | offer_type | character varying(30) | Yes | No | No | Commercial form of the offering, such as Hardware, SaaS Subscription, or Software Subscription. |
| ATTR037 | ENT006 | Business Entity | business_entity | character varying(30) | Yes | No | No | Cisco business unit or portfolio grouping associated with the product. |
| ATTR038 | ENT007 | Sales Representative Key | sales_rep_key | integer | No | Yes | No | Surrogate key uniquely identifying a sales representative dimension record. |
| ATTR039 | ENT007 | Sales Representative ID | rep_id | character varying(20) | No | No | No | Business identifier assigned to a sales representative. |
| ATTR040 | ENT007 | Sales Representative Name | rep_name | character varying(60) | Yes | No | No | Full name of the sales representative. |
| ATTR041 | ENT007 | Sales Role | sales_role | character varying(40) | Yes | No | No | Job role or commercial role performed by the sales representative. |
| ATTR042 | ENT007 | Sales Team | sales_team | character varying(40) | Yes | No | No | Team or organizational unit to which the sales representative belongs. |
| ATTR043 | ENT007 | Covered Segment | segment_covered | character varying(30) | Yes | No | No | Customer market segment primarily covered by the sales representative. |
| ATTR044 | ENT008 | Booking ID | booking_id | integer | No | Yes | No | Unique identifier for an individual booking transaction line. |
| ATTR045 | ENT008 | Order Number | order_number | character varying(20) | Yes | No | No | Business order reference associated with the booking transaction. |
| ATTR046 | ENT008 | Order Line Number | order_line_number | integer | Yes | No | No | Line number within the order identifying the booked line item. |
| ATTR047 | ENT008 | Booking Date Key | date_key | integer | Yes | No | Yes | Foreign key linking the booking to the date dimension. |
| ATTR048 | ENT008 | Customer Key | customer_key | integer | Yes | No | Yes | Foreign key linking the booking to the customer dimension. |
| ATTR049 | ENT008 | Product Key | product_key | integer | Yes | No | Yes | Foreign key linking the booking to the product dimension. |
| ATTR050 | ENT008 | Partner Key | partner_key | integer | Yes | No | Yes | Foreign key linking the booking to the partner dimension. |
| ATTR051 | ENT008 | Geography Key | geography_key | integer | Yes | No | Yes | Foreign key linking the booking to the geography dimension. |
| ATTR052 | ENT008 | Sales Representative Key | sales_rep_key | integer | Yes | No | Yes | Foreign key linking the booking to the sales representative dimension. |
| ATTR053 | ENT008 | Contract Key | contract_key | integer | Yes | No | Yes | Foreign key linking the booking to the contract dimension. |
| ATTR054 | ENT008 | Booking Type | booking_type | character varying(15) | Yes | No | No | Classification of the booking event, such as New or Renewal. |
| ATTR055 | ENT008 | Renewal Indicator | is_renewal | integer | Yes | No | No | Numeric flag indicating whether the booking represents a renewal transaction. |
| ATTR056 | ENT008 | Quantity Sold | quantity | integer | Yes | No | No | Number of units, licenses, or service quantities booked in the transaction line. |
| ATTR057 | ENT008 | Unit List Price (USD) | unit_list_price_usd | numeric(12,2) | Yes | No | No | Standard list price per unit in U.S. dollars before discounts. |
| ATTR058 | ENT008 | Discount Percentage | discount_pct | numeric(5,2) | Yes | No | No | Discount rate applied to the list price for the booked transaction. |
| ATTR059 | ENT008 | Booking Amount (USD) | booking_amount_usd | numeric(14,2) | Yes | No | No | Total booked transaction amount in U.S. dollars after pricing and discount considerations. |
| ATTR060 | ENT008 | Annual Contract Value (USD) | acv_usd | numeric(14,2) | Yes | No | No | Annualized value of the booked contract or subscription in U.S. dollars. |
| ATTR061 | ENT008 | Total Contract Value (USD) | tcv_usd | numeric(14,2) | Yes | No | No | Total contractual value of the deal across the full contract term in U.S. dollars. |

## Measures

| Measure ID | Entity ID | Measure Name | Technical Column | Business Definition | Aggregation Type |
| --- | --- | --- | --- | --- | --- |
| MEAS001 | ENT008 | Quantity Sold | quantity | Number of units, licenses, or service quantities booked in the transaction line. | Sum |
| MEAS002 | ENT008 | Unit List Price (USD) | unit_list_price_usd | Standard list price per unit in U.S. dollars before discounts. | Average |
| MEAS003 | ENT008 | Discount Percentage | discount_pct | Discount rate applied to the list price for the booked transaction. | Average |
| MEAS004 | ENT008 | Booking Amount (USD) | booking_amount_usd | Total booked transaction amount in U.S. dollars after pricing and discount considerations. | Sum |
| MEAS005 | ENT008 | Annual Contract Value (USD) | acv_usd | Annualized value of the booked contract or subscription in U.S. dollars. | Sum |
| MEAS006 | ENT008 | Total Contract Value (USD) | tcv_usd | Total contractual value of the deal across the full contract term in U.S. dollars. | Sum |

## Relationships

| Relationship ID | Parent Entity | Child Entity | Parent Attribute | Child Attribute | Relationship Type | Cardinality | Confidence Score |
| --- | --- | --- | --- | --- | --- | --- | --- |
| REL001 | Contract Dimension | Booking Transaction Fact | Contract Key | Contract Key | Referential | One-to-Many | 1.00 |
| REL002 | Customer Dimension | Booking Transaction Fact | Customer Key | Customer Key | Referential | One-to-Many | 1.00 |
| REL003 | Date Dimension | Booking Transaction Fact | Date Key | Booking Date Key | Referential | One-to-Many | 1.00 |
| REL004 | Geography Dimension | Booking Transaction Fact | Geography Key | Geography Key | Referential | One-to-Many | 1.00 |
| REL005 | Partner Dimension | Booking Transaction Fact | Partner Key | Partner Key | Referential | One-to-Many | 1.00 |
| REL006 | Product Dimension | Booking Transaction Fact | Product Key | Product Key | Referential | One-to-Many | 1.00 |
| REL007 | Sales Representative Dimension | Booking Transaction Fact | Sales Representative Key | Sales Representative Key | Referential | One-to-Many | 1.00 |

## Glossary Mapping

| Business Term | Business Definition | Technical Mapping | Entity | Attribute | Confidence Score |
| --- | --- | --- | --- | --- | --- |
| Contract Dimension | Reference table containing contract attributes used to classify bookings by commercial agreement structure, term, renewal behavior, and support coverage. | ontology.dim_contract | Contract Dimension |  | 1.00 |
| Contract Key | Surrogate key uniquely identifying a contract dimension record. | ontology.dim_contract.contract_key | Contract Dimension | Contract Key | 1.00 |
| Contract Type | Type of commercial agreement associated with a booking, such as Enterprise Agreement, SaaS Subscription, SmartNet, or Solution Support. | ontology.dim_contract.contract_type | Contract Dimension | Contract Type | 1.00 |
| Contract Term in Months | Number of months covered by the contract or agreement. | ontology.dim_contract.term_months | Contract Dimension | Contract Term in Months | 1.00 |
| Auto-Renew Indicator | Flag indicating whether the contract is configured to renew automatically at the end of its term. | ontology.dim_contract.auto_renew_flag | Contract Dimension | Auto-Renew Indicator | 1.00 |
| Coverage Level | Service or support coverage tier associated with the contract. | ontology.dim_contract.coverage_level | Contract Dimension | Coverage Level | 1.00 |
| Customer Dimension | Reference table containing customer master data used to analyze bookings by account, segment, industry, and headquarters geography. | ontology.dim_customer | Customer Dimension |  | 1.00 |
| Customer Key | Surrogate key uniquely identifying a customer dimension record or linking a booking to a customer dimension. | ontology.dim_customer.customer_key; ontology.fact_bookings.customer_key | Customer Dimension; Booking Transaction Fact | Customer Key | 0.98 |
| Customer ID | Business identifier assigned to a customer account. | ontology.dim_customer.customer_id | Customer Dimension | Customer ID | 1.00 |
| Customer Name | Official name of the customer account. | ontology.dim_customer.customer_name | Customer Dimension | Customer Name | 1.00 |
| Customer Segment | Market segment to which the customer belongs, such as Service Provider, Enterprise, or Public Sector. | ontology.dim_customer.segment | Customer Dimension | Customer Segment | 1.00 |
| Customer Industry | Industry classification of the customer account. | ontology.dim_customer.industry | Customer Dimension | Customer Industry | 1.00 |
| Account Tier | Strategic ranking or coverage tier assigned to the customer account. | ontology.dim_customer.account_tier | Customer Dimension | Account Tier | 1.00 |
| Headquarters Country | Country where the customer’s headquarters is located. | ontology.dim_customer.hq_country | Customer Dimension | Headquarters Country | 1.00 |
| Headquarters Region | Broad geographic region where the customer’s headquarters is located. | ontology.dim_customer.hq_region | Customer Dimension | Headquarters Region | 1.00 |
| Date Dimension | Calendar and fiscal reference table used to analyze bookings across reporting dates, fiscal years, quarters, and ordered fiscal periods. | ontology.dim_date | Date Dimension |  | 1.00 |
| Date Key | Surrogate or smart key representing the reporting date in YYYYMMDD-style numeric format. | ontology.dim_date.date_key | Date Dimension | Date Key | 1.00 |
| Full Date | Calendar date represented by the date dimension record. | ontology.dim_date.full_date | Date Dimension | Full Date | 1.00 |
| Month Name | Name of the calendar month associated with the date. | ontology.dim_date.month_name | Date Dimension | Month Name | 1.00 |
| Calendar Year | Four-digit calendar year associated with the reporting date. | ontology.dim_date.calendar_year | Date Dimension | Calendar Year | 1.00 |
| Fiscal Year | Fiscal year label used for internal business reporting, such as FY24. | ontology.dim_date.fiscal_year | Date Dimension | Fiscal Year | 1.00 |
| Fiscal Quarter | Fiscal quarter label associated with the date, such as FY24 Q1. | ontology.dim_date.fiscal_quarter | Date Dimension | Fiscal Quarter | 1.00 |
| Fiscal Period Sequence | Ordered sequence number of the fiscal reporting period within the profiled range. | ontology.dim_date.fiscal_period_seq | Date Dimension | Fiscal Period Sequence | 1.00 |
| Geography Dimension | Reference table containing regional, theater, and country attributes used to group bookings geographically. | ontology.dim_geography | Geography Dimension |  | 1.00 |
| Geography Key | Surrogate key uniquely identifying a geography dimension record or linking a booking to a geography dimension. | ontology.dim_geography.geography_key; ontology.fact_bookings.geography_key | Geography Dimension; Booking Transaction Fact | Geography Key | 0.98 |
| Sales Region | Top-level geographic sales region, such as Americas, APJC, or EMEA. | ontology.dim_geography.region | Geography Dimension | Sales Region | 1.00 |
| Sales Theater | Intermediate geographic grouping or theater within a region. | ontology.dim_geography.theater | Geography Dimension | Sales Theater | 1.00 |
| Country | Country associated with the geography record. | ontology.dim_geography.country | Geography Dimension | Country | 1.00 |
| Partner Dimension | Reference table containing partner master data used to analyze indirect and direct sales channels. | ontology.dim_partner | Partner Dimension |  | 1.00 |
| Partner Key | Surrogate key uniquely identifying a partner dimension record or linking a booking to a partner dimension. | ontology.dim_partner.partner_key; ontology.fact_bookings.partner_key | Partner Dimension; Booking Transaction Fact | Partner Key | 0.98 |
| Partner ID | Business identifier assigned to a partner account. | ontology.dim_partner.partner_id | Partner Dimension | Partner ID | 1.00 |
| Partner Name | Official name of the partner organization involved in the sale. | ontology.dim_partner.partner_name | Partner Dimension | Partner Name | 1.00 |
| Partner Type | Classification of the partner, such as distributor, value-added reseller, systems integrator, or direct. | ontology.dim_partner.partner_type | Partner Dimension | Partner Type | 1.00 |
| Partner Tier | Program tier or commercial ranking assigned to the partner. | ontology.dim_partner.partner_tier | Partner Dimension | Partner Tier | 1.00 |
| Route to Market | Sales channel path used to fulfill the sale, such as Direct, Reseller, or Two-Tier. | ontology.dim_partner.route_to_market | Partner Dimension | Route to Market | 1.00 |
| Product Dimension | Reference table containing product and offer attributes used to analyze bookings across portfolios, technology areas, and offer types. | ontology.dim_product | Product Dimension |  | 1.00 |
| Product Key | Surrogate key uniquely identifying a product dimension record or linking a booking to a product dimension. | ontology.dim_product.product_key; ontology.fact_bookings.product_key | Product Dimension; Booking Transaction Fact | Product Key | 0.98 |
| Product ID | Business identifier or SKU-like reference assigned to a product or offering. | ontology.dim_product.product_id | Product Dimension | Product ID | 1.00 |
| Product Name | Descriptive name of the Cisco product or offering. | ontology.dim_product.product_name | Product Dimension | Product Name | 1.00 |
| Product Family | Higher-level family grouping for related products. | ontology.dim_product.product_family | Product Dimension | Product Family | 1.00 |
| Technology Domain | Technology area or solution domain to which the product belongs. | ontology.dim_product.technology_domain | Product Dimension | Technology Domain | 1.00 |
| Offer Type | Commercial form of the offering, such as Hardware, SaaS Subscription, or Software Subscription. | ontology.dim_product.offer_type | Product Dimension | Offer Type | 1.00 |
| Business Entity | Cisco business unit or portfolio grouping associated with the product. | ontology.dim_product.business_entity | Product Dimension | Business Entity | 1.00 |
| Sales Representative Dimension | Reference table containing sales representative attributes used to analyze bookings by seller, team, role, and covered segment. | ontology.dim_sales_rep | Sales Representative Dimension |  | 1.00 |
| Sales Representative Key | Surrogate key uniquely identifying a sales representative dimension record or linking a booking to a sales representative dimension. | ontology.dim_sales_rep.sales_rep_key; ontology.fact_bookings.sales_rep_key | Sales Representative Dimension; Booking Transaction Fact | Sales Representative Key | 0.98 |
| Sales Representative ID | Business identifier assigned to a sales representative. | ontology.dim_sales_rep.rep_id | Sales Representative Dimension | Sales Representative ID | 1.00 |
| Sales Representative Name | Full name of the sales representative. | ontology.dim_sales_rep.rep_name | Sales Representative Dimension | Sales Representative Name | 1.00 |
| Sales Role | Job role or commercial role performed by the sales representative. | ontology.dim_sales_rep.sales_role | Sales Representative Dimension | Sales Role | 1.00 |
| Sales Team | Team or organizational unit to which the sales representative belongs. | ontology.dim_sales_rep.sales_team | Sales Representative Dimension | Sales Team | 1.00 |
| Covered Segment | Customer market segment primarily covered by the sales representative. | ontology.dim_sales_rep.segment_covered | Sales Representative Dimension | Covered Segment | 1.00 |
| Booking Transaction Fact | Central transactional fact table capturing individual booking transaction lines and associated financial measures. | ontology.fact_bookings | Booking Transaction Fact |  | 1.00 |
| Booking ID | Unique identifier for an individual booking transaction line. | ontology.fact_bookings.booking_id | Booking Transaction Fact | Booking ID | 1.00 |
| Order Number | Business order reference associated with the booking transaction. | ontology.fact_bookings.order_number | Booking Transaction Fact | Order Number | 1.00 |
| Order Line Number | Line number within the order identifying the booked line item. | ontology.fact_bookings.order_line_number | Booking Transaction Fact | Order Line Number | 1.00 |
| Booking Date Key | Foreign key linking the booking to the date dimension. | ontology.fact_bookings.date_key | Booking Transaction Fact | Booking Date Key | 1.00 |
| Booking Type | Classification of the booking event, such as New or Renewal. | ontology.fact_bookings.booking_type | Booking Transaction Fact | Booking Type | 1.00 |
| Renewal Indicator | Numeric flag indicating whether the booking represents a renewal transaction. | ontology.fact_bookings.is_renewal | Booking Transaction Fact | Renewal Indicator | 1.00 |
| Quantity Sold | Number of units, licenses, or service quantities booked in the transaction line. | ontology.fact_bookings.quantity | Booking Transaction Fact | Quantity Sold | 1.00 |
| Unit List Price (USD) | Standard list price per unit in U.S. dollars before discounts. | ontology.fact_bookings.unit_list_price_usd | Booking Transaction Fact | Unit List Price (USD) | 1.00 |
| Discount Percentage | Discount rate applied to the list price for the booked transaction. | ontology.fact_bookings.discount_pct | Booking Transaction Fact | Discount Percentage | 1.00 |
| Booking Amount (USD) | Total booked transaction amount in U.S. dollars after pricing and discount considerations. | ontology.fact_bookings.booking_amount_usd | Booking Transaction Fact | Booking Amount (USD) | 1.00 |
| Annual Contract Value (USD) | Annualized value of the booked contract or subscription in U.S. dollars. | ontology.fact_bookings.acv_usd | Booking Transaction Fact | Annual Contract Value (USD) | 1.00 |
| Total Contract Value (USD) | Total contractual value of the deal across the full contract term in U.S. dollars. | ontology.fact_bookings.tcv_usd | Booking Transaction Fact | Total Contract Value (USD) | 1.00 |