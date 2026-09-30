# 🔐 Brute-Force Attack Lab (Burp Suite + Hydra)

![Status](https://img.shields.io/badge/status-completed-blue)
![Focus](https://img.shields.io/badge/focus-cybersecurity-red)
![Tools](https://img.shields.io/badge/tools-Burp%20Suite%20%7C%20Hydra-orange)
![Program](https://img.shields.io/badge/program-Ethical%20Hacking%20Intern-lightgrey)

## 📌 Project Description

This project demonstrates how **brute-force attacks exploit weak authentication** in web applications and network services. Using **Burp Suite Intruder (Cluster Bomb)** and **Hydra**, attacks were simulated against a deliberately vulnerable target — `testphp.vulnweb.com` — and a local SSH service.

The report includes detailed steps, screenshots, real command output, and a **mitigation checklist** for preventing such attacks in production environments.

> ⚠️ **Disclaimer:** All testing was performed against intentionally vulnerable systems (`testphp.vulnweb.com` by Acunetix, and a local Metasploitable VM). Never use these techniques on systems without explicit authorization.

## 🎯 Objectives

- Simulate brute-force attacks on web login forms and SSH services
- Use Burp Suite Intruder (Cluster Bomb) to attack a web login
- Use Hydra to brute-force SSH credentials
- Identify valid username-password pairs (lab environment only)
- Document weaknesses and propose mitigation controls

## 🧰 Tools & Environment

| Tool | Purpose |
|------|---------|
| Burp Suite (Community/Pro) | Intercept + Intruder (Cluster Bomb) |
| Hydra v9.2 | SSH brute-force automation |
| Kali Linux | Attacker machine |
| testphp.vulnweb.com | Vulnerable web target (Acunetix) |
| Metasploitable 2 (192.168.29.135) | Vulnerable SSH target |
| Browser + Proxy | 127.0.0.1:8080 |

## 🎯 Target Overview

| Property | Value |
|----------|-------|
| **URL** | `http://testphp.vulnweb.com/login.php` (HTTP, not HTTPS) |
| **Backend** | Apache / PHP |
| **Failed login** | `200 OK` |
| **Successful login** | `302 Redirect` |
| **Purpose** | Deliberately vulnerable site by Acunetix for training |

---

## 🧪 Lab 1 — Brute Force with Burp Suite (Cluster Bomb)

### Objective
Simulate a brute-force attack on `http://testphp.vulnweb.com/login.php` using **Intruder → Cluster Bomb**.

### Step-by-Step

**1. Configure Burp Suite**
- Open Burp Suite → **Proxy → Intercept** → Intercept **ON**
- Configure browser proxy: `127.0.0.1:8080`

**2. Capture the Login Request**
- Visit the target login page
- Submit dummy credentials (e.g. `user:pass`)
- Intercept the POST request:

