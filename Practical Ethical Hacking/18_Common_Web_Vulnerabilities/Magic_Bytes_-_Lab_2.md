# 🛡️ Magic Bytes - Lab 2

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Common Web Vulnerabilities](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Common Web Vulnerabilities > Magic Bytes - Lab 2`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Magic Bytes - Lab 2** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


We ran the same things as lab well
But it did not work because here the checks are happening server side 


```bash
filename="eg.php"
```
This could not be uploaded since the server side is accepting only png or jpg in its checks

some ways to bypass this

```bash
filename="eg.php.png"  #If the htaccess file is not configured properly this will be accepted, beacuse it will try and regex .php without including .png
filename="eg.php." #extra . before png may help in some old cases
filename="eg..php" #extra . before png may help in some old cases
filename="eg.php%00.png" #null bite discards the .png wil work in some old machine
```
Another way we can use is try to upload a special htaccess file that will let us execute .asd as .php

Another thing to check if the response is 
magic bytes : they are the first few bites of the file which tell the machine what type of file it is 
Eg.


![Lab Execution Screenshot / Proof of Exploit](./assets/259_Magic_Bytes_-_Lab_2_1ced64c5-e0cb-8016-95cc-fffcc5c43d69.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

The above is the magic byte for a png file

So we did the following


![Lab Execution Screenshot / Proof of Exploit](./assets/260_Magic_Bytes_-_Lab_2_1ced64c5-e0cb-80c2-9059-ef5c4f69e39f.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

We added the payload in the png file data
And then changed the filename to .php to execute
We were still getting some error when we tried to do RCE through the url
so we edited a bit


![Lab Execution Screenshot / Proof of Exploit](./assets/261_Magic_Bytes_-_Lab_2_1ced64c5-e0cb-80ba-b870-d00865487a76.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

We cut most the middle data of the png file

And it worked

Tips: If there is website which has a blocklist in place for .php
We can try other php extensions with the same php payload
Go the image for google


![Lab Execution Screenshot / Proof of Exploit](./assets/262_Magic_Bytes_-_Lab_2_1ced64c5-e0cb-801e-9e46-cf1f121a86df.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


We also upload special files which will trick the web server in to using a custom file extension for execution




---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Common Web Vulnerabilities](./README.md) • [🏠 Master Course Index](../README.md)
