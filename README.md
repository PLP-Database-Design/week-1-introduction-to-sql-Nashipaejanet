# SQL Assignment Week 1


## *What You'll Need*
- A computer with internet access.
- A code editor (e.g., Visual Studio Code).
- MySQL Workbench or another SQL database environment.

---



## *Submission Instructions*
1. Answer every question below and put your responses in a file named `answers.md`
2. Push your completed `answers.md` file to your GitHub repository.
3. Submit the GitHub link for review.

---

## **Assignment Questions**

1. State and Explain the components of a DBMS(Database Management System)
A Database Management System (DBMS) is software that provides a systematic and efficient way to manage and manipulate databases. It is responsible for the creation, maintenance, and manipulation of databases, ensuring that data is stored, retrieved, and updated in a structured and secure manner.

Components of a DBMS

Database Engine:

The database engine is the core component of a DBMS responsible for managing data storage, retrieval, and modification. It acts as an intermediary between the user and the database, executing queries and ensuring that the operations are performed efficiently and accurately.
It handles tasks like transaction management, concurrency control, and ensuring the ACID (Atomicity, Consistency, Isolation, Durability) properties.

Database Schema:

A schema is the structure that defines how the data is organized within the database. It defines tables, views, indexes, and relationships, and it sets rules about the data types and constraints (like primary keys and foreign keys).
There are typically three levels of schema:
Internal Schema: Describes how data is physically stored in the database (low-level storage details).
Conceptual Schema: Describes the logical structure of the data (what data is stored, but not how it is stored).
External Schema: Describes the way users view the data, including user permissions and views.

Database Query Processor:

The query processor interprets and executes SQL (Structured Query Language) commands given by users or applications. It translates high-level queries into low-level operations that the DBMS can understand.
This component optimizes query performance and determines the most efficient way to access the data.

Transaction Management:

This component ensures that database transactions (sets of operations that should be treated as a single unit) are executed in a manner that maintains data integrity and consistency.
It handles ACID properties:
Atomicity: All operations within a transaction are completed; if one fails, the entire transaction is rolled back.
Consistency: The database must transition from one valid state to another.
Isolation: Transactions occur independently, without interference.
Durability: Once a transaction is committed, its results are permanent, even in the event of a system failure.

Data Dictionary:

A data dictionary stores metadata (data about data). It keeps track of all the database objects, such as tables, views, columns, and their constraints, and it provides descriptions about them.
The data dictionary helps users and administrators understand the structure and organization of the database and is used by the DBMS to enforce integrity constraints.

Database Administrator (DBA):

A Database Administrator is responsible for overseeing the operation, security, and maintenance of the database system. The DBA ensures that the database runs efficiently, manages users and access controls, performs backups, and handles database tuning and optimization.

Security and Access Control:

This component is responsible for ensuring that only authorized users and applications can access the database. It involves:
Authentication: Verifying the identity of users.
Authorization: Granting appropriate access privileges (read, write, delete, etc.).
Encryption: Protecting sensitive data by converting it into a secure format.
Audit Trails: Logging database activities to track who accessed the database and what operations were performed.

Backup and Recovery:

The backup and recovery component ensures that the database can be restored in case of failure. It regularly creates backups of the database and provides mechanisms to recover data from backups.
This ensures data durability by preventing data loss in case of hardware failure, power loss, or corruption.

Data Storage Management:

This component handles the physical storage of the data on disk or other storage devices. It optimizes data placement to minimize access time and maximize performance.
It includes indexing, caching, and the management of storage structures like tables, files, and partitions.

Concurrency Control:

This ensures that multiple users or applications can access the database simultaneously without interfering with each other, leading to data inconsistencies.
Concurrency control involves techniques such as locking, timestamping, and optimistic concurrency to handle simultaneous transactions efficiently.

2. What is a relational database? Give 4 examples.

A relational database is a type of database that stores data in tables (also known as relations), where each table consists of rows and columns. The data in these tables is organized and related to other data in other tables through the use of keys (such as primary keys and foreign keys). This structure allows for efficient data retrieval, manipulation, and integrity.

Key Features of a Relational Database:
Tables: Data is stored in tables, where each table represents an entity (e.g., users, orders, products).
Rows and Columns: Each row represents a record, and each column represents an attribute of that record.
Relationships: Tables are related to one another using foreign keys, which reference the primary key of another table.
SQL (Structured Query Language): SQL is used to interact with relational databases for querying, updating, and managing the data.
Examples of Relational Databases:
MySQL: An open-source relational database management system that is widely used for web applications and dynamic websites. It uses SQL for querying data.

PostgreSQL: An advanced open-source relational database system known for its robustness, extensibility, and support for complex queries and data types.

Microsoft SQL Server: A relational database management system developed by Microsoft, often used for enterprise-level applications. It supports a wide range of enterprise features, including high availability and security.

Oracle Database: A commercial relational database system that is commonly used for large-scale applications. It provides extensive features for managing large amounts of data in a secure and scalable manner.

3. State and Explain three classifications of SQL?

SQL (Structured Query Language) is classified into three primary categories based on its functionality:

1. Data Definition Language (DDL)
DDL is responsible for defining, modifying, and managing the structure of database objects such as tables, views, and schemas. It focuses on how the data is organized and stored.

Common DDL commands:

CREATE: Used to create new database objects like tables, views, or indexes.
Example: CREATE TABLE students (id INT, name VARCHAR(100));
ALTER: Used to modify existing database objects, such as adding or removing columns in a table.
Example: ALTER TABLE students ADD age INT;
DROP: Used to delete database objects like tables, views, or indexes.
Example: DROP TABLE students;
TRUNCATE: Used to remove all records from a table without deleting the structure of the table.
Example: TRUNCATE TABLE students;
Explanation: DDL defines the structure of the database and its objects, but it does not manage data within the objects.

2. Data Manipulation Language (DML)
DML deals with the manipulation of the data stored in the database. It is used to query, insert, update, and delete data from the tables.

Common DML commands:

SELECT: Used to retrieve data from one or more tables.
Example: SELECT * FROM students WHERE age > 18;
INSERT: Used to insert new records into a table.
Example: INSERT INTO students (id, name, age) VALUES (1, 'John Doe', 20);
UPDATE: Used to modify existing records in a table.
Example: UPDATE students SET age = 21 WHERE id = 1;
DELETE: Used to delete records from a table.
Example: DELETE FROM students WHERE age < 18;
Explanation: DML is used for manipulating the actual data in the database, either by adding, updating, deleting, or retrieving data from tables.

3. Data Control Language (DCL)
DCL is used to control access to the data stored in the database. It defines who can access the database, and what actions they can perform on the data.

Common DCL commands:

GRANT: Used to give users access rights or privileges to perform specific operations on database objects.
Example: GRANT SELECT ON students TO user1;
REVOKE: Used to remove or revoke previously granted permissions from users.
Example: REVOKE SELECT ON students FROM user1;
Explanation: DCL ensures database security by controlling permissions and access to the database objects. It is crucial in multi-user systems for defining and managing user roles and privileges.
4. What is the difference between a Primary Key and a Foreign Key?

Key Differences
1. Purpose
   Primary key: Uniquely identifies a record in a table.
   Foreign key: Establishes a relationship between two tables.
2. Uniqueness
   Primary key: Must be unique for each record.
   Foreign key: Can have duplicate values (if referencing multiple rows).
3. Null Values
   Primary key: Cannot have NULL values.
   Foreign key: Can have NULL values, depending on the constraint.
4. Reference
   Primary key References no other table.
   Foreign key: References the Primary Key (or Unique Key) of another table.
5. Number of Keys
   Primary key: There is only one Primary Key per table.
   Foreign key: There can be multiple Foreign Keys in a table.

7. What is an Entity-Relationship Diagram?
An Entity-Relationship Diagram (ERD) is a visual representation of the entities within a system and their relationships to one another. It is commonly used in database design to model the structure of a database and the interactions between different entities in the system.

Components of an ERD:
Entities:

Definition: An entity represents a real-world object or concept that has data stored about it. Entities are often represented by rectangles in ERDs.
Example: In a university system, Student, Course, and Professor could be entities.
Attributes:

Definition: Attributes are the properties or characteristics that describe an entity. Attributes are typically represented by ellipses or ovals.
Example: For the Student entity, attributes could include Student_ID, Name, Age, and Email.
Relationships:

Definition: A relationship shows how entities are related to each other. Relationships are represented by diamonds in ERDs.
Example: A Student "enrolls in" a Course, or a Professor "teaches" a Course.
Primary Key:

Definition: A primary key is an attribute (or a set of attributes) that uniquely identifies each record in an entity. In ERDs, the primary key is often underlined.
Example: Student_ID in the Student entity could be the primary key.
Foreign Key:

Definition: A foreign key is an attribute in an entity that refers to the primary key of another entity. It establishes a link between the two entities.
Example: The Student entity may have a foreign key like Course_ID to indicate which course a student is enrolled in.
Cardinality:

Definition: Cardinality defines the number of instances of one entity that can or must be associated with each instance of another entity.
Types of Cardinality:
One-to-One (1:1): One instance of an entity is related to one instance of another entity.
One-to-Many (1:N): One instance of an entity is related to many instances of another entity.
Many-to-Many (M:N): Many instances of an entity are related to many instances of another entity.

8. What are the advantages of relational databases?

1. Data Integrity and Accuracy:
Advantages:
Constraints: Relational databases support constraints like primary keys, foreign keys, and unique constraints that ensure data consistency, integrity, and accuracy.
Normalization: Through normalization, relational databases avoid data redundancy, ensuring that data is stored efficiently and correctly.
ACID Properties: Relational databases ensure transactions follow ACID (Atomicity, Consistency, Isolation, Durability) properties, making sure that the database remains in a consistent state even after system crashes or failures.
2. Ease of Use:
Advantages:
Structured Query Language (SQL): SQL is a standard language used to interact with relational databases. SQL is widely known, easy to learn, and allows for complex queries to retrieve and manipulate data.
Data Relationships: Relational databases are based on tables, which make it intuitive to model real-world relationships (e.g., one-to-many, many-to-many) between different data entities.
3. Data Redundancy Reduction:
Advantages:
Normalization: Relational databases emphasize normalization, which helps in minimizing data redundancy. This means data is not repeated across tables unnecessarily, reducing storage requirements and making updates easier.
Efficient Storage: Since redundant data is avoided, storage is more efficient, and there is less risk of inconsistencies in the data.
4. Flexibility and Scalability:
Advantages:
Scalability: Relational databases are scalable and can handle large volumes of data. Most modern relational databases support horizontal and vertical scaling to accommodate growing amounts of data.
Flexibility in Queries: With SQL, users can create complex queries to extract data in any format needed. Relational databases also support joins, which allow combining data from multiple tables in a flexible and efficient way.
5. Security:
Advantages:
User Access Control: Relational databases provide mechanisms to restrict access to data. Different user roles can be assigned different levels of access, ensuring that sensitive data is protected.
Encryption and Auditing: Many relational database systems offer built-in encryption for data at rest and in transit, as well as audit trails for monitoring access and changes to the data.
6. Consistency and Reliability:
Advantages:
ACID Compliance: The ACID properties ensure that database operations are reliable, consistent, and transaction-safe, even during system crashes or power failures. This makes relational databases particularly suitable for critical applications such as financial systems.
Data Recovery: Relational databases provide features such as transaction logs, backups, and failover mechanisms, which help recover data in case of failure.
7. Data Independence:
Advantages:
Logical and Physical Data Independence: Relational databases provide logical and physical data independence, meaning that changes made at the physical storage level (e.g., indexing or changing storage devices) do not affect how data is logically represented or accessed by users and applications.
8. Standardization and Compatibility:
Advantages:
Industry Standard: Relational databases follow a widely adopted standard (SQL) that makes it easy for developers to work across different platforms and systems. This also helps in database migration and integration with other tools or technologies.
Vendor Compatibility: Many relational database management systems (RDBMS) are compatible with each other (e.g., MySQL, PostgreSQL, Oracle, SQL Server), so you can switch between vendors or platforms with minimal effort.
9. Support for Complex Queries:
Advantages:
Complex Query Handling: Relational databases support complex queries, including aggregation, filtering, grouping, sorting, and joining data across multiple tables. This makes them powerful tools for data analysis and reporting.
Stored Procedures and Triggers: Relational databases allow the use of stored procedures and triggers to automate repetitive tasks and ensure business logic is consistently applied.
10. Backup and Recovery:
Advantages:
Automated Backups: Most relational databases offer automated backup options to ensure data is periodically saved, providing an additional layer of protection in case of system failure.
Recovery Tools: In case of a failure, relational databases typically provide advanced recovery tools to restore data to its most recent consistent state.

9. State four types of data type used to store data in tables?
   
In relational databases, tables are used to store data, and each column in a table is associated with a specific data type. Here are four common types of data types used to store data in tables:

1. Integer (INT):
Description: Used to store whole numbers (positive or negative) without any decimal points.
Example:
INT can store values like 10, -5, 1000, etc.
Use Case: Used for fields that represent counts, quantities, and other integer values such as age, quantity, or id.
2. VARCHAR (Variable Character):
Description: Used to store variable-length strings of characters. The length can vary based on the actual content.
Example:
VARCHAR(50) can store strings like "John Doe" or "New York".
Use Case: Used for storing names, addresses, email addresses, and other textual information.
3. DATE:
Description: Used to store date values (year, month, and day) in a specific format (YYYY-MM-DD).
Example:
DATE can store values like "2025-01-10" or "1990-12-25".
Use Case: Used to store dates such as birth dates, transaction dates, or any other date-related information.
4. FLOAT (or DECIMAL/REAL):
Description: Used to store numbers with decimal points, which can represent real numbers (floating-point values).
Example:
FLOAT can store values like 10.75, -3.14, or 1000.5.
Use Case: Used for storing financial values, measurements, and any data requiring precision beyond integers (e.g., price, temperature, height).

10. What is the purpose of a database management system (DBMS)?  
1. Data Storage and Retrieval:
The DBMS ensures that data is stored in a structured format (typically in tables) and can be retrieved efficiently when needed by users or applications.
It optimizes the retrieval process through indexing, querying languages like SQL, and query optimization techniques.
2. Data Integrity and Consistency:
A DBMS enforces rules to maintain the accuracy and reliability of the data. This includes data validation rules and constraints like primary keys, foreign keys, unique constraints, and checks that prevent invalid data entry.
It ensures data consistency by implementing ACID (Atomicity, Consistency, Isolation, Durability) properties for transactions, ensuring data remains consistent even in the event of failures.
3. Data Security:
A DBMS manages user access to the database to prevent unauthorized access and ensure data privacy and security.
It provides features such as user authentication, authorization, and role-based access control to restrict who can view, modify, or delete data.
4. Data Independence:
The DBMS allows for data independence by separating the data model from the application logic. This makes it easier to change the underlying database structure without affecting the applications that use the data.
5. Concurrency Control:
A DBMS handles multiple users accessing and modifying the data simultaneously by using concurrency control mechanisms to avoid conflicts or inconsistencies (e.g., deadlocks, lost updates).
It uses techniques like locking and transactions to ensure that operations on the data are performed in an orderly and isolated manner.
6. Backup and Recovery:
The DBMS provides tools to back up data regularly and restore it in case of data loss, corruption, or system failure.
It ensures the database can recover to a consistent state after a failure (e.g., using transaction logs or point-in-time recovery).
7. Data Redundancy Minimization:
The DBMS reduces redundancy by organizing data in a way that minimizes duplication, such as through normalization processes that structure data efficiently.
8. Support for Multiple Users and Applications:
A DBMS allows multiple users or applications to access the database concurrently while maintaining isolation and preventing conflicts.
It facilitates multi-user environments, ensuring data integrity and security while providing support for both batch and real-time processing.
*How to edit a [markdownfile](https://www.markdownguide.org/basic-syntax/#headings)*

###  NOTE: You should not fork the repository
