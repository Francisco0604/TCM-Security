# 🛡️ Finding Alive Domains with Httprobe

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Web Application Enumeration](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Web Application Enumeration > Finding Alive Domains with Httprobe`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Finding Alive Domains with Httprobe** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


httprobe github (tomnomnom)



![Lab Execution Screenshot / Proof of Exploit](./assets/225_Finding_Alive_Domains_with_Httprobe_1ccd64c5-e0cb-806a-ae7b-ce1f59fca6c3.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


It checks if the site/subdomaisn respond (doesnt matter what status code they give eg 200,400 etc)

adding to automation


![Lab Execution Screenshot / Proof of Exploit](./assets/226_Finding_Alive_Domains_with_Httprobe_1ccd64c5-e0cb-801a-98e0-df54b2b7bfa8.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Web Application Enumeration](./README.md) • [🏠 Master Course Index](../README.md)
