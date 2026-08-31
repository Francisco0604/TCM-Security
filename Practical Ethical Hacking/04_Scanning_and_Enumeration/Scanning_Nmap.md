# 🛡️ Scanning & Nmap

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Scanning and enumeration](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Scanning and enumeration > Scanning & Nmap`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Scanning & Nmap** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence

Some issues happened with the box, so the login was provided directly


![Lab Execution Screenshot / Proof of Exploit](./assets/024_Scanning_Nmap_1c0d64c5-e0cb-8029-a9b0-e78777856d2e.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


By using the following command we check all the devices on the network using arp 


![Lab Execution Screenshot / Proof of Exploit](./assets/025_Scanning_Nmap_1c0d64c5-e0cb-80a7-934e-ca445d15188b.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


Nmap

-sS (stealt scan)  (SYN SYN-ACK RST) (can be detected if the target has good security)

-T4 (this is used to determine the speed, T1 is really slow and T5 is really fst, T5 may miss some packets because its too fst)

-p- all pots
If we do not mention any ports nmap will scan the top 1000 ports which are most common
Whenn scanning its always a good idea to scan alll the ports

-A this scans for everything (version info, os info etc) combination of (-sV , -sC, -O and traceroute)

-sU this a udp scan, udp takes long time to scan so usualy just scan the top 1000 

Next step is to check the version info and see if there are in vulnerabilities present for them





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Scanning and enumeration](./README.md) • [🏠 Master Course Index](../README.md)
