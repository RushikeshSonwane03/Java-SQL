## Day 1 : 10-06-2024

1. SQL :- Structured Query Language -[Non Case Sensitive]
2. XAMPP :- Cross Platform, Apache, MariaDB(MySQL), PHP, Perl
3. WAMPP :- Windows, Apache, MariaDB(MySQL), PHP, Perl
4. LAMPP :- Linux, Apache, MariaDB(MySQL), PHP, Perl

- XAMPP :-  Default Ports: Apache (80,443) , MySQL(3306)

- DataType :- 
	- Strings - Char(0 - 255), Varchar(0 - 65535), Text(0 - 65535), Enum(65535), Blob(65535)
	- Numeric - Int (255), Integer, Float, Double, Bool
	- Date & Time - Date, DateTime, TimeStamp, Time, Year - [Format: Date= YYYY-MM-DD, Time= HH:MM:SS, DateTime= YYYY-MM-DD hh:mm:ss,
	- TimeStamp:TimeZone- UTC+05:30]

- SQL Commands :- 
    - DDL - Data Definiton Language (CREATE, DROP, ALTER, TRUNCATE, RENAME)
    - DML - Data Manipulation Language (INSERT, UPDATE, DELETE, CALL, LOCK)
    - TCL - Transaction Control Language (COMMIT, SAVEPOINT,ROLLBACK, SET TRANSACTION, SET CONSTRAINT)
    - DQL - Data Query Language (SELECT)
    - DCL - Data Control Language (GRANT, REVOKE) 

- CRUD :- Create, Read, Update, Delete
    - Create Database Database_Name;
    - Create Table Table_Name(Column1_Name datatype, Column2_Name datatype, Column3_Name datatype, ......);
    - Insert into Table_Name(Column1_Name datatype, Column2_Name datatype, Column3_Name datatype, ......) values(Column1_Value, Column2_Value, Column3_Value, ......);
    - Insert Multiple rows in single querry: () <- A single Tupple == Row
        - Insert into Table_Name(Column1_Name datatype),(Column1_Name datatype),(Column1_Name datatype);
    - Select * from Table_Name;
    - Update Table_Name set column_name=value where condition;
    - Delete from Table_Name where condition;

- Activity :-
```sh
    Create Database Rushi;
    Use Rushi;
    Create TABLE Student(id int(10), name varchar(100));
    Insert into Student(id, name) values(101,"abcd");
    Select * from Student;
    Update student set name="xyz" where id=101;
    Delete from Student where id=101;
    DROP TABLE Student;
    DROP DATABASE rushi;
```
========================================================================================================================================

## Day 2 : 11-06-2024

- Operations :
    - Create Database:- CREATE DATABASE Database_Name;
    - Rename Database:- RENAME DATABASE Old_Database_Name to New_Database_Name; (Removed from MYSQL due to security and Connectivity Reasons) --> Alternate way in XAMPP -> [Select database - Operations(Nav bar) - Scroll down - Select option (Rename database to) - Go.]
    - Select Database:- USE Database_Name;

- Table:-
    - Create Table student(id int(10), name varchar(100));
    - Drop table student;

    - Insert into Student(id, name) values(1,"abcd");
    - Insert into Student(id, name) values(1,"abcd"),(2,"pqrs"),(3,"mnop");

    - Delete from Student where id = 1;
    - Delete from Student;

- Truncate :- Deletes all the entries present inside the table.
    - Truncate Table table_name;

- Copy Table :-
    Insert into Destination_Table Select * from Source_Table ;  

    * Example:
        - Insert into Student1(id, name) values(1,"abcd"),(2,"pqrs"),(3,"mnop");
        - Insert into Student2 Select * from Student1 ;
        - Select * from Student2 ;

========================================================================================================================================

## Day 3 : 12-06-2024

- Alter Table :- Rename Column, Add Column, Modify Column, Drop Column.
    - RENAME Table:- ALTER TABLE present_table_name RENAME TO new_table_name;
        eg:- ALTER TABLE colleges RENAME TO student; 
    - Add Column:- ALTER TABLE table_name ADD column_name column_definition;
        eg:- ALTER TABLE student ADD Address varchar(20);
    - MODIFY Column:- ALTER TABLE table_name MODIFY column_name new_column_definition;
        eg:- ALTER TABLE student MODIFY Address varchar(500);
    - DROP Column:- ALTER TABLE table_name DROP COLUMN column_name;
        eg:- ALTER TABLE student DROP COLUMN Address;
    - ALTER RENAME Column :- ALTER TABLE table_name CHANGE Old_Column_Name New_Column_Name New_Column_Definiton;
        eg:- ALTER TABLE student CHANGE college_id college_roll_no int(10);

- SELECT CLAUSE:-
    - WHERE
    - GROUP BY + HAVING 
    - ORDER BY

    - SELECT * FROM table_name; -(Select all)
    - SELECT Column_Name from table_name; -(Select particular column)
    - SELECT Column1_Name,Column2_Name,Column3_Name from table_name; -(Select few columns)


    - KEYWORDS :-
        DISTINCT - SELECT DISTINCT column_name FROM table_name; (Select Unique values)

    - COUNT() :- 
        SELECT COUNT(column_name) FROM table_name;
        eg. 
            SELECT COUNT(name) from college;
            SELECT COUNT(DISTINCT name) from college;
            SELECT COUNT(*) from college;

    - LIMIT :-
        - SELECT * FROM table_name LIMIT number;
        
    - ORDER BY :-    
        - SELECT * FROM table_name ORDER BY column_name ASC;
        - SELECT * FROM table_name ORDER BY column_name DESC;

    - ORDER BY + LIMIT :-    
        - SELECT * FROM table_name ORDER BY column_name ASC LIMIT number;
        - SELECT * FROM table_name ORDER BY column_name DESC LIMIT number;

    - AS :-
        - SELECT original_column_name AS preview_column_name FROM table_name;
    
    - SUM() :-
        - SELECT SUM(column_name) AS "expression_name" FROM table_name;
            eg :- CREATE TABLE employee(eid int(10), salary int(255));
                Insert into employee(eid, salary) values(101, 10000), (102, 20000), (103, 30000), (104, 40000);
                SELECT SUM(SALARY) AS 'Total Salary' from employee;
    

========================================================================================================================================

## Day 4 : 13-06-2024

    - IN :-
        - SELECT * FROM table_name WHERE column_name IN (val1, val2, val3,.....); --< Searching Operation : WILL DISPLAY WHICHEVER VALUES ARE FOUND, NOT NECESSARY ALL VALUES TO BE FOUND FOR OUTPUT >
            eg :- SELECT * FROM college WHERE name IN ('abcd','efgh','ijkl'); 
    - OR :-
        - SELECT * FROM table_name WHERE column_name = value1 OR column_name = value1;
    - IS NULL - IS NOT NULL :-
        - SELECT * FROM table_name WHERE column_name IS NULL/NOT NULL;
            eg :- SELECT * FROM college WHERE id IS NULL; 
                SELECT * FROM college WHERE id IS NOT NULL; 
    - AND :- 
        - SELECT * FROM table_name WHERE condition1 AND condition2;
    
    - ORDER BY Clause :- (ASCENDING, DESCENDING, RANDOM)
        - SELECT * FROM table_name ORDER BY column_name ASC;
        - SELECT * FROM table_name ORDER BY column_name DESC;
        - SELECT * FROM table_name ORDER BY column_name RAND();
        - SELECT * FROM table_name ORDER BY column_name RAND() LIMIT Number;

- UPDATE :- 
    - UPDATE table_name SET column_name = value WHERE Condition;

========================================================================================================================================

## Day 5 : 14-06-2024

- JOINS :- To Find Records Stored in Multiple Tables.  
    - INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL JOIN
    ( A = LEFT TABLE, B = RIGHT TABLE)
        - INNER JOIN :- A ∩ B 
        - LEFT JOIN :- A - B
        - Right JOIN :- B - A
        - FULL OUTER JOIN :- A U B

    1. INNER JOIN :- SELECT * FROM table1_name INNER JOIN table2_name ON Condition ; 
                    SELECT * FROM table1_name JOIN table2_name ON Condition ; (ALTERNAME WAY) 
        eg.  
            SELECT * FROM first INNER JOIN second ON first.ID = second.ID ;
            SELECT first.ID,first.name,first.Address,second.Contact, second.Pincode FROM first INNER JOIN second ON first.ID = second.ID ;

    2. LEFT JOIN :- SELECT * FROM table1_name LEFT JOIN table2_name ON Condition ;
        eg.  
            SELECT * FROM first LEFT JOIN second ON first.ID = second.ID ;
            SELECT first.ID,first.name,first.Address,second.Contact, second.Pincode FROM first LEFT JOIN second ON first.ID = second.ID ;

    3. RIGHT JOIN :- SELECT * FROM table1_name RIGHT JOIN table2_name ON Condition ;
        eg.
            SELECT * FROM first RIGHT JOIN second ON first.ID = second.ID ;
            SELECT first.ID,first.name,first.Address,second.Contact, second.Pincode FROM first RIGHT JOIN second ON first.ID = second.ID ;

    4. FULL OUTER JOIN :- (LEFT JOIN + RIGHT JOIN = A U B) 
            - SELECT * FROM table1_name LEFT JOIN table2_name ON Condition 
              UNION
              SELECT * FROM table1_name RIGHT JOIN table2_name ON Condition ;  
        eg.  
            SELECT * FROM first LEFT JOIN second ON first.ID = second.ID
                UNION                
                SELECT * FROM first RIGHT JOIN second ON first.ID = second.ID ;
            SELECT first.ID,first.name,first.Address,second.Contact, second.Pincode FROM first LEFT JOIN second ON first.ID = second.ID 
                UNION
                SELECT first.ID,first.name,first.Address,second.Contact, second.Pincode FROM first RIGHT JOIN second ON first.ID = second.ID ;

    5. CROSS JOIN :- Returns ALL Records from BOTH the tables. 
        - SELECT * FROM table1_name CROSS JOIN table2_name;


    ( JOIN Multiple Tables :-
        - SELECT * FROM table1_name JOIN table2_name ON Condition JOIN table3_name ON Condition;
        - SELECT * FROM table1_name JOIN table2_name JOIN table3_name ON Condition; )

========================================================================================================================================

## Day 6 : 17-06-2024

- KEYS :-
    - PRIMARY KEY, FOREIGN KEY, COMPOSITE KEY, ALTERNATE KEY, UNIQUE KEY  

    1. PRIMARY KEY:- Uniquely identifies each row in the table. 
                    - It cannot have a null value.
                    - Primary Key always has a Unique data.
                    - PRIMARY KEY constraint can be applied to only one column for a Table.
        - CREATE TABLE table_name(Column_name Datatype(size), PRIMARY KEY (Column_name));
        eg. 
            CREATE TABLE studentdata(roll_no int(70), name varchar(100), PRIMARY KEY (roll_no));   // Roll_no <- Primary Key.

    2. COMPOSITE KEY :- A PRIMARY KEY made by Combination of Two or more Attributes (Data Columns). 
        - CREATE TABLE table_name(Column_name Datatype(size), PRIMARY KEY (Column1_name, Column2_name, ...));
        eg. 
            CREATE TABLE studentdata1(roll_no int(70), name varchar(100), address varchar(200), PRIMARY KEY (roll_no, name));   # Roll_no, Name <- COMPOSITE Key. (Roll_no & Name both cannot have same combination of data.)

    3. UNIQUE KEY :- It is little like PRIMARY KEY. 
                    - It can have single null value.
                    - Unique Key always has Unique data.
                    - There may be multiple UNIQUE KEY constraints for One table.
        - CREATE TABLE table_name(Column_name Datatype(size), UNIQUE KEY (Column1_name, Column2_name, ...));
        eg. 
            CREATE TABLE studentdata2(id int(70) NOT NULL, name varchar(100), email varchar(80), address varchar(200), UNIQUE KEY (id, email)); 

    4. FOREIGN KEY :- Establish a link between two tables.
                    - Foreign key in one table used to point primary key in another table.
        - CREATE TABLE table1_name(Column_name datatype(size), PRIMARY KEY(column_name));
          CREATE TABLE table2_name(Column_name datatype(size), PRIMARY KEY(column_name), FOREIGN KEY(column_name) REFERENCES table1.name(Primary_Key_Column_Name));
        eg. 
            CREATE TABLE Enrolled_Students(s_id int(50) NOT NULL, s_name varchar(50), PRIMARY KEY(s_id));
            CREATE TABLE Admission_List(s_id int(50) NOT NULL, name varchar(50), city varchar(50), PRIMARY KEY(s_id), FOREIGN KEY (s_id) REFERENCES Enrolled_Students(s_id));
            INSERT into enrolled_students values(1, 'Rushi'),(2, 'Anushka');
            SELECT * FROM enrolled_students;
            INSERT into Admission_List values(1, 'Rushi', 'Dhule'),(4, 'Manish', 'Nagaon');
            SELECT * FROM Admission_List;

    5. ALTERNATE KEY :- Keys that are qualified to become PRIMARY KEY but now as per below example, ID, ROll_no, Email all are qualified. But If I make id -> PRIMARY KEY then Roll_no & Email becomes ALTERNATE KEY. Such that, In Future I will be having alternative option for id to be assigned as PRIMARY KEY.  
        eg. 
            Student(Id int(10), Roll_no int(50), Email varchar(50));
        eg. Id, Roll_no, Email are qualified to become a primary key. But since Id is the primary key, Roll No, Email becomes the alternative key.
-- INDEXES :- When the data is Limited -> We Use JOINS & KEYS
            But if Data is not-limited -> We Use INDEXES
            - It is applied over large databases.
            - It is used to Retrieve data very Fast.
            - Indexing improves the performance of queries and applications.
            - It can reduce disk I/O by using a rapid path access method to locate data quickly.
        - Types :- PRIMARY, INDEX, UNIQUE, SPATIAL, FULLTEXT
    
    1. Primary Indexing :- 
        - CREATE TABLE table_name(column1_name datatype(size) AUTO_INCREMENT, column2_name datatype(size), PRIMARY KEY(column1_name));
        eg. 
            CREATE Table Student_indexing(id int(100) AUTO_INCREMENT, name varchar(100), PRIMARY KEY(id));
            DESCRIBE Student_indexing;
            INSERT into student_indexing(name) values('AAA'),('BBB'),('CCC'),('DDD');
            OP :- 	id  name  ----(Default Auto_Increment = 1,2,3,...)
                    1   AAA
	                2   BBB
                    3   CCC
	                4   DDD
        eg. 
            ALTER TABLE Student_indexing AUTO_INCREMENT=101;
            INSERT into student_indexing(name) values('EEE'),('FFF'),('GGG'),('HHH');
            SELECT * from student_indexing;
            OP :- 	id      name  --(Manual Auto_Increment = 101,...)
                    1       AAA
	                2       BBB
                    3       CCC
	                4       DDD
                    101     EEE
	                102     FFF
                    103     GGG 
	                104     HHH

    2. INDEX :- 
        - CREATE INDEX index_name ON table_name(Column_name Condition);
        eg. 
            CREATE INDEX sortnames ON student_indexing(name DESC);

    3. UNIQUE INDEX :- 
        - CREATE UNIQUE INDEX index_name ON table_name(column_name);
        eg. 
            CREATE UNIQUE INDEX validate_contact ON student_indexing(contact); -> (Only Unique indexs in Contact Column)

    4. FULLTEXT INDEX :- Implemented for Full-Text Searches.
            Datatypes - CHAR, VARCHAR, TEXT
        - CREATE TABLE table_name(column1_name datatype(size),column2_name datatype(size),column3_name datatype(size), FULLTEXT(column1_name, column2_name));
        - SELECT * FROM table_name WHERE MATCH(column1_name, column2_name) AGAINST('_Content_');
        eg. 
            CREATE TABLE BOOKS(title VARCHAR(220), content text, FULLTEXT(title,content));
            INSERT INTO BOOKS (title, content) VALUES
                ('Pride and Prejudice', 'It is a truth universally acknowledged, that a single man in possession of a good fortune, must be in want of a wife.'),
                ('Moby-Dick', 'Call me Ishmael. Some years ago—never mind how long precisely—having little or no money in my purse...'),
                ('Frankenstein', 'You will rejoice to hear that no disaster has accompanied the commencement of an enterprise which you have regarded with such evil forebodings.'),
                ('1984', 'It was a bright cold day in April, and the clocks were striking thirteen.'),
                ('Great Expectations', 'My father’s family name being Pirrip, and my Christian name Philip, my infant tongue could make of both names nothing longer or more explicit than Pip.'),
                ('To Kill a Mockingbird', 'When he was nearly thirteen, my brother Jem got his arm badly broken at the elbow.'),
                ('The Adventures of Huckleberry Finn', 'You don’t know about me without you have read a book by the name of The Adventures of Tom Sawyer; but that ain’t no matter.'),
                ('The Great Gatsby', 'In my younger and more vulnerable years my father gave me some advice that I’ve been turning over in my mind ever since.'),
                ('War and Peace', 'Well, Prince, so Genoa and Lucca are now just family estates of the Buonapartes.'),
                ('Ulysses', 'Stately, plump Buck Mulligan came from the stairhead, bearing a bowl of lather on which a mirror and a razor lay crossed.');
            SELECT * FROM books WHERE MATCH(title,content) AGAINST(' thirteen');

            OP :-   title	                content	
                    1984                    It was a bright cold day in April, and the clocks ...
                    To Kill a Mockingbird   When he was nearly thirteen, my brother Jem got hi...

    5. SPATIAL INDEX :- 
        - MySQL allows to Create Spatial Indexes on Geometry-values columns with NOT NULL constraint. The Spatial index creates an R-Tree index.
        - Spatial Data <- GeoSpatial Data or Geographic information is Data that identifies the geographic location of features and boundaries on Earth.
        - Usually used to store co-ordinates, topology, or other data that can be mapped.
    ---> Geometry = Datatype to store Geo-Coordinates.      
    ---> ST_GeomFromText: Converts a well-known Text(WKT) string into its corresponding GEOMETRY object.
    ---> POINT : On same location
    ---> LINESTRING : Source to Destination
    ---> POLYGON : Multiple Locations/Destinations

        eg. 
            CREATE TABLE geom(g GEOMETRY NOT NULL, SPATIAL INDEX(g));
            INSERT INTO geom VALUES(ST_GeomFromText('POINT(1 1)')),(ST_GeomFromText('LINESTRING(2 1, 6 6)')),(ST_GeomFromText('POLYGON((0 5, 2 5, 2 7, 0 7,0 5))'));
    
        eg. 
            CREATE TABLE BOOKING(name varchar(100), contact int(100), location GEOMETRY NOT NULL, SPATIAL INDEX(location));
            INSERT INTO BOOKING VALUES('RUSHI', 98765, ST_GeomFromText('LINESTRING(1 1, 7 7)'));
            SELECT * FROM Booking;


========================================================================================================================================

## Day 8 : 19-06-2024

- PL SQL :- "Procedural Language extension of SQL"
        -  It is a block structured language that can have multiple blocks in it.
            - PL/SQL block structure:
                DECLARE
                    Declaration statements;
                    BEGIN
                            Execution statements;
                        EXCEPTION
                            Exception handling statements;
                    END;
                    /

        - A line of PL/SQL text contains groups of characters known as lexical units. It can be classified as follows:
            - DELIMITER //
                BEGIN
                    ...........
                END //
            DELIMITER ;

        

- DELIMITER :-
    

    - Syntax :-
        DELIMITER //
                CREATE FUNCTION function_name(parameter datatype)
                RETURNS datatype(size)
                BEGIN
                    DECLARE variable_name datatype;
                    SET (Business Logic) ;
                    RETURN return_variable;
                END //
        DELIMITER  ;
    

        eg. [Square of a Number :-]
            (1) DELIMITER //
                    CREATE FUNCTION square(num int)
                    RETURNS int
                    BEGIN
                        RETURN num * num;
                    END //
                DELIMITER  ;
        
            (2) DELIMITER //
                    CREATE FUNCTION square1(num int)
                    RETURNS int
                    BEGIN
                        DECLARE result int;
                        SET result = num * num;
                        RETURN result;
                    END //
                DELIMITER  ;
        
            -> SELECT square(5); => 25
            -> SELECT square(255); => 65025


        eg. [Addition of Two numbers :-]
            DELIMITER //
                CREATE FUNCTION add0(num1 int, num2 int)
                RETURNS int
                BEGIN
                    DECLARE result int;
                    SET result = num1 + num2;
                    RETURN result;
                END //
            DELIMITER  ;

            -> SELECT add0(5,2); => 7

- CONTROL STATEMENTS :-
    1. IF THEN ELSE :
    Syntax-
        DELIMITER //
            CREATE FUNCTION function_name(parameter datatype)
            RETURNS datatype(size)

            BEGIN 
                DECLARE variable_name datatype(size);
                IF condition THEN
                    SET expression;
                ELSE
                    SET expression;
                END IF;
                RETURN return_variable;
            End //
        DELIMITER ;


                
        eg. [Check Even-Odd Number]
            DELIMITER //
                CREATE FUNCTION even_odd_check(num INT)
                RETURNS varchar(100)
                BEGIN
                    DECLARE result varchar(100);
                    IF num % 2 = 0 THEN
                        SET result = "Even Number";
                    ELSE
                        SET result = "Odd Number";
                    END IF;
                    RETURN result;
                End //
            DELIMITER ;

            - SELECT even_odd_check(2); => Even Number
            - SELECT even_odd_check(5); => Odd Number


        eg. [Simple Calculator Function]
            DELIMITER //
                CREATE FUNCTION calculations(num1 INT, num2 INT, op INT)
                # 1 = Addition, 
                # 2 = Substraction,
                # 3 = Multiplication,
                # 4 = Division
                RETURNS INT
                BEGIN
                    DECLARE result INT;
                    IF op = 1 THEN
                        SET result = num1 + num2;
                    ELSEIF op = 2 THEN
                        SET result = num1 - num2;
                    ELSEIF op = 3 THEN
                        SET result = num1 * num2;
                    ELSEIF op = 4 THEN
                        SET result = num1 / num2;
                    ELSE
                        SET result = 0;
                    END IF;
                    RETURN result;
                End //
            DELIMITER ;

            # Addition
            - SELECT calculations(10, 5, 1); => 15 
            # Substraction
            - SELECT calculations(10, 5, 2); => 5
            # Multiplication 
            - SELECT calculations(10, 5, 3); => 50
            # Division
            - SELECT calculations(10, 5, 4); => 2


    2. CASE :  (Switch Case)
    - Syntax-
        DELIMITER //
            CREATE FUNCTION function_name(parameter datatype)
            RETURNS datatype(size)
            BEGIN 
                DECLARE variable_name datatype(size);
                CASE parameter
                    WHEN condition1 THEN
                        SET expression;
                    WHEN condition2 THEN
                        SET expression;
                    ELSE
                        SET expression;
                END CASE;
                RETURN return_variable;
            End //
        DELIMITER ;

        eg. [Simple Calculator Function using CASE]
            DELIMITER //
                CREATE FUNCTION calculations_using_case(num1 INT, num2 INT, op INT)
                # 1 = Addition, 
                # 2 = Substraction,
                # 3 = Multiplication,
                # 4 = Division
                RETURNS INT
                BEGIN
                    DECLARE result INT;
                    CASE op
                        WHEN 1 THEN
                            SET result = num1 + num2;
                        WHEN 2 THEN
                            SET result = num1 - num2;
                        WHEN 3 THEN
                            SET result = num1 * num2;
                        WHEN 4 THEN
                            SET result = num1 / num2;
                        ELSE
                            SET result = 0;
                    END CASE;
                    RETURN result;
                End //
            DELIMITER ;

            # Addition
            - SELECT calculations(10, 5, 1); => 15 
            # Substraction
            - SELECT calculations(10, 5, 2); => 5
            # Multiplication 
            - SELECT calculations(10, 5, 3); => 50
            # Division
            - SELECT calculations(10, 5, 4); => 2

========================================================================================================================================

## Day 9 : 20-06-2024

    3. LEAVE > LOOP :  (Loop)
    - Syntax-
        DELIMITER //
            CREATE FUNCTION function_name(parameter datatype)
            RETURNS datatype(size)
            BEGIN 
                DECLARE variable_name datatype(size);
                SET expression
                loop1_name: LOOP
                    SET expression
                    LEAVE loop1_name;
                END LOOP loop1_name;
                RETURN return_variable;
            End //
        DELIMITER ;

        eg. [Loop example]
            DELIMITER //
                CREATE FUNCTION myloop1(val int)
                RETURNS INT
                BEGIN
                    DECLARE result INT;
                    DECLARE i INT;
                    SET result = 0;
                    SET i = 1;
                    loop1: LOOP
                        SET result = result + i;
                        IF i < val THEN
                            SET i = i + 1;
                            ITERATE loop1;
                        END IF;
                    LEAVE loop1;       	
                    END LOOP loop1;
                RETURN result;
                END //
            DELIMITER ;

            - SELECT myloop1(10); => 55

    3. WHILE - DO :  (Loop)
    - Syntax-
        DELIMITER //
            CREATE FUNCTION function_name(parameter datatype)
            RETURNS datatype(size)
            BEGIN 
                DECLARE variable_name datatype(size);
                SET expression
                loop1_name: WHILE condition DO
                    SET expression
                END WHILE loop1_name;
                RETURN return_variable;
            End //
        DELIMITER ;

        eg. [WHILE - DO example]
            DELIMITER //
                CREATE FUNCTION myloop2(val int)
                RETURNS INT
                BEGIN
                    DECLARE result INT;
                    DECLARE i INT;
                    SET result = 0;
                    SET i = 1;
                    loop1: WHILE i <= val DO
                        SET result = result + i;
                        SET i = i + 1;
                    END WHILE loop1;
                RETURN result;
                END //
            DELIMITER ;

            - SELECT myloop2(10); => 55

========================================================================================================================================

## Day 10 : 21-06-2024

- PROCEDURE :- It is just like procedures in other programming language.
        - Header : It contains the name of the procedure and parameters or variables passed to the procedure.
        - Body : It contains
        - Ways to Pass Parameters **IN** & **OUT**.

    - Syntax:-
        DELIMITER //
            CREATE PROCEDURE procedure_name
            (parameters...)
            BEGIN
                ......statements
            END //
        DELIMITER ;
        - CALL procedure_name(parameter_values...)

    - eg: (Insert values into a Table via Procedure)
    ->  CREATE TABLE user_registration(id INT(10), name VARCHAR(50));
    ->  DELIMITER //
            CREATE PROCEDURE registration_form
            (IN uid INT, IN uname VARCHAR(50))
            BEGIN
                INSERT INTO user_registration values(uid, uname);   
            END //
        DELIMITER ;
    ->  CALL registration_form(101,'abc');
    ->  CALL registration_form(102,'def');
    ->  CALL registration_form(103,'ghi');
    ->  SELECT * FROM user_registration;
    ==> 
        |id    | name |
        |------|------|
        |101   | abc  |
        |------|------|
        |102   | def  |
        |------|------|
        |103   | ghi  |

    - eg: (DELETE data from a Table via Procedure)
    ->  DELIMITER //
        CREATE PROCEDURE delete_registration_form(IN uid INT)
        BEGIN
            DELETE FROM user_registration WHERE id = uid;   
        END //
        DELIMITER ;
    ->  CALL delete_registration_form(103);
    ->  SELECT * FROM user_registration;
    ==> 
        |id    | name |
        |------|------|
        |101   | abc  |
        |------|------|
        |102   | def  |

- TRIGGER :- They are stored programs which automatically gets executed or fired when some event occurs.
    - For Imposing security authorizations
    - BEFORE & AFTER (INSERT, UPDATE, DELETE)

    - Syntax:-
        DELIMITER //
        CREATE TRIGGER trigger_name BEFORE/AFTER INSERT/UPDATE/DELETE ON table_name
            BEGIN
                ..... statements
            END //
        DELIMITER ;
    
    - eg: (Trigger for employee Table When data is inserted add message to it)
    -> CREATE TABLE employee(eid INT(10), ename VARCHAR(50), msg VARCHAR(100));
    -> INSERT INTO employee(eid, ename) VALUES(101,"emp1"),(102, "emp2");

    -> CREATE TABLE money(amount, int(255));

    ->  DELIMITER //
            CREATE TRIGGER payment_message AFTER INSERT ON money
            FOR EACH ROW
            BEGIN
                UPDATE employee SET msg = "Salary Credited";
            END //
        DELIMITER ;

    ->  INSERT INTO money VALUES(50000),(20000);
    ->  SELECT * FROM money;
    ->  SELECT * FROM employee;

    =>  Money Table
       | amount |
       |--------|
       | 50000  |           
       |--------|
       |20000   |

    => Employee Table
       | eid  |   ename   |     msg            |
       |------|-----------|--------------------|
       | 101  |   emp1    | Salary Credited    |   
       |------|-----------|--------------------|
       | 102  |   emp2    | Salary Credited    |


- CURSORS :- A Cursor is a temporary memory that is allocated by the database server at the time of performing the Data Manipulation Language operations on a table, such as INSERT, UPDATE and DELETE etc.

    - Need of Cursors =
    - Cursor Limitation = 

    eg. (Step1)
        CREATE TABLE customers(
            id int(255),
            name varchar(50),
            address varchar(100),
            PRIMARY KEY(id)
        );
        
        (Step2)
        INSERT INTO customers VALUES(
            (1, 'John','Pune'),
            name varchar(50),
            address varchar(100),
            PRIMARY KEY(id)
        );

