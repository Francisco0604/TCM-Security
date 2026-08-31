# 🛡️ Domain Enumeration with bloodhound

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Attacking Active Directory: Post-Compromise Enumeration ](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Attacking Active Directory: Post-Compromise Enumeration  > Domain Enumeration with bloodhound`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Domain Enumeration with bloodhound** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


Install blood hound
sudo pip install bloodhound

run
sudo neo4j console
This is requied for us to use blood hound



![Lab Execution Screenshot / Proof of Exploit](./assets/114_Domain_Enumeration_with_bloodhound_1c7d64c5-e0cb-8042-96c5-e953488f7b12.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

it will give you this link, open it
Username: neo4j : password: neo4j
It might ask you to change password always remember the password 

Run blood hound
sudo bloodhound
I will ask you for the username and password of neo4j



![Lab Execution Screenshot / Proof of Exploit](./assets/115_Domain_Enumeration_with_bloodhound_1c7d64c5-e0cb-8021-a3d6-f0ba9fe3cc09.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

-d is for domain
-ns is for name server (domain controller ip)
-c is for what are you collecting

Import all the information in blood hound
Go to the analyis tab on top
It displays all the ifo in a graphical manner 




---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Attacking Active Directory: Post-Compromise Enumeration ](./README.md) • [🏠 Master Course Index](../README.md)
