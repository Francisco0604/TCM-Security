# 🛡️ Blackpearl

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [New capstone](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > New capstone > Blackpearl`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Blackpearl** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

check the pg source code 
directory busting


![Lab Execution Screenshot / Proof of Exploit](./assets/056_Blackpearl_1c5d64c5-e0cb-8049-9b89-db99e34bb73c.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

use -d otherwise won't work



![Lab Execution Screenshot / Proof of Exploit](./assets/057_Blackpearl_1c5d64c5-e0cb-80f2-a3a9-f4076f3d3a9f.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

We do this to say that balckpeal allocates to that ip address then dns will do its magic

close and open the site on the browser again 


![Lab Execution Screenshot / Proof of Exploit](./assets/058_Blackpearl_1c5d64c5-e0cb-80ad-9aa7-e544d11c46fb.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


do directory busting again using ffuf but this time use the name of the website which you saved in etc hosts 

type navigate cms exploit on google
Trying metasploit in vid can do manual as well
use metaspolit and again shell on meterpreter
Hav to do privilage escalation now

We got the shell but we can now c username@machinename $ (shell)


![Lab Execution Screenshot / Proof of Exploit](./assets/059_Blackpearl_1c5d64c5-e0cb-80d3-a7e4-e417629fe38e.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

tty shell can be used 
can google that


![Lab Execution Screenshot / Proof of Exploit](./assets/060_Blackpearl_1c5d64c5-e0cb-80d1-93e8-f102217d07c3.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


use linpeas to check for privilage escalation

u will find something interesting in SUID 
use the gtfopen to find ways to escalate privilages




### 🎯 Vulnerability & Exploit Analysis: Navigate CMS Unauthenticated RCE
- **Attack Chain:**
  1. **VHost / DNS Routing:** Analyzed `phpinfo()` on port 80; identified internal domain name `blackpearl.tcm`.
  2. **Navigate CMS Exploitation:** Discovered Navigate CMS instance; exploited unauthenticated arbitrary file upload in `navigate_upload.php` to upload PHP web shell.
  3. **Privilege Escalation:** Executed `find / -perm -u=s -type f 2>/dev/null`; identified SUID bit set on `/usr/bin/php7.3`. Executed `php -r "pcntl_exec('/bin/sh', ['-p']);"` to escalate directly to `root`.
- **Remediation & Hardening:**
  1. Restrict write permissions on web upload directories; disable PHP execution inside uploads.
  2. Remove unnecessary SUID permissions from binary utilities.


---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to New capstone](./README.md) • [🏠 Master Course Index](../README.md)
