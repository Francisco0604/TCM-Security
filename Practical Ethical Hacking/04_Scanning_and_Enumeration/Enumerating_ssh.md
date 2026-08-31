# 🛡️ Enumerating ssh

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Scanning and enumeration](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Scanning and enumeration > Enumerating ssh`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Enumerating ssh** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


Its always good to recheck and confirm the ssh version
You can do this by trying to connect with the ssh, even if udk passwaord is fine since sometimes the ssh gives us a banner which reveals info, we want that info 





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Scanning and enumeration](./README.md) • [🏠 Master Course Index](../README.md)
