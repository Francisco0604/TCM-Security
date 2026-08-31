# 🛡️ Identifying Web Technologies Used

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Information Gathering](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Information Gathering > Identifying Web Technologies Used`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Identifying Web Technologies Used** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

1. Buildwith.com


![Lab Execution Screenshot / Proof of Exploit](./assets/021_Identifying_Web_Technologies_Used_1bfd64c5-e0cb-8037-8089-d81438110803.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


1. Wappalyzer


![Lab Execution Screenshot / Proof of Exploit](./assets/022_Identifying_Web_Technologies_Used_1bfd64c5-e0cb-807f-b7c4-e7a7fb2bd13f.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


1. whatweb

![Lab Execution Screenshot / Proof of Exploit](./assets/023_Identifying_Web_Technologies_Used_1bfd64c5-e0cb-8028-a483-fb2a53c4411c.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Information Gathering](./README.md) • [🏠 Master Course Index](../README.md)
