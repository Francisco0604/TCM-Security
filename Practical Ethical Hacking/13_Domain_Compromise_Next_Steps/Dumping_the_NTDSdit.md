# 🛡️ Dumping the NTDS.dit

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [We've Compromised the Domain - Now What? ](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > We've Compromised the Domain - Now What?  > Dumping the NTDS.dit`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Dumping the NTDS.dit** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence




![Lab Execution Screenshot / Proof of Exploit](./assets/180_Dumping_the_NTDSdit_1cad64c5-e0cb-807c-bf69-dee2220f3a1c.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*




![Lab Execution Screenshot / Proof of Exploit](./assets/181_Dumping_the_NTDSdit_1cad64c5-e0cb-80e6-959f-fd0d11fd0a0b.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


The part we wnt to crack is the nt(the end part) part of the ntlm hash
Can copy the whole thing and open excel and paste and set delimiter to : to make things easier to copy the hash

can use excel to showcase the passwords found and all that so then can use data to show in the forms of graphs and all





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to We've Compromised the Domain - Now What? ](./README.md) • [🏠 Master Course Index](../README.md)
