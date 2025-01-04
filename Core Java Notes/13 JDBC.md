# JDBC : JAVA DataBase Connectivity

- JDBC stands for **Java Database Connectivity**. 
- JDBC is the Bridge between JAVA App and Your DataBase.
- JDBC is a Java API to connect and execute the query with the database, and processing the results. 
- It is a part of **JavaSE** (Java Standard Edition). 
- JDBC API uses **JDBC drivers** to connect with the database. 

## Types of JDBC 
- There are four types of JDBC drivers:
1. JDBC-ODBC Bridge Driver
2. Native Driver
3. Network Protocol Driver
4. Thin Driver

## Steps for Connecting Database 
1. Load Driver 
   1. If pgAdmin4 : Class.forName("org.postgresql.Driver");
   2. If SQL : Class.forName("com.sql.jdbc.driver")
```sh
Exception : **ClassNotFoundException** 
:- 
"____.jar" Download and Connect to 
(projectname > Build Path > Configure Build Path > Java Build path > Libraries > Classpath > Add External JARs > (Add the JAR file) )

PostgreSQL - postgresql.jar
MySQL - mysql-connector-java.jar
```
2. Connect to Database :
2.1. To PostGreSQL (pgAdmin):
```sh
import java.sql.*;

Class.forName("org.postgresql.Driver");

Connection con; // Connection Interface

con = DriverManager.getConnection("URL","USERNAME","PASSWORD");
//PostGreSQL URL : "jdbc:postgresql://localhost:5432/DATABASE_NAME"

System.out.println("DataBase Connected Successfully");
```
2.2. To XAMPP (SQL) :
```sh
import java.sql.*;

Class.forName("com.mysql.cj.jdbc.Driver");

Connection con;

con = DriverManager.getConnection("URL","USERNAME","PASSWORD");
//XAMPP SQL URL : "jdbc:mysql://localhost:3306/DATABASE_NAME"
// USERNAME : "root"
// PASSWORD : ""

System.out.println("DataBase Connected Successfully");
```

3. Write the Query
```sh
PreparedStatement ps = con.prepareStatement("SQL_QUERY");
```
4. Execute the Query
```sh
ps.executeUpdate(); //executeUpdate() - For Updating Data[Returns 0 or 1 - Success or Failed]
```
5. Done

### JDBC_xampp_sql_Connection Example
```sh

package day34_02Dec;
import java.sql.*;
import java.util.Scanner;

public class JDBC_xampp_sql_Connection {
	public static void main(String[] args) throws Exception {
		Class.forName("com.mysql.cj.jdbc.Driver");
		Connection con;
		con = DriverManager.getConnection(
				"jdbc:mysql://localhost:3306/jdbc_database_xampp",
				"root",
				"");

		System.out.println("DataBase Connected Successfully");
		
		System.out.println(" ------------ Manager Data Entry ------------ ");
		
		Scanner s1 = new Scanner(System.in);
		
		System.out.print("Number of managers : ");
		int num = s1.nextInt();
		
		String manager_name, manager_email, manager_password; 
		
		for(int i=1; i<=num ; i++) {
			System.out.println("Enter Data for Manager " + i);

			System.out.print("Manager Name : ");
			manager_name = s1.next();
			System.out.print("Manager Email : ");
			manager_email = s1.next();
			System.out.print("Manager password :");
			manager_password = s1.next();
			
						
			PreparedStatement ps = con.prepareStatement(
					"INSERT INTO Manager_Details (mname, memail, mpass) "
					+ "values ('"+ manager_name +"','"+ manager_email +"','"+ manager_password +"');");
			ps.executeUpdate();
			
			System.out.println("Record Saved for Manager " + i);
		}
		System.out.println("Thank You !!!");
		s1.close();
	}
}



Output :-
DataBase Connected Successfully
 ------------ Manager Data Entry ------------ 
Number of managers : 3
Enter Data for Manager 1
Manager Name : Mahesh
Manager Email : M@gmail.com
Manager password :M@123
Record Saved for Manager 1
Enter Data for Manager 2
Manager Name : Chetan
Manager Email : C@gmail.com
Manager password :C@123
Record Saved for Manager 2
Enter Data for Manager 3
Manager Name : Yash
Manager Email : Y@gmail.com
Manager password :Y@123
Record Saved for Manager 3
Thank You !!!

```

### JDBC_postgresql_Connection Example
```sh
package day34_02Dec;
import java.sql.*;
import java.util.Scanner;

public class JDBC_postgresql_Connection {
	public static void main(String[] args) throws Exception {
		Class.forName("org.postgresql.Driver");
		Connection con; // Connection Interface
		con = DriverManager.getConnection("jdbc:postgresql://localhost:5432/JDBC_Demo_DB",
				"postgres","Database@123");

		System.out.println("DataBase Connected Successfully");
		System.out.println(" ------------ Customer Data Entry ------------ ");
		Scanner s1 = new Scanner(System.in);
		System.out.print("Number of Customers : ");
		int num = s1.nextInt();
		int customer_id;
		String customer_name, customer_email, customer_password; 
		for(int i=1; i<=num ; i++) {
			System.out.println("Enter Data for Customer " + i);

			System.out.print("Customer ID : ");
			customer_id = s1.nextInt();
			System.out.print("Customer Name : ");
			customer_name = s1.next();
			System.out.print("Customer Email : ");
			customer_email = s1.next();
			System.out.print("Customer password :");
			customer_password = s1.next();
			
			PreparedStatement ps = con.prepareStatement(
					"INSERT INTO Customer_Details (cid, cname, cemail, cpass) "
					+ "values ('"+ customer_id +"','"+ customer_name +"','"+ 
							customer_email +"','"+ customer_password +"');");
			ps.executeUpdate();
			System.out.println("----------------------");
			System.out.println("Record Saved for Customer " + i + "\n =======================");
		}
		System.out.println(" ||------------ Thank You !!! ------------||");
		s1.close();
	}
}

Output :-
DataBase Connected Successfully
 ------------ Customer Data Entry ------------ 
Number of Customers : 3
Enter Data for Customer 1
Customer ID : 1001
Customer Name : ABC
Customer Email : A@gmail.com
Customer password :A@123
----------------------
Record Saved for Customer 1
 =======================
Enter Data for Customer 2
Customer ID : 1002
Customer Name : PQR
Customer Email : P@gmail.com
Customer password :P@123
----------------------
Record Saved for Customer 2
 =======================
Enter Data for Customer 3
Customer ID : 1003
Customer Name : MNO
Customer Email : M@gmail.com
Customer password :M@123
----------------------
Record Saved for Customer 3
 =======================
 ||------------ Thank You !!! ------------||
```


## JDBC Connection and Data Retrieval
- Fetch Record :
```sh
	PreparedStatement ps = con.prepareStatement("Select * from Users_Data ; ");
	
	ResultSet rs = ps.executeQuery(); //ResultSet Interface. //executeQuery() - For Fetchhing Data[Return a resultset]
```

- Example :-
```sh

```






