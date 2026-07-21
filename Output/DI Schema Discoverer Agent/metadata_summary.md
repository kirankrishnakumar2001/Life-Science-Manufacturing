# Metadata Summary

| Metric | Value |
| --- | --- |
| Database Type | PostgreSQL 16.14 |
| Number of Schemas | 1 |
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

### Table DDL

```sql
CREATE TABLE ontology.dim_contract (
  contract_key integer NOT NULL,
  contract_type varchar(40),
  term_months integer,
  auto_renew_flag char(1),
  coverage_level varchar(20)
);
```

```sql
CREATE TABLE ontology.dim_customer (
  customer_key integer NOT NULL,
  customer_id varchar(20) NOT NULL,
  customer_name varchar(80),
  segment varchar(30),
  industry varchar(40),
  account_tier varchar(20),
  hq_country varchar(40),
  hq_region varchar(20)
);
```

```sql
CREATE TABLE ontology.dim_date (
  date_key integer NOT NULL,
  full_date date NOT NULL,
  month_name varchar(12),
  calendar_year integer,
  fiscal_year varchar(6),
  fiscal_quarter varchar(10),
  fiscal_period_seq integer
);
```

```sql
CREATE TABLE ontology.dim_geography (
  geography_key integer NOT NULL,
  region varchar(20),
  theater varchar(30),
  country varchar(40)
);
```

```sql
CREATE TABLE ontology.dim_partner (
  partner_key integer NOT NULL,
  partner_id varchar(20) NOT NULL,
  partner_name varchar(60),
  partner_type varchar(30),
  partner_tier varchar(30),
  route_to_market varchar(20)
);
```

```sql
CREATE TABLE ontology.dim_product (
  product_key integer NOT NULL,
  product_id varchar(30) NOT NULL,
  product_name varchar(80),
  product_family varchar(30),
  technology_domain varchar(40),
  offer_type varchar(30),
  business_entity varchar(30)
);
```

```sql
CREATE TABLE ontology.dim_sales_rep (
  sales_rep_key integer NOT NULL,
  rep_id varchar(20) NOT NULL,
  rep_name varchar(60),
  sales_role varchar(40),
  sales_team varchar(40),
  segment_covered varchar(30)
);
```

```sql
CREATE TABLE ontology.fact_bookings (
  booking_id integer NOT NULL,
  order_number varchar(20),
  order_line_number integer,
  date_key integer,
  customer_key integer,
  product_key integer,
  partner_key integer,
  geography_key integer,
  sales_rep_key integer,
  contract_key integer,
  booking_type varchar(15),
  is_renewal integer,
  quantity integer,
  unit_list_price_usd numeric(12,2),
  discount_pct numeric(5,2),
  booking_amount_usd numeric(14,2),
  acv_usd numeric(14,2),
  tcv_usd numeric(14,2)
);
```

### Constraint DDL

```sql
ALTER TABLE ontology.dim_contract ADD PRIMARY KEY (contract_key);
ALTER TABLE ontology.dim_customer ADD PRIMARY KEY (customer_key);
ALTER TABLE ontology.dim_date ADD PRIMARY KEY (date_key);
ALTER TABLE ontology.dim_geography ADD PRIMARY KEY (geography_key);
ALTER TABLE ontology.dim_partner ADD PRIMARY KEY (partner_key);
ALTER TABLE ontology.dim_product ADD PRIMARY KEY (product_key);
ALTER TABLE ontology.dim_sales_rep ADD PRIMARY KEY (sales_rep_key);
ALTER TABLE ontology.fact_bookings ADD PRIMARY KEY (booking_id);
ALTER TABLE ontology.fact_bookings ADD FOREIGN KEY (date_key) REFERENCES ontology.dim_date(date_key);
ALTER TABLE ontology.fact_bookings ADD FOREIGN KEY (sales_rep_key) REFERENCES ontology.dim_sales_rep(sales_rep_key);
ALTER TABLE ontology.fact_bookings ADD FOREIGN KEY (contract_key) REFERENCES ontology.dim_contract(contract_key);
ALTER TABLE ontology.fact_bookings ADD FOREIGN KEY (partner_key) REFERENCES ontology.dim_partner(partner_key);
ALTER TABLE ontology.fact_bookings ADD FOREIGN KEY (product_key) REFERENCES ontology.dim_product(product_key);
ALTER TABLE ontology.fact_bookings ADD FOREIGN KEY (customer_key) REFERENCES ontology.dim_customer(customer_key);
ALTER TABLE ontology.fact_bookings ADD FOREIGN KEY (geography_key) REFERENCES ontology.dim_geography(geography_key);
```

### Index DDL

```sql
CREATE UNIQUE INDEX dim_contract_pkey ON ontology.dim_contract USING btree (contract_key);
CREATE UNIQUE INDEX dim_customer_pkey ON ontology.dim_customer USING btree (customer_key);
CREATE UNIQUE INDEX dim_date_pkey ON ontology.dim_date USING btree (date_key);
CREATE UNIQUE INDEX dim_geography_pkey ON ontology.dim_geography USING btree (geography_key);
CREATE UNIQUE INDEX dim_partner_pkey ON ontology.dim_partner USING btree (partner_key);
CREATE UNIQUE INDEX dim_product_pkey ON ontology.dim_product USING btree (product_key);
CREATE UNIQUE INDEX dim_sales_rep_pkey ON ontology.dim_sales_rep USING btree (sales_rep_key);
CREATE UNIQUE INDEX fact_bookings_pkey ON ontology.fact_bookings USING btree (booking_id);
```