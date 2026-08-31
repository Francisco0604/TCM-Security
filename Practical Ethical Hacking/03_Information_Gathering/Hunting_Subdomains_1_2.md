# 🛡️ Hunting Subdomains 1 & 2

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Information Gathering](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Information Gathering > Hunting Subdomains 1 & 2`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Hunting Subdomains 1 & 2** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


1. Can use sublist3r to find domains 

![Lab Execution Screenshot / Proof of Exploit](./assets/016_Hunting_Subdomains_1_2_1bfd64c5-e0cb-80ea-aad0-dfdb7a3f2bfe.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


It searches through a lot of things


![Lab Execution Screenshot / Proof of Exploit](./assets/017_Hunting_Subdomains_1_2_1bfd64c5-e0cb-80a0-95c2-d0bced6a0c49.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


1. crt.sh
We can use this for certificate fingerprinting



![Lab Execution Screenshot / Proof of Exploit](./assets/018_Hunting_Subdomains_1_2_1bfd64c5-e0cb-80ad-afd6-ccf72609e7bd.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


1. Owasp AmassOne of the most popular and go to tools. Can find a lot more domains with this 


![Lab Execution Screenshot / Proof of Exploit](./assets/019_Hunting_Subdomains_1_2_1bfd64c5-e0cb-80f2-9b69-ffcb9eeca3a9.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


1. tomnomnomCan be used to probe the domains to check if they are alive


![Lab Execution Screenshot / Proof of Exploit](./assets/020_Hunting_Subdomains_1_2_1bfd64c5-e0cb-80a3-a301-cd75e1ebf870.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*






---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Information Gathering](./README.md) • [🏠 Master Course Index](../README.md)
