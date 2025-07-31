# 📝 Servlet Form Handling

One of the core functionalities of servlets is processing form data sent from HTML pages. When a user submits a form, the data can be handled using either the `doGet()` or `doPost()` methods.

## 📄 HTML Form Example

```html
<form action="formHandler" method="post">
  Name: <input type="text" name="username" /><br/>
  Email: <input type="text" name="email" /><br/>
  <input type="submit" value="Submit" />
</form>
```

- `action`: The URL pattern of the servlet.
- `method`: Either `GET` or `POST`.


## ⚙️ Servlet Code to Handle Form

```java
@WebServlet("/formHandler")
public class FormHandlerServlet extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
        
        String name = request.getParameter("username");
        String email = request.getParameter("email");

        response.setContentType("text/html");
        PrintWriter out = response.getWriter();

        out.println("<h2>Form Submission Received</h2>");
        out.println("<p>Name: " + name + "</p>");
        out.println("<p>Email: " + email + "</p>");
    }
}
```


## 📥 How `getParameter()` Works

- `request.getParameter("fieldName")` fetches the value of a specific form field.
- Field names in HTML form (`name="username"`) must match the parameter names in servlet.


## 🔐 GET vs POST in Form Handling

| Method | Characteristics                                 |
|--------|-------------------------------------------------|
| GET    | Form data visible in URL, suitable for searches |
| POST   | Secure, large data capacity, used for sensitive forms |


## 🚫 Common Mistakes

- Not matching input field `name` with `getParameter()`.
- Forgetting to set `Content-Type` in the response.
- Mixing `doGet()` and `doPost()` incorrectly.


## ✅ Output Example

When the form is submitted, the browser will display:

```html
<h2>Form Submission Received</h2>
<p>Name: John Doe</p>
<p>Email: john@example.com</p>
```

## 📌 Pro Tips

- Always validate data before processing or storing.
- Use `doPost()` for form submission to prevent data exposure in URLs.
- Use meaningful field `name` attributes in the HTML form.


