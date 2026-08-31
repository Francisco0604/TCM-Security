# 🛡️ Assetfinder

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Web Application Enumeration](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Web Application Enumeration > Assetfinder`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Assetfinder** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


Install assetfinder through github(tomnomnom)

Use this to install


![Lab Execution Screenshot / Proof of Exploit](./assets/220_Assetfinder_1ccd64c5-e0cb-8000-bbf0-e230f07e166a.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Can use to automate the tasks to find subdomains with assetfinder



![Lab Execution Screenshot / Proof of Exploit](./assets/221_Assetfinder_1ccd64c5-e0cb-8015-9a16-d594afa82aaa.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*






---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Web Application Enumeration](./README.md) • [🏠 Master Course Index](../README.md)
