# Day 03 – Web Architecture (Security-Oriented)

## Objective of Day 3

The goal of Day 3 is to understand **how web applications are designed and communicate**, and how this design directly impacts **security vulnerabilities and defenses**.

Most modern cyber attacks target **web applications and APIs**, so a strong understanding of web architecture is mandatory for any cybersecurity role.

---

## 1. Why Web Architecture Is Important for Security

Today, cybersecurity work mainly involves:

* Web applications
* REST APIs
* Cloud-based services

Most real-world attacks occur at the **web layer**, including:

* SQL Injection
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Broken authentication and authorization
* API abuse

If you understand how a web application **communicates internally**, you can:

* Identify vulnerable points
* Explain attack flows clearly
* Design proper defenses

---

## 2. Client–Server Model

### Meaning

Web applications follow a **client–server architecture**.

* **Client** – Requests data (browser, mobile app, API client)
* **Server** – Processes requests and returns responses

---

### Examples of Clients

* Web browsers (Chrome, Firefox)
* Mobile applications
* Tools like Postman or curl

### Examples of Servers

* Web servers (Nginx, Apache)
* Application servers (Flask, Django, Node.js)
* Database servers

---

### Request–Response Flow

1. Client sends an HTTP request
2. Server receives and processes the request
3. Server sends an HTTP response
4. Client renders or consumes the response

---

### Security Perspective

* The **client is always untrusted**
* All validation must occur on the **server side**

**Interview-ready statement:**

> Never trust client input. Always validate on the server.

---

## 3. REST APIs

### What Is an API?

An API allows **two software systems to communicate**.

REST (Representational State Transfer) is the **most widely used API design style**.

---

### Core REST Principles

**Statelessness**

* Each request is independent
* No session data stored on the server by default

**Resource-Based Design**

* Everything is treated as a resource (users, orders, products)

**Standard HTTP Methods**

* GET, POST, PUT, DELETE

---

### REST API Examples

```
GET    /api/users
POST   /api/users
GET    /api/users/5
DELETE /api/users/5
```

---

### API Security Risks

* Broken authentication
* IDOR (Insecure Direct Object Reference)
* Missing rate limiting
* Excessive data exposure

---

## 4. HTTP Methods

### GET

* Retrieves data
* Should not modify server state

Example:

```
GET /profile
```

Security risk:

* Sensitive data exposed in URLs

---

### POST

* Sends data to the server
* Used for creation and login

Example:

```
POST /login
```

Security risk:

* Injection attacks if input is not validated

---

### PUT / PATCH

* Updates existing resources

---

### DELETE

* Removes resources

---

**Interview Tip:**

> Correct HTTP method usage is important for both functionality and security.

---

## 5. HTTP Status Codes

### 2xx – Success

* 200 OK
* 201 Created

### 3xx – Redirection

* 301 Moved Permanently
* 302 Found

### 4xx – Client Errors

* 400 Bad Request
* 401 Unauthorized
* 403 Forbidden
* 404 Not Found

### 5xx – Server Errors

* 500 Internal Server Error
* 502 Bad Gateway

---

### Security Insight

* Verbose error messages can leak sensitive information
* Errors should be handled securely

---

## 6. Cookies vs Headers

## 6.1 Cookies

### What Are Cookies?

Small pieces of data stored in the browser and sent automatically with requests.

Used for:

* Session management
* Login state

Example:

```
session_id=abc123
```

---

### Cookie Security Risks

* Session hijacking
* XSS stealing cookies

### Secure Cookie Flags

* HttpOnly
* Secure
* SameSite

---

## 6.2 Headers

### What Are Headers?

Metadata sent with HTTP requests and responses.

Common headers:

* Authorization
* Content-Type
* User-Agent

Example:

```
Authorization: Bearer <token>
```

---

### Security Advantage

* Tokens in headers reduce CSRF risk compared to cookies

---

## 7. Cookies vs Headers – Comparison

| Feature           | Cookies | Headers |
| ----------------- | ------- | ------- |
| Stored in browser | Yes     | No      |
| Auto sent         | Yes     | No      |
| Used for auth     | Yes     | Yes     |
| CSRF risk         | High    | Low     |

---

## 8. Hands-On: Browser DevTools

### Why This Matters

Inspecting requests helps understand:

* How applications behave
* Where vulnerabilities exist

---

### Steps (Chrome)

1. Open any website
2. Press **F12**
3. Go to **Network** tab
4. Refresh the page
5. Click on a request

---

### What to Observe

* Request URL
* HTTP method
* Headers
* Cookies
* Status code

**Interview-ready statement:**

> I regularly inspect HTTP requests using browser DevTools to analyze application behavior.

---

## 9. End-of-Day Interview Checklist

You should be able to explain:

* Client–server communication
* REST API principles
* HTTP methods and status codes
* Cookies vs headers
* How to inspect HTTP requests

---

## Day 03 Commit Message

```
Day 03: Web architecture fundamentals and security context
```

---

## Next Day

**Day 04 – Authentication Basics**

* Password storage
* Hashing vs encryption
* bcrypt / argon2
* Salting

**Hands-on:**

* Implement password hashing in Python
