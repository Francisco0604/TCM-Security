# 🛡️ Domain Enumeration with Plumhound

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Attacking Active Directory: Post-Compromise Enumeration ](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Attacking Active Directory: Post-Compromise Enumeration  > Domain Enumeration with Plumhound`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Domain Enumeration with Plumhound** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

Sister of bloodhound
Search it on google wil get github pg of it go there copy that to the opt folder


![Lab Execution Screenshot / Proof of Exploit](./assets/116_Domain_Enumeration_with_Plumhound_1c7d64c5-e0cb-80e6-8c02-c7c9500e50f6.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

cd plumhound 
sudo pip install -r requirements,txt
—help (to check commands for yourself)

Check to c if it runs 


![Lab Execution Screenshot / Proof of Exploit](./assets/117_Domain_Enumeration_with_Plumhound_1c7d64c5-e0cb-802d-b0f0-de4dcb7a2356.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

This will pull down information from bloodhound and analyze it
Bloodhound should be open for this to work
-p is the neo4j password we set



![Lab Execution Screenshot / Proof of Exploit](./assets/118_Domain_Enumeration_with_Plumhound_1c7d64c5-e0cb-80fb-9254-d4150edc54bc.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

-x for exceute
This puts a lot of reports in a file
can read with index.html the whole thing
It gives a lot of information abt the system





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Attacking Active Directory: Post-Compromise Enumeration ](./README.md) • [🏠 Master Course Index](../README.md)
