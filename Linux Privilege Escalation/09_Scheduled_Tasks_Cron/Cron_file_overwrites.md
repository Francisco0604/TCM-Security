# 🛡️ Cron file overwrites

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [Scheduled tasks](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > Scheduled tasks > Cron file overwrites`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **Cron file overwrites**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit


Always start by


```bash
 cat /etc/crontab
```

So for this example we see the [overwrite.sh](http://overwrite.sh/) being there
We check where it is located using the locate command
and then we check for our permissions


![Privilege Escalation Proof Screenshot](./assets/029_Cron_file_overwrites_1d6d64c5-e0cb-8039-af39-d4fd2bde9a99.png)
*Figure: Privilege Escalation Proof Screenshot*

As we can see, We have the read and write permission but not the execute. But it is getting executed in the crontab (Since we have permission to overwrite it we can do that using a reverse shell only very easily. This is very common where we have the overwrite permissions and it is getting executed as root on crontab, its a easy win)

For now we do the following

```bash
echo 'cp /bin/bash /tmp/bash; chmod +s /tmp/bash' >> /usr/local/bin/overwrite.sh
```


---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to Scheduled tasks](./README.md) • [🏠 Master Course Index](../README.md)
