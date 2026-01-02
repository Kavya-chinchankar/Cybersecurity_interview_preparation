# WEEK 1 – DAY 5

## AUTHORIZATION MODELS

*(Very Detailed, Easy-to-Explain, Interview + Practical Ready)*

---

## 1. Authentication vs Authorization (Clear the Confusion)

### Authentication

Answers: **Who are you?**
Example: Login with username & password

### Authorization

Answers: **What are you allowed to do?**
Example: Can you access the admin panel?

**Rule:** Authentication happens first, authorization comes next.

---

## 2. Why Authorization Is Critical

Even with strong authentication:

* Normal users must not access admin APIs
* Students must not modify marks
* Employees must not access HR salary data

Weak authorization leads to **privilege escalation** and **broken access control**.

---

## 3. RBAC – Role-Based Access Control

### What Is RBAC?

Access is granted based on a user’s **role**.

```
User → Role → Permissions
```

### Example Roles

Admin, Manager, User

### Pros and Cons

* Simple and scalable
* Can become rigid with too many roles

**Interview line:** RBAC is simple but less flexible for complex conditions.

---

## 4. ABAC – Attribute-Based Access Control

Access decisions are based on **attributes**:

* User attributes (department)
* Resource attributes (owner)
* Environment attributes (time, location)

More flexible but complex to implement.

---

## 5. ACL – Access Control Lists

Permissions attached directly to a **resource**.

Used in file systems, cloud storage, and networking devices.

---

## 6. Least Privilege Principle

Users should have **only the minimum permissions required**.

**Interview line:** Least privilege minimizes the blast radius of attacks.

---

## 7. Common Authorization Attacks

* Privilege escalation
* IDOR
* Broken access control (OWASP Top 10)

---

## 8. Hands-On: RBAC in Flask

```python
from flask import Flask, jsonify
from functools import wraps

app = Flask(__name__)

users = {
    "kavya": {"role": "admin"},
    "arjun": {"role": "user"}
}

def role_required(required_role):
    def decorator(f):
        @wraps(f)
        def wrapper(username, *args, **kwargs):
            user = users.get(username)
            if not user:
                return jsonify({"error": "User not found"}), 404
            if user["role"] != required_role:
                return jsonify({"error": "Access denied"}), 403
            return f(username, *args, **kwargs)
        return wrapper
    return decorator

@app.route("/admin/<username>")
@role_required("admin")
def admin_dashboard(username):
    return jsonify({"message": "Welcome Admin"})
```

