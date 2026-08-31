# 🛡️ Part 2

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Networking Refresher](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Networking Refresher > Part 2`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Part 2** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


Solve without looking if possible 



![Lab Execution Screenshot / Proof of Exploit](./assets/006_Part_2_1bfd64c5-e0cb-801a-b691-e3811ceb8a70.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Networking Refresher](./README.md) • [🏠 Master Course Index](../README.md)
