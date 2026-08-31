# Pass Attacks Walkthrough

Crackmapexec —help (to know more abt the protocols tha can be used in this thing)


![Screenshot](./assets/130_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-803a-933c-fa1d80538a7d.png)

It will attemp to log in on few machines which are part of the ip range/domain


![Screenshot](./assets/131_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-8079-8a74-c7e44a256aa6.png)

In the above img we got log in into 2 machine which are THEPUNISHER and SPIDERMAN [+]
Successful Autentication happened in hydra-dc but we are not the local admin there [+]
WONDERLAND is an example of unsuccessful log in [-]

Now that we have access to the machine, the strategy would be to dump information such as hash etc using a tool like secretsdump 

We can do the same using a hash if we can not crack the hash

![Screenshot](./assets/132_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-80c3-8e5d-d22ea07bc7dc.png)

This can be done only with ntlmv1 and not with ntlmv2(ntlmv2 can be replayed)

can use —sam to dump information from security account manager

![Screenshot](./assets/133_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-808b-b8af-cd9a930b366a.png)

the data is stored in the database

![Screenshot](./assets/134_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-80ab-8c91-e844f277fc39.png)

We can do —shares to enumerate the shares and c to what we have access to

![Screenshot](./assets/135_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-80c4-9da7-c423dc51a76c.png)


![Screenshot](./assets/136_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-80d6-a496-d6c7928f6e5d.png)

We can also look at —lsa it will dump out the local security authority

![Screenshot](./assets/137_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-807b-9bd5-fa0655dac926.png)

This information may or may not be usefull but it is better to check
Can attemp to crack the hashes which you get using this locally and then log in to the machine 

To use module type -M (module name)

![Screenshot](./assets/138_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-800d-8fdd-d24b3f859183.png)
It will dump out hashes if they were recently stored

Type cmedb to enter the crackmapexec database

![Screenshot](./assets/139_Pass_Attacks_Walkthrough_1c9d64c5-e0cb-80ad-a935-f14545220386.png)
type help to get more details


---
[Back to Attacking Active Directory: Post-Compromise Attacks ](./README.md)
