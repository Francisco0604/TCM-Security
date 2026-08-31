# 🛡️ Enumerating SMB

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Scanning and enumeration](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Scanning and enumeration > Enumerating SMB`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Enumerating SMB** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

We to try to connect with the smb
We will use metaspolit for this

First we scan for the version info
using


![Lab Execution Screenshot / Proof of Exploit](./assets/027_Enumerating_SMB_1c0d64c5-e0cb-8009-81a1-dae82b627bbe.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Use smbclient to connect to the client


![Lab Execution Screenshot / Proof of Exploit](./assets/028_Enumerating_SMB_1c0d64c5-e0cb-8027-80ec-d88cdd419ad9.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


try to gain access to the sharenames(mentioned in the result above) if posiible directly





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Scanning and enumeration](./README.md) • [🏠 Master Course Index](../README.md)
