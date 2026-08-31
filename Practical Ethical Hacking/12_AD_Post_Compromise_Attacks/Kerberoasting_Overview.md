# 🛡️ Kerberoasting Overview

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Attacking Active Directory: Post-Compromise Attacks ](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Attacking Active Directory: Post-Compromise Attacks  > Kerberoasting Overview`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Kerberoasting Overview** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

Quick way to get domain admin in a network

It takes advantage of service account


![Lab Execution Screenshot / Proof of Exploit](./assets/145_Kerberoasting_Overview_1c9d64c5-e0cb-80f3-80c0-faa7f1b6137a.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


We can use the following tool to point our username and passowrd to the domain controller



![Lab Execution Screenshot / Proof of Exploit](./assets/146_Kerberoasting_Overview_1c9d64c5-e0cb-80fe-96c6-e694a3023580.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


It will spit out a long hash, We can take tht hash and try to brk it


![Lab Execution Screenshot / Proof of Exploit](./assets/147_Kerberoasting_Overview_1c9d64c5-e0cb-805e-afed-d0c1e784cd95.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*






---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Attacking Active Directory: Post-Compromise Attacks ](./README.md) • [🏠 Master Course Index](../README.md)
