# Introduction to JSP (JavaServer Pages)

JavaServer Pages (JSP) is a technology used for developing web pages that support dynamic content. It is a server-side technology that allows embedding Java code into HTML pages using special JSP tags, most commonly starting with `<%` and ending with `%>`.

JSP is part of the Java EE platform and offers a simpler way to create web-based applications compared to servlets alone.


## Why Use JSP?

- **Ease of use**: Similar to HTML with embedded Java logic.
- **Separation of concerns**: Allows separating the business logic from presentation.
- **Reusable components**: Can use JavaBeans, tag libraries, and custom tags.


## JSP Lifecycle

The JSP page goes through the following phases during its lifecycle:

1. **Translation** – The JSP is converted into a servlet.
2. **Compilation** – The servlet is compiled into bytecode.
3. **Initialization** – The `jspInit()` method is called.
4. **Execution** – The `_jspService()` method is called to process requests.
5. **Destruction** – The `jspDestroy()` method is called when the JSP is taken out of service.


## JSP vs Servlet

| Feature       | JSP                             | Servlet                         |
|---------------|----------------------------------|----------------------------------|
| Syntax        | HTML with Java code              | Java code only                  |
| Best for      | Presentation layer               | Business logic layer            |
| Complexity    | Easier to write and maintain     | More complex to write directly  |
| Compilation   | Compiled to servlets internally  | Already written as Java class   |


## Example: Basic JSP Page

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" %>
<html>
<head><title>Welcome</title></head>
<body>
    <h2>Hello from JSP!</h2>
    <p>Current time: <%= new java.util.Date() %></p>
</body>
</html>
