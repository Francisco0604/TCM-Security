# Dumping and Cracking Hashes

If i get an account and log in, it is better to dumb secrets for more information, can use a tool such as secretsdump

With password

![Screenshot](./assets/141_Dumping_and_Cracking_Hashes_1c9d64c5-e0cb-802e-98f9-d8c37a9802b7.png)
U can try to crack the dcc hash or other hashes and c if anything good you get

The main things you are looking for are the SAM hashes

![Screenshot](./assets/142_Dumping_and_Cracking_Hashes_1c9d64c5-e0cb-80a1-ad77-df4ab1aa455a.png)
The important ones here are the administrator and any other user accounts
Guest, defaultaccount and utility account are not that grt

If the passwords are stored on the registory we can see it in clear text
wdigest (only on older versions) we can use this protocol also to check for password stored in clear text
U can also switch the wdigest on and wait for someone to log in so can get their password (close the switch after your work is done, otherwise you will be leaving back vulnerabilities bck which is not good)
Use wdigest as lst resort if you actually very desperate
Go through all the accounts you can access through using secretsdump

This is how to do it with hash

![Screenshot](./assets/143_Dumping_and_Cracking_Hashes_1c9d64c5-e0cb-803d-b3ad-c911c22b1edf.png)

General pathaway/methadology (fcastle is the local user)

![Screenshot](./assets/144_Dumping_and_Cracking_Hashes_1c9d64c5-e0cb-80f8-947c-dfdbfdc32175.png)

We can crack the hashesh 
We need only nt portion to crack the passowrd (the lst part)
Can crack the hash using hash cat or other hash cracker


---
[Back to Attacking Active Directory: Post-Compromise Attacks ](./README.md)
