# 🛡️ Linux Privilege Escalation

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [Introduction](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > Introduction > Linux Privilege Escalation`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **Linux Privilege Escalation**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit


Go to the site the full course is like here only
[https://tryhackme.com/room/linuxprivescarena](https://tryhackme.com/room/linuxprivescarena)
- 📄 **[Introduction](./Introduction.md)**- 📄 **[Initial enumeration](./Initial_enumeration.md)**- 📄 **[Exploring automated tools](./Exploring_automated_tools.md)**- 📄 **[Escalation path](./Escalation_path.md)**- 📄 **[Capstone](./Capstone.md)**


---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to Introduction](./README.md) • [🏠 Master Course Index](../README.md)
