# 🛡️ Brute force - Lab 1

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Common Web Vulnerabilities](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Common Web Vulnerabilities > Brute force - Lab 1`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Brute force - Lab 1** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

It might seem easy but may take long time if not done correctly

We need to have resonably sized lists 
we have to be aware that the accounts may get blocked or our ip might get blocked
Always say inside of  restiction  like bug bounty programme specification(automated tools : 5 / sec)

Don't underestimate brute forcing it can be very useful


![Lab Execution Screenshot / Proof of Exploit](./assets/263_Brute_force_-_Lab_1_1cfd64c5-e0cb-80a5-87a0-d21b19d5f0fc.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


This is a basic log in page which we are given 
We can do brute forcing from a variety of ways on this 
For now we wil intercept the request we sent to log and attack with burp
We choose the xeno top 100 request from seclist 

We then try the same attack with ffuf
We copy the request from burp and then put the keyword FUZZ 
Use the same word list
Use —request proto http
After tht 
We use the fs filter to filter by size to find the other response 





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Common Web Vulnerabilities](./README.md) • [🏠 Master Course Index](../README.md)
