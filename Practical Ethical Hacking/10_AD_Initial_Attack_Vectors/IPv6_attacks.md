# 🛡️ IPv6 attacks

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Attacking Active Directory: Initial Attack Vectors](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Attacking Active Directory: Initial Attack Vectors > IPv6 attacks`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **IPv6 attacks** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


Mostly on a network no uses ipv6 evn tho it is enabled if that is the case
Attacker can act as the dns and get authentication to the domain controller
When someone logs in and uses their credentials that comes to us in the form of ntlm
Then we do a ldap relay to the domain controller with the ntlm credentials
LDAP stands for Lightweight Directory Access Protocol
We can use the tool man in the middle 6 to create a new accout for us
Very hard to detect as of 2021 


![Lab Execution Screenshot / Proof of Exploit](./assets/106_IPv6_attacks_1c7d64c5-e0cb-805c-bece-caf957ca4a2a.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*






---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Attacking Active Directory: Initial Attack Vectors](./README.md) • [🏠 Master Course Index](../README.md)
