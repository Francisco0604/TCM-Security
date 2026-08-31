# 🛡️ Stored passwords

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [Passwords & File Permissions](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > Passwords & File Permissions > Stored passwords`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **Stored passwords**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit


Usually it is a best practice to check the history of the commands ran when u get into a machine
Even looking at bash history is a good thing 

```bash
ls -la
#somthing o bash history will pop up use cat on it
```

In the vid


![Privilege Escalation Proof Screenshot](./assets/006_Stored_passwords_1d1d64c5-e0cb-8033-83e1-c9976edaad2f.png)
*Figure: Privilege Escalation Proof Screenshot*

We already got the password here only

Another way to go about this is by using linpeas
Specifically going  on the linpeas pg on github and goin to the section where the stored passwords are there and using their commands
Ofcourse running the whole linpeas is grt

somtimes the passwords are stored in plain text in the ovpn file
So better to cat those and see for yourself if anything is there 



---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to Passwords & File Permissions](./README.md) • [🏠 Master Course Index](../README.md)
