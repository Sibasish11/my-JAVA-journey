# JDBC CRUD Operations in Java

CRUD stands for:
- **Create** (Insert)
- **Read** (Select)
- **Update**
- **Delete**

This guide provides a full implementation of CRUD operations using JDBC on a sample `Student` table.


## 🗄️ Table Structure: `Student`

```sql
CREATE TABLE Student (
  id INT PRIMARY KEY,
  name VARCHAR(50),
  age INT
);
```


## ✅ 1. Insert (Create)

```java
PreparedStatement pstmt = con.prepareStatement("INSERT INTO Student VALUES (?, ?, ?)");
pstmt.setInt(1, 101);
pstmt.setString(2, "Ravi");
pstmt.setInt(3, 20);
pstmt.executeUpdate();
System.out.println("Inserted successfully");
```


## ✅ 2. Select (Read)

```java
Statement stmt = con.createStatement();
ResultSet rs = stmt.executeQuery("SELECT * FROM Student");
while (rs.next()) {
    System.out.println(rs.getInt(1) + " " + rs.getString(2) + " " + rs.getInt(3));
}
```


## ✅ 3. Update

```java
PreparedStatement pstmt = con.prepareStatement("UPDATE Student SET age = ? WHERE id = ?");
pstmt.setInt(1, 21);
pstmt.setInt(2, 101);
pstmt.executeUpdate();
System.out.println("Updated successfully");
```


## ✅ 4. Delete

```java
PreparedStatement pstmt = con.prepareStatement("DELETE FROM Student WHERE id = ?");
pstmt.setInt(1, 101);
pstmt.executeUpdate();
System.out.println("Deleted successfully");
```


## 🚀 Full CRUD Flow Summary

1. Establish DB connection.
2. Use `PreparedStatement` for each operation.
3. Execute and handle exceptions.


## 📌 Best Practices

- Always close `ResultSet`, `Statement`, and `Connection`.
- Use try-with-resources.
- Use `PreparedStatement` over `Statement` for input safety.

