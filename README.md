
# Databases

## Relational Databases ![mysqldownload](https://user-images.githubusercontent.com/114578618/195858167-b4ae6082-d376-44f2-951e-f762d1d07594.png)![ms3download](https://user-images.githubusercontent.com/114578618/195859896-602ebada-d592-4421-8558-b38c4f4f6e9b.png)![pgsdownload](https://user-images.githubusercontent.com/114578618/195858073-de817956-6540-423b-ad0c-d0c9f196539d.png)

Databases are efficient ways of storing and managing data. Databases store organised or structured data using relational model which stores data in two dimensional format like tables, represented in rows and columns

Each row in a table represents a single record with unique ID called Key. A record is a meaningful and consistent way of combining information about something.  
A column represents a field of attribute or an item of information. 

Relational database management systems also known as RDBMS are softwares used to create and manage databases.

Structured Query Language also called SQL is the Language used to talk to databases. Functions like Create, Read, Update and Delete are some of the basic functions in perfomed in a Relational Database Management System.

Data in a database could be consumed by applications ( e.g Reporting Application like Power BI) or directly queried by people

Examples of relational database management system are: Microsoft sql server, mySql, etc..


                     Diagram of a relational model
![relational1](https://user-images.githubusercontent.com/114623144/194963864-2e4c379c-ca55-4eff-ab98-b13d037e78ec.png)

## What is a schema 

This is the way a database is structured. Schema's are a formal description of the organisation and structure of data in a database. This includes definition of tables, views, columns, data types, indexes, constraints,relationships, etc. Schemas are important for consistency and efficiency. Databases work With schema's.

Relational databases have schema's while non relational databases like NoSql databases e.g. MongoDB are schema-less.

## What is a table

A colletion of related data held in rows and columns. Data within databases are held in tables.

                    CREATE TABLE Persons (
                     PersonID int,
                     LastName varchar(255),
                     FirstName varchar(255),
                     Address varchar(255),
                     City varchar(255)
                    );

## How to design a databsase  🖌️

A database design is the process of organizing, classifying and indentifying relationships between data with a view to producing a detailed data model of the database. 

## What does a good database look like

 ✔️ A good database is one with no duplicate information or duplication is to kept to very minimum. 
 
      Duplicate data also called redundant data is bad for databases. It wastes spaces and
      increases the posibility of errors

✔️ A good database has Information sub divided into broad subject areas.

      Example subject areas are: Product, Customer.etc.. This will help to reduce data redundancy

✔️ A good database accomodates data processing and reporting needs.
      
      A good way of tackling this will be to plan ahead for the purpose of the database, ensuring all
      reporting needs are met

✔️ A good database ensure correctness and completeness of information. 

    This value of a database is in the information it holds. If a database does not contain correct
    information, any report that pulls information from it will also be incorrect.
  
##  Database design

✔️ Determine the purpose of your Database.

      This is how you intend to use the database. You could elicit requirement to determine its use
      case. Example use case: A Customer database that keeps a list of customer related information.

✔️ Gather and organize all forms of information required

      After you have determined the purpose of your database, you need to gather all data needed to be
      stored on the database. Consider your reporting requirements, all user requirements and any other
      related data needs

✔️ Divide information into tables

      Divide data into subject based tables. Choose major entities for subjects


✔️ Specify primary keys - Choose a column or several columns to uniquly identify each rows
  
     Primary Keys 🗝
    
         Each table should have a column or a set of columns that uniquely identifies each row.
         This is called. the Primary Key. For example on a 'Customer Table', a good primary key
         will be the Customer Id rather than the Customer Name, as several other customers can
         have same names. You could also use arbitrary unique number or an autogenerated unique
         numbers as Primary Keys. Primary Keys cannot have duplicate values.
    
         A Primary Key must have a value. If when selecting your primary key, there is a possibility
         of the key to have an unknown or unassigned value, this cannot be used as a Primary Key. 
    
         The Primary Key value should not change. This is because within a relational database, tables
         can reference other tables via their Primary Keys and if the primary key changes, you will
         have to update all the Primary keys on the tables being referenced. If a Primary Key changes,
         it can increase the risk of primary keys being out of synch with tables referencing it.
    
         In summary, 
         A primary key cannot be NULL. 
         A primary key value must be unique. 
         A primary key value should rarely change. 
         A primary key must be given a value one a new record is inserted
    
     Composite keys 🗝🗝  
    
         These are primary keys comprising multiple columns used to identify a record uniquely

✔️ Specify table cardinalities or relationships

   By creating relationships between the tables, we can bring varying information together in meaningful ways.
   The different relationships are detailed below:
    
  ✔️ One - to - Many
  
  ![Screenshot 2022-10-19 at 17 20 22](https://user-images.githubusercontent.com/114578618/196759682-7eba73a5-e555-443e-9964-fb5fca7e014f.png) 
            
    This speaks about the relationship between two entities (tables), where an element in an entity A links
    to many elements in entity B, but element in entity B links to one and only one element in entity A
    Example: each department in a Department table can have one or more employees in the Employee table.
    In actual fact a one-to-many relationship, each occurrence of data in one entity could be related to zero 
    or more occurrences of data in a second entity. Example: In a "Company Database" where a Manager on the 
    'Managers Table' can manage zero or multiple Employees on the 'Employee Table', whereas the 'Employee' can 
    only have one Manager
        
 
 
  ✔️ One - to - One
  
   ![11](https://user-images.githubusercontent.com/114578618/196760771-11bc165c-d928-49fb-9186-56cb0206fd4f.png)            
    
    This is when Tables have a single relationships with each other. For example a 'Product Table' having 
    productID as its Primary Key will have a one to one relationship to a Product suplement table called 
    'Product Details Table'
            
  ✔️ Many - to - Many
  
  ![3](https://user-images.githubusercontent.com/114578618/196768663-e3ba642c-7ee4-43c0-967b-62237b7f5062.png)
  
    This speaks about two tables with multiple references to each other. Example: on a "Product Order"
    Database. An 'Order Table' can have single order with more than one product on the 'Product Table'
    and also a single Product on the 'Product Table'can appear on many orders on the 'Orders Table'
        

✔️ Normalisation - Apply normalisation rules

   Normalisation is a process of efficiently organising data in a database to eliminate redundancy and inconsistent dependencies. 
   This includes creating Tables and establishing relationmships between these tables.
   
   The rules for database Normalisations are called 'Normal Forms'. 
   
   If a database conforms to the first normal form, then the database is said to be in the first normal form
   If it adheres to the first three normal forms, the database is considered to be in the third normal form.
   
   There are about 5 Normal forms, but only the first three are goiing to be described here. 
   
  1.  First normal form (1NF)
         - Each cell should contain a single value. 
               We need to eliminate repeating groups of columns in a cell (e.g. item1, item2, ..)
         - Creation of separate tables for related data
         - Identify each set of related data with a primary key
            
            
   2. Second normal form (2NF)
         - The table is already in 1NF
         - Every non-key column is fully dependent on the primary key (or composite key)
               E.g, An 'OrderDetails' table having primary key comprising 'ProductID' and 'OrderId'. If unit_price is only
               dependent on 'ProductID' it should not be kept in 'OrderDetails' Table but the 'Product' table. On the other
               hand. If unit_price is also dependent on the particular Order. It can be kept in 'OrderDetails' table
         - Create separate table for sets of values that apply to multiple records. 
               E.g, Customer Address can be stored on Customer Address table intstead of multiple tables that use it 
               like Orders, Shipping, Invoicing tables
         - Relate these tables using a Foreign key
         
   3. Third normal form (3NF)
         - The table is already in 2NF
         - Eliminate field that do not depend on the key. Columns should not depend on each other but only the primary key
               E.g, on a 'Product' table with 'ProductID' as primary key. Discount_rate should not belong to 'Product' table
               if it depends on unit_price on the same table.
         - Note: Whilst 3NF is desirable, it might not always be practical. creation of separate smaller tables to remove 
               inter-column relationships in some instances might degrade performance. Ensure you are fully aware of your
               design decisions and document it
  
##  ACID properties and RDBMS

Four cruial properties define relational database transations: atomiity, onsisteny, isolation and durability - Typially alled ACID
#### 1. Atomicity
       Defines all the elements that make up a complete database transaction.
#### 2.  Consistency
       Defines the rules for maintaining data points in a correct state after a transaction.
#### 3.  Isolation
       Keeps the effct of a transaction invisible to pothers until it is committed to avoid confusion.
#### 4.  Durability
        Ensures the data changes becomes permanent once the transaction is committed.




## NoSQL / Unstructured / Semi Structured Databases ![MongoDB_Logo svg (1)](https://user-images.githubusercontent.com/114623144/197126191-c019ad97-872b-4dec-a16b-09f1b4a19063.png)


NoSQL Database is a non-relational Data Management System that does not require a fixed schema. It avoids joins and is easy to scale. 
The major purpose of using a NoSQL database is for distributed data stores with humongous data storage needs. 
NoSQL is used for Big data and real-time web apps. For example, companies like Twitter, Facebook and Google collect terabytes of user data every single day. The system response time becomes slow when you use RDBMS for massive volumes of data.

Traditional RDBMS uses SQL syntax to store and retrieve data for further insights. Instead, a NoSQL database system encompasses a wide range of database technologies that can store structured, semi-structured, unstructured and polymorphic data. 

## Features of NoSQL Databases

 1. Non-relational
    - NoSQL databases never follow the relational model
    - Never provide tables with flat fixed-column records
    - Work with self-contained aggregates or BLOBs
    - Doesn’t require object-relational mapping and data normalization
    - No complex features like query languages, query planners,referential integrity joins, ACID


2. Schema-free
    - NoSQL databases are either schema-free or have relaxed schemas
    - Do not require any sort of definition of the schema of the data
    - Offers heterogeneous structures of data in the same domain

  

3. Simple API
   - Offers easy to use interfaces for storage and querying data provided
   - APIs allow low-level data manipulation & selection methods
   - Text-based protocols mostly used with HTTP REST with JSON
   - Mostly used no standard based NoSQL query language
   - Web-enabled databases running as internet-facing services


4. Distributed
   - Multiple NoSQL databases can be executed in a distributed fashion
   - Offers auto-scaling and fail-over capabilities
   - Often ACID concept can be sacrificed for scalability and throughput
   - Mostly no synchronous replication between distributed nodes Asynchronous Multi-Master Replication, peer-to-peer, HDFS Replication
   - Only providing eventual consistency
   
 
 ![image](https://user-images.githubusercontent.com/114623144/197124279-053e13c0-fd18-4213-9674-502cf032278e.png)


## Query Mechanism tools for NoSQL

The most common data retrieval mechanism is the REST-based retrieval of a value based on its key/ID with GET resource
Document store Database offers more difficult queries as they understand the value in a key-value pair. For example, CouchDB allows defining views with MapReduce

## What is the CAP Theorem?

CAP theorem is also called brewer’s theorem. It states that is impossible for a distributed data store to offer more than two out of three guarantees

1.	Consistency
2.	Availability
3.	Partition Tolerance

✔️Consistency:

The data should remain consistent even after the execution of an operation. This means once data is written, any future read request should contain that data. For example, after updating the order status, all the clients should be able to see the same data.

✔️Availability:

The database should always be available and responsive. It should not have any downtime.

✔️Partition Tolerance:

Partition Tolerance means that the system should continue to function even if the communication among the servers is not stable. For example, the servers can be partitioned into multiple groups which may not communicate with each other. Here, if part of the database is unavailable, other parts are always unaffected.

## Eventual Consistency

The term “eventual consistency” means to have copies of data on multiple machines to get high availability and scalability. Thus, changes made to any data item on one machine has to be propagated to other replicas.
Data replication may not be instantaneous as some copies will be updated immediately while others in due course of time. These copies may be mutually, but in due course of time, they become consistent. Hence, the name eventual consistency.


## BASE: Basically Available, Soft state, Eventual consistency

- 	Basically, available means DB is available all the time as per CAP theorem

- 	Soft state means even without an input; the system state may change

-  	Eventual consistency means that the system will become consistent over time

![image](https://user-images.githubusercontent.com/114623144/197130035-f0304c65-340c-4fc8-a654-9601e4200b7e.png)

 
## Advantages of NoSQL

  -	Can be used as Primary or Analytic Data Source

  -	Big Data Capability

  -	No Single Point of Failure

  -	Easy Replication

  -	No Need for Separate Caching Layer

  -	It provides fast performance and horizontal scalability.

  -	Can handle structured, semi-structured, and unstructured data with equal effect

  -	Object-oriented programming which is easy to use and flexible

  -	NoSQL databases don’t need a dedicated high-performance server

  -	Support Key Developer Languages and Platforms

  -	Simple to implement than using RDBMS

  -	It can serve as the primary data source for online applications.

  -	Handles big data which manages data velocity, variety, volume, and complexity

  -	Excels at distributed database and multi-data center operations

  -	Eliminates the need for a specific caching layer to store data

  -	Offers a flexible schema design which can easily be altered without downtime or service disruption

## Disadvantages of NoSQL

  -	No standardization rules

  -	Limited query capabilities

  -	RDBMS databases and tools are comparatively mature

  -	It does not offer any traditional database capabilities, like consistency when multiple transactions are performed simultaneously.

  -	When the volume of data increases it is difficult to maintain unique values as keys become difficult

  -	Doesn’t work as well with relational data

  -	The learning curve is stiff for new developers

  -	Open source options so not so popular for enterprises.

## Summary

  -	NoSQL is a non-relational DMS, that does not require a fixed schema, avoids joins, and is easy to scale

  -	The concept of NoSQL databases became popular with Internet giants like Google, Facebook, Amazon, etc. who deal with huge volumes of data

  -	In the year 1998- Carlo Strozzi use the term NoSQL for his lightweight, open-source relational database

  -	NoSQL databases never follow the relational model it is either schema-free or has relaxed schemas

  -	Four types of NoSQL Database are 1). Key-value Pair Based 2). Column-oriented Graph 3). Graphs based 4). Document-oriented

  -	NOSQL can handle structured, semi-structured, and unstructured data with equal effect

  -	CAP theorem consists of three words Consistency, Availability, and Partition Tolerance

  -	BASE stands for Basically Available, Soft state, Eventual consistency

  -	The term “eventual consistency” means to have copies of data on multiple machines to get high availability and scalability

  -	NOSQL offer limited query capabilities







