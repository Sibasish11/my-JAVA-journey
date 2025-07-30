# JDBC Connectivity Steps

This guide explains how to connect a Java application to a database using JDBC (Java Database Connectivity). JDBC provides a standard API for database access in Java.


## 🧭 Step-by-Step JDBC Process

### ✅ Step 1: Import Required Packages

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;
```

You need to import the `java.sql` package classes to use JDBC.


### ✅ Step 2: Load and Register the JDBC Driver

```java
Class.forName("com.mysql.cj.jdbc.Driver");
```

This loads the JDBC driver into memory. Most modern JDBC drivers auto-register, so this step is optional for newer Java versions.


### ✅ Step 3: Establish a Connection

```java
String url = "jdbc:mysql://localhost:3306/mydatabase";
String user = "root";
String password = "password";

Connection con = DriverManager.getConnection(url, user, password);
```

- **URL format**: `jdbc:<db_type>://<host>:<port>/<db_name>`
- Replace with your actual DB credentials.


### ✅ Step 4: Create a Statement or PreparedStatement

```java
Statement stmt = con.createStatement();
```

Or use a `PreparedStatement` for dynamic/secure queries (more later).


### ✅ Step 5: Execute the Query

```java
ResultSet rs = stmt.executeQuery("SELECT * FROM students");

while (rs.next()) {
    System.out.println(rs.getInt("id") + " " + rs.getString("name"));
}
```

- Use `executeQuery()` for SELECT
- Use `executeUpdate()` for INSERT/UPDATE/DELETE


### ✅ Step 6: Close the Connection

```java
con.close();
```

Always close the connection to free resources.


## 🧪 Full Working Example

```java
import java.sql.*;

public class JDBCExample {
    public static void main(String[] args) {
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            Connection con = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306/mydatabase", "root", "password");

            Statement stmt = con.createStatement();
            ResultSet rs = stmt.executeQuery("SELECT * FROM students");

            while (rs.next()) {
                System.out.println(rs.getInt(1) + " " + rs.getString(2));
            }

            con.close();
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```


## ✅ Summary

| Step | Action                          | Method/Class                      |
|------|----------------------------------|-----------------------------------|
| 1    | Import JDBC packages             | `java.sql.*`                      |
| 2    | Load JDBC driver                 | `Class.forName()`                 |
| 3    | Establish DB connection          | `DriverManager.getConnection()`   |
| 4    | Create SQL statement             | `Statement / PreparedStatement`   |
| 5    | Execute SQL and process results  | `executeQuery() / executeUpdate()`|
| 6    | Close the connection             | `Connection.close()`              |

