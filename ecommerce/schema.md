# Ecommerce

Modellare un e-commerce:

Ci sono `clienti` che effettuano `ordini`.
Un ordine può contenere più `prodotti` e viene preparato da un `dipendente`.
Un ordine ha associato uno o più `pagamenti` (considerando eventuali tentativi falliti)

## Tables

- users
- customers
- employees
- orders
- products
- payments
- transactions
- roles
- order_product (pivot)
- category_product (pivot)
- role_user (pivot)

## Table: customers

- id BIGINT PK AI NOTNULL UNIQUE
- user_id
- name VARCHAR(20) NOT NULL
- lastname VARCHAR(20) NOT NULL
- street_address VARCHAR(50)
- city VARCHAR(120)
- post_code VARCHAR(20)
- phone_number
- role_id

## Table: employees

- id
- user_id
- name
- lastname
- role_id

## Table: orders

- id BIGINT PK AI NOTNULL UNIQUE
- client_id UNSIGNED BININT FK
- employee_id UNSIGNED BININT FK
- status VARCHAR(20) NOT NULL
- date DATETIME NOT NULL

## Table: products

- id BIGINT PK AI NOTNULL UNIQUE
- category_id UNSIGNED BININT FK
- name VARCHAR(50) NOT NULL
- description TEXT NULL
- price DECIMAL(7,2) NOT NULL // 99.999,99
- weight FLOAT(5, 2)

## Table: categories

- id BIGINT PK AI NOTNULL UNIQUE
- name VARCHAR(50) NOT NULL
- slug VARCHAR(50) NOT NULL

## Table (pivot) order_product

- id BIGINT PK AI NOTNULL UNIQUE
- order_id UNSIGNED BININT FK
- product_id UNSIGNED BININT FK
- quantity TINYINT NOT NULL

## Table: transactions

- id BIGINT PK AI NOTNULL UNIQUE
- order_id UNSIGNED BININT FK
- payment_id UNSIGNED BININT FK
- date DATETIME NOT NULL
- amount DECIMAL(12,2) NOT NULL
- status VARCHR(20) NOT NULL

## Table: payments

- id BIGINT PK AI NOTNULL UNIQUE
- name VARCHAR(50) NOT NULL
- slug VARCHAR(50) NOT NULL

## Table: roles

- id BIGINT PK AI NOTNULL UNIQUE
- name VARCHAR(50) NOT NULL
- slug VARCHAR(50) NOT NULL

## Table: users

- id
- email VARCHAR(255) NOT NULL
- password
