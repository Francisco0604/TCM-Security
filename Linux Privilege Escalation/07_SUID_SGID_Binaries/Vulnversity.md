# 🛡️ Vulnversity

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [SUID](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > SUID > Vulnversity`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **Vulnversity**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit


Do the THM  Box all details are provided there

scan the ip
bruteforce to check what what directories exist in the webiste use fuff or any other tool

Tried getting the reverse shell it failed
tried form the box of try hack me failed there as well

Used gtfobins to find suid vul



---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to SUID](./README.md) • [🏠 Master Course Index](../README.md)
