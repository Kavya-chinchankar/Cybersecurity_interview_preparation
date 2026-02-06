# WEEK 2 – DAY 12: Cross-Site Request Forgery (CSRF)

## 📌 Overview

Cross-Site Request Forgery (CSRF) is a **critical web vulnerability** where an attacker tricks a **logged-in user’s browser** into performing **unintended actions** on a trusted application.

Unlike XSS, CSRF does **not execute attacker code** in the browser.  
Instead, it **abuses browser trust in cookies**, making the server believe the request is legitimate.

This module explains CSRF **from first principles to real-world defense**, exactly as expected in **OWASP interviews and backend security roles**.

---

## 🎯 Learning Objectives

After completing this module, you will be able to:

- Explain **what CSRF is and why it works**
- Describe the **complete CSRF attack flow**
- Simulate a **real CSRF attack**
- Understand **why cookies enable CSRF**
- Implement **CSRF tokens correctly**
- Configure **SameSite cookies**
- Answer **CSRF interview questions confidently**

---

## 🔐 What is CSRF?

> CSRF is an attack where a **victim’s authenticated browser** is tricked into making an **unauthorized request** to a trusted website **without the user’s knowledge**.

Key facts:
- Victim is **already logged in**
- Browser **automatically sends cookies**
- Server **cannot distinguish intent**
- Attack performs **state-changing actions**

---

## 🧠 Why CSRF Works (Mental Model)

### Browser Behavior
- Automatically attaches cookies
- Does not understand user intent

### Server Behavior
- Sees a valid session cookie
- Assumes request is legitimate

### Result
> The server executes a malicious request **as if the user made it**

---

## 🔁 CSRF Attack Flow (Real Example)

### Scenario: Email Change

1. User logs into `bank.com`
2. Browser stores session cookie
3. User visits attacker site `evil.com`
4. Hidden request executes:

```html
<img src="https://bank.com/change-email?email=attacker@evil.com">
