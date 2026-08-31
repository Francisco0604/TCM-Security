# 🛡️ Academy

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [New capstone](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > New capstone > Academy`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Academy** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

username : root
password : tcm

root@academy : dhclient

ssh mostly attack as bruteforce in a pentest to c

Gonna use hashcat to crack hash password

Use dirb or ffuf to find other directories

open academy

upload reverse shell


![Lab Execution Screenshot / Proof of Exploit](./assets/041_Academy_1c4d64c5-e0cb-80a6-8f1c-fe4d298b2a90.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


After getting shell allivate your privilages


![Lab Execution Screenshot / Proof of Exploit](./assets/042_Academy_1c4d64c5-e0cb-80ff-be73-fff0bde25ca0.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Set up a python http server

go to temp directory on the shell which u got and wget the file to allivate privilage

if we want validation that a cronjob is running and we are not getting it with the basic commands use pspy
download the pspy64 bit on ur deive and then run it on the target machine


![Lab Execution Screenshot / Proof of Exploit](./assets/043_Academy_1c4d64c5-e0cb-80b9-a44f-e9077d096f08.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


- 📄 **[My attempt](./My_attempt.md)**


### 🎯 Vulnerability & Exploit Analysis: Laravel Web Application RCE
- **Attack Chain:**
  1. **Web Fuzzing:** Directory enumeration using `ffuf` / `gobuster` revealed exposed `.env` file and application debug mode.
  2. **App Key Extraction:** Extracted `APP_KEY` from exposed Laravel `.env` configuration.
  3. **PHP Deserialization:** Used `phpggc` to generate serialized payload encrypted with the extracted application key, achieving unauthenticated Remote Code Execution.
  4. **Privilege Escalation:** Sudo misconfiguration / internal service enumeration leading to `root`.
- **Remediation & Hardening:**
  1. Disable Laravel Debug Mode in production (`APP_DEBUG=false`).
  2. Block web server access to `.env` files in Apache/Nginx configuration.


---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to New capstone](./README.md) • [🏠 Master Course Index](../README.md)
