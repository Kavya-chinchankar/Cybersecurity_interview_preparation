# WEEK 2 – DAY 13: Security Misconfiguration

## 📌 Overview

Security Misconfiguration happens when applications, servers, or cloud resources are deployed with **unsafe defaults**, unnecessary services, exposed management interfaces, or sensitive information left accessible.

No sophisticated exploit is required.

Attackers simply discover **what is already open**.

This is one of the **most common real-world breach causes** and a critical topic for backend engineers, DevSecOps professionals, and security analysts.

---

## 🎯 Learning Objectives

After completing this module, you will be able to:

- Identify dangerous default configurations
- Recognize exposure risks in infrastructure and applications
- Understand real attack impact
- Harden a Flask application for production
- Explain misconfiguration risks in interviews

---

## 🔐 What is Security Misconfiguration?

> Security Misconfiguration refers to insecure or incomplete configuration of applications, frameworks, servers, or cloud environments that allows unauthorized access or data exposure.

Key insight:
- No password cracking needed
- No advanced exploit required
- The system is already open

---

## 🤔 Why It Is So Common

Typical reasons include:

- Focus on feature delivery over security
- Default settings never changed
- Debug or admin interfaces left enabled
- Secrets stored in code
- Public cloud storage or open security groups

Most incidents result from **human oversight**.

---

## 🌐 Open Ports

### What Are Ports?

Ports are communication endpoints for services.

Examples:
- 80 → HTTP  
- 443 → HTTPS  
- 22 → SSH  
- 3306 → MySQL  

---

### Why Open Ports Are Dangerous

They may:
- Expose internal services
- Allow brute-force attempts
- Provide direct access to databases
- Reveal running software versions

---

### Attacker Mindset

> “What services are reachable?”

Example discovery tool:

```bash
nmap -sS target_ip
