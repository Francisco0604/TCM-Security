# 🛡️ Gaining a shell

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Attacking Active Directory: Initial Attack Vectors](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Attacking Active Directory: Initial Attack Vectors > Gaining a shell`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Gaining a shell** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

Couple of methods to do this

we can use metasploit 
With password


![Lab Execution Screenshot / Proof of Exploit](./assets/100_Gaining_a_shell_1c6d64c5-e0cb-8075-9581-eea9fb900370.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


With hash


![Lab Execution Screenshot / Proof of Exploit](./assets/101_Gaining_a_shell_1c6d64c5-e0cb-80b3-9f59-de63f6e612d1.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Metasploit is a bit noisy and in a real time enviroment there is a chance it might get caught


![Lab Execution Screenshot / Proof of Exploit](./assets/102_Gaining_a_shell_1c6d64c5-e0cb-8076-8b07-faac28cb4534.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


We can use [psexec.py](http://psexec.py/) It wont get detected as much

with password


![Lab Execution Screenshot / Proof of Exploit](./assets/103_Gaining_a_shell_1c6d64c5-e0cb-80f2-a384-c523423ad563.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


With hash


![Lab Execution Screenshot / Proof of Exploit](./assets/104_Gaining_a_shell_1c6d64c5-e0cb-809e-975a-f6cf8635a154.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Always set the payload to x64 on metasploit

If automatic does not work try the others (Native upload works the best)


![Lab Execution Screenshot / Proof of Exploit](./assets/105_Gaining_a_shell_1c6d64c5-e0cb-807f-a0e6-c0d0a4ec4465.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*






---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Attacking Active Directory: Initial Attack Vectors](./README.md) • [🏠 Master Course Index](../README.md)
