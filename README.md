# 🔐 Brute-Force Attack Using Hydra (Lab Project)

![Status](https://img.shields.io/badge/status-completed-blue)
![Focus](https://img.shields.io/badge/focus-cybersecurity-red)
![Tool](https://img.shields.io/badge/tool-Hydra-orange)

## 📌 Project Description

This project demonstrates a **brute-force attack simulation** using the **Hydra** tool against a vulnerable test system. The purpose of this lab is **educational only** — to understand how weak credentials can be exploited and how to defend against such attacks.

> ⚠️ **Disclaimer:** All testing was performed in a controlled lab environment on systems I own or have explicit permission to test. Never use these techniques on systems without authorization.

## 🎯 Objectives

- Perform brute-force attacks on different services
- Identify valid username-password pairs (lab environment only)
- Study Hydra command syntax
- Learn mitigation techniques against brute-force attacks

## 🧰 Tools & Environment

| Tool | Purpose |
|------|---------|
| Hydra | Brute-force attack tool |
| Kali Linux | Attacker machine |
| Metasploitable / DVWA | Target (vulnerable VM) |
| Wireshark | Traffic analysis |

## 🚀 Attack Workflow

1. **Reconnaissance** — identify open services (SSH, FTP, HTTP login)
2. **Wordlist prep** — use `rockyou.txt` or custom lists
3. **Run Hydra** — example command:
   ```bash
   hydra -l admin -P /usr/share/wordlists/rockyou.txt 192.168.1.10 ssh
