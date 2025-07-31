# 🌐 Servlet Introduction

In the world of web development with Java, **Servlets** play a foundational role. Servlets are Java programs that run on a **Java-enabled web server** or **application server** and handle **client requests** (typically HTTP) and generate **dynamic web content** (typically HTML).


## 🚀 What is a Servlet?

A **Servlet** is a Java class that extends the capabilities of servers that host applications accessed by means of a request-response programming model. It is part of the **Java EE (Jakarta EE)** specification and forms the backbone of Java web development.

Servlets are managed by a **Servlet container** (like Apache Tomcat), which handles the servlet lifecycle and provides necessary infrastructure.


## 📋 Key Characteristics

- Written in **Java**
- Resides on the **server-side**
- Capable of generating **dynamic content**
- Follows a **request-response** model (usually HTTP)
- Can interact with databases, services, and APIs


## 🔁 Servlet Life Cycle

The servlet lifecycle consists of **3 main phases**:

```
               +------------------+
               |   Loaded by the  |
               |  ServletContainer|
               +--------+---------+
                        |
                    init()  <-- Called once
                        |
                   service() <-- Called per request
                        |
                    destroy() <-- Called once at end
```

### 1. `init()`
- Called only once when the servlet is instantiated.
- Used to initialize resources like database connections.

### 2. `service()`
- Called every time the servlet receives a request.
- Delegates to `doGet()`, `doPost()`, etc., depending on the HTTP method.

### 3. `destroy()`
- Called only once when the servlet is being removed from memory.
- Used to release any resources.


## 🔄 Comparison: Servlet vs CGI

| Feature            | CGI                    | Servlet                 |
|--------------------|-------------------------|--------------------------|
| Language           | Typically Perl/C/C++     | Java                     |
| Execution          | New process per request | Single instance, multithreaded |
| Performance        | Slower                  | Faster                   |
| Portability        | Limited                 | Platform-independent     |
| Security           | Basic                   | Strong security model    |


## ✅ Advantages of Servlets

- **Performance:** Efficient request handling using threads.
- **Portability:** Runs on any platform with a compatible servlet container.
- **Scalability:** Can handle thousands of requests using multithreading.
- **Integration:** Can be integrated with JDBC, EJB, JSP, etc.
- **Security:** Inherits Java's robust security features.


## 🧠 Summary

Servlets are:
- Powerful Java-based server-side components
- Used to build scalable, secure, and maintainable web applications
- Preferred over older technologies like CGI due to performance and manageability




