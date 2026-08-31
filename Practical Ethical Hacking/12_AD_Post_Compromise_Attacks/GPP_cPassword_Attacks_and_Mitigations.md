# 🛡️ GPP / cPassword Attacks and Mitigations

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Attacking Active Directory: Post-Compromise Attacks ](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Attacking Active Directory: Post-Compromise Attacks  > GPP / cPassword Attacks and Mitigations`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **GPP / cPassword Attacks and Mitigations** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

This is an older attack but there chances that it might just work 


![Lab Execution Screenshot / Proof of Exploit](./assets/169_GPP_cPassword_Attacks_and_Mitigations_1cad64c5-e0cb-8073-8edd-e6bf9d84de5b.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*




![Lab Execution Screenshot / Proof of Exploit](./assets/170_GPP_cPassword_Attacks_and_Mitigations_1cad64c5-e0cb-80b6-9bf4-d224c865fcd2.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Can do with metasploit as well
smb_enum_gpp


![Lab Execution Screenshot / Proof of Exploit](./assets/171_GPP_cPassword_Attacks_and_Mitigations_1cad64c5-e0cb-808c-86fc-c3741de9df43.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Mitigation


![Lab Execution Screenshot / Proof of Exploit](./assets/172_GPP_cPassword_Attacks_and_Mitigations_1cad64c5-e0cb-80fe-b2c6-f3c4bba623e4.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Attacking Active Directory: Post-Compromise Attacks ](./README.md) • [🏠 Master Course Index](../README.md)
