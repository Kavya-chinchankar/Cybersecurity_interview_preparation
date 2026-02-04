# WEEK 2 – DAY 9

## BROKEN AUTHENTICATION (OWASP TOP 10)

---

## 1. WHAT IS BROKEN AUTHENTICATION?

### Simple Definition

> Broken Authentication occurs when authentication mechanisms are **incorrectly designed or implemented**, allowing attackers to **compromise user identities**.

This is **not about one bug** — it is about **system-level weakness** in how identities are managed.

---

## 2. WHY BROKEN AUTHENTICATION IS SO COMMON

Authentication systems fail because:

* Developers focus on **functionality over abuse scenarios**
* Attackers reuse leaked credentials
* Systems trust tokens/sessions too much
* Rate limiting and monitoring are missing

---

## 3. CREDENTIAL STUFFING

### What Is Credential Stuffing?

Attackers take:

* Email/password lists from previous breaches
* Automatically try them on other websites

This works because **users reuse passwords**.

---

### How Attack Happens

1. Attacker gets breach dump
2. Uses bot or script
3. Tries thousands of logins per minute
4. Successful logins are sold or abused

---

### Why Traditional Login Fails

* Correct credentials look “legitimate”
* No brute-force pattern per account
* Same IP may rotate

---

## 4. WEAK PASSWORD POLICIES

### Secure Password Policy (Interview-Ready)

* Minimum 12 characters
* Block common passwords
* Rate-limit attempts
* Hash with bcrypt / Argon2
* Optional MFA

---

## 5. SESSION FIXATION

### What Is Session Fixation?

> An attacker forces a user to use a **known session ID**, then hijacks the session after login.

---

### Prevention

* Regenerate session ID on login
* Secure cookies (HttpOnly, Secure)

---

## 6. HANDS-ON: BRUTE FORCE SIMULATION

```python
passwords = ["123456", "password", "admin", "qwerty"]

for pwd in passwords:
    response = login("admin", pwd)
    if response.success:
        print("Password found:", pwd)
```

---

## 7. RATE LIMITING DEFENSE (FLASK)

```python
from flask_limiter import Limiter
from flask_limiter.util import get_remote_address

limiter = Limiter(
    get_remote_address,
    app=app,
    default_limits=["5 per minute"]
)
```

---

## 8. INTERVIEW QUESTIONS

**Brute force vs credential stuffing?**
Brute force guesses; credential stuffing reuses real credentials.

**Is rate limiting enough?**
No — combine with MFA, strong passwords, and monitoring.

---

## 9. DAY-9 SELF-CHECK

You are ready if you can:

* Explain credential stuffing
* Simulate brute force logic
* Implement rate limiting
* Explain session fixation

---

## NEXT: DAY 10 – BROKEN ACCESS CONTROL
 