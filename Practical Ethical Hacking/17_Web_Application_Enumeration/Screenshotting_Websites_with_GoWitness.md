# 🛡️ Screenshotting Websites with GoWitness

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Web Application Enumeration](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Web Application Enumeration > Screenshotting Websites with GoWitness`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Screenshotting Websites with GoWitness** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence



GoWitness - [https://github.com/sensepost/gowitness](https://github.com/sensepost/gowitness)

This tool will go through all the websites mentioned and will take a screenshot of it

The syntax of this changes all the times so check




---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Web Application Enumeration](./README.md) • [🏠 Master Course Index](../README.md)
