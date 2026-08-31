# 🛡️ LLMNR Poisoning Overview

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Attacking Active Directory: Initial Attack Vectors](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Attacking Active Directory: Initial Attack Vectors > LLMNR Poisoning Overview`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **LLMNR Poisoning Overview** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

Attacking Active Directory: Initial Attack Vectors 


![Lab Execution Screenshot / Proof of Exploit](./assets/073_LLMNR_Poisoning_Overview_1c5d64c5-e0cb-8044-b047-f8f46572329e.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

Stands for Link-Local Multicast Name Resolution

Why do we care

When we intercept the traffic we can intercept a username and a hash (this is a type of Man in the middle attack)

Eg. actual machine is \\hackme but the user misspelled 


![Lab Execution Screenshot / Proof of Exploit](./assets/074_LLMNR_Poisoning_Overview_1c5d64c5-e0cb-8027-9c8f-fc549313c091.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


run responder


![Lab Execution Screenshot / Proof of Exploit](./assets/075_LLMNR_Poisoning_Overview_1c5d64c5-e0cb-8020-b911-f4ac883c5e93.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

It can listen to traffic and grab the hash

try to do to a file share but with wrong thing in the end to direct to responder


![Lab Execution Screenshot / Proof of Exploit](./assets/076_LLMNR_Poisoning_Overview_1c5d64c5-e0cb-802b-adf2-f9fff7dffdf7.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


When we do the above we can get a hash


![Lab Execution Screenshot / Proof of Exploit](./assets/077_LLMNR_Poisoning_Overview_1c5d64c5-e0cb-8047-b51e-e9fb458de963.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


If the hash is weak enough we can crack it using hashcat


![Lab Execution Screenshot / Proof of Exploit](./assets/078_LLMNR_Poisoning_Overview_1c5d64c5-e0cb-8083-9950-e9111264d7e4.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*






---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Attacking Active Directory: Initial Attack Vectors](./README.md) • [🏠 Master Course Index](../README.md)
