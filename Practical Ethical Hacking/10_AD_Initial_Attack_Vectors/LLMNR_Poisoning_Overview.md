# LLMNR Poisoning Overview

Attacking Active Directory: Initial Attack Vectors 

![Screenshot](./assets/073_LLMNR_Poisoning_Overview_1c5d64c5-e0cb-8044-b047-f8f46572329e.png)
Stands for Link-Local Multicast Name Resolution

Why do we care

When we intercept the traffic we can intercept a username and a hash (this is a type of Man in the middle attack)

Eg. actual machine is \\hackme but the user misspelled 

![Screenshot](./assets/074_LLMNR_Poisoning_Overview_1c5d64c5-e0cb-8027-9c8f-fc549313c091.png)

run responder

![Screenshot](./assets/075_LLMNR_Poisoning_Overview_1c5d64c5-e0cb-8020-b911-f4ac883c5e93.png)
It can listen to traffic and grab the hash

try to do to a file share but with wrong thing in the end to direct to responder

![Screenshot](./assets/076_LLMNR_Poisoning_Overview_1c5d64c5-e0cb-802b-adf2-f9fff7dffdf7.png)

When we do the above we can get a hash

![Screenshot](./assets/077_LLMNR_Poisoning_Overview_1c5d64c5-e0cb-8047-b51e-e9fb458de963.png)

If the hash is weak enough we can crack it using hashcat

![Screenshot](./assets/078_LLMNR_Poisoning_Overview_1c5d64c5-e0cb-8083-9950-e9111264d7e4.png)



---
[Back to Attacking Active Directory: Initial Attack Vectors](./README.md)
