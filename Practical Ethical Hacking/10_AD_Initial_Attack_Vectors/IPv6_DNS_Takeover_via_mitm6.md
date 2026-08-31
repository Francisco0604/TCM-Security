# IPv6 DNS Takeover via mitm6


Install mitm6


![Screenshot](./assets/107_IPv6_DNS_Takeover_via_mitm6_1c7d64c5-e0cb-80fa-a810-d2c73f21213b.png)

Does not get installed then see youtube or github

Run these attacks only in small sprints if you run it longer than 5-10 mins it might crash the system or will not be able to authenticate people
set up mitm6 n ntlmreplay
run the ntlmrelap first then the mitm6

![Screenshot](./assets/108_IPv6_DNS_Takeover_via_mitm6_1c7d64c5-e0cb-8042-8d18-eb13826b7994.png)
-d is for the domain


![Screenshot](./assets/109_IPv6_DNS_Takeover_via_mitm6_1c7d64c5-e0cb-80bb-81e5-d779efe169ae.png)
-6 is for ipv6
-t for target
-wh for wpad (WPAD is a protocol that allows devices on a network to automatically discover and configure proxy settings.)
That fakewpad is our choice we can put anything there 
-l is for loot it will create a folder

When someone logs in it will create a new user for us 

The new user created will have access to [secretsdump.py](http://secretsdump.py/) and  the group Enterprise admins


---
[Back to Attacking Active Directory: Initial Attack Vectors](./README.md)
