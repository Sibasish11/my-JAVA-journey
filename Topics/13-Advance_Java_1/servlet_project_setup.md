# 🚀 Servlet Project Setup Guide

Before you can run or deploy servlets, you must properly set up your Java servlet project. This includes configuring an IDE like Eclipse/IntelliJ, setting up a servlet container (e.g., Apache Tomcat), and writing deployment descriptors.


## 🧰 Tools You’ll Need

| Tool               | Purpose                          |
|--------------------|----------------------------------|
| **JDK**            | Java Development Kit             |
| **Apache Tomcat**  | Servlet container / web server   |
| **IDE**            | Eclipse / IntelliJ / VS Code     |
| **Web Browser**    | To access the servlet            |


## 🏗️ Project Structure

```
MyServletProject/
├── WEB-INF/
│   ├── web.xml
│   └── classes/
│       └── MyServlet.class
├── index.html
```



## 🔧 Steps to Setup Servlet Project in Eclipse

### 1. Create Dynamic Web Project
- Open Eclipse → File → New → **Dynamic Web Project**
- Name it: `MyServletProject`
- Target Runtime: Choose **Apache Tomcat**

### 2. Write Servlet Code
- Inside `src`, create your servlet class:

```java
@WebServlet("/hello")
public class MyServlet extends HttpServlet {
    protected void doGet(HttpServletRequest req, HttpServletResponse res)
        throws ServletException, IOException {
        res.setContentType("text/html");
        PrintWriter out = res.getWriter();
        out.print("<h3>Hello from Servlet</h3>");
    }
}
```

OR

Manually configure servlet mapping in `web.xml`:

```xml
<web-app>
    <servlet>
        <servlet-name>MyServlet</servlet-name>
        <servlet-class>MyServlet</servlet-class>
    </servlet>
    <servlet-mapping>
        <servlet-name>MyServlet</servlet-name>
        <url-pattern>/hello</url-pattern>
    </servlet-mapping>
</web-app>
```

### 3. Run on Server
- Right-click project → Run As → Run on Server
- Output opens at: `http://localhost:8080/MyServletProject/hello`


## 📝 Notes

- `WEB-INF/web.xml` is the deployment descriptor.
- If you're using `@WebServlet` annotation, `web.xml` is optional (Servlet 3.0+).
- Ensure your servlet is compiled and placed inside `/WEB-INF/classes`.


## 🔍 Common Errors

| Error                              | Reason                                |
|-----------------------------------|----------------------------------------|
| 404 Not Found                     | Servlet URL mapping incorrect          |
| HTTP 500 - Class Not Found        | Class file not compiled or mislocated |
| Server not starting               | Tomcat not properly configured         |


## ✅ Final Checklist

- [x] Tomcat configured in IDE  
- [x] Servlet extends `HttpServlet`  
- [x] `doGet()` or `doPost()` overridden  
- [x] URL mapping done in `web.xml` or annotation  
- [x] Project deployed and running on server  


