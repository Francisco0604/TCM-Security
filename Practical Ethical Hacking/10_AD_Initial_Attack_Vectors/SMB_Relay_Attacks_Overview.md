# 🛡️ SMB Relay Attacks Overview

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Attacking Active Directory: Initial Attack Vectors](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Attacking Active Directory: Initial Attack Vectors > SMB Relay Attacks Overview`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **SMB Relay Attacks Overview** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

If hash cant b cracked, can use smb replay if it is enabled or target machine to ain access


![Lab Execution Screenshot / Proof of Exploit](./assets/088_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-80ac-b9a7-cdb831eece17.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


We can use nmap to check the snb port. We are mainly looking for “ Message siging enabled but not required “ . This can be used as a proof of concept as well


![Lab Execution Screenshot / Proof of Exploit](./assets/089_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-80ad-8f02-d98000b3125f.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Rember we had said everything below should be on, But for this attack we need the snb and http to be off because we jst dont need tht to captured but we want to relay them 


![Lab Execution Screenshot / Proof of Exploit](./assets/090_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-8059-bc63-eba5df82c008.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Run responder


![Lab Execution Screenshot / Proof of Exploit](./assets/091_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-8085-89aa-e258f630823f.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Set up relay


![Lab Execution Screenshot / Proof of Exploit](./assets/092_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-807d-a539-ca311490a53f.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*

When responder catches a hash it will forward that to this 

Make an evnt to occur


![Lab Execution Screenshot / Proof of Exploit](./assets/093_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-803d-b92f-c21251de9ea7.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*




![Lab Execution Screenshot / Proof of Exploit](./assets/094_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-8049-97ef-d7cf956c8fba.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Other alternative wins (pay attention to the commands )

We can add a -I to get an interactive shell


![Lab Execution Screenshot / Proof of Exploit](./assets/095_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-80cb-9dbd-d19027e9bb93.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*




![Lab Execution Screenshot / Proof of Exploit](./assets/096_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-80cc-aac1-d2002e933cf8.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


The following whoami can be used as proof of concept


![Lab Execution Screenshot / Proof of Exploit](./assets/097_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-800a-844d-c2ed6e0af801.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*






---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Attacking Active Directory: Initial Attack Vectors](./README.md) • [🏠 Master Course Index](../README.md)
