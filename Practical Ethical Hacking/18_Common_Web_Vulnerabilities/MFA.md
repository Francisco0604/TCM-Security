# 🛡️ MFA

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Common Web Vulnerabilities](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Common Web Vulnerabilities > MFA`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **MFA** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

We get the same log in and this time we are given a username and password and told to atk another username
We first enter own credentials, and we are then given a code to enter to log in

The first few things which comes to mind is 
Can use the code to under with another user name
Cause the webpage still has the username section to edit and a code section to put the code

The other method we can use is brute forcing since the code is only 6 digits long and it is only numbers

So we took the mfa code and put it in the section and before sending it we intercept it with burp 
There we change the username and send
And we are successfully in 





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Common Web Vulnerabilities](./README.md) • [🏠 Master Course Index](../README.md)
