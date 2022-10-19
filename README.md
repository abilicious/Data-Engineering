
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

## What is a table

## What is a schema 

This is the way a database is structured. Relational databases have schema's while non relational databases like NoSql databases e.g. MongoDB are schema-less.
schema's are a formal description of the organisation and structure of data in a database. This inclusdes definition of table, columns, data types, indexes, constraints, etc.
Schemas are important for consistency and efficiency. Databases work With schema's

## How to create a table with its schema

Typically a schema will be created as part of a table creation process within the RDBMS using SQL language.
Schema of a table is the structure of the table, data types and contstraints


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
 
      Duplicate data also called redundant data is bad with databases. It wastes spaces and
      increases the posibility of errors

✔️ A good database has Information sub divided into broad subject areas.

      Example subject areas are: Product, Customer. This will help to reduce data redundancy

✔️ A good database accomodates data processing and reporting needs.
      
      A good way of tackling this will be to plan ahead the purpose of the database, ensuring all
      reporting needs are met

✔️ A good database ensure correctness and completeness of information. 

    This is important because if the database does not contain correct information, 
    Any report that pulls information from it will also be incorrect.
  
##  What is the design process

📣 Determine the purpose of your Database.

     ✔️ This is how you intend to use the database. You could elicit requirement or conduct similar exercise
      to determine its use. Example: a Customer database that keeps a list of customer related information.

📣 Gather and organize all forms of information required

      ✔️ After you have determined the purpose of your database, you need to gather data needed to be
      stored on the database. Consider reporting requirements, user requirements etc.. and what other information
      you will need to satisfy these

📣 Divide information into tables

      ✔️ Divide data into subject based tables. Choose major entities for subjects


📣 Specify primary keys - Choose a column or several columns to uniquly identify each rows
  
    ✔️ Primary Keys 🗝
    
         Each table should have a column or a set of columns that uniquely identifies each row. This is called
         the Primary Key. For example on a 'Customer Table', a good primary key will be the Customer Id rather 
         than the Customer Name, as several other customers can have same names. You could also use arbitrary 
         unique number or an autogenerated unique numbers as Primary Keys. Primary Keys cannot have duplicate 
         values.
    
         A Primary Key must have a value. If when selecting your primary key, there is a possibility of the key
         to have an unknown or unassigned value, this cannot be used as a Primary Key. 
    
         The Primary Key value should not change. This is because within a relational database, tables can reference
         other tables via their Primary Keys and if the primary key changes, you will have to update all the Primary 
         keys on the tables being referenced. If a Primary Key changes, it can increase the risk of primary keys being
         out of synch with tables referencing it.
    
         In summary, 
         A primary key cannot be NULL. 
         A primary key value must be unique. 
         A primary key value should rarely change. 
         A primary key must be given a value one a new record is inserted
    
    ✔️ Composite keys 🗝🗝  
    
         These are primary keys comprising multiple columns used to identify a record uniquely

📣 Specify table cardinalities or table relationships

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
  
    This speaks about two tables with multiple references to each other. Example: on a "Product Order" Database, 
    An 'Order Table' can have single order with more than one product on the 'Product Table' and also a single 
    Product on the 'Product Table'can appear on many orders on the 'Orders Table'
        

📣 Normalisation - Applying Normalisation rules

   Normalisation is a process of efficiently organising data in a database to eliminate redundancy and inconsistent dependencies. 
   This includes creating Tables and establishing relationmships between these tables.
   
   The rules for database Normalisations are called 'Normal Forms'. 
   
   If a database conforms to the first normal form, then the database is said to be in the first normal form
   If it adheres to the first three normal forms, the database is considered to be in the third normal form.
   
   There are about 5 Normal forms, but only the first three are considered to be the highest level necessary for most applications. 
   
    ✔️ First normal form (1NF)
            - Each cell should contain a single value. 
               We need to eliminate repeating groups of columns in a cell (e.g. item1, item2, ..)
            - Creation of separate tables for related data
            - Identify each set of related data with a primary key
            
            
    ✔️ Second normal form (2NF)
         - The table is already in 1NF
         - Every non-key column is fully dependent on the primary key (or composite key)
               E.g, An 'OrderDetails' table having primary key comprising 'ProductID' and 'OrderId'. If unit_price is only
               dependent on 'ProductID' it should not be kept in 'OrderDetails' Table but the 'Product' table. On the other
               hand. If unit_price is also dependent on the particular Order. It can be kept in 'OrderDetails' table
         - Create separate table for sets of values that apply to multiple records. 
               E.g, Customer Address can be stored on Customer Address table intstead of multiple tables that use it 
               like Orders, Shipping, Invoicing tables
         - Relate these tables using a Foreign key
         
     ✔️ Third normal form (3NF)
         - The table is already in 2NF
         - Eliminate field that do not depend on the key. Columns should not depend on each other but only the primary key
               E.g, on a 'Product' table with 'ProductID' as primary key. Discount_rate should not belong to 'Product' table
               if it depends on unit_price on the same table.
         - Note: Whilst 3NF is desirable, it might not always be practical. creation of separate smaller tables to remove 
               inter-column relationships in some instances might degrade performance. Ensure you are fully aware of your
               design decisions and document it
  


## Un Structured or Semi Structured Databases
It could also describe storage of non structured or Document data in NoSql  Databases like Mongo DB.







