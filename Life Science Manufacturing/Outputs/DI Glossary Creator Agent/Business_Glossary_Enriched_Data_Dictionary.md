# Business Glossary Data Dictionary

## Domain Context
**Domain Name:** Cisco Sales Bookings and Revenue Analytics

**Business Overview:**
This business domain represents Cisco's sales booking operations for enterprise networking, security, collaboration, observability, and software subscription products. The model captures completed customer bookings and supports analysis of sales performance across customers, products, partners, geographies, sales representatives, contracts, and fiscal periods. The schema follows a Kimball star schema pattern with `ontology.fact_bookings` as the central fact table and surrounding dimensions that provide descriptive business context.

## Schema Analysis Summary

| Metric | Value |
| --- | --- |
| Database Type | PostgreSQL |
| Schema | ontology |
| Tables | 8 |
| Columns | 61 |
| Primary Keys | 8 |
| Foreign Keys | 7 |
| Fact Table | ontology.fact_bookings |
| Dimension Tables | ontology.dim_contract, ontology.dim_customer, ontology.dim_date, ontology.dim_geography, ontology.dim_partner, ontology.dim_product, ontology.dim_sales_rep |

## Relationship Summary

| Parent Table | Child Table | Referenced Columns | Relationship Type | Business Meaning |
| --- | --- | --- | --- | --- |
| ontology.dim_contract | ontology.fact_bookings | contract_key -> contract_key | One-to-Many | A contract type or coverage model can apply to many booking transactions. |
| ontology.dim_customer | ontology.fact_bookings | customer_key -> customer_key | One-to-Many | A customer can have many bookings over time. |
| ontology.dim_date | ontology.fact_bookings | date_key -> date_key | One-to-Many | Multiple bookings can occur on the same reporting date or fiscal period. |
| ontology.dim_geography | ontology.fact_bookings | geography_key -> geography_key | One-to-Many | Many bookings can be associated with the same sales geography. |
| ontology.dim_partner | ontology.fact_bookings | partner_key -> partner_key | One-to-Many | A partner may participate in many bookings. |
| ontology.dim_product | ontology.fact_bookings | product_key -> product_key | One-to-Many | A product can appear in many booking transactions. |
| ontology.dim_sales_rep | ontology.fact_bookings | sales_rep_key -> sales_rep_key | One-to-Many | A sales representative can manage many bookings. |

## Table-Level Business Glossary

| Technical Table Name | Business Term | Business Definition | Business Description | Business Category | Remarks |
| --- | --- | --- | --- | --- | --- |
| ontology.dim_contract | Contract Dimension | Reference table containing contract attributes used to classify bookings by commercial agreement structure, term, renewal behavior, and support coverage. | Provides descriptive contract context for recurring revenue, support agreements, and subscription analysis. | Contract Management | Profiling suggests one row per contract definition. |
| ontology.dim_customer | Customer Dimension | Reference table containing customer master data used to analyze bookings by account, segment, industry, and headquarters geography. | Enables customer-centric reporting and commercial segmentation. | Customer Management | Profiling suggests one row per customer. |
| ontology.dim_date | Date Dimension | Calendar and fiscal reference table used to analyze bookings across reporting dates, fiscal years, quarters, and ordered fiscal periods. | Supports time-series analysis, financial reporting, and period-based performance tracking. | Time Management | Profiling suggests one row per quarter-end style reporting date. |
| ontology.dim_geography | Geography Dimension | Reference table containing regional, theater, and country attributes used to group bookings geographically. | Supports regional performance analysis and sales territory reporting. | Geographic Management | Profiling suggests one row per geography mapping. |
| ontology.dim_partner | Partner Dimension | Reference table containing partner master data used to analyze indirect and direct sales channels. | Supports channel effectiveness, route-to-market analysis, and partner segmentation. | Partner Management | Profiling suggests one row per partner. |
| ontology.dim_product | Product Dimension | Reference table containing product and offer attributes used to analyze bookings across portfolios, technology areas, and offer types. | Supports product performance and business entity reporting. | Product Management | Profiling suggests one row per product. |
| ontology.dim_sales_rep | Sales Representative Dimension | Reference table containing sales representative attributes used to analyze bookings by seller, team, role, and covered segment. | Supports sales performance management and territory analysis. | Sales Management | Profiling suggests one row per sales representative. |
| ontology.fact_bookings | Booking Transaction Fact | Central transactional fact table capturing individual booking transaction lines and associated financial measures. | Stores measurable sales outcomes such as booking amount, ACV, TCV, quantity, pricing, and discount metrics linked to all core business dimensions. | Revenue Analytics | Profiling suggests one row per booking transaction line. |

## Enriched Data Dictionary

| Table Name | Column Name | Technical Name | Business Term | Business Definition | Business Description | Data Type | Business Category | Remarks |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ontology.dim_contract | contract_key | contract_key | Contract Key | Surrogate key uniquely identifying a contract dimension record. | Technical identifier used to join contract attributes to booking transactions. | integer | Key / Contract Management | Primary Key; unique and complete. |
| ontology.dim_contract | contract_type | contract_type | Contract Type | Type of commercial agreement associated with a booking, such as Enterprise Agreement, SaaS Subscription, SmartNet, or Solution Support. | Describes the contractual model governing the sale or service coverage. | character varying(40) | Contract Management | Distinct business contract categories observed. |
| ontology.dim_contract | term_months | term_months | Contract Term in Months | Number of months covered by the contract or agreement. | Used to evaluate contract duration and recurring revenue timing. | integer | Contract Management | Profiled range 0 to 36 months. |
| ontology.dim_contract | auto_renew_flag | auto_renew_flag | Auto-Renew Indicator | Flag indicating whether the contract is configured to renew automatically at the end of its term. | Supports renewal planning and recurring revenue analysis. | character(1) | Contract Management | Low-cardinality flag; values observed Y/N. |
| ontology.dim_contract | coverage_level | coverage_level | Coverage Level | Service or support coverage tier associated with the contract. | Indicates the entitlement or support level included in the agreement. | character varying(20) | Contract Management | Diverse values observed including 24x7 and Expert. |
| ontology.dim_customer | customer_key | customer_key | Customer Key | Surrogate key uniquely identifying a customer dimension record. | Technical identifier used to link customer information to bookings. | integer | Key / Customer Management | Primary Key; unique and complete. |
| ontology.dim_customer | customer_id | customer_id | Customer ID | Business identifier assigned to a customer account. | Operational customer reference used alongside the surrogate key. | character varying(20) | Customer Management | Unique and complete. |
| ontology.dim_customer | customer_name | customer_name | Customer Name | Official name of the customer account. | Used for reporting, account analysis, and sales tracking. | character varying(80) | Customer Management | Unique in sample data. |
| ontology.dim_customer | segment | segment | Customer Segment | Market segment to which the customer belongs, such as Service Provider, Enterprise, or Public Sector. | Supports segmentation analysis and go-to-market reporting. | character varying(30) | Customer Management | Service Provider dominates profiled sample. |
| ontology.dim_customer | industry | industry | Customer Industry | Industry classification of the customer account. | Used to evaluate bookings and revenue by industry vertical. | character varying(40) | Customer Management | Telecommunications dominates profiled sample. |
| ontology.dim_customer | account_tier | account_tier | Account Tier | Strategic ranking or coverage tier assigned to the customer account. | Helps prioritize customer management and sales focus. | character varying(20) | Customer Management | Values observed include Growth and Strategic. |
| ontology.dim_customer | hq_country | hq_country | Headquarters Country | Country where the customer’s headquarters is located. | Supports global customer analysis and territory alignment. | character varying(40) | Customer Management | Five countries represented in sample. |
| ontology.dim_customer | hq_region | hq_region | Headquarters Region | Broad geographic region where the customer’s headquarters is located. | Used for regional segmentation and executive reporting. | character varying(20) | Customer Management | Values include Americas, APJC, and EMEA. |
| ontology.dim_date | date_key | date_key | Date Key | Surrogate or smart key representing the reporting date in YYYYMMDD-style numeric format. | Used to join booking transactions to calendar and fiscal time attributes. | integer | Key / Time Management | Primary Key; unique and complete. |
| ontology.dim_date | full_date | full_date | Full Date | Calendar date represented by the date dimension record. | Base reporting date used for daily or periodic analysis. | date | Time Management | Coverage spans 2023-09-15 to 2026-06-15. |
| ontology.dim_date | month_name | month_name | Month Name | Name of the calendar month associated with the date. | Supports grouping and display of bookings by month. | character varying(12) | Time Management | Balanced across March, June, September, December in sample. |
| ontology.dim_date | calendar_year | calendar_year | Calendar Year | Four-digit calendar year associated with the reporting date. | Supports reporting by standard calendar year. | integer | Time Management | Values span 2023 to 2026. |
| ontology.dim_date | fiscal_year | fiscal_year | Fiscal Year | Fiscal year label used for internal business reporting, such as FY24. | Supports finance and executive performance reporting. | character varying(6) | Time Management | Values observed FY24 to FY26. |
| ontology.dim_date | fiscal_quarter | fiscal_quarter | Fiscal Quarter | Fiscal quarter label associated with the date, such as FY24 Q1. | Used to analyze performance by quarter. | character varying(10) | Time Management | Twelve distinct quarter labels observed. |
| ontology.dim_date | fiscal_period_seq | fiscal_period_seq | Fiscal Period Sequence | Ordered sequence number of the fiscal reporting period within the profiled range. | Helps sort and trend periods chronologically. | integer | Time Management | Values observed 1 to 12. |
| ontology.dim_geography | geography_key | geography_key | Geography Key | Surrogate key uniquely identifying a geography dimension record. | Technical identifier used to join geographic attributes to bookings. | integer | Key / Geographic Management | Primary Key; unique and complete. |
| ontology.dim_geography | region | region | Sales Region | Top-level geographic sales region, such as Americas, APJC, or EMEA. | Supports high-level geographic reporting and territory analysis. | character varying(20) | Geographic Management | Three regions represented. |
| ontology.dim_geography | theater | theater | Sales Theater | Intermediate geographic grouping or theater within a region. | Provides a more detailed sales territory breakdown beneath region. | character varying(30) | Geographic Management | Each theater appears unique in sample. |
| ontology.dim_geography | country | country | Country | Country associated with the geography record. | Supports country-level analysis of bookings and sales activity. | character varying(40) | Geographic Management | All sample countries are unique. |
| ontology.dim_partner | partner_key | partner_key | Partner Key | Surrogate key uniquely identifying a partner dimension record. | Technical identifier used to join partner information to bookings. | integer | Key / Partner Management | Primary Key; unique and complete. |
| ontology.dim_partner | partner_id | partner_id | Partner ID | Business identifier assigned to a partner account. | Operational reference for the partner record. | character varying(20) | Partner Management | Unique and complete. |
| ontology.dim_partner | partner_name | partner_name | Partner Name | Official name of the partner organization involved in the sale. | Used in channel reporting and partner performance analysis. | character varying(60) | Partner Management | Unique in sample data. |
| ontology.dim_partner | partner_type | partner_type | Partner Type | Classification of the partner, such as distributor, VAR, systems integrator, or direct. | Describes the role the partner plays in the sales ecosystem. | character varying(30) | Partner Management | VAR is dominant in sample. |
| ontology.dim_partner | partner_tier | partner_tier | Partner Tier | Program tier or commercial ranking assigned to the partner. | Used to assess partner status and alignment with channel strategy. | character varying(30) | Partner Management | Diverse values with one repeated tier. |
| ontology.dim_partner | route_to_market | route_to_market | Route to Market | Sales channel path used to fulfill the sale, such as Direct, Reseller, or Two-Tier. | Supports analysis of channel mix and partner-led motions. | character varying(20) | Partner Management | Reseller is dominant in sample. |
| ontology.dim_product | product_key | product_key | Product Key | Surrogate key uniquely identifying a product dimension record. | Technical identifier used to join product attributes to bookings. | integer | Key / Product Management | Primary Key; unique and complete. |
| ontology.dim_product | product_id | product_id | Product ID | Business identifier or SKU-like reference assigned to a product or offering. | Operational identifier used in product management and reporting. | character varying(30) | Product Management | Unique and complete. |
| ontology.dim_product | product_name | product_name | Product Name | Descriptive name of the Cisco product or offering. | Used for product-level sales analysis and portfolio reporting. | character varying(80) | Product Management | Unique in sample data. |
| ontology.dim_product | product_family | product_family | Product Family | Higher-level family grouping for related products. | Supports portfolio rollups across similar products. | character varying(30) | Product Management | Families such as Catalyst, Firepower, and Meraki observed. |
| ontology.dim_product | technology_domain | technology_domain | Technology Domain | Technology area or solution domain to which the product belongs. | Supports analysis across networking, security, collaboration, and related domains. | character varying(40) | Product Management | Moderate diversity across technology areas. |
| ontology.dim_product | offer_type | offer_type | Offer Type | Commercial form of the offering, such as Hardware, SaaS Subscription, or Software Subscription. | Distinguishes how the product is sold and monetized. | character varying(30) | Product Management | Hardware is dominant in sample. |
| ontology.dim_product | business_entity | business_entity | Business Entity | Cisco business unit or portfolio grouping associated with the product. | Supports executive reporting across major business portfolios. | character varying(30) | Product Management | Security has strongest representation in sample. |
| ontology.dim_sales_rep | sales_rep_key | sales_rep_key | Sales Representative Key | Surrogate key uniquely identifying a sales representative dimension record. | Technical identifier used to join seller attributes to bookings. | integer | Key / Sales Management | Primary Key; unique and complete. |
| ontology.dim_sales_rep | rep_id | rep_id | Sales Representative ID | Business identifier assigned to a sales representative. | Operational reference for the seller. | character varying(20) | Sales Management | Unique and complete. |
| ontology.dim_sales_rep | rep_name | rep_name | Sales Representative Name | Full name of the sales representative. | Used in seller performance and account coverage reporting. | character varying(60) | Sales Management | Unique in sample data. |
| ontology.dim_sales_rep | sales_role | sales_role | Sales Role | Job role or commercial role performed by the sales representative. | Supports performance analysis by role type. | character varying(40) | Sales Management | Account Executive is dominant in sample. |
| ontology.dim_sales_rep | sales_team | sales_team | Sales Team | Team or organizational unit to which the sales representative belongs. | Used to analyze performance by team or coverage model. | character varying(40) | Sales Management | All values unique in sample. |
| ontology.dim_sales_rep | segment_covered | segment_covered | Covered Segment | Customer market segment primarily covered by the sales representative. | Indicates the go-to-market segment focus of the seller. | character varying(30) | Sales Management | Service Provider dominates sample. |
| ontology.fact_bookings | booking_id | booking_id | Booking ID | Unique identifier for an individual booking transaction line. | Primary transactional key for the fact table. | integer | Key / Revenue Analytics | Primary Key; unique and complete. |
| ontology.fact_bookings | order_number | order_number | Order Number | Business order reference associated with the booking transaction. | Used to trace the booking back to the originating sales order. | character varying(20) | Revenue Analytics | Unique in sample data. |
| ontology.fact_bookings | order_line_number | order_line_number | Order Line Number | Line number within the order identifying the booked line item. | Supports line-level transaction detail within an order. | integer | Revenue Analytics | Constant at 1 in sample; still important for line-grain modeling. |
| ontology.fact_bookings | date_key | date_key | Booking Date Key | Foreign key linking the booking to the date dimension. | Associates each booking with its reporting date and fiscal attributes. | integer | Revenue Analytics | Foreign Key to ontology.dim_date. |
| ontology.fact_bookings | customer_key | customer_key | Customer Key | Foreign key linking the booking to the customer dimension. | Associates each booking with the purchasing customer account. | integer | Revenue Analytics | Foreign Key to ontology.dim_customer. |
| ontology.fact_bookings | product_key | product_key | Product Key | Foreign key linking the booking to the product dimension. | Associates each booking with the product or offering sold. | integer | Revenue Analytics | Foreign Key to ontology.dim_product. |
| ontology.fact_bookings | partner_key | partner_key | Partner Key | Foreign key linking the booking to the partner dimension. | Associates each booking with the channel or fulfillment partner. | integer | Revenue Analytics | Foreign Key to ontology.dim_partner. |
| ontology.fact_bookings | geography_key | geography_key | Geography Key | Foreign key linking the booking to the geography dimension. | Associates each booking with a sales geography. | integer | Revenue Analytics | Foreign Key to ontology.dim_geography; only one distinct value in sample. |
| ontology.fact_bookings | sales_rep_key | sales_rep_key | Sales Representative Key | Foreign key linking the booking to the sales representative dimension. | Associates each booking with the responsible seller. | integer | Revenue Analytics | Foreign Key to ontology.dim_sales_rep. |
| ontology.fact_bookings | contract_key | contract_key | Contract Key | Foreign key linking the booking to the contract dimension. | Associates each booking with its commercial agreement structure. | integer | Revenue Analytics | Foreign Key to ontology.dim_contract. |
| ontology.fact_bookings | booking_type | booking_type | Booking Type | Classification of the booking event, such as New or Renewal. | Used to separate new business from recurring or renewal activity. | character varying(15) | Revenue Analytics | New bookings are 60% of sample. |
| ontology.fact_bookings | is_renewal | is_renewal | Renewal Indicator | Numeric flag indicating whether the booking represents a renewal transaction. | Supports renewal rate analysis and recurring revenue reporting. | integer | Revenue Analytics | Values observed 0/1; aligns with booking_type. |
| ontology.fact_bookings | quantity | quantity | Quantity Sold | Number of units, licenses, or service quantities booked in the transaction line. | Supports volume analysis and price-to-quantity calculations. | integer | Revenue Analytics | Range 4 to 250 in sample. |
| ontology.fact_bookings | unit_list_price_usd | unit_list_price_usd | Unit List Price (USD) | Standard list price per unit in U.S. dollars before discounts. | Used to evaluate pricing, discounting, and commercial performance. | numeric(12,2) | Revenue Analytics | Range 8000.00 to 50000.00 in sample. |
| ontology.fact_bookings | discount_pct | discount_pct | Discount Percentage | Discount rate applied to the list price for the booked transaction. | Supports margin and pricing effectiveness analysis. | numeric(5,2) | Revenue Analytics | Range 0.11 to 0.28 in sample; appears stored as decimal fraction. |
| ontology.fact_bookings | booking_amount_usd | booking_amount_usd | Booking Amount (USD) | Total booked transaction amount in U.S. dollars after pricing and discount considerations. | Core measure for sales bookings and revenue analytics. | numeric(14,2) | Revenue Analytics | Range 130000.00 to 2670000.00 in sample. |
| ontology.fact_bookings | acv_usd | acv_usd | Annual Contract Value (USD) | Annualized value of the booked contract or subscription in U.S. dollars. | Used to measure recurring annualized revenue contribution. | numeric(14,2) | Revenue Analytics | Average lower than TCV, consistent with annualized contract logic. |
| ontology.fact_bookings | tcv_usd | tcv_usd | Total Contract Value (USD) | Total contractual value of the deal across the full contract term in U.S. dollars. | Used to assess total revenue committed over the contract lifespan. | numeric(14,2) | Revenue Analytics | Average exceeds ACV, consistent with multi-period contract valuation. |

## Primary Keys

| Table Name | Primary Key Column | Business Meaning |
| --- | --- | --- |
| ontology.dim_contract | contract_key | Unique identifier for a contract definition. |
| ontology.dim_customer | customer_key | Unique identifier for a customer record. |
| ontology.dim_date | date_key | Unique identifier for a reporting date record. |
| ontology.dim_geography | geography_key | Unique identifier for a geography record. |
| ontology.dim_partner | partner_key | Unique identifier for a partner record. |
| ontology.dim_product | product_key | Unique identifier for a product record. |
| ontology.dim_sales_rep | sales_rep_key | Unique identifier for a sales representative record. |
| ontology.fact_bookings | booking_id | Unique identifier for a booking transaction line. |

## Foreign Keys

| Child Table | Foreign Key Column | Parent Table | Parent Key | Business Meaning |
| --- | --- | --- | --- | --- |
| ontology.fact_bookings | contract_key | ontology.dim_contract | contract_key | Connects each booking to its contract structure and coverage attributes. |
| ontology.fact_bookings | customer_key | ontology.dim_customer | customer_key | Connects each booking to the customer that purchased the offering. |
| ontology.fact_bookings | date_key | ontology.dim_date | date_key | Connects each booking to reporting date and fiscal attributes. |
| ontology.fact_bookings | geography_key | ontology.dim_geography | geography_key | Connects each booking to a sales geography. |
| ontology.fact_bookings | partner_key | ontology.dim_partner | partner_key | Connects each booking to the partner or channel involved in fulfillment. |
| ontology.fact_bookings | product_key | ontology.dim_product | product_key | Connects each booking to the booked product or offering. |
| ontology.fact_bookings | sales_rep_key | ontology.dim_sales_rep | sales_rep_key | Connects each booking to the responsible sales representative. |

## Profiling-Based Business Notes

| Table Name | Profiling Insight | Business Interpretation |
| --- | --- | --- |
| ontology.dim_contract | auto_renew_flag is mostly Y | Most profiled contract definitions support recurring renewal behavior. |
| ontology.dim_customer | Service Provider and Telecommunications dominate | The sample customer set is concentrated in telecom-oriented service provider accounts. |
| ontology.dim_date | Balanced quarterly-style distribution across fiscal years FY24 to FY26 | The date dimension is structured for fiscal performance reporting over multiple years. |
| ontology.dim_geography | Geography dimension spans 3 regions | The model supports global analysis, though regional sample distribution is limited. |
| ontology.dim_partner | Reseller-led routes dominate | Channel-driven sales are important in the business process. |
| ontology.dim_product | Hardware and Security are highly represented | The profiled sample leans toward hardware and security-related bookings. |
| ontology.dim_sales_rep | Service Provider coverage dominates | Sales coverage in the sample aligns with the dominant customer segment. |
| ontology.fact_bookings | New bookings exceed renewals; all facts map to one geography_key | Sample fact activity is concentrated and may not yet reflect full geographic diversity. |

## Business Glossary Output Format

| Table Name | Column Name | Business Term | Business Definition | Business Description | Data Type | Business Category |
| --- | --- | --- | --- | --- | --- | --- |
| ontology.fact_bookings | booking_amount_usd | Booking Amount (USD) | Total booked transaction amount in U.S. dollars after pricing and discount considerations. | Core measure for sales bookings and revenue analytics. | numeric(14,2) | Revenue Analytics |
| ontology.fact_bookings | acv_usd | Annual Contract Value (USD) | Annualized value of the booked contract or subscription in U.S. dollars. | Used to measure recurring annualized revenue contribution. | numeric(14,2) | Revenue Analytics |
| ontology.fact_bookings | tcv_usd | Total Contract Value (USD) | Total contractual value of the deal across the full contract term in U.S. dollars. | Used to assess total revenue committed over the contract lifespan. | numeric(14,2) | Revenue Analytics |

## File Write Confirmation
This document is intended to be stored in the GitHub repository path:
`Life Science Manufacturing/Outputs/DI Glossary Creator Agent/Business_Glossary_Enriched_Data_Dictionary.md`
