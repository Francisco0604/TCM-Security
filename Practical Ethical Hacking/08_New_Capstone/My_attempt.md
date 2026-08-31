# My attempt

192.168.182.129/24

21/tcp open  ftp     vsftpd 3.0.3

22/tcp open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)

Apache httpd 2.4.38 ((Debian))


![Screenshot](./assets/044_My_attempt_1c1d64c5-e0cb-80f4-bd98-db65a3f08b64.png)
Version information displayed during error

Connected using ftp

read the file

![Screenshot](./assets/045_My_attempt_1c1d64c5-e0cb-80c0-8e47-fcf050c50bd7.png)

Password in hash : cd73502828457d15655bbd7a63fb0bc8
Used [https://crackstation.net/](https://crackstation.net/) to crack the hashed password

![Screenshot](./assets/046_My_attempt_1c1d64c5-e0cb-8075-b1c2-eed560928b0d.png)

Password : student

used ffuf to do directory busting 

went to academy and logged in

Found that the upload img was not validated correctly 

Downloaded a reverse shel

got shell on target but no sudo privilage

now to escalate privilage i downloaded [linpeas.sh](http://linpeas.sh/) amd then host a python http server


---
[Back to New capstone](./README.md)
