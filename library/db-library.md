# DB Library

## Table: books

- id BIGINT PK AI NOTNULL UNIQUE
- title VARCHAR(80) NOTNULL
- plot TEXT NULL
- year YEAR NULL
- author VARCHAR(80) NOTNULL
- notes TEXT NULL

## Table: genres

- id BIGINT PK AI NOTNULL UNIQUE
- name VARCHAR(20)
- slug VARCHAR(20)

## Table: copies

- id BIGINT PK AI NOTNULL UNIQUE
- book_id UNSIGNED BININT FK
- condition_id UNSIGNED BININT FK
- ISBN CHAR(13) NOTNULL UNIQUE
- edition TINYINT() NULL
- pages SMALLINT NULL
- publisher VARCHAR(80) NULL
- language VARCHAR(5) NOTNULL
- price DECIMAL(6,2) NULL //9.999,99
- notes TEXT NULL

## Table: loans

- id BIGINT PK AI NOTNULL UNIQUE
- copy_id UNSIGNED BININT FK
- user_id UNSIGNED BIGINT FK
- start_date DATE
- end_date DATE

## Table: conditions

- id BIGINT PK AI NOTNULL UNIQUE
- name VARCHAR(20)
- slug VARCHAR(20)

## Table: users

- id BIGINT PK AI NOTNULL UNIQUE
- name VARCHAR(30)
- lastname VARCHAR(50)

## user_profile

- id BIGINT PK AI NOTNULL UNIQUE
- user_id UNSIGNED BININT FK
- address VARCHAR(20)
- phone_number VARCHAR(20)
- date_of_birth DATE
