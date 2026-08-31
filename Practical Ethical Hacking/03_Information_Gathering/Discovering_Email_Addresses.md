# 🛡️ Discovering Email Addresses

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Information Gathering](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Information Gathering > Discovering Email Addresses`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **Discovering Email Addresses** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


1. hunter.io

![Lab Execution Screenshot / Proof of Exploit](./assets/009_Discovering_Email_Addresses_1bfd64c5-e0cb-8075-9f58-f19ff9372516.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


After signing in with google you get more information 
eg. Checking in which department who works n no blur



![Lab Execution Screenshot / Proof of Exploit](./assets/010_Discovering_Email_Addresses_1bfd64c5-e0cb-8038-bbab-fa08b6447a6f.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


1. phonebook.cz
can search for domains and url also


![Lab Execution Screenshot / Proof of Exploit](./assets/011_Discovering_Email_Addresses_1bfd64c5-e0cb-8040-9d24-c93d34adb24e.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


1. voilanorbert.com


![Lab Execution Screenshot / Proof of Exploit](./assets/012_Discovering_Email_Addresses_1bfd64c5-e0cb-8038-943a-fa208774de49.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


4.clearbit

it has to be used in chrome.
It is a chrome extension which offers a lot of success

1. [tools.verifyemailaddres.io](http://4.tools.verifyemailaddres.io/) (emailhippo)
you can use this to verify email addresses



![Lab Execution Screenshot / Proof of Exploit](./assets/013_Discovering_Email_Addresses_1bfd64c5-e0cb-807f-80f4-fdb74fea6939.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*


1. email-checker.net/validate
can be used to validate the email 



![Lab Execution Screenshot / Proof of Exploit](./assets/014_Discovering_Email_Addresses_1bfd64c5-e0cb-8006-b37a-f06e3608b952.png)
*Figure: Lab Execution Screenshot / Proof of Exploit*





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Information Gathering](./README.md) • [🏠 Master Course Index](../README.md)
