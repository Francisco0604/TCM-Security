# 🛡️ Capturing Hashes with Responder

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Attacking Active Directory: Initial Attack Vectors](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Attacking Active Directory: Initial Attack Vectors > Capturing Hashes with Responder`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Capturing Hashes with Responder** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


Best time to run responder is early in the morning before everyone logs in
Responder needs to be ran with sudo or as root

sudo responder -I eth0 -dwPv 

-I is probably for ip address


![Lab Execution Screenshot / Proof of Exploit](./assets/079_Capturing_Hashes_with_Responder_1c5d64c5-e0cb-8073-942e-f6dc6dbc036f.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*



![Lab Execution Screenshot / Proof of Exploit](./assets/080_Capturing_Hashes_with_Responder_1c5d64c5-e0cb-808d-bfe5-f71b835adcc4.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*



![Lab Execution Screenshot / Proof of Exploit](./assets/081_Capturing_Hashes_with_Responder_1c5d64c5-e0cb-8033-8cfe-c77de6ae9bcc.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

-v for increased verbosity

After running, always make sure to check if your ip matches and is correct


![Lab Execution Screenshot / Proof of Exploit](./assets/082_Capturing_Hashes_with_Responder_1c5d64c5-e0cb-8012-bf1d-da66eda92b0e.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Make sure that all of the following are on


![Lab Execution Screenshot / Proof of Exploit](./assets/083_Capturing_Hashes_with_Responder_1c5d64c5-e0cb-804c-877c-d1c497885156.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Tried to gain access to the attacker ip simply to generate traffic 

got the ntlm hash


![Lab Execution Screenshot / Proof of Exploit](./assets/084_Capturing_Hashes_with_Responder_1c5d64c5-e0cb-80c5-b002-e20a85f23f42.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*






---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Attacking Active Directory: Initial Attack Vectors](./README.md) • [🏠 Master Course Index](../README.md)
