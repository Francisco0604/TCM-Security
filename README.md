# 🛡️ TCM Security - Penetration Testing & Cybersecurity Portfolio

![Security](https://img.shields.io/badge/Security-Offensive%20%26%20Defensive-red.svg)
![Certifications](https://img.shields.io/badge/Certifications-PNPT%20%7C%20OSCP%20%7C%20eJPT-blue.svg)
![Status](https://img.shields.io/badge/Status-Active%20Knowledge%20Base-brightgreen.svg)

Welcome to the **TCM Security** offensive and defensive cybersecurity repository. This repository serves as a centralized hub for hands-on course write-ups, enterprise lab walkthroughs, Active Directory attack graphs, web security assessments, privilege escalation methodologies, and capstone machine proofs of work completed across **TCM Security** training tracks.

> [!NOTE]
> **Note on Documentation Progression:**  
> Earlier modules reflect earlier stages of learning and practical note-taking, and are being progressively revised and expanded to current documentation standards.

---

## 📚 Courses & Certification Tracks

| Course / Certification Path | Description | Status |
|---|---|---|
| 📂 [**Practical Ethical Hacking (PEH)**](./Practical%20Ethical%20Hacking/README.md) | Flagship ethical hacking curriculum: 21 modules covering Networking, OSINT, Scanning, Active Directory (Initial $\rightarrow$ Domain Compromise), Web App Pentesting, Wireless, and 5 Capstone Machines. | ✅ **Completed Track** (Notes & Lab Proofs) |
| 📂 [**Linux Privilege Escalation**](./Linux%20Privilege%20Escalation/README.md) | Comprehensive local privilege escalation curriculum: 12 modules covering System Enumeration, Kernel Exploits, Sudo Misconfigurations (`LD_PRELOAD`), SUID Binaries, POSIX Capabilities, Cron Wildcards, NFS `no_root_squash`, Docker Escapes, and 3 Capstone Machines. | ✅ **Completed Track** (Notes & Lab Proofs) |

---

## 🚀 Featured Showcases

### 1. 🛡️ [Practical Ethical Hacking (PEH)](./Practical%20Ethical%20Hacking/README.md)
- 📖 [**PEH Master Dashboard & MITRE ATT&CK Mapping**](./Practical%20Ethical%20Hacking/README.md)
- ⚡ [**Pentester's Master Playbook & CLI Cheat Sheet**](./Practical%20Ethical%20Hacking/PENTESTER_PLAYBOOK_CHEATSHEET.md)
- 🎯 [**Capstone Machine Walkthroughs**](./Practical%20Ethical%20Hacking/08_New_Capstone/README.md) (*Blue, Academy, Dev, Butler, Blackpearl*)
- 🏰 [**Active Directory Attack Series**](./Practical%20Ethical%20Hacking/10_AD_Initial_Attack_Vectors/README.md) (*LLMNR, SMB Relay, BloodHound, Kerberoasting, Mimikatz, DCSync, Golden Tickets*)

### 2. 🐧 [Linux Privilege Escalation](./Linux%20Privilege%20Escalation/README.md)
- 📖 [**Linux PrivEsc Dashboard & Attack Matrix**](./Linux%20Privilege%20Escalation/README.md)
- ⚡ [**Linux PrivEsc Master CLI Cheat Sheet**](./Linux%20Privilege%20Escalation/LINUX_PRIVESC_CHEATSHEET.md)
- 🏆 [**Capstone Machine Walkthroughs**](./Linux%20Privilege%20Escalation/12_Capstone_Walkthroughs/README.md) (*LazyAdmin, Anonymous, Tomghost / Ghostcat*)
- 🔬 [**Sudo & SUID Exploitation Guides**](./Linux%20Privilege%20Escalation/06_Sudo_Exploitation/README.md) (*LD_PRELOAD, GTFOBins, CVE-2019-14287, Baron Samedit*)

---

## 🔒 Confidentiality & Data Sanitization Notice

All write-ups, configuration scripts, terminal outputs, and proof screenshots within this repository have been strictly sanitized:
- **Zero Live Secrets:** Internal API keys, tokens, and sensitive strings are scrubbed (`[REDACTED]`).
- **Private Identifiers:** Personal emails and real user identity tokens are obfuscated.
- **Isolated Testing Subnets:** Target IPs and domain environments shown represent isolated testing environments (`10.0.2.x`, `192.168.182.x`, `marvel.local`, `htb.local`, `thm.local`).

---

*Maintained by Francisco Afonso • Portfolio & Lab Proofs.*
