# 🛡️ Amass

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Web Application Enumeration](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Web Application Enumeration > Amass`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Amass** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


amass github for installation guide
Follow steps from source



![Lab Execution Screenshot / Proof of Exploit](./assets/222_Amass_1ccd64c5-e0cb-8013-9083-e09c8e51a2a4.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Simple run



![Lab Execution Screenshot / Proof of Exploit](./assets/223_Amass_1ccd64c5-e0cb-80be-8012-ff9d72f04ac2.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Addin to script



![Lab Execution Screenshot / Proof of Exploit](./assets/224_Amass_1ccd64c5-e0cb-805e-bc39-d6f8c4abebb0.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Amass takes a long time to search through things





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Web Application Enumeration](./README.md) • [🏠 Master Course Index](../README.md)
