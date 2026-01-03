# WEEK 1 – DAY 6

## SESSION vs TOKEN AUTHENTICATION

*(Ultra-detailed, beginner-friendly, security-correct notes)*

---

## 1. Why Authentication State Management Matters

After a user logs in, the system must remember:

> "This user is authenticated"

This is called **authentication state management**.

Two common approaches:

1. **Session-based authentication**
2. **Token-based authentication (JWT)**

---

## 2. Cookies (Foundation Concept)

### What Is a Cookie?

A **cookie** is a small piece of data stored in the **browser**, sent automatically with every request to the server.

Example:

```
session_id=abc123xyz
```

### What Cookies Are Used For

* Session tracking
* Authentication
* Preferences

### Security Risks of Cookies

* XSS can steal cookies
* CSRF attacks
* Session hijacking

### Secure Cookie Flags (Interview Must-Know)

* **HttpOnly** – JavaScript cannot access the cookie
* **Secure** – Sent only over HTTPS
* **SameSite** – Mitigates CSRF

---

## 3. Session-Based Authentication

### What Is a Session?

A **session** stores authentication state on the **server**.

Flow:

* Browser stores a **session ID** in a cookie
* Server stores session data

### Session Authentication Flow

1. User logs in
2. Server creates a session
3. Server stores session data
4. Session ID sent to browser as cookie
5. Browser sends cookie with every request
6. Server validates session ID

### Diagram

```
Browser ──(session_id)──> Server
          <── session data stored on server
```

### Advantages

* Simple to implement
* Easy logout / invalidation
* Secure for traditional web apps

### Disadvantages

* Server-side state
* Harder to scale
* Load balancer issues without sticky sessions

**Interview line:**

> Sessions are stateful and stored on the server, which complicates scaling.

---

## 4. Token-Based Authentication (JWT)

### What Is a Token?

A **token** proves authentication without server-side session storage.

### What Is JWT?

**JSON Web Token** is a self-contained authentication token.

Structure:

```
HEADER.PAYLOAD.SIGNATURE
```

---

## 5. JWT Structure

### Header

Defines token type and algorithm.

```json
{
  "alg": "HS256",
  "typ": "JWT"
}
```

### Payload

Contains **claims** (user identity, role, expiry).

```json
{
  "user_id": 101,
  "role": "admin",
  "exp": 1710000000
}
```

⚠ Payload is **Base64 encoded, not encrypted**.

### Signature

Ensures token integrity and authenticity using a secret key.

**Interview line:**

> JWTs are signed, not encrypted.

---

## 6. Access Tokens vs Refresh Tokens

### Access Token

* Short-lived (5–15 minutes)
* Sent with every request

```
Authorization: Bearer <access_token>
```

### Refresh Token

* Long-lived
* Used to obtain new access tokens

### Why Two Tokens?

Limits damage if an access token is compromised.

---

## 7. Session vs JWT Comparison

| Feature          | Session | JWT    |
| ---------------- | ------- | ------ |
| Stored on server | Yes     | No     |
| Stateless        | No      | Yes    |
| Scalability      | Harder  | Easier |
| Logout           | Easy    | Hard   |
| API usage        | Rare    | Common |

---

## 8. Security Risks in Token Authentication

* Token leakage
* Storing JWTs in localStorage
* No expiration
* Weak secret keys

---

## 9. Hands-On: JWT Authentication in Flask

### Install Dependencies

```bash
pip install flask flask-jwt-extended
```

### Basic Setup

```python
from flask import Flask, jsonify, request
from flask_jwt_extended import (
    JWTManager, create_access_token,
    create_refresh_token, jwt_required,
    get_jwt_identity
)

app = Flask(__name__)
app.config["JWT_SECRET_KEY"] = "super-secret-key"
jwt = JWTManager(app)
```

### Mock User Database

```python
users = {
    "kavya": {"password": "password123", "role": "admin"},
    "arjun": {"password": "userpass", "role": "user"}
}
```

### Login Endpoint

```python
@app.route("/login", methods=["POST"])
def login():
    data = request.get_json()
    username = data.get("username")
    password = data.get("password")

    user = users.get(username)
    if not user or user["password"] != password:
        return jsonify({"error": "Invalid credentials"}), 401

    return jsonify({
        "access_token": create_access_token(identity=username),
        "refresh_token": create_refresh_token(identity=username)
    })
```

### Protected Route

```python
@app.route("/dashboard")
@jwt_required()
def dashboard():
    user = get_jwt_identity()
    return jsonify({"message": f"Welcome {user}"})
```

### Refresh Endpoint

```python
@app.route("/refresh", methods=["POST"])
@jwt_required(refresh=True)
def refresh():
    user = get_jwt_identity()
    return jsonify({"access_token": create_access_token(identity=user)})
```

---

## 10. Real-World Usage

* Access token stored in memory
* Refresh token stored securely
* Tokens sent via Authorization header

---

## 11. End-of-Day Interview Checklist

You should confidently explain:

* Cookies and security flags
* Session authentication flow
* JWT structure
* Access vs refresh tokens
* Session vs JWT trade-offs
* JWT authentication in Flask

---

## Day 7 Preview

**Weekly Revision + Interview Thinking**

* Revise Days 1–6

