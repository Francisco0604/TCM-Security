# 📁 Docker

> **Curriculum:** TCM Security — Linux Privilege Escalation  
> **Module Description:** Abusing docker socket / group membership to mount host filesystem root (/) and achieve instant host root takeover.

---

## 🎯 Learning Objectives & Methodology
Mastering **Docker** involves understanding both the attacker's path to root elevation and the system administrator's hardening requirements.

---



## 📝 Core Documentation & Lab Notes

THM - Ultratech

ip = 10.10.151.206

Nmap

```bash
21/tcp    vsftpd 3.0.3
22/tcp    OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
8081/tcp  Node.js Express framework
31331/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))

Aggressive OS guesses: Linux 4.15 (98%)
```

8081

```bash
**Browsered to the port and found :**
UltraTech API v0.1.3
```

31331

```bash
**Browsered to the port and found :**
The second comtact page gives the error of not found while revealing the apache info
```


![Privilege Escalation Proof Screenshot](./assets/031_Docker_1d7d64c5-e0cb-8098-9ce2-e95343bdbd28.png)
*Figure: Privilege Escalation Proof Screenshot*


Browse to robots.txt


![Privilege Escalation Proof Screenshot](./assets/032_Docker_1d7d64c5-e0cb-8071-963b-f6e834b28b6f.png)
*Figure: Privilege Escalation Proof Screenshot*

Browse to the sitmap which is provided


![Privilege Escalation Proof Screenshot](./assets/033_Docker_1d7d64c5-e0cb-8046-b403-ffc0499b87ea.png)
*Figure: Privilege Escalation Proof Screenshot*

Saw more webpages here
Opened the /partners.html


![Privilege Escalation Proof Screenshot](./assets/034_Docker_1d7d64c5-e0cb-80eb-ac01-df0f116ef817.png)
*Figure: Privilege Escalation Proof Screenshot*


Opened burp

Saw this weird ping request


![Privilege Escalation Proof Screenshot](./assets/035_Docker_1d7d64c5-e0cb-8029-8bed-f477991bcdb9.png)
*Figure: Privilege Escalation Proof Screenshot*

Copied the url and browsed to it


![Privilege Escalation Proof Screenshot](./assets/036_Docker_1d7d64c5-e0cb-809a-9ac3-d915da850b16.png)
*Figure: Privilege Escalation Proof Screenshot*

This seems like remote code execution is possible

And yes it is possible


![Privilege Escalation Proof Screenshot](./assets/037_Docker_1d7d64c5-e0cb-8089-acc4-ffd06687d713.png)
*Figure: Privilege Escalation Proof Screenshot*


```bash
`ls`
```
Used backticks instead of quotes it worked

Read the above file and got hash(with username) used crackstation to crack it


![Privilege Escalation Proof Screenshot](./assets/038_Docker_1d7d64c5-e0cb-80fe-ab2b-c083178d9386.png)
*Figure: Privilege Escalation Proof Screenshot*


Got access to the machine

Used the gtfobins to find docker shell exploit 
found
Elevated to root after using it (jst had to change some alibaba thing to bash)



---
[⬅ Back to Linux Privilege Escalation Master Index](../README.md)
