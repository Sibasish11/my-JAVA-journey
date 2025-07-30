# JDBC Statements in Java

JDBC provides three core types of statements to execute SQL commands:

- **Statement**
- **PreparedStatement**
- **CallableStatement**

Each serves a different purpose based on the complexity and security needs of the query.


## 🔹 1. Statement

Used for executing static SQL queries without parameters.

```java
Statement stmt = con.createStatement();
ResultSet rs = stmt.executeQuery("SELECT * FROM employee");
```

- Not precompiled
- Susceptible to SQL injection
- Suitable for one-time, simple queries


## 🔹 2. PreparedStatement

Used for dynamic queries with input parameters. Precompiled by the database engine.

```java
PreparedStatement pstmt = con.prepareStatement("SELECT * FROM employee WHERE id = ?");
pstmt.setInt(1, 101);
ResultSet rs = pstmt.executeQuery();
```

- Prevents SQL injection
- Better performance for repeated use
- Supports input parameter binding


## 🔹 3. CallableStatement

Used to execute **stored procedures** in the database.

```java
CallableStatement cstmt = con.prepareCall("{call getEmployee(?)}");
cstmt.setInt(1, 101);
ResultSet rs = cstmt.executeQuery();
```

- Invokes stored procedures
- Can return multiple result sets and output parameters
- Used in enterprise-level applications


## 🧾 Comparison Table

| Feature                | Statement       | PreparedStatement    | CallableStatement        |
|------------------------|-----------------|----------------------|---------------------------|
| Dynamic Input Support  | ❌ No           | ✅ Yes               | ✅ Yes                    |
| Precompiled            | ❌ No           | ✅ Yes               | ✅ Yes                    |
| SQL Injection Safe     | ❌ No           | ✅ Yes               | ✅ Yes                    |
| Use Case               | Simple Queries  | Repetitive Queries   | Stored Procedures         |


## ✅ When to Use?

- `Statement`: For static, one-time queries.
- `PreparedStatement`: For queries with input parameters, security, and performance.
- `CallableStatement`: When working with stored procedures in DB.

