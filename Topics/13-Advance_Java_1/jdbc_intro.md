# JDBC Basics

**JDBC (Java Database Connectivity)** is an API in Java that enables Java applications to interact with a wide range of databases. It acts as a bridge between Java programs and relational database systems like MySQL, Oracle, PostgreSQL, etc.


## 🔍 What is JDBC?

JDBC is a standard Java API that facilitates:

- Establishing a connection with the database
- Sending SQL queries and updates
- Retrieving and processing the results
- Managing database resources

It belongs to the `java.sql` and `javax.sql` packages.


## 🧩 Why JDBC?

| Benefit                    | Description                                                                 |
|---------------------------|-----------------------------------------------------------------------------|
| Vendor Independence        | Connects with any relational DB that has a JDBC driver                      |
| Simple Integration         | Makes it easy to write SQL within Java programs                             |
| Secure and Efficient       | Provides connection pooling, prepared statements, and transaction support   |


## 🛠️ JDBC Architecture

```
Java Application
       |
       V
 JDBC API (java.sql)
       |
       V
 JDBC Driver Manager
       |
       V
JDBC Driver (Vendor-specific)
       |
       V
  Database (e.g., MySQL)
```


## 📦 Key JDBC Interfaces

| Interface            | Description                                                           |
|----------------------|-----------------------------------------------------------------------|
| `DriverManager`      | Manages the list of database drivers                                  |
| `Connection`         | Represents a session with a specific database                         |
| `Statement`          | Used to execute SQL queries                                           |
| `PreparedStatement`  | Precompiled SQL statements with parameter placeholders                |
| `ResultSet`          | Holds the data retrieved from the database                           |


## ✅ Steps to Use JDBC

```java
import java.sql.*;

public class DBExample {
    public static void main(String[] args) throws Exception {
        // 1. Load JDBC Driver
        Class.forName("com.mysql.cj.jdbc.Driver");

        // 2. Establish Connection
        Connection conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/mydb", "user", "password");

        // 3. Create Statement
        Statement stmt = conn.createStatement();

        // 4. Execute Query
        ResultSet rs = stmt.executeQuery("SELECT * FROM students");

        // 5. Process Results
        while(rs.next()) {
            System.out.println(rs.getInt(1) + " " + rs.getString(2));
        }

        // 6. Close Connections
        rs.close();
        stmt.close();
        conn.close();
    }
}
```


## 📝 Summary

- JDBC is essential for connecting Java apps with relational databases.
- It includes steps like loading driver, connecting, querying, and closing resources.
- JDBC simplifies database operations in backend applications.

