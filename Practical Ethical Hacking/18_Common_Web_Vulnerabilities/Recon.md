# 🛡️ Recon

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Common Web Vulnerabilities](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Common Web Vulnerabilities > Recon`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Recon** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

Found an idor reference:


![Lab Execution Screenshot / Proof of Exploit](./assets/265_Recon_1cfd64c5-e0cb-806b-9891-e2c64bf347f3.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Did sign in
In the rating part found out that can inject js


![Lab Execution Screenshot / Proof of Exploit](./assets/266_Recon_1cfd64c5-e0cb-80cb-840d-f88703bf038c.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


After Fuzzing


![Lab Execution Screenshot / Proof of Exploit](./assets/267_Recon_1cfd64c5-e0cb-8036-9f93-c1f03609a0a4.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

Was forbiden to open assets and admin





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Common Web Vulnerabilities](./README.md) • [🏠 Master Course Index](../README.md)
