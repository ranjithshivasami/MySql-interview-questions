# Mysql Interview questions

1. ###  Describe **BLOB** in MySQL. What is it used for?

    **BLOB** or Binary Large Object can be used to store binary data in MySQL. Sometimes binary data like images need to be stored in SQL databases. For example you might want to store user photos along with other user details in the database table. Binary data of the user photo can be saved as a BLOB. By using BLOB, we will not require separate storage for images. BLOB helps in removing complexity and providing portability in such cases.

2. ### How are **VARCHAR** and **CHAR** different. Talk about cases where you will use one over other.

    Both **CHAR** and **VARCHAR** data types store characters up to specified length.

    * CHAR stores characters of fixed length while VARCHAR can store characters of variable length.
    * Storage and retrieval of data is different in CHAR and VARCHAR.
    * CHAR internally takes fixed space, and if stored character length is small, it is padded by trailing space characters. VARCHAR has 1 or 2 byte prefix along with stored characters.
    * CHAR has slightly better performance.
    * CHAR has memory allocation equivalent to the maximum size specified while VARCHAR has variable length memory allocation.

3. ### What is self referencing foreign key? Give an example.

    A foreign key which is stored in a table itself is called to be **self referencing foreign key.**

    For example consider an Employee database table. It has employee_id as primary key as well as a manager_id which is employee_id of his manager. If we create a foreign key constraint, as a manager is also an employee, manager_id will reference to empolyee_id in the same table. The Employee table with self referencing foreign key manager_id can be created using below statement.

    ```
    CREATE TABLE `Employee`( 
    `name` VARCHAR(25) NOT NULL, 
    `employee_id` CHAR(9) NOT NULL, 
    `manager_id` CHAR(9) NOT NULL, 
    `salary` decimal(10,2) NULL,  
    PRIMARY KEY(`employee_id`),
    FOREIGN KEY (manager_id) REFERENCES employee(employee_id) ON DELETE CASCADE
    );
    ```
4. ### What is the difference between Data Definition Language (DDL) and Data Manipulation Language (DML)?

    * Data definition language (DDL) commands are the commands which are used to define the database. CREATE, ALTER, DROP and TRUNCATE are some common DDL commands.

    * Data manipulation language (DML) commands are commands which are used for manipulation or modification of data. INSERT, UPDATE and DELETE are some common DML commands.



