# 🛡️ Cracking Our Captured Hashes

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Attacking Active Directory: Initial Attack Vectors](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Attacking Active Directory: Initial Attack Vectors > Cracking Our Captured Hashes`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Cracking Our Captured Hashes** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

Copy the hash in a file to use in hashcat
Another tool you can use is John the reaper
It is not ideal to crack hashes on the vm
Since to crack hashes it uses the gpu so its better to run it on base os 

we can use the  —help | grep with the hash type if we know what hash it is so we can get all the hash module of that ; Below we are using NTLMv2 since the hash type was the sm


![Lab Execution Screenshot / Proof of Exploit](./assets/085_Cracking_Our_Captured_Hashes_1c6d64c5-e0cb-8071-8a3c-c7a5e79eb570.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*




![Lab Execution Screenshot / Proof of Exploit](./assets/086_Cracking_Our_Captured_Hashes_1c6d64c5-e0cb-80c5-8a6b-d22c45349e54.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*






---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Attacking Active Directory: Initial Attack Vectors](./README.md) • [🏠 Master Course Index](../README.md)
