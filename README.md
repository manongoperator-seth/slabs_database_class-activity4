# AUTHOR: TSHEGOFATSO

## 1. Database Purpose

The purpose of the Library Management System is
to store and manage information about books,
library members and borrowing records.

## 2. Table Separation

The database will contain three main tables:

1. Books - stores book information.
2. Members - stores library member details.
3. Borrowings - tracks borrowed books.

Separating tables helps prevent data duplication.

## 3. Members Table Fields

- member_id - INTEGER, PRIMARY KEY
- first_name - VARCHAR(50)
- last_name - VARCHAR(50)
- email - VARCHAR(100)
- phone_number - VARCHAR(20)
- registration_date - DATE

The primary key is member_id because it uniquely identifies each member.

## 4. My postgres entries

The authors table uses author_id as its primary key.

The books table uses author_id as a foreign key to reference the authors table.

 List of tables
 Schema |  Name   | Type  |  Owner
--------+---------+-------+----------
 public | authors | table | postgres
 public | books   | table | postgres
(2 rows)


library_db=# INSERT INTO authors (author_name)
library_db-# VALUES
library_db-# ('Tshego Manong'),
library_db-# ('GhostBoy'),
library_db-# ('Dipuo');
INSERT 0 3
library_db=# INSERT INTO books (title, published_year, author_id)
library_db-# VALUES
library_db-# ('The thing', 1996, 1),
library_db-# ('How I Married Mary', 2025, 2),
library_db-# ('The Tomorrow Truth', 2026, 3);
INSERT 0 3
library_db=# SELECT
library_db-# books.title,
library_db-# books.published_year,
library_db-# authors.author_name
library_db-# FROM books
library_db-# JOIN authors
library_db-# ON books.author_id = authors.author_id;
       title        | published_year |  author_name
--------------------+----------------+---------------
 The thing          |           1996 | Tshego Manong
 How I Married Mary |           2025 | GhostBoy
 The Tomorrow Truth |           2026 | Dipuo
(3 rows)

# EVERYTHING WAS SUCCESSFUL.
