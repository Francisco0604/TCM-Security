# Docker

Docker socket and group abuse, mounting host root (/) to container.

---



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

![Screenshot](./assets/031_Docker_1d7d64c5-e0cb-8098-9ce2-e95343bdbd28.png)

Browse to robots.txt

![Screenshot](./assets/032_Docker_1d7d64c5-e0cb-8071-963b-f6e834b28b6f.png)
Browse to the sitmap which is provided

![Screenshot](./assets/033_Docker_1d7d64c5-e0cb-8046-b403-ffc0499b87ea.png)
Saw more webpages here
Opened the /partners.html

![Screenshot](./assets/034_Docker_1d7d64c5-e0cb-80eb-ac01-df0f116ef817.png)

Opened burp

Saw this weird ping request

![Screenshot](./assets/035_Docker_1d7d64c5-e0cb-8029-8bed-f477991bcdb9.png)
Copied the url and browsed to it

![Screenshot](./assets/036_Docker_1d7d64c5-e0cb-809a-9ac3-d915da850b16.png)
This seems like remote code execution is possible

And yes it is possible

![Screenshot](./assets/037_Docker_1d7d64c5-e0cb-8089-acc4-ffd06687d713.png)

```bash
`ls`
```
Used backticks instead of quotes it worked

Read the above file and got hash(with username) used crackstation to crack it

![Screenshot](./assets/038_Docker_1d7d64c5-e0cb-80fe-ab2b-c083178d9386.png)

Got access to the machine

Used the gtfobins to find docker shell exploit 
found
Elevated to root after using it (just had to change some alibaba thing to bash)



---
[Back to Linux Privilege Escalation Index](../README.md)
