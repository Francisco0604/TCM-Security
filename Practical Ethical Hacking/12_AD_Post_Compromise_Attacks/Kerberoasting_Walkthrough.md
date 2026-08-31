# 🛡️ Kerberoasting Walkthrough

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Attacking Active Directory: Post-Compromise Attacks ](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Attacking Active Directory: Post-Compromise Attacks  > Kerberoasting Walkthrough`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Kerberoasting Walkthrough** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

To perform kerberos


![Lab Execution Screenshot / Proof of Exploit](./assets/148_Kerberoasting_Walkthrough_1c9d64c5-e0cb-8000-9e59-dc1251ef5598.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


When the last log in is never be careful it can be a honeypot account


![Lab Execution Screenshot / Proof of Exploit](./assets/149_Kerberoasting_Walkthrough_1c9d64c5-e0cb-80a3-a4ec-dbe610ac5daf.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Can crack the hash then which was generated





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Attacking Active Directory: Post-Compromise Attacks ](./README.md) • [🏠 Master Course Index](../README.md)
