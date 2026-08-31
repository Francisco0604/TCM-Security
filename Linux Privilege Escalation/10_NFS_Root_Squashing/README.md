# NFS Root Squashing

NFS no_root_squash misconfigurations, remote SUID root shell creation.

---





```bash
cat /etc/exports
```
Check for folders with no root squash
(what it means is, the folder will be sharable and can be mounted if there is no root squash)

then we do this

![Screenshot](./assets/030_NFS_Root_Squashing_1d7d64c5-e0cb-80a1-a707-cb97f27e5fac.png)

then we give it +s by using chmod 
then we just need to execute that file
./x
And we are root



---
[Back to Linux Privilege Escalation Index](../README.md)
