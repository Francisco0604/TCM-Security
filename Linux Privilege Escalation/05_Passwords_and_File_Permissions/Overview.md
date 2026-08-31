# 🛡️ Overview

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [Passwords & File Permissions](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > Passwords & File Permissions > Overview`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **Overview**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit


We are goin to look at few different escalation paths 
Stored passwords (which we hunted in the enumeration section)
Weak file permissions
ssh keys



---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to Passwords & File Permissions](./README.md) • [🏠 Master Course Index](../README.md)
