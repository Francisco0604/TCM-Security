# 🛡️ User Enumeration

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [Initial enumeration](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > Initial enumeration > User Enumeration`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **User Enumeration**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit


We will do this to find out who we are and what permission we are allowed 

To find out who you are

```bash
whoami
```

To check our id (user id, grp id(user/admin)

```bash
id
```

To check what privileges we hav 

```bash
sudo -l
```

To check if can read files
To check all users

```bash
cat etc/passwd
```
To just get the usernames

```bash
cat etc/passwd | cut -d : -f 1
```

To check if we can read sensitive files

```bash
cat etc/shadow
```

To check if there is anything good in history typed before

```bash
history
```



---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to Initial enumeration](./README.md) • [🏠 Master Course Index](../README.md)
