# WEEK 2 – DAY 11: Cross-Site Scripting (XSS)

## 📌 Overview

Cross-Site Scripting (XSS) is one of the **most common and dangerous client-side vulnerabilities** in web applications.  
It allows attackers to execute **malicious JavaScript in a victim’s browser**, often leading to **session hijacking, account takeover, and data theft**.

This module provides a **textbook-level yet practical explanation** of XSS, covering:
- How XSS works internally
- All major XSS types
- Real exploitation techniques
- Correct and incorrect defenses
- Interview-ready explanations

---

## 🎯 Learning Objectives

After completing this module, you will be able to:

- Explain **what XSS is and why it is dangerous**
- Distinguish between **Reflected, Stored, and DOM-based XSS**
- Manually test and inject XSS payloads
- Understand how browsers execute malicious scripts
- Implement **correct XSS defenses**
- Confidently answer **XSS interview questions**

---

## 🔐 What is Cross-Site Scripting (XSS)?

> XSS occurs when an application allows **untrusted user input** to be executed as JavaScript in another user’s browser.

Key characteristics:
- XSS is a **client-side attack**
- The server acts as a **delivery mechanism**
- The attack executes **in the victim’s browser**
- The script runs with the **victim’s privileges**

---

## 🚨 Why XSS Is Dangerous

An attacker can:
- Steal cookies and session tokens
- Perform actions as the victim
- Deface websites
- Redirect users to malicious sites
- Inject malware or keyloggers

XSS directly breaks **user trust** and frequently leads to **account compromise**.

---

## 🧠 How XSS Works (Mental Model)

1. Application accepts user input  
2. Input is reflected or stored  
3. Browser interprets it as JavaScript  
4. Attacker’s code executes with victim’s access  

---

## 🧨 Types of XSS

### A. Reflected XSS

**Definition:**  
Malicious script is immediately reflected in the HTTP response.

**Example URL:**
```http
/search?q=<script>alert(1)</script>
