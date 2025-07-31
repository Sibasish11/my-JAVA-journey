# 🔄 Handling doGet() and doPost() in Servlets

When building Java web applications with Servlets, two primary methods are used to handle HTTP requests:

- `doGet()` → Handles **GET** requests (typically when the user types a URL or clicks a link)
- `doPost()` → Handles **POST** requests (usually from form submissions)


## 🧠 Key Differences

| Feature           | `doGet()`                         | `doPost()`                        |
|------------------|-----------------------------------|-----------------------------------|
| Data visibility   | Data sent in URL (query string)   | Data sent in body (not visible)   |
| Size limit        | Limited (URL length restriction)  | Larger data allowed               |
| Use case          | Reading data (search, view pages) | Submitting data (forms, uploads)  |
| Caching           | Can be cached by browser          | Not cached                        |


## 🧪 Example: Using both `doGet()` and `doPost()`

```java
@WebServlet("/login")
public class LoginServlet extends HttpServlet {

    // Handles GET requests
    protected void doGet(HttpServletRequest req, HttpServletResponse res)
        throws ServletException, IOException {
        res.setContentType("text/html");
        PrintWriter out = res.getWriter();
        out.println("<form method='post' action='login'>");
        out.println("Username: <input type='text' name='username'><br>");
        out.println("Password: <input type='password' name='password'><br>");
        out.println("<input type='submit' value='Login'>");
        out.println("</form>");
    }

    // Handles POST requests
    protected void doPost(HttpServletRequest req, HttpServletResponse res)
        throws ServletException, IOException {
        String user = req.getParameter("username");
        String pass = req.getParameter("password");

        res.setContentType("text/html");
        PrintWriter out = res.getWriter();

        if("admin".equals(user) && "1234".equals(pass)) {
            out.println("<h3>Welcome, " + user + "</h3>");
        } else {
            out.println("<h3>Invalid Credentials</h3>");
        }
    }
}
```


## 🌐 Form Behavior in HTML

```html
<form method="post" action="login">
  <input type="text" name="username">
  <input type="password" name="password">
  <input type="submit" value="Login">
</form>
```

- `method="get"` → sends data in URL
- `method="post"` → sends data in body



## 🔍 Quick Recap

- `doGet()` is used for retrieving/displaying data.
- `doPost()` is used for processing/submitting sensitive data.
- Always use `doPost()` for forms with passwords or personal data.
- It's a good practice to override both methods and redirect to appropriate logic.



