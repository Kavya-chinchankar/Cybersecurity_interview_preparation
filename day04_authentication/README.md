# WEEK 1 – DAY 4

## AUTHENTICATION BASICS

*(Very Detailed, Easy-to-Explain, Interview-Ready)*

---

## 1. What Is Authentication? (Start From Zero)

**Authentication** answers one question:

> “Who are you?”

It verifies the **identity** of a user before allowing access.

Examples:

* Login with username & password
* OTP-based login
* Biometrics (fingerprint, face ID)

Authentication is the **first gate** of security.
If authentication fails, **everything behind it is exposed**.

---

## 2. Why Password Storage Is CRITICAL

A very common beginner mistake is:

> “Just store passwords in the database.”

❌ This is **extremely dangerous**.

### Why?

If the database is compromised:

* Attackers obtain all user passwords
* Users often reuse passwords across sites
* One breach leads to multiple account takeovers

**Golden Rule:**

> “Passwords must never be stored in plain text.”

---

## 3. Plain Text Passwords (WHAT NOT TO DO)

### Example (Bad Practice)

```
username | password
kavya    | mypassword123
```

### Why This Is Dangerous

* Anyone with DB access can read passwords
* Insider threats become trivial
* Immediate full account compromise

**Interview Line:**

> “Storing passwords in plain text is a critical security vulnerability.”

---

## 4. Hashing vs Encryption (VERY IMPORTANT)

This is a **frequently asked interview topic**.

---

## 4.1 Hashing

### Simple Meaning

Hashing converts input into a **fixed-length value** using a one-way function.

* One-way process
* Original password cannot be recovered

Example:

```
password123 → a94a8fe5ccb19ba61c4c0873d391e987
```

Even if attackers steal the hash, they **cannot reverse it directly**.

### Key Properties

* Same input → same hash
* Small input change → completely different hash
* Not reversible

---

## 4.2 Encryption

### Simple Meaning

Encryption transforms data using a **secret key** and **can be reversed**.

* Two-way process
* Used for protecting data in transit or storage

---

### Hashing vs Encryption (Interview Table)

| Feature            | Hashing | Encryption |
| ------------------ | ------- | ---------- |
| Reversible         | ❌ No    | ✅ Yes      |
| Used for passwords | ✅ Yes   | ❌ No       |
| Needs key          | ❌ No    | ✅ Yes      |

**Strong Interview Line:**

> “Passwords should be hashed, not encrypted, because authentication requires verification—not recovery.”

---

## 5. Why Normal Hashing (SHA-256) Is NOT Enough

Many beginners think:

> “I will hash passwords using SHA-256.”

❌ This is **still insecure**.

### Why?

* SHA-256 is designed to be **fast**
* Attackers can compute billions of hashes per second using GPUs

Fast hashes enable **brute-force and dictionary attacks**.

---

## 6. Password Hashing Algorithms (Correct Approach)

Password hashing algorithms are **intentionally slow**.

### Why Slow Is Good

* Increases attacker cost
* Limits brute-force attempts
* Protects users even after DB leaks

---

### 6.1 bcrypt

* Adaptive hashing algorithm
* Uses configurable **cost factor**
* Widely supported in backend frameworks

---

### 6.2 Argon2 (Modern Best Practice)

* Winner of Password Hashing Competition
* Memory-hard (resists GPU attacks)
* Recommended by security standards

**Interview Recommendation:**

> “Argon2 is the modern best practice, with bcrypt as a strong and widely adopted alternative.”

---

## 7. Salting (EXTREMELY IMPORTANT)

---

## 7.1 What Is a Salt?

A **salt** is a randomly generated value added to a password **before hashing**.

```
password + random_salt → hash
```

---

## 7.2 Why Salting Matters

Without salt:

* Same passwords produce same hashes
* Rainbow table attacks work

With salt:

* Same passwords produce different hashes
* Rainbow tables become useless

### Example

Without salt:

```
password123 → hash1
password123 → hash1
```

With salt:

```
password123 + salt1 → hashA
password123 + salt2 → hashB
```

**Important:** Modern algorithms like **bcrypt and Argon2 manage salting automatically**.

---

## 8. Authentication Flow (Step-by-Step)

### Signup Flow

1. User submits password
2. Server hashes password
3. Hash is stored in database

---

### Login Flow

1. User enters password
2. Server hashes input
3. Hash is compared with stored hash
4. Match → authentication success

**Interview Line:**

> “Passwords are never decrypted; they are only verified.”

---

## 9. Hands-On: Password Hashing in Python

### 9.1 Using bcrypt

```python
import bcrypt

password = "MySecurePassword123"
password_bytes = password.encode('utf-8')

hashed_password = bcrypt.hashpw(password_bytes, bcrypt.gensalt())

# Verification
bcrypt.checkpw(password_bytes, hashed_password)
```

**Key Observations:**

* Salt is automatic
* Hash changes every time
* Verification still succeeds

---

### 9.2 Using Argon2

```python
from argon2 import PasswordHasher

ph = PasswordHasher()
hash = ph.hash("MySecurePassword123")
ph.verify(hash, "MySecurePassword123")
```

---

## 10. Common Authentication Mistakes (Interview Gold)

* Storing plain text passwords
* Using MD5 / SHA-1 / SHA-256
* No login rate limiting
* Weak password policies
* Logging passwords

---

## 11. End-of-Day Interview Readiness Checklist

You should confidently explain:

* Why passwords must be hashed
* Hashing vs encryption
* bcrypt vs Argon2
* Salting and its purpose
* Authentication flow
* Secure password handling in backend systems

---

