# 🛡️ Dom -Lab 1

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Common Web Vulnerabilities](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Common Web Vulnerabilities > Dom -Lab 1`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Dom -Lab 1** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


When we sent information we could see that there was no going or coming back from the server, so since this is happening completly locally and is a vulnerability from the client side it is DOM based 

When type and execute the following to check if it is vulnerable


![Lab Execution Screenshot / Proof of Exploit](./assets/236_Dom_-Lab_1_1cdd64c5-e0cb-80ce-8e28-e858a16e2437.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

It will not execute
This is because evn tho the code is being added to the page it isnt being called, if this was partof the page when it  was loaded then it would have loaded


```javascript
<img src=x onerror="prompt(1)">
```

When the page tries to find x it will get an error and on error it will load our payload

To forward to another pg

```javascript
<img src=x onerror="windows.location.href='https://siteurl.com'">
```





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Common Web Vulnerabilities](./README.md) • [🏠 Master Course Index](../README.md)
