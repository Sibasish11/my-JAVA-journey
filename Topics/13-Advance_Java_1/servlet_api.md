# 📘 Servlet API Overview

Java Servlets are built on a rich and well-structured **Servlet API**, which provides all the classes and interfaces needed to handle HTTP requests and responses, manage configuration, and control the servlet lifecycle.

Understanding the Servlet API is essential to developing robust web applications using Java.


## 🧩 Servlet API Packages

The core packages used in servlet programming are:

### 1. `javax.servlet.*` (or `jakarta.servlet.*` in newer versions)
Contains general classes and interfaces for all servlets.

### 2. `javax.servlet.http.*` (or `jakarta.servlet.http.*`)
Contains classes specific to **HTTP** protocol, like `HttpServlet`, `HttpServletRequest`, and `HttpServletResponse`.


## 🧱 Key Interfaces and Classes

| Component                  | Description |
|---------------------------|-------------|
| `Servlet` (interface)      | Defines lifecycle methods: `init()`, `service()`, `destroy()` |
| `GenericServlet` (class)   | Implements `Servlet` and provides skeletal implementation |
| `HttpServlet` (class)      | Extends `GenericServlet`, adds HTTP-specific methods like `doGet()`, `doPost()` |
| `ServletRequest`           | Provides request information like parameters, headers, etc. |
| `ServletResponse`          | Used to generate a response to the client |
| `HttpServletRequest`       | Extends `ServletRequest` for HTTP-specific features |
| `HttpServletResponse`      | Extends `ServletResponse` for HTTP-specific features |
| `ServletConfig`            | Provides config data to a servlet (like init parameters) |
| `ServletContext`           | Provides information about the web application as a whole |


## 🔁 Servlet API Hierarchy (Simplified)

```
                        +----------------------+
                        |      Servlet         | (Interface)
                        +----------------------+
                                   |
                         +------------------+
                         | GenericServlet   | (Abstract Class)
                         +------------------+
                                   |
                          +-----------------+
                          |   HttpServlet   | (Class)
                          +-----------------+
```


## 🧪 Example: Basic `HttpServlet` Skeleton

```java
import javax.servlet.*;
import javax.servlet.http.*;
import java.io.*;

public class MyServlet extends HttpServlet {
    public void doGet(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
        
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        out.println("<h2>Hello from Servlet!</h2>");
    }
}
```


## 🌐 Deployment Descriptor (`web.xml`) Sample

Servlets can be mapped using `web.xml`:

```xml
<servlet>
    <servlet-name>MyServlet</servlet-name>
    <servlet-class>MyServlet</servlet-class>
</servlet>

<servlet-mapping>
    <servlet-name>MyServlet</servlet-name>
    <url-pattern>/hello</url-pattern>
</servlet-mapping>
```


## 📌 Summary

- The **Servlet API** provides the necessary tools to write and manage Java servlets.
- Key components include `HttpServlet`, `HttpServletRequest`, and `HttpServletResponse`.
- Understanding these classes/interfaces is crucial for handling web requests and responses efficiently.




