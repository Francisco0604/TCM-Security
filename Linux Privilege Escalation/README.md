# Linux Privilege Escalation - Notes & Lab Walkthroughs

Study notes, practical escalation vectors, commands, and capstone machine write-ups based on the Linux Privilege Escalation course by TCM Security.

> **Note on Documentation Progression:**  
> Earlier modules reflect earlier stages of learning and practical note-taking, and are being progressively revised to current documentation standards.

---

## Course Modules

| # | Module | Topics Covered |
|---|---|---|
| 01 | [Introduction](./01_Introduction/README.md) | Linux filesystem hierarchy, permissions model (rwx/octal), course methodology |
| 02 | [Initial Enumeration](./02_Initial_Enumeration/README.md) | System, user, network, and process enumeration; password hunting |
| 03 | [Automated Tools](./03_Automated_Tools/README.md) | LinPEAS, LinEnum, Linux Exploit Suggester (LES), pspy process monitor |
| 04 | [Kernel Exploits](./04_Kernel_Exploits/README.md) | Kernel architecture discovery, C exploit compilation, Dirty COW / PwnKit |
| 05 | [Passwords & File Permissions](./05_Passwords_and_File_Permissions/README.md) | Stored passwords in configs, weak permissions on /etc/passwd and /etc/shadow, SSH keys |
| 06 | [Sudo Exploitation](./06_Sudo_Exploitation/README.md) | Sudo privileges (sudo -l), GTFOBins, LD_PRELOAD, CVE-2019-14287, Baron Samedit |
| 07 | [SUID / SGID Binaries](./07_SUID_SGID_Binaries/README.md) | SUID binaries, GTFOBins, Shared Object (.so) injection, symlinks, PATH hijacking |
| 08 | [Linux Capabilities](./08_Linux_Capabilities/README.md) | POSIX capabilities (getcap), cap_setuid, Python/Perl capability abuse |
| 09 | [Scheduled Tasks (Cron)](./09_Scheduled_Tasks_Cron/README.md) | Crontab auditing, writable scripts, wildcard argument injection, CMesS |
| 10 | [NFS Root Squashing](./10_NFS_Root_Squashing/README.md) | NFS no_root_squash misconfigurations, remote SUID root shell creation |
| 11 | [Docker Privilege Escalation](./11_Docker_Privilege_Escalation/README.md) | Docker socket and group abuse, mounting host root (/) to container |
| 12 | [Capstone Walkthroughs](./12_Capstone_Walkthroughs/README.md) | Capstone machine walkthroughs: LazyAdmin, Anonymous, and Tomghost |

---

## Cheatsheet & Quick Reference
- [Linux Privilege Escalation Master Cheat Sheet](./LINUX_PRIVESC_CHEATSHEET.md)
