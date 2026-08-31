# 🛡️ Actual walkthrough

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Common Web Vulnerabilities](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Common Web Vulnerabilities > Actual walkthrough`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Actual walkthrough** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


Enumeration


![Lab Execution Screenshot / Proof of Exploit](./assets/268_Actual_walkthrough_1cfd64c5-e0cb-80c5-9054-d97564e1b53d.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


After logging in when you get message can edit that on top in url
This led to us being able to do xss


![Lab Execution Screenshot / Proof of Exploit](./assets/269_Actual_walkthrough_1cfd64c5-e0cb-8073-83ca-e5cd8fae0201.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Did the same in review 
This is a stored xss which is way more dangerouse


![Lab Execution Screenshot / Proof of Exploit](./assets/270_Actual_walkthrough_1cfd64c5-e0cb-8050-9872-f4efa913a3ca.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Found an entry point for sql injection in url


![Lab Execution Screenshot / Proof of Exploit](./assets/271_Actual_walkthrough_1cfd64c5-e0cb-802b-9f27-e32229ec6522.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

Found username and hashes of paasword from here

Used hashcat to crack the password





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Common Web Vulnerabilities](./README.md) • [🏠 Master Course Index](../README.md)
