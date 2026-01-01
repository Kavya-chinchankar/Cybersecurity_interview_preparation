# 30-Day Cybersecurity Preparation Plan (MNC-Oriented)

## Overview

This repository documents my **30-day, 4-hours-per-day cybersecurity preparation journey**, focused on **Application Security, Platform Security, and Entry–Mid Level Security Engineer roles** at MNCs.

The goal of this repository is to:

* Demonstrate **consistent daily security learning**
* Showcase **hands-on labs and secure coding practices**
* Build **interview-ready security depth**
* Present security concepts in a **clear, explainable, industry-aligned manner**

Each day has **one structured Git commit**, reflecting real-world engineering discipline.

---

## Tech Stack Used

* Python
* Flask
* SQLite / MongoDB (where applicable)
* JWT, bcrypt
* OWASP tools (Burp Suite, ZAP)
* Linux / Kali Linux

---

## Repository Structure

```
cybersecurity-30-days/
│
├── day01_fundamentals/
├── day02_networking/
├── day03_web_architecture/
├── day04_authentication/
├── day05_authorization/
├── day06_sessions_tokens/
├── day07_revision/
│
├── day08_sql_injection/
├── day09_broken_auth/
├── day10_access_control/
├── day11_xss/
├── day12_csrf/
├── day13_misconfiguration/
├── day14_revision/
│
├── day15_burp_suite/
├── day16_owasp_zap/
├── day17_secure_code_review/
├── day18_file_uploads/
├── day19_api_security/
├── day20_logging_monitoring/
├── day21_revision/
│
├── day22_cloud_security/
├── day23_network_security/
├── day24_incident_response/
├── day25_threat_modeling/
├── day26_secure_design/
├── day27_vulnerable_app/
├── day28_hardening/
├── day29_interview_prep/
└── day30_final_review/
```

---

## Daily Commit & README Log

### Day 1 – Cybersecurity Fundamentals

**Topics**:

* CIA Triad
* Threats vs Vulnerabilities vs Risk
* Attack Surface
* Defense in Depth

**Hands-on**:

* Kali Linux setup
* Installed Burp Suite, ZAP

**Commit Message**:

```
Day 01: Cybersecurity fundamentals and security mindset
```

---

### Day 2 – Networking for Security

**Topics**:

* TCP/IP, DNS, HTTP/HTTPS
* Ports and Protocols
* TLS basics

**Hands-on**:

* Wireshark traffic analysis
* HTTPS handshake inspection

**Commit Message**:

```
Day 02: Networking basics for security and packet analysis
```

---

### Day 3 – Web Architecture

**Topics**:

* Client–Server Model
* REST APIs
* HTTP Methods and Status Codes

**Hands-on**:

* Browser DevTools request inspection

**Commit Message**:

```
Day 03: Web architecture and HTTP fundamentals
```

---

### Day 4 – Authentication Basics

**Topics**:

* Password storage
* Hashing vs Encryption
* bcrypt and salting

**Hands-on**:

* Implemented password hashing in Flask

**Commit Message**:

```
Day 04: Secure password storage using bcrypt
```

---

### Day 5 – Authorization Models

**Topics**:

* RBAC, ABAC, ACL
* Least privilege principle

**Hands-on**:

* Role-based access control in Flask

**Commit Message**:

```
Day 05: Authorization models and RBAC implementation
```

---

### Day 6 – Session vs Token Authentication

**Topics**:

* Sessions vs JWT
* Access vs Refresh Tokens

**Hands-on**:

* JWT-based login API

**Commit Message**:

```
Day 06: Session-based vs token-based authentication
```

---

### Day 7 – Weekly Revision

**Focus**:

* Security concept revision
* Interview-style explanations

**Commit Message**:

```
Day 07: Week 1 revision and interview notes
```

---

### Day 8 – Injection Attacks

**Topics**:

* SQL Injection
* NoSQL Injection

**Hands-on**:

* Exploited vulnerable queries
* Fixed using parameterized queries

**Commit Message**:

```
Day 08: SQL and NoSQL injection attacks and prevention
```

---

### Day 9 – Broken Authentication

**Topics**:

* Credential stuffing
* Brute force attacks

**Hands-on**:

* Simulated brute force
* Added rate limiting

**Commit Message**:

```
Day 09: Broken authentication risks and mitigations
```

---

### Day 10 – Broken Access Control

**Topics**:

* IDOR
* Missing authorization checks

**Hands-on**:

* Exploited IDOR
* Fixed ownership validation

**Commit Message**:

```
Day 10: Broken access control and IDOR fixes
```

---

### Day 11 – Cross-Site Scripting (XSS)

**Topics**:

* Reflected, Stored, DOM XSS

**Hands-on**:

* XSS injection
* Escaping and CSP implementation

**Commit Message**:

```
Day 11: XSS vulnerabilities and defense techniques
```

---

### Day 12 – CSRF

**Topics**:

* CSRF attack flow
* Tokens and SameSite cookies

**Hands-on**:

* CSRF simulation
* CSRF protection

**Commit Message**:

```
Day 12: CSRF attacks and prevention mechanisms
```

---

### Day 13 – Security Misconfiguration

**Topics**:

* Debug mode risks
* Secrets exposure

**Hands-on**:

* Secured Flask configuration

**Commit Message**:

```
Day 13: Security misconfiguration hardening
```

---

### Day 14 – OWASP Revision

**Focus**:

* Mapping OWASP Top 10 to projects

**Commit Message**:

```
Day 14: OWASP Top 10 revision and mapping
```

---

### Day 15 – Burp Suite

**Hands-on**:

* Intercepting requests
* Repeater and Intruder usage

**Commit Message**:

```
Day 15: Burp Suite hands-on testing
```

---

### Day 16 – OWASP ZAP

**Hands-on**:

* Passive and active scanning

**Commit Message**:

```
Day 16: OWASP ZAP scanning and remediation
```

---

### Day 17 – Secure Code Review

**Focus**:

* Identifying insecure patterns

**Commit Message**:

```
Day 17: Secure code review practices
```

---

### Day 18 – File Upload Security

**Topics**:

* MIME attacks
* Path traversal

**Commit Message**:

```
Day 18: Secure file upload implementation
```

---

### Day 19 – API Security

**Topics**:

* Rate limiting
* Replay attacks

**Commit Message**:

```
Day 19: API security and rate limiting
```

---

### Day 20 – Logging and Monitoring

**Hands-on**:

* Audit logs for authentication

**Commit Message**:

```
Day 20: Security logging and monitoring
```

---

### Day 21 – Weekly Revision

**Commit Message**:

```
Day 21: Week 3 revision and mock questions
```

---

### Day 22 – Cloud Security Basics

**Topics**:

* IAM
* Shared responsibility model

**Commit Message**:

```
Day 22: Cloud security fundamentals
```

---

### Day 23 – Network Security

**Topics**:

* WAF
* DDoS basics

**Commit Message**:

```
Day 23: Network security and DDoS mitigation
```

---

### Day 24 – Incident Response

**Topics**:

* Detection to recovery

**Commit Message**:

```
Day 24: Incident response lifecycle
```

---

### Day 25 – Threat Modeling

**Topics**:

* STRIDE

**Commit Message**:

```
Day 25: Threat modeling using STRIDE
```

---

### Day 26 – Secure System Design

**Designs**:

* Secure authentication service

**Commit Message**:

```
Day 26: Secure system design concepts
```

---

### Day 27 – Vulnerable Application

**Hands-on**:

* Built intentionally vulnerable app

**Commit Message**:

```
Day 27: Vulnerable application development
```

---

### Day 28 – Hardening

**Hands-on**:

* Fixed vulnerabilities
* Re-scanned

**Commit Message**:

```
Day 28: Application hardening and security fixes
```

---

### Day 29 – Interview Preparation

**Focus**:

* Security explanations
* Project walkthroughs

**Commit Message**:

```
Day 29: Cybersecurity interview preparation
```

---

### Day 30 – Final Review

**Focus**:

* Resume alignment
* GitHub cleanup

**Commit Message**:

```
Day 30: Final review and repository completion
```

---

## Final Outcome

* Strong application security foundation
* Demonstrable hands-on security skills
* Interview-ready explanations

---

## Author

**Kavya Krishna Chinchankar**
M.Tech – Cybersecurity
Aspiring Application / Platform Security Engineer


