# JSP Directives

JSP Directives provide global information that helps the JSP container in translating and processing the JSP page. These are placed at the top of the page and do **not produce any output** directly.


## 📌 Types of Directives in JSP

JSP supports **three main types of directives**:

| Directive     | Purpose                                         |
|---------------|-------------------------------------------------|
| `page`        | Defines page-level attributes (e.g., encoding, language). |
| `include`     | Includes a static file during translation phase. |
| `taglib`      | Declares use of custom tags using a tag library. |


## 🧩 1. Page Directive

Used to define attributes that apply to the entire JSP page.

**Syntax:**
```jsp
<%@ page attribute="value" %>
```
### Common Attributes:

| Attribute     | Description                                 |
| ------------- | ------------------------------------------- |
| `language`    | Programming language used (default: `java`) |
| `contentType` | MIME type of response (e.g., `text/html`)   |
| `import`      | Java class imports (like in Java classes)   |
| `errorPage`   | Redirect page if error occurs               |
| `isErrorPage` | Whether this JSP is an error-handling page  |

## 🧩 2. Include Directive
### Includes contents of another static file at translation time.

###### Syntax:
```java
<%@ include file="header.jsp" %>
```
- The included file is merged during compilation.
- Good for common layouts like headers, footers, etc.

## 🧩 3. Taglib Directive
### Used to define and use custom tags via tag libraries (like JSTL).

## Syntax:

```java
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
```

##### uri: Identifies the tag library.

##### prefix: Used to access tags.

### Example (JSTL):
```java
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<c:if test="${user.loggedIn}">
  <p>Welcome, ${user.name}!</p>
</c:if>
```

#### ✅ Summary Table:

| Directive | Use Case                          | Syntax Example                         |
| --------- | --------------------------------- | -------------------------------------- |
| `page`    | Set page properties like encoding | `<%@ page contentType="text/html" %>`  |
| `include` | Include static content            | `<%@ include file="footer.jsp" %>`     |
| `taglib`  | Use custom/JSTL tags              | `<%@ taglib uri="..." prefix="..." %>` |


