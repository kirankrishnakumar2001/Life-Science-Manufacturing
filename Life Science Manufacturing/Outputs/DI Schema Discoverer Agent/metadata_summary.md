# Metadata Summary

| Metric | Value |
| --- | --- |
| Database Type | PostgreSQL |
| Number of Schemas | 2 |
| Number of Tables | 8 |
| Number of Columns | 61 |
| Number of Primary Keys | 8 |
| Number of Foreign Keys | 7 |
| Number of Views | 0 |
| Number of Procedures/Functions | 0 |
| Number of Triggers | 0 |
| Number of Sequences | 0 |

## Relationships

| Parent Table | Child Table | Referenced Columns | Relationship Type |
| --- | --- | --- | --- |
| ontology.dim_contract | ontology.fact_bookings | contract_key -> contract_key | One-to-Many |
| ontology.dim_customer | ontology.fact_bookings | customer_key -> customer_key | One-to-Many |
| ontology.dim_date | ontology.fact_bookings | date_key -> date_key | One-to-Many |
| ontology.dim_geography | ontology.fact_bookings | geography_key -> geography_key | One-to-Many |
| ontology.dim_partner | ontology.fact_bookings | partner_key -> partner_key | One-to-Many |
| ontology.dim_product | ontology.fact_bookings | product_key -> product_key | One-to-Many |
| ontology.dim_sales_rep | ontology.fact_bookings | sales_rep_key -> sales_rep_key | One-to-Many |

## DDL Definitions

```sql
-- TABLE: ontology.dim_contract
CREATE TABLE ontology.dim_contract (
  contract_key integer NOT NULL,
  contract_type character varying(40),
  term_months integer,
  auto_renew_flag character(1),
  coverage_level character varying(20)
);

-- TABLE: ontology.dim_customer
CREATE TABLE ontology.dim_customer (
  customer_key integer NOT NULL,
  customer_id character varying(20) NOT NULL,
  customer_name character varying(80),
  segment character varying(30),
  industry character varying(40),
  account_tier character varying(20),
  hq_country character varying(40),
  hq_region character varying(20)
);

-- TABLE: ontology.dim_date
CREATE TABLE ontology.dim_date (
  date_key integer NOT NULL,
  full_date date NOT NULL,
  month_name character varying(12),
  calendar_year integer,
  fiscal_year character varying(6),
  fiscal_quarter character varying(10),
  fiscal_period_seq integer
);

-- TABLE: ontology.dim_geography
CREATE TABLE ontology.dim_geography (
  geography_key integer NOT NULL,
  region character varying(20),
  theater character varying(30),
  country character varying(40)
);

-- TABLE: ontology.dim_partner
CREATE TABLE ontology.dim_partner (
  partner_key integer NOT NULL,
  partner_id character varying(20) NOT NULL,
  partner_name character varying(60),
  partner_type character varying(30),
  partner_tier character varying(30),
  route_to_market character varying(20)
);

-- TABLE: ontology.dim_product
CREATE TABLE ontology.dim_product (
  product_key integer NOT NULL,
  product_id character varying(30) NOT NULL,
  product_name character varying(80),
  product_family character varying(30),
  technology_domain character varying(40),
  offer_type character varying(30),
  business_entity character varying(30)
);

-- TABLE: ontology.dim_sales_rep
CREATE TABLE ontology.dim_sales_rep (
  sales_rep_key integer NOT NULL,
  rep_id character varying(20) NOT NULL,
  rep_name character varying(60),
  sales_role character varying(40),
  sales_team character varying(40),
  segment_covered character varying(30)
);

-- TABLE: ontology.fact_bookings
CREATE TABLE ontology.fact_bookings (
  booking_id integer NOT NULL,
  order_number character varying(20),
  order_line_number integer,
  date_key integer,
  customer_key integer,
  product_key integer,
  partner_key integer,
  geography_key integer,
  sales_rep_key integer,
  contract_key integer,
  booking_type character varying(15),
  is_renewal integer,
  quantity integer,
  unit_list_price_usd numeric(12,2),
  discount_pct numeric(5,2),
  booking_amount_usd numeric(14,2),
  acv_usd numeric(14,2),
  tcv_usd numeric(14,2)
);

-- CONSTRAINT: ontology.dim_date
ALTER TABLE ontology.dim_date ADD CONSTRAINT dim_date_pkey PRIMARY KEY (date_key);

-- CONSTRAINT: ontology.fact_bookings
ALTER TABLE ontology.fact_bookings ADD CONSTRAINT fk_booking_contract FOREIGN KEY (contract_key) REFERENCES dim_contract(contract_key);

-- CONSTRAINT: ontology.fact_bookings
ALTER TABLE ontology.fact_bookings ADD CONSTRAINT fk_booking_sales_rep FOREIGN KEY (sales_rep_key) REFERENCES dim_sales_rep(sales_rep_key);

-- CONSTRAINT: ontology.fact_bookings
ALTER TABLE ontology.fact_bookings ADD CONSTRAINT fk_booking_geography FOREIGN KEY (geography_key) REFERENCES dim_geography(geography_key);

-- CONSTRAINT: ontology.fact_bookings
ALTER TABLE ontology.fact_bookings ADD CONSTRAINT fk_booking_partner FOREIGN KEY (partner_key) REFERENCES dim_partner(partner_key);

-- CONSTRAINT: ontology.fact_bookings
ALTER TABLE ontology.fact_bookings ADD CONSTRAINT fk_booking_product FOREIGN KEY (product_key) REFERENCES dim_product(product_key);

-- CONSTRAINT: ontology.fact_bookings
ALTER TABLE ontology.fact_bookings ADD CONSTRAINT fk_booking_customer FOREIGN KEY (customer_key) REFERENCES dim_customer(customer_key);

-- CONSTRAINT: ontology.fact_bookings
ALTER TABLE ontology.fact_bookings ADD CONSTRAINT fk_booking_date FOREIGN KEY (date_key) REFERENCES dim_date(date_key);

-- CONSTRAINT: ontology.fact_bookings
ALTER TABLE ontology.fact_bookings ADD CONSTRAINT fact_bookings_pkey PRIMARY KEY (booking_id);

-- CONSTRAINT: ontology.dim_customer
ALTER TABLE ontology.dim_customer ADD CONSTRAINT dim_customer_pkey PRIMARY KEY (customer_key);

-- CONSTRAINT: ontology.dim_product
ALTER TABLE ontology.dim_product ADD CONSTRAINT dim_product_pkey PRIMARY KEY (product_key);

-- CONSTRAINT: ontology.dim_partner
ALTER TABLE ontology.dim_partner ADD CONSTRAINT dim_partner_pkey PRIMARY KEY (partner_key);

-- CONSTRAINT: ontology.dim_geography
ALTER TABLE ontology.dim_geography ADD CONSTRAINT dim_geography_pkey PRIMARY KEY (geography_key);

-- CONSTRAINT: ontology.dim_sales_rep
ALTER TABLE ontology.dim_sales_rep ADD CONSTRAINT dim_sales_rep_pkey PRIMARY KEY (sales_rep_key);

-- CONSTRAINT: ontology.dim_contract
ALTER TABLE ontology.dim_contract ADD CONSTRAINT dim_contract_pkey PRIMARY KEY (contract_key);

-- INDEX: ontology.dim_date
CREATE UNIQUE INDEX dim_date_pkey ON ontology.dim_date USING btree (date_key);

-- INDEX: ontology.dim_customer
CREATE UNIQUE INDEX dim_customer_pkey ON ontology.dim_customer USING btree (customer_key);

-- INDEX: ontology.dim_product
CREATE UNIQUE INDEX dim_product_pkey ON ontology.dim_product USING btree (product_key);

-- INDEX: ontology.dim_partner
CREATE UNIQUE INDEX dim_partner_pkey ON ontology.dim_partner USING btree (partner_key);

-- INDEX: ontology.dim_geography
CREATE UNIQUE INDEX dim_geography_pkey ON ontology.dim_geography USING btree (geography_key);

-- INDEX: ontology.dim_sales_rep
CREATE UNIQUE INDEX dim_sales_rep_pkey ON ontology.dim_sales_rep USING btree (sales_rep_key);

-- INDEX: ontology.dim_contract
CREATE UNIQUE INDEX dim_contract_pkey ON ontology.dim_contract USING btree (contract_key);

-- INDEX: ontology.fact_bookings
CREATE UNIQUE INDEX fact_bookings_pkey ON ontology.fact_bookings USING btree (booking_id);
```