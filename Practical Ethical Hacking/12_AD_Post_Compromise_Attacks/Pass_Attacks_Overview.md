# 🛡️ Pass Attacks Overview

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Attacking Active Directory: Post-Compromise Attacks ](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Attacking Active Directory: Post-Compromise Attacks  > Pass Attacks Overview`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Pass Attacks Overview** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

we can use knwn passwords and hash to do lateral movement 


![Lab Execution Screenshot / Proof of Exploit](./assets/119_Pass_Attacks_Overview_1c9d64c5-e0cb-8056-b390-dce04e5f1dd1.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


We can use crackmapexec, It is used to password 
The passowed we might have captured from anywhere (responder, glabal hash etc)



![Lab Execution Screenshot / Proof of Exploit](./assets/120_Pass_Attacks_Overview_1c9d64c5-e0cb-80e3-b3ea-d9ce3fdfb4d0.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


can also do this  using hash which can get from metasploit 


![Lab Execution Screenshot / Proof of Exploit](./assets/121_Pass_Attacks_Overview_1c9d64c5-e0cb-806e-b0a9-e8d6b547dd1d.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


or can use secretsdump (it can also c all the accounts tied up in the machine and domain)


![Lab Execution Screenshot / Proof of Exploit](./assets/122_Pass_Attacks_Overview_1c9d64c5-e0cb-8055-9776-f5a2094d9405.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


this is how to pass the hash


![Lab Execution Screenshot / Proof of Exploit](./assets/123_Pass_Attacks_Overview_1c9d64c5-e0cb-8000-96bf-ce0d8087375f.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


we can do alot of things using crackmapexec
Like dumping the sam


![Lab Execution Screenshot / Proof of Exploit](./assets/124_Pass_Attacks_Overview_1c9d64c5-e0cb-80a2-9aa4-efcca3b3ec7a.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


can also enumerate shares


![Lab Execution Screenshot / Proof of Exploit](./assets/125_Pass_Attacks_Overview_1c9d64c5-e0cb-80ff-8d9d-d7ef26c4aa3c.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


also lsa (local security authority)


![Lab Execution Screenshot / Proof of Exploit](./assets/126_Pass_Attacks_Overview_1c9d64c5-e0cb-807f-924c-cba6b0e66164.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


It also has inbuilt modules


![Lab Execution Screenshot / Proof of Exploit](./assets/127_Pass_Attacks_Overview_1c9d64c5-e0cb-80bb-9401-ea69e53bcede.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


lsassy one of the modules, can be used to dump out lsass (they enforce the security polices) and it also stores credentials. If there is active user login we may b able to dump out the credentials


![Lab Execution Screenshot / Proof of Exploit](./assets/128_Pass_Attacks_Overview_1c9d64c5-e0cb-8097-ae90-f492efaba16c.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


It also has a database. it shows where all the users worked and wt passwords they have 


![Lab Execution Screenshot / Proof of Exploit](./assets/129_Pass_Attacks_Overview_1c9d64c5-e0cb-80fd-a77e-f6e907b03cc2.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*






---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Attacking Active Directory: Post-Compromise Attacks ](./README.md) • [🏠 Master Course Index](../README.md)
