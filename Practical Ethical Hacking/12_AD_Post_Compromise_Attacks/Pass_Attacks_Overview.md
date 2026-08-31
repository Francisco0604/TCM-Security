# Pass Attacks Overview

we can use knwn passwords and hash to do lateral movement 

![Screenshot](./assets/119_Pass_Attacks_Overview_1c9d64c5-e0cb-8056-b390-dce04e5f1dd1.png)

We can use crackmapexec, It is used to password 
The passowed we might have captured from anywhere (responder, glabal hash etc)


![Screenshot](./assets/120_Pass_Attacks_Overview_1c9d64c5-e0cb-80e3-b3ea-d9ce3fdfb4d0.png)

can also do this  using hash which can get from metasploit 

![Screenshot](./assets/121_Pass_Attacks_Overview_1c9d64c5-e0cb-806e-b0a9-e8d6b547dd1d.png)

or can use secretsdump (it can also c all the accounts tied up in the machine and domain)

![Screenshot](./assets/122_Pass_Attacks_Overview_1c9d64c5-e0cb-8055-9776-f5a2094d9405.png)

this is how to pass the hash

![Screenshot](./assets/123_Pass_Attacks_Overview_1c9d64c5-e0cb-8000-96bf-ce0d8087375f.png)

we can do alot of things using crackmapexec
Like dumping the sam

![Screenshot](./assets/124_Pass_Attacks_Overview_1c9d64c5-e0cb-80a2-9aa4-efcca3b3ec7a.png)

can also enumerate shares

![Screenshot](./assets/125_Pass_Attacks_Overview_1c9d64c5-e0cb-80ff-8d9d-d7ef26c4aa3c.png)

also lsa (local security authority)

![Screenshot](./assets/126_Pass_Attacks_Overview_1c9d64c5-e0cb-807f-924c-cba6b0e66164.png)

It also has inbuilt modules

![Screenshot](./assets/127_Pass_Attacks_Overview_1c9d64c5-e0cb-80bb-9401-ea69e53bcede.png)

lsassy one of the modules, can be used to dump out lsass (they enforce the security polices) and it also stores credentials. If there is active user login we may b able to dump out the credentials

![Screenshot](./assets/128_Pass_Attacks_Overview_1c9d64c5-e0cb-8097-ae90-f492efaba16c.png)

It also has a database. it shows where all the users worked and wt passwords they have 

![Screenshot](./assets/129_Pass_Attacks_Overview_1c9d64c5-e0cb-80fd-a77e-f6e907b03cc2.png)



---
[Back to Attacking Active Directory: Post-Compromise Attacks ](./README.md)
