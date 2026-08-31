# Domain Enumeration with bloodhound


Install blood hound

```bash
sudo pip install bloodhound
```

run

```bash
sudo neo4j console
```
This is requied for us to use blood hound


![Screenshot](./assets/114_Domain_Enumeration_with_bloodhound_1c7d64c5-e0cb-8042-96c5-e953488f7b12.png)
it will give you this link, open it
Username: neo4j : password: neo4j
It might ask you to change password always remember the password 

Run blood hound

```bash
sudo bloodhound
```
I will ask you for the username and password of neo4j


![Screenshot](./assets/115_Domain_Enumeration_with_bloodhound_1c7d64c5-e0cb-8021-a3d6-f0ba9fe3cc09.png)
-d is for domain
-ns is for name server (domain controller ip)
-c is for what are you collecting

Import all the information in blood hound
Go to the analyis tab on top
It displays all the ifo in a graphical manner 


---
[Back to Attacking Active Directory: Post-Compromise Enumeration ](./README.md)
