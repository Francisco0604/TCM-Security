# Dev

target_ip : 192.168.182.130

22/tcp    open  ssh      OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)

80/tcp    open  http     Apache httpd 2.4.38 ((Debian))

111/tcp   open  rpcbind  2-4 (RPC #100000)

2049/tcp  open  nfs      3-4 (RPC #100003)

8080/tcp  open  http     Apache httpd 2.4.38 ((Debian))
|_http-title: PHP 7.3.27-1~deb10u1 - phpinfo()
|_http-server-header: Apache/2.4.38 (Debian)
| http-open-proxy: Potentially OPEN proxy.
|_Methods supported:CONNECTION

Discovered on port 8080

![Screenshot](./assets/047_Dev_1c5d64c5-e0cb-8002-a3fb-fa1e5ed9c539.png)

use ffuf to enumerate directories on both http ports
finding directory listing can be a finding
connected to the nfs server
used showmount 
then mount (somehow i couldn't do it)
used fcrackzip to crack the password of the zip file got from the nfs server

![Screenshot](./assets/048_Dev_1c5d64c5-e0cb-802c-9584-e075a5d7da8e.png)


![Screenshot](./assets/049_Dev_1c5d64c5-e0cb-80c0-80f5-e97323844c50.png)
The id_rsa file can be used to connect through ssh

![Screenshot](./assets/050_Dev_1c5d64c5-e0cb-802d-b6ca-e01c100b0bd6.png)

After enumeration of directories o and check them 

![Screenshot](./assets/051_Dev_1c5d64c5-e0cb-8021-bc16-d61cb0b6d7df.png)

search for boltwire exploit
focus on LFI

Use gtfo bins site to look at various escalation techniques



---
[Back to New capstone](./README.md)
