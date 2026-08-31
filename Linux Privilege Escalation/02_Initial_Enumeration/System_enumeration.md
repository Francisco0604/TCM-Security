# 🛡️ System enumeration

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [Initial enumeration](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > Initial enumeration > System enumeration`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **System enumeration**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit


To check the hostname

```bash
hostname
```

Gives more info than hostname (better)

```bash
uname -a
```
This better to find easy exploits
Can search the versions which we get as results in this on google to see if there is any vulnerabilities

Similar to the above one

```bash
cat /proc/version
cat /etc/issue
```

To take a quick peak at the architecture

```bash
lscpu
```
if exploits need 4 cores to work but udk how many cores are part of the cpu then can run this and see

To check what services are running 

```bash
 ps -aux
```



---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to Initial enumeration](./README.md) • [🏠 Master Course Index](../README.md)
