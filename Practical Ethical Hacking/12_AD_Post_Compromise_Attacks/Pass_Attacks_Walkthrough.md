# 🛡️ Pass Attacks Walkthrough

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Attacking Active Directory: Post-Compromise Attacks ](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Attacking Active Directory: Post-Compromise Attacks  > Pass Attacks Walkthrough`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Pass Attacks Walkthrough** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

Crackmapexec —help (to know more abt the protocols tha can be used in this thing)



![Lab Execution Screenshot / Proof of Exploit](./assets/130_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-803a-933c-fa1d80538a7d.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


It will attemp to log in on few machines which are part of the ip range/domain



![Lab Execution Screenshot / Proof of Exploit](./assets/131_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-8079-8a74-c7e44a256aa6.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


In the above img we got log in into 2 machine which are THEPUNISHER and SPIDERMAN [+]
Successful Autentication happened in hydra-dc but we are not the local admin there [+]
WONDERLAND is an example of unsuccessful log in [-]

Now that we have access to the machine, the strategy would be to dump information such as hash etc using a tool like secretsdump 

We can do the same using a hash if we can not crack the hash


![Lab Execution Screenshot / Proof of Exploit](./assets/132_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-80c3-8e5d-d22ea07bc7dc.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


This can be done only with ntlmv1 and not with ntlmv2(ntlmv2 can be replayed)

can use —sam to dump information from security account manager


![Lab Execution Screenshot / Proof of Exploit](./assets/133_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-808b-b8af-cd9a930b366a.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


the data is stored in the database


![Lab Execution Screenshot / Proof of Exploit](./assets/134_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-80ab-8c91-e844f277fc39.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


We can do —shares to enumerate the shares and c to what we have access to


![Lab Execution Screenshot / Proof of Exploit](./assets/135_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-80c4-9da7-c423dc51a76c.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*




![Lab Execution Screenshot / Proof of Exploit](./assets/136_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-80d6-a496-d6c7928f6e5d.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


We can also look at —lsa it will dump out the local security authority


![Lab Execution Screenshot / Proof of Exploit](./assets/137_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-807b-9bd5-fa0655dac926.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


This information may or may not be usefull but it is better to check
Can attemp to crack the hashes which you get using this locally and then log in to the machine 

To use module type -M (module name)


![Lab Execution Screenshot / Proof of Exploit](./assets/138_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-800d-8fdd-d24b3f859183.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

It will dump out hashes if they were recently stored

Type cmedb to enter the crackmapexec database


![Lab Execution Screenshot / Proof of Exploit](./assets/139_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-80ad-a935-f14545220386.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

type help to get more details




---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Attacking Active Directory: Post-Compromise Attacks ](./README.md) • [🏠 Master Course Index](../README.md)
