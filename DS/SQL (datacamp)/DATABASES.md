Database - it stores data

Relational database - defines relationships between tables of data inside the database

SQL - Structured Query Language

Tables - organized into rows and columns

rows - records
columns - fields

unique identifiers are used to identify records in a table
![[Pasted image 20250207102244.png]]

## Data types ##

**String (STR)**- sequence of characters such as letters of punctuations

**VARCHAR** - is a flexible and popular string data type in SQL. it can hold much more complex characters

**Integers (INT)** - stores whole numbers. flexible and popular integer data type in SQL 

**Float** - numbers that has decimal points.

**NUMERIC** - is a type of **Float** that can store up to 38 digits total

**DATE** - a datatype that holds dates

**You can find datatypes by looking at a database schema**

Servers - usually used for data access or website access.



Primary keys - parang ID numbers, walang same na ganito
so this is unique identifiers sa isang table, sa bawat table may ganito

Foreign keys -

Isipin mo may dalawa kang table (parang spreadsheet):

1. **`Customers` table:** Nandito info ng mga customer mo (CustomerID, Name, Address). Yung `CustomerID` dito ang **Primary Key** (unique ID ng bawat customer).
2. **`Orders` table:** Nandito yung mga order (OrderID, Product, CustomerID).

Yung **`CustomerID`** sa `Orders` table ang **Foreign Key**.

**Ano'ng ginagawa nito?**

- **Link/Ugnayan:** Kinokonekta niya yung `Orders` table pabalik sa `Customers` table. Sinasabi niya na yung order na 'yun ay para sa _specific_ na customer na nasa `Customers` table.
- **Data Integrity (Para Tama Lagi):** Pinipigilan ka nitong maglagay ng `CustomerID` sa `Orders` table na _wala_ naman talaga sa `Customers` table. Hindi pwedeng may order para sa customer na hindi existing.

**In short:** Ang Foreign Key ay parang "link" o "reference" sa Primary Key ng ibang table para mapanatiling konektado at tama ang data sa magkaibang tables. Gets?

![[Pasted image 20250408073159.png]]

SO GANITO
sa transactions table merong primary key and foreign key
and sa customers table merong primary key
so ang foreign key sa transactions ay yung primary key sa customers, ang foreign key ay isang primary key sa isang table pero nasa ibang table sya, kaya magiging foreign key sya dun if hindi yun yung primary key nya


![[Pasted image 20250420162529.png]]
create table

insert table
