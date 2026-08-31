# 🛡️ Finding Subdomains

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Web Application Enumeration](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Web Application Enumeration > Finding Subdomains`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Finding Subdomains** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

- 📄 **[Assetfinder](./Assetfinder.md)**- 📄 **[Amass](./Amass.md)**




---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Web Application Enumeration](./README.md) • [🏠 Master Course Index](../README.md)
