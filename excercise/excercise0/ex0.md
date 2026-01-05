# Exercise 0 - fundamental concepts of data modeling

These exercises are for you to learn fundamental concepts in data modeling. Many of them can be done with pen and paper, physical whiteboard or with an ERD software such as Lucidchart. It is good practice to work analogue as an important part of data modeling is to align various stakeholders with a mix of technical and business knowledge. It is also advised to discuss with your peers as data modeling usually is not done in solitude.

## 0. Library Bookly

A library called Bookly keeps track of books and members who borrow them. Each book has a title, author, and ISBN number. Each member has a membership ID, name, and contact information. A member can borrow multiple books, but each book can be borrowed by only one member at a time.

a) Identify the `entities` and `attributes` for each entity.

BOOK(book_id, title, author, ISBN_number)
Borrow(borrow_id, book_id, member_id, borrow_date, return_date)
MEMBER(member_id, name, email, phonenumber, address)

b) Determine the `relationship` between member and books.

many-to-one/one-to-many (depending on how you look at it)

c) Draw a `conceptual ERD` using crow foots notation.

<img src ="DM_excercise01.png" width =500>

## 1. Conceptual ERD to words

This is an ERD conceptual diagram that a database designer and the business stakeholders agreed upon in a car rental company called Carent.

<img src="https://github.com/kokchun/assets/blob/main/data_modeling/car_rental.png?raw=true" alt="course structure" width="500">

a) Describe the entities in this conceptual ERD.

The entities are Customer, Rental and Car.

b) Write out the relationship labels.

customer_id and car_id

c) Describe the relationships between the entities (one-to-many, one-to-one and many-to-many).

Customer one-to-mant Rental.
Car one-to-many Rental.

d) Define the relationship statement for example: "A Customer can have one or more Rentals".

Rental have can have one or no Customer. A Customer can have one or more Rentals.
Rental have one or no Car. A Car can be in one or more Rentals.


## 2. University management system

A university needs a system to manage students, courses, and professors.

- each student can enroll in multiple courses.
- each course is taught by one professor.
- a teacher can teach multiple courses.

a) Identify entities and their relationships

Student many-to-many Course.

Teacher one-to-many Course.

b) Come up with possible attributes for the entities

Student(student_id, major, start_year)

Teacher(teacher_id, subjects, salary)

Course(student_id, teacher_id, type, hp)

c) Draw conceptual ERD with cardinalities 

<img src ="DM_excercise02.png" width =500>

d) Define business rules (e.g. a student can enroll in max 4 courses)

A Teacher can teach max 5 courses.
A Student can enroll in max 7 courses.
A Course needs to be at least 10 hp.

## 3. Onshop

An e-commerce platform Onshop manages customers, orders, and products.

- a customer can place multiple orders.
- each order contains multiple products.
- a product can belong to multiple categories.

a) Identify key entities and their attributes (e.g., customer_name, order_date)

Customer(customer_id, customer_name, phonenumber, email, address)

Order(order_id, order_items, order_date, total_cost, payment)

Product(product_id, categorie, cost)

b) Sketch the conceptual ERD.

<img src ="DM_excercise003.png" width =600>

c) Define business rules

A Customer can place several orders that contains at least one product.
An Order must contain one or more products, an Order can be placed by one Customer.
A Product can belong in multiple categories.
A Category contains mutliple Products.


## 4. Theoretical questions

a) What is a conceptual data model, and why is it important?

The conceptual model is like the big picture. That is where you build a foundation to see what relations and touples you should have. It is importat to start with thist so that you don't miss anything och make the database more complicated or complex than it have to.

b) Storing age in a database, is that a good idea, why?

It is not a good idea cause you have to chane the age each year. A better solutin is to put in the birth year.

c) What are the three types of data structures, and how do they differ?

Structured data: SQL, tables, csv-files. RDBMS, ACID compiance, querys. 

Semi structured data: ex. json. Schema flexibility, NoSQL, cloud object storage.  

Unstructured data: pictures, sound, film, documents. Things that don't hav a structure, object storage.

They differ in the structure, if it is easy to put them in a clear structure.

d) Give examples of how each data structure is used in real-world applications

Structured data can be used for inventory tracking, order tracking osv.

Semistructured data can where you need flexibility like social media.  

Unstructured data can be used for e.g. snapchat wehere you take pictures and record videos.

e) What is cardinality in data modeling, and why is it important?

Cardinality is the relation between two entities. It shows the relationship between the entities without having to write it with letters.
It is importat cause it is the base for building the database.

f) What are the different steps of data modeling?

You start by talking to the stakeholdes to see what they want in the database. Then you look at what the entities are before you do the conceptual model. After that you create the logical model and the last step is the physical model which is ready for implementation.

g) What factors influence the choice between using an RDBMS and NoSQL?

It depends on what data structure you use/are to put in to the database. RDBMS is used when having structured data and NoSQL is used when having for example json-file.

## Glossary
Fill out the meaning of the terms below:

| Glossary         | Meaning |
| ---------------- | ------- |
| RDBMS            |Relational Database Management System         |
| relational model |logical way to organize data in databases using relations, tuples and attributes         |
| conceptual model |discriptive framework representing the key elements, entities, of a system         |
| logical model    |visual diagram mapping out structure and relationships of a data structure         |
| physical model   |database structure, implementary ready       |
| ERD              |Entity Relationship Diagrams         |
| data modeling    |Turn messy data into structured         |
| data integrity   |ensures data si accurat e, consistent, complete and reliable        |
| data consistency |data is uniform, accurate and reliable         |
| field            |structures, organizes, and defines the relationships between data elements         |
| attribute        |columns         |
| data type        |informs the compiler or interpreter how to interpret, store, and manipulate data         |
| data redundancy  |the storage of the same data in multiple locations         |
| transaction      |captures detailed, real-time records of business events (purchases, transfers) using ACID-compliant relational databases for integrity         |
| cardinality      |the uniqueness of data values within a column (high vs. low) or the numerical relationship between data in different tables (one-to-one, one-to-many, many-to-many)         |
| one-to-one       |one row in a table may be linked with only one row in another table and vice versa         |
| one-to-many      |one row in a table may be linked with one or more rows in another table    |