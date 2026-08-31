# 🛡️ Password hunting

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [Initial enumeration](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > Initial enumeration > Password hunting`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **Password hunting**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit


quick dirty commands for password hunting are

To colour cordinate
This will grab everything that conatins the “PASSWORD=” in files

```bash
grep --color=auto -rnw '/' -ie "PASSWORD=" --color=always 2> dev/null
```

To locate any file with the name password  (we can use many variations instead of password like pass, pwd and many more )

```bash
locate password | more
locate pass | more
```

To hunt down ssh keys (again can use many variations

```bash
find / -name -id_rsa 2> /dev/null
find / -name authorized_keys 2> /dev/null
```

To find password of hidden files 

```bash
grep -r "password" . --include=".*"
```

If too many permission denied and invalid argument

```bash
grep -r "password" . --include=".*" 2>&1 | grep -v "Permission denied" | grep -v "Invalid argument"
```



---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to Initial enumeration](./README.md) • [🏠 Master Course Index](../README.md)
