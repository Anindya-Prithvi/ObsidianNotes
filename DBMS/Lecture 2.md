# Lectio Secunda
**Everything is from Silberschatz**

Purpose of DBS: To provide users with abstract view of data
- Data models: A collection of conceptual tools for describing data, data relationships, data semantics, and consistency constraints.
- Data abstraction: Hide complexity with layers

## Data Models
- Entity-relationship data model (mainly for database-design)
- Relational model
- Object-based data models (Object oriented and object relational)
- Semi-structured data model (XML)
- Network model
- Heirarchical model

## View of Data (Levels of Abstraction)
- View level: Can hide info. for security.
- Logical level: Describes stores data and relationship (Name: string, CustID: Integer,...)
- Physical level: Describes how a record is stored. (e.g. customer)
- Logical data independence: ability to modify logical scheme without rewriting application program
- Physical data independence: ability to modify physical schema without changing logical schema

## Data Definition Language (DDL)
- Example: 
  ```sql
  create table customer (
						ID 		char(5),
						name 	varchar(20),
						City 	varchar(20),
						Balance numeric(8,2));
  ```
- DDL compiler generates a set of table templates stored in a data dictionary
- data dictionary contains metadata (i.e. data about data)
	- Database schema
	- Integrity contraints (ID to identify)
	- Authorization: Who is allowed to access

## Data Manipulation Language (DML)
- Procedural DML : Require user to specify what data are needed and how to get those data. (Relational algebra?)
- Declarative/non-proc DML : Require a user to specify what data are needed without specifying how to get those data. (Easy)
	- SQL: one of more tables as input and single table as output
	- Eg: find all customers in 'Agra' whose balance $\geq$ 1Lakh.
	```sql
	select name
	from customer
	where city='Agra' and Balance>100000;```
	- To be able to compute complex functions SQL is embedded in some higher-level language
	- Application programs generally access databases through one of
		- Language extn. to allow embedded sql
		- API (e.g. ODBC/JDBC??) which allow SQL queries to be sent to database

## Query processing 
![[DBMS/Pasted image 20220119233101.png]]

Weird lecture. 