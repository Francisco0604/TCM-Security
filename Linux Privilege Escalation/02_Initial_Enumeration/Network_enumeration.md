# 🛡️ Network enumeration

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [Initial enumeration](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > Initial enumeration > Network enumeration`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **Network enumeration**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit


To check ip 

```bash
ifconfig
ip a
```

To check the route

```bash
route
ip route
```
Another way to look at this is by arp table

```bash
arp -a
ip neigh
```

To identify what ports are open and what communications exist

```bash
netstat -ano
```
(hacker mind : when see 2 machine communicating try to find and exploit which can use against them )
Another thing we want to identify is if there are any open ports that we did not pick up on earlier and what are they doing



---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to Initial enumeration](./README.md) • [🏠 Master Course Index](../README.md)
