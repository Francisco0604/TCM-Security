# 🛡️ XXE - External Entities Injection

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Common Web Vulnerabilities](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Common Web Vulnerabilities > XXE - External Entities Injection`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **XXE - External Entities Injection** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


Some websites use XML to transfer data we can use the XXE attack 

XML entity is a simple way of representing data for special characters
For eg & < >  we hav amp lt and gt respectively 

An enternal entity is a custom entity whose defination is outside the document and therefore needs to be located as the xml is passed
By abusing the above we can:
We can read files as well as get some remote execution with this attack 

For this there is already files which are there in the file we extracted the course from


![Lab Execution Screenshot / Proof of Exploit](./assets/264_XXE_-_External_Entities_Injection_1cfd64c5-e0cb-8095-9045-e198c9ea109b.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Can find other exploit for remote code execution in payloadforall things github

This is not smthing we find often but it is good to test for if you see the target accepting xml

Also sending xml data through api endpoints which accepts JSONs, as sometimes they will also accept xml and then after further testing can find out that the endpoint is vulnerable





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Common Web Vulnerabilities](./README.md) • [🏠 Master Course Index](../README.md)
