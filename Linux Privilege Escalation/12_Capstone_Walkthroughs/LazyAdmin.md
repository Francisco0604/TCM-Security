# 🛡️ LazyAdmin

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [Capstone](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > Capstone > LazyAdmin`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **LazyAdmin**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit


ip= 10.10.17.117

Apache 2.4.18


![Privilege Escalation Proof Screenshot](./assets/040_LazyAdmin_1d8d64c5-e0cb-804e-9d45-df4f43a5f656.png)
*Figure: Privilege Escalation Proof Screenshot*


Wepalyzer - OS ubuntu 


![Privilege Escalation Proof Screenshot](./assets/041_LazyAdmin_1d8d64c5-e0cb-80cf-931b-c97281605194.png)
*Figure: Privilege Escalation Proof Screenshot*


Did directory busting and found pg by sweet rice


![Privilege Escalation Proof Screenshot](./assets/042_LazyAdmin_1d8d64c5-e0cb-805e-8aa0-d64bf49680c7.png)
*Figure: Privilege Escalation Proof Screenshot*


Found this as an exploit by googling


![Privilege Escalation Proof Screenshot](./assets/043_LazyAdmin_1d8d64c5-e0cb-8018-a2c8-ec93d2babc18.png)
*Figure: Privilege Escalation Proof Screenshot*


Downloaded the file and found password in hash and a username
(got too focused and fogot to write notes, below is wtever i remember)

There was another directory for log in 
Used that
Put the passward and username in that and got login
There was a place to upload files uploaded a reverse shell there with listner on nc
Got shell
Used sudo -l
Found that i hav privilage of perl and backup with no password
The backup file had a reverse shell listner command like
I put my ip there 
And i got a reverse shell again but this time as root



---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to Capstone](./README.md) • [🏠 Master Course Index](../README.md)
