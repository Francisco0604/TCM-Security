# 🛡️ Domain Enumeration with ldapdomaindump

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Attacking Active Directory: Post-Compromise Enumeration ](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Attacking Active Directory: Post-Compromise Enumeration  > Domain Enumeration with ldapdomaindump`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Domain Enumeration with ldapdomaindump** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


This for gethering information


![Lab Execution Screenshot / Proof of Exploit](./assets/113_Domain_Enumeration_with_ldapdomaindump_1c7d64c5-e0cb-8019-a0c4-d620249ab34f.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

the ip address of ldaps if the one of the domain controller 





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Attacking Active Directory: Post-Compromise Enumeration ](./README.md) • [🏠 Master Course Index](../README.md)
