# Abusing ZeroLogon


It is very very powerful and can destroy the domain
We can set the domain controller password to null , we have to restore the password also otherwise we will destroy the domain

What is ZeroLogon? - [https://www.trendmicro.com/en_us/what-is/zerologon.html](https://www.trendmicro.com/en_us/what-is/zerologon.html)
dirkjanm CVE-2020-1472 - [https://github.com/dirkjanm/CVE-2020-1472](https://github.com/dirkjanm/CVE-2020-1472)
SecuraBV ZeroLogon Checker - [https://github.com/SecuraBV/CVE-2020-1472](https://github.com/SecuraBV/CVE-2020-1472)

You can run the checker to see if the target is vulnerable and that is it
In a real pentest do not do anything further as it would probably wipe out the domain if udk wha tu are doing

Useuage is given

![Screenshot](./assets/191_Abusing_ZeroLogon_1cbd64c5-e0cb-8042-89e5-ee676c92378f.png)

Run the exploit

![Screenshot](./assets/192_Abusing_ZeroLogon_1cbd64c5-e0cb-8046-8791-e5c38683ddc3.png)

Use secrets dump to dump out secrets of the machine

![Screenshot](./assets/193_Abusing_ZeroLogon_1cbd64c5-e0cb-809a-85fb-fafff5bb1cdd.png)

The attack is done now

to restore
Take the administrator hash

![Screenshot](./assets/194_Abusing_ZeroLogon_1cbd64c5-e0cb-80d4-b769-d628f57e1ad1.png)

This is what we are goin to use to restore the dc

![Screenshot](./assets/195_Abusing_ZeroLogon_1cbd64c5-e0cb-80ed-b2e1-fde3d6839e4f.png)


![Screenshot](./assets/196_Abusing_ZeroLogon_1cbd64c5-e0cb-80f6-b6ff-dd7f1d2f664a.png)


---
[Back to Additional Active Directory Attacks](./README.md)
