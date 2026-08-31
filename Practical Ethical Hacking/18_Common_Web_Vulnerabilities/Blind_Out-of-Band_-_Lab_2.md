# 🛡️ Blind / Out-of-Band - Lab 2

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Common Web Vulnerabilities](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Common Web Vulnerabilities > Blind / Out-of-Band - Lab 2`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Blind / Out-of-Band - Lab 2** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence




![Lab Execution Screenshot / Proof of Exploit](./assets/240_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-80ca-b1ab-e87946496cdb.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

The Search is reflected back in the target
We do not get any more response from the web pg, the Website OK is a status 200



![Lab Execution Screenshot / Proof of Exploit](./assets/241_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-80b4-b624-d64c747eaff1.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

If we enter any bs then we get Website not found 


```bash
tcm-sec.com; whoami; asd
```
we get Website Found on this


![Lab Execution Screenshot / Proof of Exploit](./assets/242_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-808f-8ac0-f9af4dfe3569.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

If notice carefully can see that the ‘ ; ‘ is missing in the target even though we searched for it
so what is happening is it is filtering out the semi colons 

To get the proper response of this we will have to set up a webserver (can use netcat or webhooks.site, jst do not use webhooks in an actual bug bounty or pentest because we do not wnt to leak data)

Then can try to insert a command with “backticks”

```bash
?'whoami'
```

Can use the following to make request to ourself
Goal of this was to check if can get another line of code execution with \n


![Lab Execution Screenshot / Proof of Exploit](./assets/243_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-8068-80a2-f26b426dd0a7.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

Set a python server


![Lab Execution Screenshot / Proof of Exploit](./assets/244_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-8069-9e6d-fb22ba247186.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

Since we know that the semi colon is getting filtered we will avoid using payloads with php

In this case we will try to upload a shell and trigger it

So ya, do this


![Lab Execution Screenshot / Proof of Exploit](./assets/245_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-8019-af37-f7a200e07347.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


then well, do this 


![Lab Execution Screenshot / Proof of Exploit](./assets/246_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-80c5-a038-e7c4608b305c.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


open the python webserver in tmp folder since the file is there


![Lab Execution Screenshot / Proof of Exploit](./assets/247_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-804b-a362-dd8b2829c902.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Rename file (Not important but he normally uses this)


![Lab Execution Screenshot / Proof of Exploit](./assets/248_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-8091-a649-ff3b937f3304.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

Set up http server with pyhton in this

Then final step


![Lab Execution Screenshot / Proof of Exploit](./assets/249_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-80b9-80a6-d5696a004f91.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


This method which was shown above may not work anymore 

{ interrupt
New method


![Lab Execution Screenshot / Proof of Exploit](./assets/250_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-80e3-9617-f38dadfa24ad.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

 interrupt over }

We can now set up a listener on netcat
And open the rev.php on localhost
we should get the shell





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Common Web Vulnerabilities](./README.md) • [🏠 Master Course Index](../README.md)
