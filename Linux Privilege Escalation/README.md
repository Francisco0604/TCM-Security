# 🐧 Linux Privilege Escalation
## Comprehensive Offensive Methodology, Lab Proofs & Capstone Walkthroughs

![Linux Security](https://img.shields.io/badge/OS-Linux%20Hardening-yellow.svg)
![Privilege Escalation](https://img.shields.io/badge/PrivEsc-Local%20Elevation%20%28LPE%29-red.svg)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE-Privilege%20Escalation-blue.svg)
![Status](https://img.shields.io/badge/Coursework-100%25%20Complete-brightgreen.svg)

---

## 📜 Executive Summary & Author Proof Statement

This repository contains the complete, hands-on technical write-ups, vulnerability mechanics, and defensive hardening strategies completed as part of **TCM Security's Linux Privilege Escalation** curriculum.

The documentation covers every practical vector required to escalate from a low-privileged system shell to full `root` administrative compromise on Linux systems:
1. **Manual & Automated System Enumeration** (*OS architecture, environment, listening ports, process tracking with `pspy`*)
2. **Kernel Exploitation** (*Dirty COW, PwnKit, OverlayFS, compiling local exploits*)
3. **Password & Credential Exposure** (*Config scraping, `/etc/passwd` & `/etc/shadow` misconfigurations, unencrypted SSH keys*)
4. **Sudo Misconfigurations** (*`sudo -l` GTFOBins escapes, `LD_PRELOAD` shared library injection, CVE-2019-14287, CVE-2021-3156*)
5. **SUID / SGID & Shared Object Injection** (*SUID binaries, `.so` library hijacking, PATH hijacking*)
6. **POSIX Capabilities Abuse** (*`cap_setuid`, `cap_dac_read_search`, Python/Perl capabilities*)
7. **Scheduled Tasks & Crontab** (*Writable scripts, wildcard argument injection with `tar`/`rsync`, systemd timers*)
8. **NFS `no_root_squash` & Docker Group Takeovers**
9. **Capstone Machine Assessments** (*LazyAdmin, Anonymous, Tomghost / Ghostcat*)

---

## 🎯 MITRE ATT&CK® Enterprise Mapping

| MITRE ATT&CK Tactic | Technique ID | Technique Name | Demonstrated In Module |
|---|---|---|---|
| **Discovery** | `T1082` | System Information Discovery | [Module 02](./02_Initial_Enumeration/README.md) |
| **Discovery** | `T1087.001` | Local Account Discovery | [Module 02](./02_Initial_Enumeration/README.md) |
| **Discovery** | `T1057` | Process Discovery (`pspy` / `ps aux`) | [Module 02 & 03](./03_Automated_Tools/README.md) |
| **Credential Access** | `T1552.001` | Credentials in Files (History, Configs) | [Module 05](./05_Passwords_and_File_Permissions/README.md) |
| **Privilege Escalation** | `T1068` | Exploitation for Privilege Escalation (Kernel) | [Module 04](./04_Kernel_Exploits/README.md) |
| **Privilege Escalation** | `T1548.003` | Sudo and Sudo Caching | [Module 06](./06_Sudo_Exploitation/README.md) |
| **Privilege Escalation** | `T1548.001` | Setuid and Setgid Binaries | [Module 07](./07_SUID_SGID_Binaries/README.md) |
| **Privilege Escalation** | `T1053.003` | Scheduled Task/Job: Cron & Timers | [Module 09](./09_Scheduled_Tasks_Cron/README.md) |
| **Privilege Escalation** | `T1611` | Escape to Host (Docker / Containers) | [Module 11](./11_Docker_Privilege_Escalation/README.md) |
| **Lateral Movement / PrivEsc** | `T1021.002` | Remote Services: SMB / NFS `no_root_squash` | [Module 10](./10_NFS_Root_Squashing/README.md) |

---

## 📚 Linux Privilege Escalation Modules

| # | Module Folder | Scope & Key Laboratory Topics | Status |
|---|---|---|---|
| **01** | [**01_Introduction**](./01_Introduction/README.md) | Linux Architecture, Permissions Model (rwx/Octal), Course Methodology | ✅ Complete |
| **02** | [**02_Initial_Enumeration**](./02_Initial_Enumeration/README.md) | System, User, Network, and Process Enumeration, Password Hunting | ✅ Complete |
| **03** | [**03_Automated_Tools**](./03_Automated_Tools/README.md) | LinPEAS, LinEnum, Linux Exploit Suggester (LES), `pspy` Process Monitor | ✅ Complete |
| **04** | [**04_Kernel_Exploits**](./04_Kernel_Exploits/README.md) | Kernel Architecture Identification, C Exploit Compilation, Dirty COW / PwnKit | ✅ Complete |
| **05** | [**05_Passwords_and_File_Permissions**](./05_Passwords_and_File_Permissions/README.md) | Stored Passwords, Weak Permissions on `/etc/passwd` & `/etc/shadow`, SSH Keys | ✅ Complete |
| **06** | [**06_Sudo_Exploitation**](./06_Sudo_Exploitation/README.md) | Sudo Rights (`sudo -l`), GTFOBins, `LD_PRELOAD`, CVE-2019-14287, Baron Samedit | ✅ Complete |
| **07** | [**07_SUID_SGID_Binaries**](./07_SUID_SGID_Binaries/README.md) | SUID Binaries, GTFOBins, Shared Object (`.so`) Injection, Symlinks, PATH Hijacking | ✅ Complete |
| **08** | [**08_Linux_Capabilities**](./08_Linux_Capabilities/README.md) | POSIX Capabilities (`getcap`), `cap_setuid`, Python/Perl Capability Abuse | ✅ Complete |
| **09** | [**09_Scheduled_Tasks_Cron**](./09_Scheduled_Tasks_Cron/README.md) | Crontab Auditing, Writable Scripts, Wildcard Tar/Rsync Injection, CMesS | ✅ Complete |
| **10** | [**10_NFS_Root_Squashing**](./10_NFS_Root_Squashing/README.md) | NFS `no_root_squash` Misconfigurations, Remote SUID Shell Creation | ✅ Complete |
| **11** | [**11_Docker_Privilege_Escalation**](./11_Docker_Privilege_Escalation/README.md) | Docker Socket & Group Abuse, Mounting Host Root (`/`) to Container | ✅ Complete |
| **12** | [**12_Capstone_Walkthroughs**](./12_Capstone_Walkthroughs/README.md) | Capstone Walkthroughs: **LazyAdmin**, **Anonymous**, and **Tomghost (Ghostcat)** | ✅ Complete |

---

## ⚡ Quick Reference
- 📖 [**Linux Privilege Escalation Master Cheat Sheet**](./LINUX_PRIVESC_CHEATSHEET.md) — Comprehensive command syntax, one-liners, and exploitation templates.

---

## 🔒 Confidentiality & Data Sanitization Notice
All write-ups, configuration scripts, terminal outputs, and proof screenshots within this repository have been strictly sanitized (`[REDACTED]`) and represent isolated laboratory testbeds (`10.0.2.x`, `192.168.182.x`, `thm.local`).

---

*Maintained by Francisco Afonso • TCM Security Linux Privilege Escalation.*
